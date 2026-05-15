# linkml.xsl

This builder currently ships with CIMTool.

## Builder Description

The **[linkml.xsl](linkml.xsl)** builder generates a [LinkML](https://linkml.io/) schema file (`*.linkml.yaml`) representing the classes, attributes, and associations defined in a **CIMTool** profile. The generated schema conforms to the [LinkML specification](https://linkml.io/linkml-model/docs/) and includes the license, copyright, class definitions, type definitions, and enumeration definitions derived from the profile.

The generated LinkML schema can be used with LinkML toolchain utilities for code generation across multiple target languages, data validation, and schema documentation. LinkML is an open-source framework for defining schemas for structured and semi-structured data.

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

The recommended best practice is to rename the builder file  (from ```linkml.xsl``` to ```custom-linkml.xsl``` for example) before importing. On import this will be interpreted as a new builder and you will be allowed to enter values in the Type and Extension fields.

>*NOTE: </br>CIMTool requires that file extensions be unique and will prevent you from entering an extension already assigned to a builder. This is because an artifact's name is derived by concatenating the base name of the CIMTool ```.owl``` profile with the file extension assigned to the builder. Therefore, a unique file extension must be assigned to each builder when imported. The file extension for a builder can be modified later from within the "Maintain XSLT Transform Builders" screen.*

A blank Includes File Name row indicates that no XSLT include file is required for this builder.

| Field | Value |
|---|---|
| Builder XSLT Name: | `linkml.xsl` |
| Includes File Name: |  |
| Transform Builder Type: | `TRANSFORM` |
| File Extension of Generated Files: | `linkml.yaml` |

## License

This builder is released under the [Apache 2.0](../../LICENSE) license and was developed under sponsorship of the UCAIug.
