# apache-avro-schema.xsl

This builder currently ships with CIMTool.

## Builder Description

The **[apache-avro-schema.xsl](apache-avro-schema.xsl)** builder generates an [Apache Avro](https://avro.apache.org/) schema file (`*.avsc`) defining the record types and fields corresponding to the classes and attributes in a **CIMTool** profile. The generated schema conforms to the [Apache Avro specification](https://avro.apache.org/docs/current/specification/) and can be used with Avro-compatible serialization frameworks for compact, efficient data exchange between systems.

<!-- TODO: Insert representative sample output from the builder here -->
```
(sample output placeholder)
```

## XSLT Version

This builder is XSLT 2.0 compliant.

## Author

Todd Viegut [@tviegut] on behalf of UCAIug.

## Submission Date

14-May-2026

## Builder NTE Configuration

Given this builder ships with CIMTool the below table highlights the existing NTE (Name/Type/Extension) settings for the builder.  We strongly recommend that you do not import customized versions of this shipped builder over the original in your local CIMTool installation. Doing so will force regeneration of any existing builder-generated artifacts for projects in your workspace that have this builder enabled.

The recommended best practice is to rename the builder file  (from ```apache-avro-schema.xsl``` to ```custom-apache-avro-schema.xsl``` for example) before importing. On import this will be interpreted as a new builder and you will be allowed to enter values in the Type and Extension fields.

>*NOTE: </br>CIMTool requires that file extensions be unique and will prevent you from entering an extension already assigned to a builder. This is because an artifact's name is derived by concatenating the base name of the CIMTool ```.owl``` profile with the file extension assigned to the builder. Therefore, a unique file extension must be assigned to each builder when imported. The file extension for a builder can be modified later from within the "Maintain XSLT Transform Builders" screen.*

A blank Includes File Name row indicates that no XSLT include file is required for this builder.

| Field | Value |
|---|---|
| Builder XSLT Name: | `apache-avro-schema.xsl` |
| Includes File Name: |  |
| Transform Builder Type: | `TEXT` |
| File Extension of Generated Files: | `avsc` |

## License

This builder is released under the [Apache 2.0](../../LICENSE) license and was developed under sponsorship of the UCAIug.
