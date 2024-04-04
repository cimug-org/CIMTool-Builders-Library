# CIMTool-Builders-Library

![image](readme-icons/image-header-1.png)

<div class="footer border-top border-gray-light mt-5 pt-3 text-right text-gray">
        This site is open source. <a href="https://github.com/cimug-org/CIMTool-Builders-Library/edit/main/README.md">Improve this page</a>.
      </div>

This site is open source. [Improve this page](https://github.com/cimug-org/CIMTool-Builders-Library/edit/main/README.md)
      
This is the official UCAIug repository for custom **CIMTool** [XSLT](https://www.w3schools.com/xml/xsl_intro.asp) builders and is provided as a public space to create, collaborate and contribute back builders for the benefit of the **CIMTool** community at large.  This library of builders can be used in [CIMTool](https://cimtool.ucaiug.io/) to generate various types of target artifacts from a **CIMTool** profile definition.  

Would you like a custom builder that generates C/C++ objects from your CIMTool profiles? Perhaps you've wished there was a builder to create [Apache Avro](https://avro.apache.org/) schemas for data serialization or one that would automatically generate a [Google Protocol Buffers](https://developers.google.com/protocol-buffers/docs/overview) ```.proto``` file?  You can now with **CIMTool**'s custom builder import feature.

Included in this library is the base set of XSLT transforms that comes shipped with **CIMTool**. These have been included to serve as examples or starting points that can be either extended or used as working examples when creating new XSLT builders.

Feel free to initiate a [discussion](https://github.com/cimug-org/CIMTool-Builders-Library/discussions) around a new idea for a custom builder or to post a question on the discussions board. Please contribute new builders to this library using the submission process outlined towards the end of this page.

## Current Library of Builders
![image](readme-icons/icons8-folder-tree-96.png)

#### Builders Shipped with CIMTool:

| XSLT Builder | Output Type | Description |
|------------------|------------------|------------------|
| [xsd.xsl](shipped-builders/xsd/builder.md) | XSD schema | The **xsd.xsl** builder generates an XSD schema that is compliant with the [IEC 62361-100:2016](https://webstore.iec.ch/publication/25114) (CIM Profiles to XML Schema Mapping) standard. Additionally, these schemas are compatible with the [IEC 61968-100:2013](https://webstore.iec.ch/publication/6198) (Implementation Profiles) standard used for enterprise integration.|
| [xsd-part100-ed2.xsl](shipped-builders/xsd-part100-ed2/builder.md) | XSD schema | This builder is similar to the xsd.xsl builder above in that it also generates an XSD schema that is compliant with **IEC 62361-100:2016**.  However, these generated schemas are uniquely compatible with the new [IEC 61968-100:2022](https://webstore.iec.ch/publication/67766) published standard which is not backwards compatible with [IEC 61968-100:2013](https://webstore.iec.ch/publication/6198). |
| [legacy-rdfs.xsl](shipped-builders/legacy-rdfs/builder.md) | RDFS schema | The **legacy-rdfs.xsl** builder generates an early RDFS schema format used prior to that officially defined within the [IEC 61970-501:2006](https://webstore.iec.ch/publication/6215) published standard. |
| [legacy-rdfs-augmented.xsl](shipped-builders/legacy-rdfs-augmented/builder.md) | RDFS schema | The **legacy-rdfs-augmented.xsl** builder generates RDFS schema in primary alignment with that defined within the [IEC 61970-501:2006](https://webstore.iec.ch/publication/6215) published standard. |
| [rdfs-2020.xsl](shipped-builders/rdfs-2020/builder.md) | RDFS schema | This **rdfs-2020.xsl** builder generates RDFS2020 compliant schemas that reflect that latest de facto agreements on extensions post [IEC 61970-501:2006](https://webstore.iec.ch/publication/6215). |
| [jpa.xsl](shipped-builders/jpa/builder.md) | Java source file | The **jpa.xsl** builder generates a Java source file (```*.java```) containing JPA classes compatible with JPA 2.2 and earlier. The defined JPA classes can be utilized in Java applications for persisting profiles to a database. |
| [scala.xsl](shipped-builders/scala/builder.md) | Scala source file | The **scala.xsl** builder produces a Scala source file (```*.scala```) that defines a vocabulary for a profile definition. These source files contain Scala classes/objects representative of those in the profile and may be used in applications implemented in the Scala programming language. |
| [sql.xsl](shipped-builders/sql/builder.md) | SQL DDL file | The **sql.xsl** builder generates an ANSI SQL-compliant DDL (Data Definition Language) script (```*.sql```) that can be used to create the database tables and fields corresponding to the classes and attributes represented in a profile. |
| [profile-doc-rtf.xsl](shipped-builders/profile-doc-rtf/builder.md) | Microsoft Word file | The **profile-doc-rtf.xsl** builder produces a Microsoft Word compatible RTF (Rich Text Format) document that contains the complete documentation for all classes, attributes and associations defined in a profile. |
| [html.xsl](shipped-builders/html/builder.md) | HTML file | The **html.xsl** builder generates a standalone HTML file containing the complete documentation for all classes, attributes and associations defined in a profile. |
| [json-schema-draft-07.xsl](shipped-builders/json-schema-draft-07/builder.md) | JSON schema | The **json-schema-draft-07.xsl** builder generates a JSON schema compliant with the draft **IEC 62361-104** standard (CIM Profiles to JSON schema Mapping). The version of the JSON schema specification that the schema conforms to is draft-07. |
| [json-schema-draft-2020-12.xsl](shipped-builders/json-schema-draft-2020-12/builder.md) | JSON schema | The **json-schema-draft-2020-12.xsl** builder generates a JSON schema compliant with the draft **IEC 62361-104** standard (CIM Profiles to JSON schema Mapping). The version of the JSON schema specification that the schema conforms to is draft-2020-12. |

#### Community Developed Builders:

| XSLT Builder | Output Type | Description |
|------------------|------------------|------------------|
| [json-schema-draft-07-jsonschema2pojo.xsl](custom-builders/json-schema-draft-07-jsonschema2pojo/builder.md) | Specialized JSON schema |  The **json-schema-draft-07-jsonschema2pojo.xsl** builder produces a specialized JSON schema to be used as input into the jsonschema2pojo open source Maven or Gradle build plugins to generate annotated Java classes for data-binding with Jackson 2.x or Gson. This custom builder was derived from the **json-schema-draft-07.xsl** builder and is intended to serve as a companion builder to it. |
| [json-schema-draft-2020-12-jsonschema2pojo.xsl](custom-builders/json-schema-draft-2020-12-jsonschema2pojo/builder.md) | Specialized JSON schema | The **json-schema-draft-2020-12-jsonschema2pojo.xsl** builder produces a specialized JSON schema to be used as input into the jsonschema2pojo open source Maven or Gradle build plugins to generate annotated Java classes for data-binding with Jackson 2.x or Gson. This custom builder was derived from the **json-schema-draft-2020-12.xsl** builder and is intended to serve as a companion builder to it. |

## Background
**CIMTool** ships with a variety of different types of builders that generate artifacts based on a profile. Examples of existing builders include those that generate XSD schemas, JPA Java source code, RDBMS DDL scripts, RDFS profiles, and RTF Word docs among others.

A subcategory of builders supported by **CIMTool** are those that are based on XSLT transforms. In the below screenshot the builders that are selected are those that generate target files using XSLT transforms (click the image to enlarge):

[![image](readme-icons/cimtool-profile-summary-tab.png)](https://raw.githubusercontent.com/cimug-org/CIMTool-Builders-Library/main/readme-icons/cimtool-profile-summary-tab.png)

Starting with the **CIMTool.1.10.0.RC1** release, the ability to import and configure custom user-defined XSLT transforms and have them automatically added to the list of builders was introduced. This new feature opened up a wide range of possibilities for end users to more easily extend the builder capabilities beyond that shipped with the product. No longer do you need to know Eclipse plugin development.

CIMTool's internal XSLT processor was originally the [Apache Xalan](https://xalan.apache.org/) project that shipped as part of the Java JDK/JRE.  Xalan, however, is a W3C [XSLT 1.0](https://www.w3.org/TR/xslt-10/) compliant XSLT processor.  To support the much richer feature sets defined in the [XSLT 2.0](https://www.w3.org/TR/xslt-20/) and [XSLT 3.0](https://www.w3.org/TR/xslt-30/) specifications the XSLT processing engine was replaced by  [Saxon HE 10.8](https://saxonica.com/html/documentation10/about/index.html) in the **CIMTool.1.10.0** production release.

The screenshots below illustrate how to access the new import and maintenance screens (click on the images to present a larger view):

From the "Import" wizards screen... | ...Launch the "Import XSLT Transform Builder" screen
---------|---------
[![image](https://user-images.githubusercontent.com/63370413/186978949-cf9cdbfe-e1e4-43ae-b8b6-91e212426a98.png)](https://user-images.githubusercontent.com/63370413/186978949-cf9cdbfe-e1e4-43ae-b8b6-91e212426a98.png) | [![image](https://user-images.githubusercontent.com/63370413/186978126-ec4fca57-53a1-4e16-a998-d3519371ebcc.png)](https://user-images.githubusercontent.com/63370413/186978126-ec4fca57-53a1-4e16-a998-d3519371ebcc.png)

From the "Profile Summary" tab... | ...Launch the "Manage XSLT Transform Builders" screen
---------|---------
[![image](https://user-images.githubusercontent.com/63370413/186978387-015e3f32-7683-4623-bb8a-017e97102db6.png)](https://user-images.githubusercontent.com/63370413/186978387-015e3f32-7683-4623-bb8a-017e97102db6.png) |[![image](https://user-images.githubusercontent.com/63370413/188269652-758f2e79-e1fe-4c4a-99c3-8cc21923fcc5.png)](https://user-images.githubusercontent.com/63370413/188269652-758f2e79-e1fe-4c4a-99c3-8cc21923fcc5.png)

## How XSLT Builders Work

As a working example, the screenshot below illustrates a **CIMTool** profile named GetUsagePointGroups. The profile is represented as a [web ontology language](https://en.wikipedia.org/wiki/Web_Ontology_Language) file and appears in the **CIMTool** project as the  ```GetUsagePointGroups.owl``` bordered in blue. An ```.owl``` file is a public standalone artifact that can be imported or copied into other **CIMTool** projects.

What is not well known is that **CIMTool** has an alternate internal representation for a profile that is used specifically by XSLT builders. This internal representation is an XML format structured in such a manner so as to support straightforward and efficient XSLT transformations into any target output.  This internal representation is exposed and available for viewing using the XML builder bordered in red in the screenshot.

[![image](readme-icons/GetUsagePointGroups-profile.png)](https://raw.githubusercontent.com/cimug-org/CIMTool-Builders-Library/main/readme-icons/GetUsagePointGroups-profile.png)

<br/>The file generated by the XML builder appears below. Noteworthy observations include:

- the namespace ```xmlns:m="http://ucaiug.org/2022/GetUsagePointGroups#"``` of the profile is declared on the outermost ```<Catalog>``` XML element.
- the ```<Root>``` XML elements correspond to all classes declared as **concrete** in the profile i.e. those represented by the ![image](readme-icons/rootelement.png) icon and bordered in green in the above screenshot.
- the ```<ComplexType>``` XML elements correspond to all non-concrete classes declared in the profile i.e. those represented by the ![image](readme-icons/element.png) icon.
- a class's attributes and associations are defined by the ```<Simple>``` or ```<Instance>``` XML elements respectively.
- for primitive typed attributes (e.g. string, float, etc.) an ```xstype``` XSD attribute is specified with a corresponding value from the set of W3C XSD [primitive datatypes](https://www.w3.org/TR/2012/REC-xmlschema11-2-20120405/datatypes.html#built-in-primitive-datatypes).
- the comments on class and attribute defined in the profile are included in the ```<Comment>``` XML elements.
- minimum and maximum cardinality is declared via the ```minOccurs``` and ```maxOccurs``` attributes in each of the XML elements.

The significance of this internal representation is that it serves as the input into any XSLT builder(s) enabled for a profile. The XML builder itself is made available only so end users can view the internal representation. It does not need to be checked for XSLT builders to function.

```XML
<?xml version="1.0" encoding="UTF-8"?>
<Catalog xmlns="http://langdale.com.au/2005/Message#"
         xmlns:m="http://ucaiug.org/2022/GetUsagePointGroups#"
         ontologyURI="http://iec.ch/TC57/CIM100"
         baseURI="http://iec.ch/TC57/GetUsagePointGroups#"
         name="GetUsagePointGroups">
   <Package name="Base" basePackage="http://iec.ch/TC57/CIM100#Package_Base">
      <Comment>This package models configuration of ICCP required for bilateral exchanges.</Comment>
      <ParentPackage name="IEC61970"
                     basePackage="http://iec.ch/TC57/CIM100#Package_IEC61970"/>
   </Package>
   <Package name="Core" basePackage="http://iec.ch/TC57/CIM100#Package_Core">
      <Comment>Contains the core PowerSystemResource and ConductingEquipment entities shared by all applications plus common collections of those entities. Not all applications require all the Core entities.  This package does not depend on any other package except the Domain package, but most of the other packages have associations and generalizations that depend on it.</Comment>
      <ParentPackage name="Base" basePackage="http://iec.ch/TC57/CIM100#Package_Base"/>
   </Package>
   <Package name="IEC61968"
            basePackage="http://iec.ch/TC57/CIM100#Package_IEC61968">
      <Comment>The IEC 61968 subpackages of the CIM are developed, standardized and maintained by the UCA community including its working groups and task forces.</Comment>
      <Comment>Currently, normative parts of the model support the needs of information exchange defined in IEC 61968-3, IEC 61968-4, IEC 61968-5, IEC 61968-6, IEC 61968-8, IEC 61968-9 and in IEC 61968-13.</Comment>
      <ParentPackage name="TC57CIM" basePackage="http://iec.ch/TC57/CIM100#Package_TC57CIM"/>
   </Package>
   <Package name="IEC61970"
            basePackage="http://iec.ch/TC57/CIM100#Package_IEC61970">
      <Comment>Top package for IEC 61970.</Comment>
      <ParentPackage name="TC57CIM" basePackage="http://iec.ch/TC57/CIM100#Package_TC57CIM"/>
   </Package>
   <Package name="Metering"
            basePackage="http://iec.ch/TC57/CIM100#Package_Metering">
      <Comment>This package contains the core information classes that support end device applications with specialized classes for metering and premises area network devices, and remote reading functions. These classes are generally associated with the point where a service is delivered to the customer.</Comment>
      <ParentPackage name="IEC61968"
                     basePackage="http://iec.ch/TC57/CIM100#Package_IEC61968"/>
   </Package>
   <Package name="TC57CIM" basePackage="http://iec.ch/TC57/CIM100#Package_TC57CIM">
      <Comment>The IEC 61968 subpackages of the CIM are developed, standardized and maintained by the UCA community including its working groups and task forces.</Comment>
      <Comment>Currently, normative parts of the model support the needs of information exchange defined in IEC 61968-3, IEC 61968-4, IEC 61968-5, IEC 61968-6, IEC 61968-8, IEC 61968-9 and in IEC 61968-13.</Comment>
   </Package>
   <Root name="DemandResponseProgram"
         baseClass="http://iec.ch/TC57/CIM100#DemandResponseProgram"
         package="Metering"
         packageURI="http://iec.ch/TC57/CIM100#Package_Metering"
         minOccurs="0"
         maxOccurs="unbounded">
      <Comment>Demand response program.</Comment>
      <Stereotype label="Concrete">http://langdale.com.au/2005/UML#concrete</Stereotype>
      <Simple dataType="http://www.w3.org/2001/XMLSchema#string"
              xstype="string"
              name="mRID"
              baseProperty="http://iec.ch/TC57/CIM100#IdentifiedObject.mRID"
              minOccurs="0"
              maxOccurs="1">
         <Comment>Master resource identifier issued by a model authority. The mRID is unique within an exchange context. Global uniqueness is easily achieved by using a UUID, as specified in RFC 4122, for the mRID. The use of UUID is strongly recommended.</Comment>
         <Comment>For CIMXML data files in RDF syntax conforming to IEC 61970-552, the mRID is mapped to rdf:ID or rdf:about attributes that identify CIM object elements.</Comment>
      </Simple>
      <Simple dataType="http://www.w3.org/2001/XMLSchema#string"
              xstype="string"
              name="type"
              baseProperty="http://iec.ch/TC57/CIM100#DemandResponseProgram.type"
              minOccurs="0"
              maxOccurs="1">
         <Comment>Type of demand response program; examples are CPP (critical-peak pricing), RTP (real-time pricing), DLC (direct load control), DBP (demand bidding program), BIP (base interruptible program). Note that possible types change a lot and it would be impossible to enumerate them all.</Comment>
      </Simple>
      <Instance baseClass="http://iec.ch/TC57/CIM100#Name"
                type="Name"
                name="Names"
                baseProperty="http://iec.ch/TC57/CIM100#IdentifiedObject.Names"
                minOccurs="0"
                maxOccurs="unbounded"
                inverseBaseProperty="http://iec.ch/TC57/CIM100#Name.IdentifiedObject">
         <Comment>All names of this identified object.</Comment>
      </Instance>
      <InverseInstance baseClass="http://iec.ch/TC57/CIM100#IdentifiedObject"
                       type="IdentifiedObject"
                       name="IdentifiedObject"
                       baseProperty="http://iec.ch/TC57/CIM100#Name.IdentifiedObject"
                       minOccurs="0"
                       maxOccurs="1"
                       inverseBaseProperty="http://iec.ch/TC57/CIM100#IdentifiedObject.Names">
         <Comment>Identified object that this name designates.</Comment>
      </InverseInstance>
   </Root>
   <ComplexType name="Name"
                baseClass="http://iec.ch/TC57/CIM100#Name"
                package="Core"
                packageURI="http://iec.ch/TC57/CIM100#Package_Core"
                minOccurs="0"
                maxOccurs="unbounded">
      <Comment>The Name class provides the means to define any number of human readable  names for an object. A name is &lt;b&gt;not&lt;/b&gt; to be used for defining inter-object relationships. For inter-object relationships instead use the object identification 'mRID'.</Comment>
      <Simple dataType="http://www.w3.org/2001/XMLSchema#string"
              xstype="string"
              name="name"
              baseProperty="http://iec.ch/TC57/CIM100#Name.name"
              minOccurs="1"
              maxOccurs="1">
         <Comment>Any free text that name the object.</Comment>
      </Simple>
      <Instance baseClass="http://iec.ch/TC57/CIM100#NameType"
                type="NameType"
                name="NameType"
                baseProperty="http://iec.ch/TC57/CIM100#Name.NameType"
                minOccurs="0"
                maxOccurs="1"
                inverseBaseProperty="http://iec.ch/TC57/CIM100#NameType.Names">
         <Comment>Type of this name.</Comment>
      </Instance>
      <InverseInstance baseClass="http://iec.ch/TC57/CIM100#Name"
                       type="Name"
                       name="Names"
                       baseProperty="http://iec.ch/TC57/CIM100#NameType.Names"
                       minOccurs="0"
                       maxOccurs="unbounded"
                       inverseBaseProperty="http://iec.ch/TC57/CIM100#Name.NameType">
         <Comment>All names of this type.</Comment>
      </InverseInstance>
   </ComplexType>
   <ComplexType name="NameType"
                baseClass="http://iec.ch/TC57/CIM100#NameType"
                package="Core"
                packageURI="http://iec.ch/TC57/CIM100#Package_Core"
                minOccurs="0"
                maxOccurs="unbounded">
      <Comment>Type of name. Possible values for attribute 'name' are implementation dependent but standard profiles may specify types. An enterprise may have multiple IT systems each having its own local name for the same object, e.g. a planning system may have different names from an EMS. An object may also have different names within the same IT system, e.g. localName as defined in CIM version 14. The definition from CIM14 is:</Comment>
      <Comment>The localName is a human readable name of the object. It is a free text name local to a node in a naming hierarchy similar to a file directory structure. A power system related naming hierarchy may be: Substation, VoltageLevel, Equipment etc. Children of the same parent in such a hierarchy have names that typically are unique among them.</Comment>
      <Simple dataType="http://www.w3.org/2001/XMLSchema#string"
              xstype="string"
              name="description"
              baseProperty="http://iec.ch/TC57/CIM100#NameType.description"
              minOccurs="0"
              maxOccurs="1">
         <Comment>Description of the name type.</Comment>
      </Simple>
      <Simple dataType="http://www.w3.org/2001/XMLSchema#string"
              xstype="string"
              name="name"
              baseProperty="http://iec.ch/TC57/CIM100#NameType.name"
              minOccurs="1"
              maxOccurs="1">
         <Comment>Name of the name type.</Comment>
      </Simple>
      <Instance baseClass="http://iec.ch/TC57/CIM100#NameTypeAuthority"
                type="NameTypeAuthority"
                name="NameTypeAuthority"
                baseProperty="http://iec.ch/TC57/CIM100#NameType.NameTypeAuthority"
                minOccurs="0"
                maxOccurs="1"
                inverseBaseProperty="http://iec.ch/TC57/CIM100#NameTypeAuthority.NameTypes">
         <Comment>Authority responsible for managing names of this type.</Comment>
      </Instance>
      <InverseInstance baseClass="http://iec.ch/TC57/CIM100#NameType"
                       type="NameType"
                       name="NameTypes"
                       baseProperty="http://iec.ch/TC57/CIM100#NameTypeAuthority.NameTypes"
                       minOccurs="0"
                       maxOccurs="unbounded"
                       inverseBaseProperty="http://iec.ch/TC57/CIM100#NameType.NameTypeAuthority">
         <Comment>All name types managed by this authority.</Comment>
      </InverseInstance>
   </ComplexType>
   <ComplexType name="NameTypeAuthority"
                baseClass="http://iec.ch/TC57/CIM100#NameTypeAuthority"
                package="Core"
                packageURI="http://iec.ch/TC57/CIM100#Package_Core"
                minOccurs="0"
                maxOccurs="unbounded">
      <Comment>Authority responsible for creation and management of names of a given type; typically an organization or an enterprise system.</Comment>
      <Simple dataType="http://www.w3.org/2001/XMLSchema#string"
              xstype="string"
              name="description"
              baseProperty="http://iec.ch/TC57/CIM100#NameTypeAuthority.description"
              minOccurs="0"
              maxOccurs="1">
         <Comment>Description of the name type authority.</Comment>
      </Simple>
      <Simple dataType="http://www.w3.org/2001/XMLSchema#string"
              xstype="string"
              name="name"
              baseProperty="http://iec.ch/TC57/CIM100#NameTypeAuthority.name"
              minOccurs="1"
              maxOccurs="1">
         <Comment>Name of the name type authority.</Comment>
      </Simple>
   </ComplexType>
   <Root name="UsagePoint"
         baseClass="http://iec.ch/TC57/CIM100#UsagePoint"
         package="Metering"
         packageURI="http://iec.ch/TC57/CIM100#Package_Metering"
         minOccurs="0"
         maxOccurs="unbounded">
      <Comment>Logical or physical point in the network to which readings or events may be attributed. Used at the place where a physical or virtual meter may be located; however, it is not required that a meter be present.</Comment>
      <Stereotype label="Concrete">http://langdale.com.au/2005/UML#concrete</Stereotype>
      <Simple dataType="http://www.w3.org/2001/XMLSchema#string"
              xstype="string"
              name="mRID"
              baseProperty="http://iec.ch/TC57/CIM100#IdentifiedObject.mRID"
              minOccurs="0"
              maxOccurs="1">
         <Comment>Master resource identifier issued by a model authority. The mRID is unique within an exchange context. Global uniqueness is easily achieved by using a UUID, as specified in RFC 4122, for the mRID. The use of UUID is strongly recommended.</Comment>
         <Comment>For CIMXML data files in RDF syntax conforming to IEC 61970-552, the mRID is mapped to rdf:ID or rdf:about attributes that identify CIM object elements.</Comment>
      </Simple>
      <Instance baseClass="http://iec.ch/TC57/CIM100#Name"
                type="Name"
                name="Names"
                baseProperty="http://iec.ch/TC57/CIM100#IdentifiedObject.Names"
                minOccurs="0"
                maxOccurs="unbounded"
                inverseBaseProperty="http://iec.ch/TC57/CIM100#Name.IdentifiedObject">
         <Comment>All names of this identified object.</Comment>
      </Instance>
      <InverseInstance baseClass="http://iec.ch/TC57/CIM100#IdentifiedObject"
                       type="IdentifiedObject"
                       name="IdentifiedObject"
                       baseProperty="http://iec.ch/TC57/CIM100#Name.IdentifiedObject"
                       minOccurs="0"
                       maxOccurs="1"
                       inverseBaseProperty="http://iec.ch/TC57/CIM100#IdentifiedObject.Names">
         <Comment>Identified object that this name designates.</Comment>
      </InverseInstance>
   </Root>
   <Root name="UsagePointGroup"
         baseClass="http://iec.ch/TC57/CIM100#UsagePointGroup"
         package="Metering"
         packageURI="http://iec.ch/TC57/CIM100#Package_Metering"
         minOccurs="0"
         maxOccurs="unbounded">
      <Comment>Abstraction for management of group communications within a two-way AMR system or the data for a group of related usage points. Commands can be issued to all of the usage points that belong to a usage point group using a defined group address and the underlying AMR communication infrastructure.</Comment>
      <Stereotype label="Concrete">http://langdale.com.au/2005/UML#concrete</Stereotype>
      <Simple dataType="http://www.w3.org/2001/XMLSchema#string"
              xstype="string"
              name="mRID"
              baseProperty="http://iec.ch/TC57/CIM100#IdentifiedObject.mRID"
              minOccurs="0"
              maxOccurs="1">
         <Comment>Master resource identifier issued by a model authority. The mRID is unique within an exchange context. Global uniqueness is easily achieved by using a UUID, as specified in RFC 4122, for the mRID. The use of UUID is strongly recommended.</Comment>
         <Comment>For CIMXML data files in RDF syntax conforming to IEC 61970-552, the mRID is mapped to rdf:ID or rdf:about attributes that identify CIM object elements.</Comment>
      </Simple>
      <Instance baseClass="http://iec.ch/TC57/CIM100#Name"
                type="Name"
                name="Names"
                baseProperty="http://iec.ch/TC57/CIM100#IdentifiedObject.Names"
                minOccurs="0"
                maxOccurs="unbounded"
                inverseBaseProperty="http://iec.ch/TC57/CIM100#Name.IdentifiedObject">
         <Comment>All names of this identified object.</Comment>
      </Instance>
      <InverseInstance baseClass="http://iec.ch/TC57/CIM100#IdentifiedObject"
                       type="IdentifiedObject"
                       name="IdentifiedObject"
                       baseProperty="http://iec.ch/TC57/CIM100#Name.IdentifiedObject"
                       minOccurs="0"
                       maxOccurs="1"
                       inverseBaseProperty="http://iec.ch/TC57/CIM100#IdentifiedObject.Names">
         <Comment>Identified object that this name designates.</Comment>
      </InverseInstance>
   </Root>
</Catalog>
```

## Creating and Submitting a Custom Builder

The following approach is recommended for creating, testing and submitting a custom builder.

### Step 1:  Create a Branch to Work In

First, request to be added as collaborator to the **CIMTool-Builders-Library** repository.  Create a branch off of ```main``` to develop your custom builder. A branch will isolate your development work from other branches in the repository.

We ask you to name your branch to match what your XSLT will be named (e.g. ```google-proto-buffers.xsl```).

### Step 2:  Builder Setup Conventions

Once you have created and cloned your branch make a subfolder under ```custom-builders``` that matches the name of your builder minus the ```.xsl``` extension.

Make a copy of the```\builder-submissions\builder-submission-template.md``` file and place it in your newly created subfolder. Rename it to ```builder.md``` and update its contents as outlined in the instructions contained in it.  Feel free to review other builders as examples.

If you are deriving an XSLT from an existing builder then copy the builder into your new folder and rename it. By convention the name of your ```.xsl``` should match the folder name plus the ```.xsl``` file extension. If creating a new XSLT builder be sure to include the Apache 2.0 copyright header as shown next. This is the copyright associated with the XSLT builder and not that included in the generated output:

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!--
  Copyright 2024 UCAIug

  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at

  https://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.

  See the License for the specific language governing permissions and
  limitations under the License.
-->
<xsl:stylesheet exclude-result-prefixes="a"
    version="3.0"
    xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
    xmlns:xs="http://www.w3.org/2001/XMLSchema"
    xmlns:a="http://langdale.com.au/2005/Message#"
    xmlns:sawsdl="http://www.w3.org/ns/sawsdl">

    <xsl:output xmlns:xalan="http://xml.apache.org/xslt" method="xml" omit-xml-declaration="no" indent="yes" xalan:indent-amount="4" />
    <xsl:param name="copyright" />
    <xsl:param name="version"/>
    <xsl:param name="baseURI"/>
    <xsl:param name="ontologyURI"/>
    <xsl:param name="envelope">Profile</xsl:param>
      ...
      ...
      ...
</xsl:stylesheet>
```

### Step 3:  Developing Your Builder

### Overview of Internal Profile Representation

Below is a comprehensive list of elements that may appear in the ```.xml``` internal representation of a profile used as input to XSLT builders. Some builders handle all of them while others ignore in-lined anonymous definitions. Which way you implement your builder is highly dependent on the output that your builder will be generating. For example, the [xsd.xsl](shipped-builders/xsd/builder.md) and [json-schema-draft-07.xsl](shipped-builders/json-schema-draft-07/builder.md) schema builders handle the in-line type definition elements since the specifications for those output types support anonymous in-lined type definitions. However, the [scala.xsl](shipped-builders/scala/builder.md), [profile-doc-rtf.xsl](shipped-builders/profile-doc-rtf/builder.md), and [sql.xsl](shipped-builders/sql/builder.md) builders do not. The recommendation is to handle them in your builder if your builder's generated output type supports them.

The top-level elements that appear in an ```.xml``` profile indicate the various types defined and used in a profile and may include the following:

- **Root** elements - all types declared as 'concrete' in the profile
- **ComplexType** elements - non-concrete types in the profile (i.e. abstract types)
- **CompoundType** elements - types in the profile stereotyped as &lt;&lt;Compound&gt;&gt; in the CIM
- **EnumeratedType** elements - types in the profile that are CIM enumerations
- **SimpleType** elements - types in the profile stereotyped as &lt;&lt;CIMDatatype&gt;&gt; in the CIM

A top-level type further specifies child elements that indicate the attributes or associations defined for it. These elements may be from the set:

- **Simple** elements - represent attributes defined as primitive types in the CIM. These elements will contain an @xstype attribute to specify the primitive.
- **Instance** elements - represent associations in the profile. These elements will contain a @type attribute to specify the type within the profile that the association references.
- **InverseInstance** elements - an **InverseInstance** element will always accompany an **Instance** element in the profile and as the name implies will represent the inverse of the association defined by the **Instance** element. It is specifically included for XSLT builders that may need to know this (e.g. commonly RDFS builders)
- **Reference** elements - also represent associations but ones that must be handled uniquely. These elements will contain a @type attribute to specify the type the reference association is for.  The referent may or may not be represented elsewhere in the profile. When the referent is not represented in the profile, and thus is external to the profile, it may be defined in the contextual model as an abstract class with no concrete sub classes. XSLT builders may transform these elements into a variety of different ways depending on the type of builder and the specific target output.  In the case of [xsd.xsl](shipped-builders/xsd/builder.md) and [json-schema-draft-2020-12.xsl](shipped-builders/json-schema-draft-2020-12/builder.md) builders additional attributes/elements named ```ref``` and ```referenceType``` are generated in the target output. The ```ref``` is used to hold an identifier (i.e. used for the purposes of referencing) and an optional ```referenceType``` used to define the kind of identifier specified by the ```ref``` (e.g. 'mRID' or 'Names.name'). This unique mapping relevant for XSD and JSON schema generation is formally defined within the IEC 62361-100 and IEC 62361-104 standards respectively. Other builders may handle output for **Reference** elements in a completley different manner (see: [rdfs-2020.xsl](shipped-builders/rdfs-2020/builder.md) for example)
- **InverseReference** elements - an **InverseReference** element will always accompany a **Reference** element in the profile and as the name implies will represent the inverse of the association defined by the **Reference** element. It is specifically included for XSLT builders that may need to know this (e.g. commonly RDFS builders)
- **Domain** elements - represent attributes that have a type defined that corresponds to a &lt;&lt;CIMDatatype&gt;&gt; class in the CIM. These types currently resolve to a primitive in CIMTool and therefore the XML child element will contain an @xstype attribute to specify the primitive.
- **Enumerated** elements - represents an attribute in a class who's referent type is an enumeration defined in the profile. These elements will contain a @type attribute to specify the referent enumeration.
- **Choice** elements - represents a union property defined for a class which is an association that references a super class in the profile. In this context, the union property essentially offers a choice for what the referent type can be. Specifically, the options for the referent type are the subclasses of the union superclass defined in the profile.

There are two additional specialized cases of child elements for specifying an attribute or association defined for a type. These represent what might be described as an in-lined anonymous definition for the referent type of the attribute or association. They do not represent an actual UML construct in the CIM but rather a particular profiling approach relevant to specific target schema specifications or generated output types (e.g. XSD and JSON schema or anonymous types in Java) that support such in-line anonymous types (see: [Associations and Anonymous Classes](https://wiki.cimtool.org/Associations_and_Anonymous_Classes.html) and [Why There Are so Many Top Level Definitions in an XML Schema Profile](https://wiki.cimtool.org/Why_There_Are_so_Many_Top_Level_Definitions_in_an_XML_Schema_Profile.html) - these articles also are provided as PDF files in the ```\articles``` folder). The child elements for these specialized cases are:

- **SimpleEnumerated** elements - a variant of **Enumerated** this element represents an attribute in a class who's referent type is an enumeration. However, this variant will not contain a @type attribute to specify the referent enumeration. Rather the enumeration is defined anonymously as an in-lined type definition. See the [xsd.xsl](shipped-builders/xsd/builder.md) and [json-schema-draft-2020-12.xsl](shipped-builders/json-schema-draft-2020-12/builder.md) for examples of builders handling **SimpleEnumerated** elements.
- **Complex** elements - a variant of **ComplexType** this element represents an association in a class who's referent type is a CIM class. However, this element will not contain a @type attribute to specify the referent type. Rather the type is defined anonymously as an in-lined type definition. Again, see the [xsd.xsl](shipped-builders/xsd/builder.md) and [json-schema-draft-2020-12.xsl](shipped-builders/json-schema-draft-2020-12/builder.md) for examples of builders handling **Complex** elements.

Finally, there are a couple of additional elements to highlight that are used for specific purposes within the internal representation:
- **Comment** elements - represent a comment that appears on either a class, attribute or association role end.
- **EnumeratedValue** elements - this element only appears within the **EnumeratedType** or **SimpleEnumerated** elements and represents an enumeration literal defined for the enumeration.
- **SuperType** elements - may be present in either a **Root** or **ComplexType** element to indicate the parent/super type of the class represented by the **Root** or **ComplexType**.

### Development and Testing

Turning now to developing and testing your builder. Provided in the table at the end of this README is a list of tooling both free and commercial for developing and testing XSLT transforms.  This list is by no means comprehensive but is a good starting point. The intent is that one of these options (or a similar option) is used to create, edit and debug your XSLT builder using the ```.xml``` internal representations as input. Each of the individual toolsets outlined has its own instructions on how to run/debug XSLTs in their environments. You can utilize one of the existing stable builders in this library to experiment with in the environment. For an introductory tutorial on XSLT visit the [W3C XSLT tutorial](https://www.w3schools.com/xml/xsl_intro.asp).

Also provided in the ```/builder-submissions``` folder in this repository is the **CIMTool-Test-Project**. This project contains two ```.owl``` profiles along with their respective ```.xml``` files. The **EndDeviceControlsTestProfilWithAnonymousTypes.owl** profile and its corresponding [EndDeviceControlsTestProfilWithAnonymousTypes.xml](builder-submissions/CIMTool-Test-Project/Profiles/EndDeviceControlsTestProfileWithAnonymousTypes.xml) contain all possible XML elements as just described while the **EndDeviceControlsTestProfile.owl** and its corresponding [EndDeviceControlsTestProfile.xml](builder-submissions/CIMTool-Test-Project/Profiles/EndDeviceControlsTestProfile.xml) file are defined without anonymous type definitions. The project has been provided as a matter of convenience. You can use it to create your own profile definitions or utilize just the pre-generated ```.xml``` files for testing your builder depending on whether your builder's target output supports anonymous classes.

### Internal XSLT Parameters Passed By CIMTool

Finally, **CIMTool** internally passes along the following parameters into all XSLT builders:

- **baseURI** - the baseURI is the namespace specified in the Namespace field on the Profile Summary tab for a profile.
- **ontologyURI** - the ontologyURI is the namespace URI specified at the time a CIM schema is imported into a CIMTool project.  It is the URI that appears in the 'Namespace URI' field on properties dialog for the schema. Some builders needed this additional URI for use in their generated output (refer to the [rdfs-2020.xsl](shipped-builders/rdfs-2020/builder.md) for an example).
- **envelope** - the envelope is the value specified in the Name field on the Description tab for the profile.
- **copyright** - the text of a multi-line copyright if one is configured for the project.
- **copyright-single-line** - the text of a single-line copyright if one is configured for the project.

For copyright support you must determine which of the two your builder will use. Most likely your builder will utilize the multiline **copyright**. Refer to existing builders in this library for examples of how these four internally passed parameters are used. Currently only the JSON schema related builders utilize the **copyright-single-line** as JSON has certain constraints related to carriage returns in descriptions and comments within schemas and therefore requies a single line copyright notice.

### NTE (Name/Type/Extension) Assignment

All builders have what is referred to as a NTE (Name/Type/Extension) configuration entry assigned to them when imported into **CIMTool**. This information is used internally by **CIMTool** for different purposes.

The **Name** component of a NTE is static and is auto-assigned during import and is based on the file name of the XSLT file minus the ```.xsl``` extension. You should stick to standard ascii alphanumeric characters and avoid any special characters in your XSLT file name.

For the **Type** component assigned to the builder there are three variants of XSLT transforms that your builder can be categorized in. As to which variant your builder falls into is dependent upon the type of output it will be generating:
- **XSD** - This type should only be used if your are generating an XSD based schema as your output. This is because specialized validation on XSDs are performed after they are generated by this category of builder.
- **TEXT** - This type is typically assigned for builders that generating some type of code such as Java, C#, Python, etc.
- **TRANSFORM** - This is the most generalized category. Examples of existing builders that fall into this category are the [profile-doc-rtf.xsl](shipped-builders/profile-doc-rtf/builder.md) which generates an MS Word document in the RTF (Rich Text Format).

Finally, the **Extension** component of your assigned NTE is literally the extension that will be used for the file generated by your builder. It must be unique relative to other builders in the CIMTool-Builders-Library repository. Example extensions and the corresponding output files for a ficticious profile named SubstationEquipment:
- **schema.json** - SubstationEquipment.schema.json
- **xsd** - SubstationEquipment.xsd
- **simplified-doc.rtf** - SubstationEquipment.simplified-doc.rtf

Please note that you can experiment with your builder and test it by assigning a type of **TEXT** during import and review what **CIMTool** generates.  If there are issues delete the builder using the 'Maintain XSLT Builders' dialog (shown earlier) and reimport your builder as a **TRANSFORM** builder and recheck your output. This has been known to correct issues for certain builders that for example had their encoding set to ASCII:

```XML
<xsl:output indent="no" method="text" encoding="ASCII"/>
```

### Step 4:  Final Pre-Commit Checklist for Review

Once you've determined your builder is ready confirm the following items:

1. The detailed description in your ```builder.md``` has been completed.  If there are particular aspects of your builder that should be highlighted this should be done here. For example, if your builder warrants it, you may include images in your builder's folder and display them within the description section of your builder.md file.  A great example of this is the [profile-doc-rtf.xsl](shipped-builders/profile-doc-rtf/builder.md) builder.
2. You've uploaded a NTE (Name/Type/Extension) Import wizard screenshot named ```import-builder.png``` (e.g. [import-builder.png](shipped-builders/xsd/import-builder.png)) file to your custom builder's folder. You can refer to existing builders as examples.
3. Your builder is using either the ```$copyright``` or ```$copyright-single-line``` parameter to generate a copyright as part of its generated output.  A copyright is relevant for most builders.
4. You have added a new row to the **Community Developed Builders** table in this README. The description in the row entry is typically a simplified version of the description in your builder's ```builders.md``` summarizing your builder.

### Step 5:  Pull Request

When ready, commit your changes, push to GitHub, and create a [Pull](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) request so that your commits can be reviewed and approved for inclusion in the library.

## Commercial and Open Source XSLT Editors/Debuggers

Third-party tooling can be used to create and test new XSLT transforms for use as builders. The table below provides a examples of available free and commercial products.

| | Product / Edition | Description |
|---------|---------|---------|
![image](https://www.eclipse.org/downloads/assets/public/images/logo-eclipse.png) | *Eclipse Foundation's XSLT Project <br/>(Free)* | XSL Tools brings XSLT development to the Eclipse platform. Its scope is to provide basic XSL editing and debugging support to compliment and leverage the XML and source editing support within **Web Tools Platform**. <br/><br/>The XSL Tools project focuses specifically on the Transformation engine of the W3C XSL Specification. This project is concerned with the XSL Transformation language for **XSLT 1.0** and **XSLT 2.0**.
![image](https://raw.githubusercontent.com/DeltaXML/vscode-xslt-tokenizer/ed51154082720b8e2a2f93463054ebdc0bdde074/deltaxmlLogo.png) | *XSLT/XPath extensions for Visual Studio Code<br/>(Free)* | This VSCode extension provides comprehensive language support for **XSLT 3.0** and **XPath 3.1**. Visit the [Quick Start ReadMe](https://marketplace.visualstudio.com/items?itemName=deltaxml.xslt-xpath) or the full [XSLT/XPath User Guide](https://deltaxml.github.io/vscode-xslt-xpath/) for a more comprehensive overview.<br/><br/>For an introduction to the **XSLT 3.0** features available in this XSLT/XPath extension for Visual Studio Code view this [YouTube](https://www.youtube.com/watch?v=fdxfXaJw6SY) video.<br/><br/>**Note:** Microsoft's free [Visual Studio Code](https://code.visualstudio.com/download) is a streamlined code editor with support for development operations like debugging, task running, and version control. It aims to provide just the tools a developer needs for a quick code-build-debug cycle and leaves more complex workflows to fuller featured IDEs, such as [Visual Studio IDE](https://visualstudio.microsoft.com/)
![image](https://www.altova.com/images/logos/xmlspy_2022.png) | *Altova XMLSpy 2022 Enterprise Edition*<br/>*Altova XMLSpy 2022 Professional Edition<br/>(Commercial products)* | **XMLSpy** provides a rich XSLT Editor, Profiler, and Debugger that supports:<ul><li>XSLT 1.0, XSLT 2.0, and XSLT 3.0<li>syntax coloring, line numbering, bookmarking, source folding, & code completion<li>interactive XPath Building and Testing<li>XSLT validation & troubleshooting</ul>For detailed information visit [XSLT/XPath User Guide](https://deltaxml.github.io/vscode-xslt-xpath/) for XMLSpy 2022 Enterprise Edition or [Processing with XSLT and XQuery](https://www.altova.com/manual/XMLSpy/spyprofessional/xsxml_processing.html) using XMLSpy 2022 Professional Edition.
![image](https://www.oxygenxml.com/img/Developer80.png) | *Oxygen XML Developer<br/>(Commercial products)*<br/> | **Oxygen XML Developer** offers a powerful XSLT and XQuery debugger that provides full control over the debugging process. Two dedicated perspectives are available, one for XSLT and one for XQuery debugging, both offering specialized views and actions that allow you to troubleshoot and perfect your documents. Visit their [Oxygen XML Developer overview](https://www.oxygenxml.com/xml_developer.html) page for more details.
![image](https://sparxsystems.com/images/earose.png) | *Enterprise Architect<br/>(Commercial product)* | **Enterprise Architect** provides basic facilities for modeling and executing XSL Transforms that can be used to convert XML input documents into other types of documents. Stylesheets are the XSL components used to transform the content. Note that the XSL processor used in EA is built from the Apache Xalan Project so you will be limited to **XSLT 1.0** compliant transform builders.<br/><br/>Visit the Sparx EA [online user guide](https://sparxsystems.com/enterprise_architect_user_guide/15.0/model_domains/xml_to_html_transformation.html) for information on how to [model](https://sparxsystems.com/enterprise_architect_user_guide/15.0/model_domains/model_an_xsl_transformation.html), [execute](https://sparxsystems.com/enterprise_architect_user_guide/15.0/model_domains/execute_an_xsl_transformation.html) and [debug](https://sparxsystems.com/enterprise_architect_user_guide/15.0/model_domains/debug_an_xsl_transformation.html) XSL transforms from within EA.
**[EditX]** | *EditiX XSLT Editor 2022<br/>(Commercial product)* | <ul><li>XSLT 1.0 / 2.0 / 3.0 editor<li>Debugger with breakpoints (current, next elements, next breakpoint)<li>Debugger with XPath context and XSLT location<li>Syntax colors for XSLT elements and output elements<li>XML Data source preview<li>XML Output preview</ul>Visit the [XSLT Editor](https://www.editix.com/features/xslt_editor.html) page for details.

## License

Distributed under the Apache 2.0 license. See [LICENSE](LICENSE) for more information.
