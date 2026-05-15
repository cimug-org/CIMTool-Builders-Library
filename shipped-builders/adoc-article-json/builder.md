# adoc-article-json.xsl

This builder currently ships with CIMTool.

## Builder Description

The **[adoc-article-json.xsl](adoc-article-json.xsl)** builder generates an [AsciiDoc](https://asciidoc.org/) file containing documentation for all classes, attributes, and associations defined in a **CIMTool** profile. The generated output is a complete, standalone document with a full document header, suitable for direct publication using the AsciiDoc toolchain or conversion to HTML, PDF, and other output formats via tools such as [Asciidoctor](https://asciidoctor.org/). The documentation content is structured around JSON schema concepts.

This builder is the article-doctype counterpart to the **[adoc-inline-json.xsl](../adoc-inline-json/builder.md)** builder.

## XSLT Version

This builder is XSLT 3.0 compliant.

## Author

Todd Viegut [@tviegut] on behalf of UCAIug.

## Submission Date

14-May-2026

## Builder NTE Configuration

Given this builder ships with CIMTool the below table highlights the existing NTE (Name/Type/Extension) settings for the builder.  We strongly recommend that you do not import customized versions of this shipped builder over the original in your local CIMTool installation. Doing so will force regeneration of any existing builder-generated artifacts for projects in your workspace that have this builder enabled.

The recommended best practice is to rename the builder file  (from ```adoc-article-json.xsl``` to ```custom-adoc-article-json.xsl``` for example) before importing. On import this will be interpreted as a new builder and you will be allowed to enter values in the Type and Extension fields.

>*NOTE: </br>CIMTool requires that file extensions be unique and will prevent you from entering an extension already assigned to a builder. This is because an artifact's name is derived by concatenating the base name of the CIMTool ```.owl``` profile with the file extension assigned to the builder. Therefore, a unique file extension must be assigned to each builder when imported. The file extension for a builder can be modified later from within the "Maintain XSLT Transform Builders" screen.*

A blank Includes File Name row indicates that no XSLT include file is required for this builder.

| Field | Value |
|---|---|
| Builder XSLT Name: | `adoc-article-json.xsl` |
| Includes File Name: |  |
| Transform Builder Type: | `TEXT` |
| File Extension of Generated Files: | `article-json.adoc` |

## License

This builder is released under the [Apache 2.0](../../LICENSE) license and was developed under sponsorship of the UCAIug.
