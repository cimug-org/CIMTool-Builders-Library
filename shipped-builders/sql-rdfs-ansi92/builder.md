# sql-rdfs-ansi92.xsl

This builder currently ships with CIMTool.

## Builder Description

> **Important:** This builder is specifically intended for use with profiles designed to generate RDFS as their primary schema artifact. For such profiles, defined using the formal CIM profiling approach for RDFS schemas, this builder generates a complementary SQL DDL script that is structurally aligned with the RDFS schema. It is designed to be used alongside the companion **[jpa-rdfs.xsl](../jpa-rdfs/builder.md)** and **[csharp-ef-rdfs.xsl](../csharp-ef-rdfs/builder.md)** builders.

The **[sql-rdfs-ansi92.xsl](sql-rdfs-ansi92.xsl)** builder generates an ANSI SQL-compliant DDL script (`*.rdfs-ansi92.sql`) that creates the database tables, columns, foreign key relationships, and indexes corresponding to the classes, attributes, and associations defined in a **CIMTool** profile.

A key distinction from the companion **[sql.xsl](../sql/builder.md)** builder is the RDFS-schema-aware primary key strategy. In the CIM, `IdentifiedObject` is the universal root class for all persistent, independently-addressable objects and carries the `mRID` (master resource identifier) attribute. For all profile classes in the `IdentifiedObject` hierarchy, this builder uses `mRID` as a natural `VARCHAR(100) PRIMARY KEY`. For the small but important subset of CIM classes that do not inherit from `IdentifiedObject` — such as `CurveData`, `RegularTimePoint`, and `TapChangerTablePoint` — a surrogate `id VARCHAR(100) PRIMARY KEY` column is emitted together with a heuristic `UNIQUE` constraint spanning all required (`NOT NULL`) non-surrogate columns. `EnumeratedType` classes receive a `name VARCHAR(100) PRIMARY KEY` column. `CompoundType` classes receive the same surrogate `id VARCHAR(100) PRIMARY KEY` pattern.

This builder is designed to be used in conjunction with the companion **[jpa-rdfs.xsl](../jpa-rdfs/builder.md)** and **[csharp-ef-rdfs.xsl](../csharp-ef-rdfs/builder.md)** builders, which apply the identical primary key detection logic to generate structurally aligned JPA and Entity Framework Core persistence layers respectively.

<!-- TODO: Insert representative sample output from the builder here -->
```
(sample output placeholder)
```

## XSLT Version

This builder is XSLT 3.0 compliant.

## Author

Todd Viegut [@tviegut] on behalf of UCAIug.

## Submission Date

14-May-2026

## Builder NTE Configuration

Given this builder ships with CIMTool the below table highlights the existing NTE (Name/Type/Extension) settings for the builder.  We strongly recommend that you do not import customized versions of this shipped builder over the original in your local CIMTool installation. Doing so will force regeneration of any existing builder-generated artifacts for projects in your workspace that have this builder enabled.

The recommended best practice is to rename the builder file  (from ```sql-rdfs-ansi92.xsl``` to ```custom-sql-rdfs-ansi92.xsl``` for example) before importing. On import this will be interpreted as a new builder and you will be allowed to enter values in the Type and Extension fields.

>*NOTE: </br>CIMTool requires that file extensions be unique and will prevent you from entering an extension already assigned to a builder. This is because an artifact's name is derived by concatenating the base name of the CIMTool ```.owl``` profile with the file extension assigned to the builder. Therefore, a unique file extension must be assigned to each builder when imported. The file extension for a builder can be modified later from within the "Maintain XSLT Transform Builders" screen.*

A blank Includes File Name row indicates that no XSLT include file is required for this builder.

| Field | Value |
|---|---|
| Builder XSLT Name: | `sql-rdfs-ansi92.xsl` |
| Includes File Name: |  |
| Transform Builder Type: | `TEXT` |
| File Extension of Generated Files: | `rdfs-ansi92.sql` |

## License

This builder is released under the [Apache 2.0](../../LICENSE) license and was developed under sponsorship of the UCAIug.
