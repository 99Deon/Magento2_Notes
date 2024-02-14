# Declarative Schema

Declarative schema simplifies the installation and upgrade processes for Adobe Commerce and Magento Open Source. Previously, developers had to write PHP database scripts for each new version, covering various operations such as **installing/upgrading** database schema and data, and invoking other required operations.

Declarative schema introduces a new approach where developers declare the final desired state of the database. The system automatically adjusts to this state without redundant operations. This eliminates the need for developers to write scripts for every new version and allows data to be deleted when a module is uninstalled.

While declarative schema implementation is not mandatory for Adobe Commerce and Magento Open Source 2.3, upgrade scripts will be phased out in its favor.

## Preparing a Module for Declarative Schema

To prepare a module for declarative schema, developers must:

1. Develop a data patch and/or schema patch.
2. Configure the declarative schema for the module.
3. Convert upgrade scripts to declarative schema (applicable only to modules released with upgrade scripts).

Once a module is converted to the declarative schema approach, it cannot be reverted to upgrade scripts.

## Data Patch Terminology

- **Data Patch:** A class containing data modification instructions, possibly with dependencies on other patches.
- **Revertable Data Patch:** Contains a `revert()` method to revert changes, typically related to database changes.
- **Migration:** A non-revertable data patch with complex operations like application layer changes or SQL deletes.
- **Schema Patch:** A class with custom schema modification instructions, allowing complex operations like adding triggers or renaming entities.
- **Revertable Schema Patch:** Contains a `revert()` method to revert schema changes, affecting the database only.

 # Declarative Schema Migration Guide

This guide provides instructions for migrating installation and upgrade scripts to declarative schema in Adobe Commerce and Magento Open Source. Declarative schema offers commands to facilitate conversion, testing, and ensuring backward compatibility for modules.

## Installation and Upgrade Schema Conversion

To convert pre-2.3 migration scripts into declarative schema, use the Schema Listener Tool. Run commands such as `setup:install` or `setup:upgrade` with the `--convert-old-scripts=1` parameter.

### Troubleshooting

- Only DDL operations represented in `\Magento\Framework\DB\Adapter\Pdo\Mysql` are supported.
- Custom DDL operations and raw SQL in scripts are ignored.
- DDL statements in Recurring files are not transferred.

## Data Scripts Conversion

Old data scripts require manual conversion. Use `setup:db-declaration:generate-patch` to generate patch stubs. Ensure backward compatibility by implementing `\Magento\Framework\Setup\Patch\PatchVersionInterface`.

## Dry Run Mode

Utilize dry run mode (`--dry-run=1`) to review generated DDL SQL statements without altering the database, ensuring safety and aiding in debugging.

## Safe Installation and Rollback

Prevent data loss during schema modifications with `--safe-mode=1` for safe installations and `--data-restore=1` for rollback during upgrades.

## Schema Whitelist Creation

Maintain backward compatibility by generating a whitelist of tables, columns, and keys added with declarative schema using `setup:db-declaration:generate-whitelist`.

## Reference ID Resolution

Ensure consistency between `referenceId` attributes in `db_schema.xml` and system-generated constraint and index names.

This guide offers comprehensive instructions for migrating install/upgrade scripts to declarative schema, ensuring compatibility and safety throughout the process.
