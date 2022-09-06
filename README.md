# CIMTool-XSLT-Builders

This is the official UCAI CIMug repository for custom **CIMTool** XSLT transform builders and is provided as a public space to create, collaborate and contribute back builders for the benefit of the CIMTool community at large.  This "library" of builders can be used in **CIMTool** to generate various types of target artifacts from a CIMTool profile definition.  

Would you like a custom builder that generates C/C++ objects from your CIMTool profiles? Perhaps you've wished there was a builder to create [Apache Avro](https://avro.apache.org/) schemas for data serialization or one that would automatically generate a [Google Protocol Buffers](https://developers.google.com/protocol-buffers/docs/overview) ```.proto``` file? Now there can be.

Included in this library is the base set of XSLT transforms that comes shipped with **CIMTool** (see the `\shipped` folder for the full list). These have been included to serve as examples or starting points that can be either extended or used as working examples when creating new XSLT transforms.

Please feel free to initiate a [discussion](https://github.com/CIMug-org/CIMTool-XSLT-Builders/discussions) around a new idea for a custom builder or to post a question on the discussions board. To contribute a new custom builder to this library please refer to the HOWTO later in this README.

## Background
**CIMTool** ships with a variety of different types of builders that generate artifacts based on a profile. Examples of existing builders include those that generate XSD schemas, JPA Java source code, RDBMS DDL scripts, RDFS profiles, and RTF Word docs among others.

Further, a subcategory of builders supported by **CIMTool** are those that are based on XSLT transforms. In the below screenshot the builders that are selected are those that generate target files using XSLT transforms (click the image to enlarge):

[![image](https://raw.githubusercontent.com/CIMug-org/CIMTool-XSLT-Builders/main/images/cimtool-profile-summary-tab.png)](https://raw.githubusercontent.com/CIMug-org/CIMTool-XSLT-Builders/main/images/cimtool-profile-summary-tab.png)

Starting with the **CIMTool.1.10.0.RC1** release, the ability to import and configure custom user-defined XSLT transforms and have them automatically added to the list of builders was introduced. This new feature opened up a wide range of possibilities for end users to more easily extend the builder capabilities beyond that shipped with the product. No longer do you need to know Eclipse plugin development.

CIMTool's internal XSLT processor was originally the [Apache Xalan](https://xalan.apache.org/) project that shipped as part of the Java JDK/JRE.  Xalan, however, is a W3C [XSLT 1.0](https://www.w3.org/TR/xslt-10/) compliant XSLT processor.  To support the much richer feature sets defined in the [XSLT 2.0](https://www.w3.org/TR/xslt-20/) and [XSLT 3.0](https://www.w3.org/TR/xslt-30/) specifications the XSLT processing engine was replaced by  [Saxon HE 10.8](https://saxonica.com/html/documentation10/about/index.html) in the **CIMTool.1.10.0** production release.

The screenshots below illustrate how to access the new import and maintenance screens (click on the images to present a larger view):

From the "Import" wizards screen... | ...Launch the "Import XSLT Transform Builder" screen
---------|---------
[![image](https://user-images.githubusercontent.com/63370413/186978949-cf9cdbfe-e1e4-43ae-b8b6-91e212426a98.png)](https://user-images.githubusercontent.com/63370413/186978949-cf9cdbfe-e1e4-43ae-b8b6-91e212426a98.png) | [![image](https://user-images.githubusercontent.com/63370413/186978126-ec4fca57-53a1-4e16-a998-d3519371ebcc.png)](https://user-images.githubusercontent.com/63370413/186978126-ec4fca57-53a1-4e16-a998-d3519371ebcc.png)

From the "Profile Summary" tab... | ...Launch the "Manage XSLT Transform Builders" screen
---------|---------
[![image](https://user-images.githubusercontent.com/63370413/186978387-015e3f32-7683-4623-bb8a-017e97102db6.png)](https://user-images.githubusercontent.com/63370413/186978387-015e3f32-7683-4623-bb8a-017e97102db6.png) |[![image](https://user-images.githubusercontent.com/63370413/188269652-758f2e79-e1fe-4c4a-99c3-8cc21923fcc5.png)](https://user-images.githubusercontent.com/63370413/188269652-758f2e79-e1fe-4c4a-99c3-8cc21923fcc5.png)

## Commercial and Open Source XSLT Editors/Debuggers

Third-party tooling can be used to create and test new XSLT transforms for use as builders. The table below provides a examples of both free and commercial products that can be used to develop **CIMTool** XSLT-based builders.

</br> | Product / Edition | Description
---------|---------|---------
![image](https://raw.githubusercontent.com/DeltaXML/vscode-xslt-tokenizer/ed51154082720b8e2a2f93463054ebdc0bdde074/deltaxmlLogo.png) | <nobr>*XSLT/XPath extensions for Visual Studio Code</br>(Free)*</nobr> | This VSCode extension provides comprehensive language support for **XSLT 3.0** and **XPath 3.1**. Visit the [Quick Start ReadMe](https://marketplace.visualstudio.com/items?itemName=deltaxml.xslt-xpath) or the full [XSLT/XPath User Guide](https://deltaxml.github.io/vscode-xslt-xpath/) for a more comprehensive overview.</br></br>For an introduction to the **XSLT 3.0** features available in this XSLT/XPath extension for Visual Studio Code view this [YouTube](https://www.youtube.com/watch?v=fdxfXaJw6SY) video.</br></br>**Note:** Microsoft's free [Visual Studio Code](https://code.visualstudio.com/download) is a streamlined code editor with support for development operations like debugging, task running, and version control. It aims to provide just the tools a developer needs for a quick code-build-debug cycle and leaves more complex workflows to fuller featured IDEs, such as [Visual Studio IDE](https://visualstudio.microsoft.com/)
![image](https://www.altova.com/images/logos/xmlspy_2022.png) | <nobr>*Altova XMLSpy 2022 Enterprise Edition*</nobr></br><nobr>*Altova XMLSpy 2022 Professional Edition</br>(Commercial products)*</nobr> | **XMLSpy** provides a rich XSLT Editor, Profiler, and Debugger that supports:<ul><li>XSLT 1.0, XSLT 2.0, and XSLT 3.0<li>syntax coloring, line numbering, bookmarking, source folding, & code completion<li>interactive XPath Building and Testing<li>XSLT validation & troubleshooting</ul>For detailed information visit [XSLT/XPath User Guide](https://deltaxml.github.io/vscode-xslt-xpath/) for XMLSpy 2022 Enterprise Edition or [Processing with XSLT and XQuery](https://www.altova.com/manual/XMLSpy/spyprofessional/xsxml_processing.html) using XMLSpy 2022 Professional Edition.
![image](https://www.oxygenxml.com/img/Developer80.png) | <nobr>*Oxygen XML Developer</br>(Commercial products)*</nobr></br><nobr> | **Oxygen XML Developer** offers a powerful XSLT and XQuery debugger that provides full control over the debugging process. Two dedicated perspectives are available, one for XSLT and one for XQuery debugging, both offering specialized views and actions that allow you to troubleshoot and perfect your documents. Visit their [Oxygen XML Developer overview](https://www.oxygenxml.com/xml_developer.html) page for more details.
![image](https://sparxsystems.com/images/earose.png) | <nobr>*Enterprise Architect</br>(Commercial product)*</nobr>| **Enterprise Architect** provides basic facilities for modeling and executing XSL Transforms that can be used to convert XML input documents into other types of documents. Stylesheets are the XSL components used to transform the content. Note that the XSL processor used in EA is built from the Apache Xalan Project so you will be limited to **XSLT 1.0** compliant transform builders.</br></br>Visit the Sparx EA [online user guide](https://sparxsystems.com/enterprise_architect_user_guide/15.0/model_domains/xml_to_html_transformation.html) for information on how to [model](https://sparxsystems.com/enterprise_architect_user_guide/15.0/model_domains/model_an_xsl_transformation.html), [execute](https://sparxsystems.com/enterprise_architect_user_guide/15.0/model_domains/execute_an_xsl_transformation.html) and [debug](https://sparxsystems.com/enterprise_architect_user_guide/15.0/model_domains/debug_an_xsl_transformation.html) XSL transforms from within EA.
**[EditX]** |<nobr>*EditiX XSLT Editor 2022</br>(Commercial product)*</nobr> | <ul><li>XSLT 1.0 / 2.0 / 3.0 editor<li>Debugger with breakpoints (current, next elements, next breakpoint)<li>Debugger with XPath context and XSLT location<li>Syntax colors for XSLT elements and output elements<li>XML Data source preview<li>XML Output preview</ul>Visit the [XSLT Editor](https://www.editix.com/features/xslt_editor.html) page for details.

## Contributing a new XSLT builder to the library

> NOTE:  We strongly recommend you do not import modified base XSLT transforms over the existing builders shipped with your local CIMTool installation. Doing so will regenerate  existing builder-generated artifacts that may be in your projects if the builder is selected for a profile.

## License

Distributed under the Apache 2.0 license. See [LICENSE](LICENSE) for more information.
