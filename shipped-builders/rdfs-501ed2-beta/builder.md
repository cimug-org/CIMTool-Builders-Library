# rdfs-501ed2-beta.xsl

This builder currently ships with CIMTool.

## Builder Description

The **[rdfs-501ed2-beta.xsl](rdfs-501ed2-beta.xsl)** builder generates an RDFS schema file (`*.rdfs-501ed2-beta.rdfs`) targeting the [IEC 61970-501 Ed 2](https://webstore.iec.ch/publication/6215) standard. This is a beta implementation reflecting the latest proposed extensions to the standard and is provided for evaluation and feedback purposes.

This builder is the intended successor to the **[rdfs-2020.xsl](../rdfs-2020/builder.md)** builder. Users who are currently using the **rdfs-2020.xsl** builder and wish to evaluate the **IEC 61970-501 Ed 2** alignment are encouraged to test this builder and provide feedback to the UCAIug community.

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

The recommended best practice is to rename the builder file  (from ```rdfs-501ed2-beta.xsl``` to ```custom-rdfs-501ed2-beta.xsl``` for example) before importing. On import this will be interpreted as a new builder and you will be allowed to enter values in the Type and Extension fields.

>*NOTE: </br>CIMTool requires that file extensions be unique and will prevent you from entering an extension already assigned to a builder. This is because an artifact's name is derived by concatenating the base name of the CIMTool ```.owl``` profile with the file extension assigned to the builder. Therefore, a unique file extension must be assigned to each builder when imported. The file extension for a builder can be modified later from within the "Maintain XSLT Transform Builders" screen.*

A blank Includes File Name row indicates that no XSLT include file is required for this builder.

| Field | Value |
|---|---|
| Builder XSLT Name: | `rdfs-501ed2-beta.xsl` |
| Includes File Name: |  |
| Transform Builder Type: | `TRANSFORM` |
| File Extension of Generated Files: | `rdfs-501ed2-beta.rdfs` |

## License

This builder is released under the [Apache 2.0](../../LICENSE) license and was developed under sponsorship of the UCAIug.
