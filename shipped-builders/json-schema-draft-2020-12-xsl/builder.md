# json-schema-draft-2020-12.xsl

This builder currently ships with CIMTool.

## Builder Description

The **[json-schema-draft-2020-12.xsl](json-schema-draft-2020-12.xsl)** builder generates a JSON schema compliant with the draft **IEC 62361-104** standard (CIM Profiles to JSON schema Mapping). The version of the JSON schema specification that the schema conforms to is [draft-2020-12](https://json-schema.org/draft/2020-12/release-notes.html).

The following is an example of a generated JSON schema:

```JSON
{
     "$comment": "Copyright 2022 UCAIug SPDX-License-Identifier: Apache-2.0",
     "$id": "http://ucaiug.org/2022/GetUsagePointGroups.schema.json",
     "$schema": "https://json-schema.org/draft/2020-12/schema",
     "title": "GetUsagePointGroups",
     "description": "",
     "namespace": "http://ucaiug.org/2022/GetUsagePointGroups#",
     "type": "object",
     "additionalProperties": false,
     "properties": {
         "DemandResponseProgram": {
             "type": "array",
             "items": {
                 "$ref": "#/$defs/DemandResponseProgram"
             }
         },
         "UsagePoint": {
             "type": "array",
             "items": {
                 "$ref": "#/$defs/UsagePoint"
             }
         },
         "UsagePointGroup": {
             "type": "array",
             "items": {
                 "$ref": "#/$defs/UsagePointGroup"
             }
         }
     },
     "$defs": {
          "DemandResponseProgram": {
              "title": "DemandResponseProgram",
              "description": "Demand response program.",
              "modelReference": "http://iec.ch/TC57/CIM-generic#DemandResponseProgram",
              "type": "object",
              "additionalProperties": false,
              "properties": {
                  "mRID": {
                      "description": "Master resource identifier issued by a model authority. The mRID is unique within an exchange context. Global uniqueness is easily achieved by using a UUID, as specified in RFC 4122, for the mRID. The use of UUID is strongly recommended. For CIMXML data files in RDF syntax conforming to IEC 61970-552, the mRID is mapped to rdf:ID or rdf:about attributes that identify CIM object elements.",
                      "modelReference": "http://iec.ch/TC57/CIM-generic#IdentifiedObject.mRID",
                      "type": "string"
                  },
                  "type": {
                      "description": "Type of demand response program; examples are CPP (critical-peak pricing), RTP (real-time pricing), DLC (direct load control), DBP (demand bidding program), BIP (base interruptible program). Note that possible types change a lot and it would be impossible to enumerate them all.",
                      "modelReference": "http://iec.ch/TC57/CIM-generic#DemandResponseProgram.type",
                      "type": "string"
                  },
                  "Names": {
                      "description": "All names of this identified object.",
                      "modelReference": "http://iec.ch/TC57/CIM-generic#IdentifiedObject.Names",
                      "type": "array",
                      "items": {
                          "$ref": "#/$defs/Name"
                      }
                  }
              }
          },
          "Name": {
              "title": "Name",
              "description": "The Name class provides the means to define any number of human readable names for an object. A name is <b>not</b> to be used for defining inter-object relationships. For inter-object relationships instead use the object identification 'mRID'.",
              "modelReference": "http://iec.ch/TC57/CIM-generic#Name",
              "type": "object",
              "additionalProperties": false,
              "properties": {
                  "name": {
                      "description": "Any free text that name the object.",
                      "modelReference": "http://iec.ch/TC57/CIM-generic#Name.name",
                      "type": "string"
                  },
                  "NameType": {
                      "description": "Type of this name.",
                      "modelReference": "http://iec.ch/TC57/CIM-generic#Name.NameType",
                      "$ref": "#/$defs/NameType"
                  }
              },
              "required": [
                  "name"
              ]
          },
          "NameType": {
              "title": "NameType",
              "description": "Type of name. Possible values for attribute 'name' are implementation dependent but standard profiles may specify types. An enterprise may have multiple IT systems each having its own local name for the same object, e.g. a planning system may have different names from an EMS. An object may also have different names within the same IT system, e.g. localName as defined in CIM version 14. The definition from CIM14 is: The localName is a human readable name of the object. It is a free text name local to a node in a naming hierarchy similar to a file directory structure. A power system related naming hierarchy may be: Substation, VoltageLevel, Equipment etc. Children of the same parent in such a hierarchy have names that typically are unique among them.",
              "modelReference": "http://iec.ch/TC57/CIM-generic#NameType",
              "type": "object",
              "additionalProperties": false,
              "properties": {
                  "description": {
                      "description": "Description of the name type.",
                      "modelReference": "http://iec.ch/TC57/CIM-generic#NameType.description",
                      "type": "string"
                  },
                  "name": {
                      "description": "Name of the name type.",
                      "modelReference": "http://iec.ch/TC57/CIM-generic#NameType.name",
                      "type": "string"
                  },
                  "NameTypeAuthority": {
                      "description": "Authority responsible for managing names of this type.",
                      "modelReference": "http://iec.ch/TC57/CIM-generic#NameType.NameTypeAuthority",
                      "$ref": "#/$defs/NameTypeAuthority"
                  }
              },
              "required": [
                  "name"
              ]
          },
          "NameTypeAuthority": {
              "title": "NameTypeAuthority",
              "description": "Authority responsible for creation and management of names of a given type; typically an organization or an enterprise system.",
              "modelReference": "http://iec.ch/TC57/CIM-generic#NameTypeAuthority",
              "type": "object",
              "additionalProperties": false,
              "properties": {
                  "description": {
                      "description": "Description of the name type authority.",
                      "modelReference": "http://iec.ch/TC57/CIM-generic#NameTypeAuthority.description",
                      "type": "string"
                  },
                  "name": {
                      "description": "Name of the name type authority.",
                      "modelReference": "http://iec.ch/TC57/CIM-generic#NameTypeAuthority.name",
                      "type": "string"
                  }
              },
              "required": [
                  "name"
              ]
          },
          "UsagePoint": {
              "title": "UsagePoint",
              "description": "Logical or physical point in the network to which readings or events may be attributed. Used at the place where a physical or virtual meter may be located; however, it is not required that a meter be present.",
              "modelReference": "http://iec.ch/TC57/CIM-generic#UsagePoint",
              "type": "object",
              "additionalProperties": false,
              "properties": {
                  "mRID": {
                      "description": "Master resource identifier issued by a model authority. The mRID is unique within an exchange context. Global uniqueness is easily achieved by using a UUID, as specified in RFC 4122, for the mRID. The use of UUID is strongly recommended. For CIMXML data files in RDF syntax conforming to IEC 61970-552, the mRID is mapped to rdf:ID or rdf:about attributes that identify CIM object elements.",
                      "modelReference": "http://iec.ch/TC57/CIM-generic#IdentifiedObject.mRID",
                      "type": "string"
                  },
                  "Names": {
                      "description": "All names of this identified object.",
                      "modelReference": "http://iec.ch/TC57/CIM-generic#IdentifiedObject.Names",
                      "type": "array",
                      "items": {
                          "$ref": "#/$defs/Name"
                      }
                  }
              }
          },
          "UsagePointGroup": {
              "title": "UsagePointGroup",
              "description": "Abstraction for management of group communications within a two-way AMR system or the data for a group of related usage points. Commands can be issued to all of the usage points that belong to a usage point group using a defined group address and the underlying AMR communication infrastructure.",
              "modelReference": "http://iec.ch/TC57/CIM-generic#UsagePointGroup",
              "type": "object",
              "additionalProperties": false,
              "properties": {
                  "mRID": {
                      "description": "Master resource identifier issued by a model authority. The mRID is unique within an exchange context. Global uniqueness is easily achieved by using a UUID, as specified in RFC 4122, for the mRID. The use of UUID is strongly recommended. For CIMXML data files in RDF syntax conforming to IEC 61970-552, the mRID is mapped to rdf:ID or rdf:about attributes that identify CIM object elements.",
                      "modelReference": "http://iec.ch/TC57/CIM-generic#IdentifiedObject.mRID",
                      "type": "string"
                  },
                  "Names": {
                      "description": "All names of this identified object.",
                      "modelReference": "http://iec.ch/TC57/CIM-generic#IdentifiedObject.Names",
                      "type": "array",
                      "items": {
                          "$ref": "#/$defs/Name"
                      }
                  }
              }
          },
          "GetUsagePointGroups": {
               "$ref": "#"
          }
     }
}
```

## XSLT Version

This builder is XSLT 1.0 compliant.

## Author

Todd Viegut [@tviegut] on behalf of UCAIug.

## Submission Date

20-Jun-2022

## Builder NTE Configuration

Given this builder ships with CIMTool the below screenshot highlights the existing NTE (Name/Type/Extension) settings for the builder.  We strongly recommend that you do not import customized versions of this shipped builder over the original in your local CIMTool installation. Doing so will force regeneration of any existing builder-generated artifacts for projects in your workspace that have this builder enabled.

The recommended best practice is to rename the builder file  (from ```json-schema-draft-2020-12.xsl``` to ```custom-json-schema-draft-2020-12.xsl``` for example) before importing. On import this will be interpreted as a new builder and you will be allowed to enter values in the Type and Extension fields.

>*NOTE: </br>CIMTool requires that file extensions be unique and will prevent you from entering an extension already assigned to a builder. This is because an artifact's name is derived by concatenating the base name of the CIMTool ```.owl``` profile with the file extension assigned to the builder. Therefore, a unique file extension must be assigned to each builder when imported. The file extension for a builder can be modified later from with the "Maintain XSLT Transform Builders" screen.*

![image](import-builder.png)

## License

This builder is released under the [Apache 2.0](../../LICENSE) license and was developed under sponsorship of the UCAIug.
