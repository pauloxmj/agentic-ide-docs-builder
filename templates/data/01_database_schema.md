<template target_path="docs/data/01_database_schema.md">
# Database Schema & Relations

> **Agent Directive:** This document is the absolute source of truth for the database structure. Do not invent columns, tables, or relations. If a required field is missing here, you must ask the user to update this schema before proceeding with code generation. Never generate migration files unless explicitly requested.

## Strict Rules
[Analyze the ORM/SQL schema and define the naming conventions, e.g., use `snake_case` for all table and column names.]
[Define primary key rules based on existing tables, e.g., All tables must have a UUID `id` primary key and `created_at` / `updated_at` timestamps.]

## Schema Map

[For every core operational table mapped in the project's ORM or SQL files, generate a markdown table like the example below:]

### 1. `[TableName]`
| Column | Type | Constraints | Description |
| :--- | :--- | :--- | :--- |
| `id` | [Type] | PRIMARY KEY | [Description] |
| `[col_name]` | [Type] | [Constraints] | [Description] |

## Entity-Relationship Diagram (ERD)
[Generate a Mermaid ERD summarizing the relations mapped above.]
</template>
