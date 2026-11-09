# puml-rdfs-t2b.xsl

This builder currently ships with CIMTool.

## Builder Description

The **[puml-rdfs-t2b.xsl](puml-rdfs-t2b.xsl)** builder produces a [PlantUML](https://plantuml.com) class diagram representing the profile (for an RDFS schema) that this builder is executed for. The layout of the diagram is top-to-bottom (i.e. t2b).

The following is an example of a PlantUML class diagram generated from a CGMES Topology profile:

![image](sample-puml-rdfs-t2b.png)

Prior to CIMTool 2.3.0 this builder was named ```puml-t2b.xsl```. It was renamed so that its name identifies the profile representation it diagrams (RDFS), alongside the [puml-xsd-t2b.xsl](../puml-xsd-t2b/builder.md) and [puml-json-t2b.xsl](../puml-json-t2b/builder.md) builders.

## XSLT Version

This builder is XSLT 3.0 compliant.

## Release History

| CIMTool Release | Release Date | Changes |
|---|---|---|
| [2.3.0](https://cimtool.ucaiug.io/release-notes/) | 08-Jun-2026 | Upgraded to XSLT 3.0. Renamed from ```puml-t2b.xsl``` ([#176](https://github.com/cimug-org/CIMTool/issues/176)). Diagrams now apply CIMTool's PlantUML preferences for colours, dark mode, shadowing, spacing and hiding CIMDatatypes, compounds, enumerations or primitives ([#172](https://github.com/cimug-org/CIMTool/issues/172)), and now include CIMDatatype, primitive and compound classes. |
| [2.2.0](https://cimtool.ucaiug.io/release-notes/) | 01-Oct-2024 | Added to CIMTool as ```puml-t2b.xsl``` ([#143](https://github.com/cimug-org/CIMTool/issues/143)). |

## Author

Todd Viegut [@tviegut] on behalf of UCAIug.

## Submission Date

01-Oct-2024

## Builder NTE Configuration

Given this builder ships with CIMTool the below screenshot highlights the existing NTE (Name/Type/Extension) settings for the builder.  We strongly recommend that you do not import customized versions of this shipped builder over the original in your local CIMTool installation. Doing so will force regeneration of any existing builder-generated artifacts for projects in your workspace that have this builder enabled.

The recommended best practice is to rename the builder file  (from ```plantuml-t2b.xsl``` to ```custom-plantuml-t2b.xsl``` for example) before importing. On import this will be interpreted as a new builder and you will be allowed to enter values in the Type and Extension fields.

> NOTE: CIMTool requires that file extensions be unique and will prevent you from entering an extension already assigned to a builder. This is because an artifact's name is derived by concatenating the base name of the CIMTool ```.owl``` profile with the file extension assigned to the builder. Therefore, a unique file extension must be assigned to each builder when imported. The file extension for a builder can be modified later from within the "Maintain XSLT Transform Builders" screen.*


![image](import-builder.png)

## License

This builder is released under the [Apache 2.0](../../LICENSE) license and was developed under sponsorship of the UCAIug.
