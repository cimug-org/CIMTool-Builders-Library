# profile-doc-rtf.xsl

This builder currently ships with CIMTool.

## Builder Description

The **[profile-doc-rtf.xsl](profile-doc-rtf.xsl)** builder produces a Microsoft Word compatible RTF ([Rich Text Format](https://en.wikipedia.org/wiki/Rich_Text_Format)) document that contains the complete documentation for all classes, attributes and associations defined in a profile.

![image](sample-rtf.png)

## XSLT Version

This builder is XSLT 1.0 compliant.

## Author

Todd Viegut [@tviegut] on behalf of UCAIug.

## Submission Date

19-Aug-2022

## Builder NTE Configuration

Given this builder ships with CIMTool the below screenshot highlights the existing NTE (Name/Type/Extension) settings for the builder.  We strongly recommend that you do not import customized versions of this shipped builder over the original in your local CIMTool installation. Doing so will force regeneration of any existing builder-generated artifacts for projects in your workspace that have this builder enabled.

The recommended best practice is to rename the builder file  (from ```profile-doc-rtf.xsl``` to ```custom-rofile-doc-rtf.xsl``` for example) before importing. On import this will be interpreted as a new builder and you will be allowed to enter values in the Type and Extension fields.

>*NOTE: </br>CIMTool requires that file extensions be unique and will prevent you from entering an extension already assigned to a builder. This is because an artifact's name is derived by concatenating the base name of the CIMTool ```.owl``` profile with the file extension assigned to the builder. Therefore, a unique file extension must be assigned to each builder when imported. The file extension for a builder can be modified later from with the "Maintain XSLT Transform Builders" screen.*

![image](import-builder.png)

## License

This builder is released under the [Apache 2.0](../../LICENSE) license and was developed under sponsorship of the UCAIug.
