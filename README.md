# CIMTool-XSLT-Builders

This is the official UCAI CIMug repository for custom **CIMTool** XSLT transform builders and is provided as a public space to create, collaborate and contribute back builders for the benefit of the CIMTool community at large.  This "library" of builders can be used in **CIMTool** to generate various types of target artifacts from a CIMTool profile definition.  

Would you like a custom builder that generates C/C++ objects from your CIMTool profiles? Perhaps you've wished there was a builder to create [Apache Avro](https://avro.apache.org/) schemas for data serialization or one that would automatically generate a [Google Protocol Buffers](https://developers.google.com/protocol-buffers/docs/overview) ```.proto``` file? Now there can be.

Included in this library is the base set of XSLT transforms that comes shipped with **CIMTool** (see the `\shipped` folder for the full list). These have been included to serve as examples or starting points that can be either extended or used as working examples when creating new XSLT transforms.

Please feel free to initiate a [discussion](https://github.com/CIMug-org/CIMTool-XSLT-Builders/discussions) around a new idea for a custom builder or to post a question on the discussions board. To contribute a new custom builder to this library please refer to the HOWTO later in this README.

## Background
**CIMTool** supports a variety of different types of builders that generate artifacts based on a profile. Examples of builders include those that generate XSD schemas, JPA Java source code, RDBMS DDL scripts, RDFS profiles, and RTF Word docs among others.

Further, a subcategory of builders supported by **CIMTool** are those that are based on XSLT transforms. In the below screenshot the builders that are selected are those that generate target files using XSLT transforms:

[![image](https://raw.githubusercontent.com/CIMug-org/CIMTool-XSLT-Builders/main/images/cimtool-profile-summary-tab.png)](https://raw.githubusercontent.com/CIMug-org/CIMTool-XSLT-Builders/main/images/cimtool-profile-summary-tab.png)

Starting with the **CIMTool.1.10.0.RC1** release, the ability to import and configure custom user-defined XSLT transforms and have them automatically added to the list of builders was introduced. This new feature opened up a wide range of possibilities for end users to more easily extend the builder capabilities beyond that shipped with the product. No longer does one need to know Eclipse plugin development.

CIMTool's internal XSLT processor was originally the [Apache Xalan](https://xalan.apache.org/) project that shipped as part of the Java JDK/JRE.  Xalan, however, is a W3C [XSLT 1.0](https://www.w3.org/TR/xslt-10/) compliant XSLT processor.  To support the much richer feature sets defined in the [XSLT 2.0](https://www.w3.org/TR/xslt-20/) and [XSLT 3.0](https://www.w3.org/TR/xslt-30/) specifications the XSLT processing engine was replaced by  [Saxon HE 10.8](https://saxonica.com/html/documentation10/about/index.html) in the **CIMTool.1.10.0** production release.

The screenshots below illustrate how to access these new screens (click on the images to present a larger view):

From the Select Import Wizards Screen... | ...Launch the "Import XSLT Transform Builder" Screen
---------|---------
[![image](https://user-images.githubusercontent.com/63370413/186978949-cf9cdbfe-e1e4-43ae-b8b6-91e212426a98.png)](https://user-images.githubusercontent.com/63370413/186978949-cf9cdbfe-e1e4-43ae-b8b6-91e212426a98.png) | [![image](https://user-images.githubusercontent.com/63370413/186978126-ec4fca57-53a1-4e16-a998-d3519371ebcc.png)](https://user-images.githubusercontent.com/63370413/186978126-ec4fca57-53a1-4e16-a998-d3519371ebcc.png)

From the Profile Summary Tab... | ...Launch the "Manage XSLT Transform Builders" Screen
---------|---------
[![image](https://user-images.githubusercontent.com/63370413/186978387-015e3f32-7683-4623-bb8a-017e97102db6.png)](https://user-images.githubusercontent.com/63370413/186978387-015e3f32-7683-4623-bb8a-017e97102db6.png) |[![image](https://user-images.githubusercontent.com/63370413/188269652-758f2e79-e1fe-4c4a-99c3-8cc21923fcc5.png)](https://user-images.githubusercontent.com/63370413/188269652-758f2e79-e1fe-4c4a-99c3-8cc21923fcc5.png)

## Third-Party tools and application to create, test and run a new XSLT builder

Vendor / Product | Description
---------|---------
<nobr>*Altova XMLSpy 2022 Enterprise Edition*</nobr></br><nobr>*Altova XMLSpy 2022 Professional Edition</br>(Commercial products)*</nobr> | **XMLSpy** provides a rich XSLT Editor, Profiler, and Debugger:<ul><li>- [x]Create and Edit XSLT Documents<li>Support for XSLT 1.0, XSLT 2.0, and XSLT 3.0<li>Integration with RaptorXML Servers for faster transformation<li>Syntax coloring, line numbering, bookmarking, & source folding<li>Code completion & context-sensitive entry helpers<li>Interactive XPath Builder and Tester<li>Revolutionary XSLT back-mapping<li>XSLT validation & troubleshooting<li>XSL Outline window<li>Info window for viewing & configuring related files<li>Support for Java, JavaScript, C#, & VBScript in XSLT<li>Integrated Web browser</ul>For detailed information Visit [XSLT Processing](https://www.altova.com/manual/XMLSpy/spyenterprise/xsxslt_processing.html) using Altova's XMLSpy 2022 Enterprise Edition or [Processing with XSLT and XQuery](https://www.altova.com/manual/XMLSpy/spyprofessional/xsxml_processing.html) using Altova's XMLSpy 2022 Professional Edition</br></br>([see XMLSpy's edition comparison chart](https://www.altova.com/xmlspy-xml-editor/editions))
<nobr>*Oxygen XML Editor</br>(Commercial product)*</nobr></br><nobr> | **XMLSpy** provides a rich XSLT Editor, Debugger and Profiler. Visit the [Altova XMLSpy 2022 Enterprise Edition XSLT](https://www.altova.com/manual/XMLSpy/spyenterprise/xsxslt_processing.html) page for full details.
<nobr>*EditiX XSLT Editor 2022</br>(Commercial product)*<nobr> | XSLT 1.0 / 2.0 / 3.0 editor</br>Debugger with breakpoints (current, next elements, next breakpoint)</br>Debugger with XPath context and XSLT location</br>Syntax colors for XSLT elements and output elements</br>XML Data source preview</br>XML Output preview</br></br>See the [XSLT Editor](https://www.editix.com/features/xslt_editor.html) page for full details.</br></br>![image](https://www.editix.com/features/images/xsltEditor.png)

This enhancement allows for the use of tools such as Altova’s XMLSpy to create and test XSLT 1.0 transforms and then import and manage them in CIMTool.

## Contributing a new XSLT builder to the library

> NOTE:  We strongly recommend you do not import modified base XSLT transforms over the existing builders shipped with your local CIMTool installation. Doing so will regenerate  existing builder-generated artifacts that may be in your projects if the builder is selected for a profile.
