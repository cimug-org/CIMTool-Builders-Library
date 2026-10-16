# puml-xsd-t2b.xsl

This builder currently ships with CIMTool.

## Builder Description

The **[puml-xsd-t2b.xsl](puml-xsd-t2b.xsl)** builder produces a [PlantUML](https://plantuml.com) class diagram representing the profile (for an XSD schema) that this builder is executed for. The diagram uses XSD terminology, showing the document root, complex types, simple types and choices, and marks properties that are generated as XSD attributes. The layout of the diagram is top-to-bottom (i.e. t2b).

Colors and other display options are taken from the PlantUML preferences in CIMTool and can be overridden for an individual diagram. For a left-to-right layout use the [puml-xsd-l2r.xsl](../puml-xsd-l2r/builder.md) builder.

The following is an example of a PlantUML class diagram generated from a ComModuleConfig profile:

![image](sample-puml-xsd-t2b.png)

## XSLT Version

This builder is XSLT 3.0 compliant.

## Release History

| CIMTool Release | Release Date | Changes |
|---|---|---|
| [2.3.0](https://cimtool.ucaiug.io/release-notes/) | 08-Jun-2026 | Added to CIMTool ([#176](https://github.com/cimug-org/CIMTool/issues/176)). |

## Author

Todd Viegut [@tviegut] on behalf of UCAIug.

## Submission Date

23-Oct-2024

## Builder NTE Configuration

Given this builder ships with CIMTool the below screenshot highlights the existing NTE (Name/Type/Extension) settings for the builder.  We strongly recommend that you do not import customized versions of this shipped builder over the original in your local CIMTool installation. Doing so will force regeneration of any existing builder-generated artifacts for projects in your workspace that have this builder enabled.

The recommended best practice is to rename the builder file  (from ```puml-xsd-t2b.xsl``` to ```custom-puml-xsd-t2b.xsl``` for example) before importing. On import this will be interpreted as a new builder and you will be allowed to enter values in the Type and Extension fields.

>*NOTE: </br>CIMTool requires that file extensions be unique and will prevent you from entering an extension already assigned to a builder. This is because an artifact's name is derived by concatenating the base name of the CIMTool ```.owl``` profile with the file extension assigned to the builder. Therefore, a unique file extension must be assigned to each builder when imported. The file extension for a builder can be modified later from within the "Maintain XSLT Transform Builders" screen.*

![image](import-builder.png)

## License

This builder is released under the [Apache 2.0](../../LICENSE) license and was developed under sponsorship of the UCAIug.
