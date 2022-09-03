# CIMTool-XSLT-Builders

This is the official UCAI CIMug repository for custom **CIMTool** XSLT transform builders and is provided as a public space to create, collaborate and contribute back builders for the benefit of the CIMTool community at large.  This "library" of builders can be used in **CIMTool** to generate various types of target artifacts from a CIMTool profile definition.  

Would you like a custom builder that generates C/C++ objects from your CIMTool profiles? Perhaps you've wished there was a builder to create [Apache Avro](https://avro.apache.org/) schemas for data serialization or one that would automatically generate a [Google Protocol Buffers](https://developers.google.com/protocol-buffers/docs/overview) ```.proto``` file? Now there can be.

Included in this library is the base set of XSLT transforms that comes shipped with **CIMTool** (see the `\shipped` folder for the full list). These have been included to serve as examples or starting points that can be either extended or used as working examples when creating new XSLT transforms.

Please feel free to initiate a [discussion](https://github.com/CIMug-org/CIMTool-XSLT-Builders/discussions) around a new idea for a custom builder or to post a question on the discussions board. To contribute a new custom builder to this library please refer to the HOWTO later in this README.

## Background
**CIMTool** supports a variety of different types of builders that generate artifacts based on a profile. Examples of builders include those that generate XSD schemas, JPA Java source code, RDBMS DDL scripts, RDFS profiles, and RTF Word docs among others.

Further, a subcategory of builders supported by **CIMTool** are those that are based on XSLT transforms. In the below screenshot the builders that are selected are those that generate target files using XSLT transforms:

[![image](/images/cimtool-profile-summary-tab.png)](https://raw.githubusercontent.com/CIMug-org/CIMTool-XSLT-Builders/main/images/cimtool-profile-summary-tab.png)

Starting with the **CIMTool.1.10.0.RC1** release, the ability to import and configure custom user-defined XSLT transforms and have them automatically added to the list of builders was introduced. This new feature opened up a wide range of possibilities for end users to more easily extend the builder capabilities beyond that shipped with the product. No longer does one need to know Eclipse plugin development.

CIMTool's internal XSLT processor was originally the [Apache Xalan](https://xalan.apache.org/) project that shipped as part of the Java JDK/JRE.  Xalan, however, is a W3C [XSLT 1.0](https://www.w3.org/TR/xslt-10/) compliant XSLT processor.  To support the much richer feature set defined in the [XSLT 2.0 specification](https://www.w3.org/TR/xslt-20/) and  [XSLT 3.0 specification](https://www.w3.org/TR/xslt-30/) the XSLT engine has been replaced by [Saxon HE 10.8](https://saxonica.com/html/documentation10/about/index.html).

The screenshots below illustrate how to access these new screens (click on the images to present a larger view):

From the Select Import Wizards Screen... | ...Launch the Import XSLT Builder Screen
---------|---------
[![image](https://user-images.githubusercontent.com/63370413/186978949-cf9cdbfe-e1e4-43ae-b8b6-91e212426a98.png)](https://user-images.githubusercontent.com/63370413/186978949-cf9cdbfe-e1e4-43ae-b8b6-91e212426a98.png) | [![image](https://user-images.githubusercontent.com/63370413/186978126-ec4fca57-53a1-4e16-a998-d3519371ebcc.png)](https://user-images.githubusercontent.com/63370413/186978126-ec4fca57-53a1-4e16-a998-d3519371ebcc.png)

From the Profile Summary Tab... | ...Launch the Manage XSLT Transform Builders Screen
---------|---------
[![image](https://user-images.githubusercontent.com/63370413/186978387-015e3f32-7683-4623-bb8a-017e97102db6.png)](https://user-images.githubusercontent.com/63370413/186978387-015e3f32-7683-4623-bb8a-017e97102db6.png) |[![image](https://user-images.githubusercontent.com/63370413/188269652-758f2e79-e1fe-4c4a-99c3-8cc21923fcc5.png)](https://user-images.githubusercontent.com/63370413/188269652-758f2e79-e1fe-4c4a-99c3-8cc21923fcc5.png)

## Third-Party tools and application to create, test and run a new XSLT builder

This enhancement allows for the use of tools such as Altova’s XMLSpy to create and test XSLT 1.0 transforms and then import and manage them in CIMTool.

## Contributing a new XSLT builder to the library

> NOTE:  We strongly recommend you do not import modified base XSLT transforms over the existing builders shipped with your local CIMTool installation. Doing so will regenerate  existing builder-generated artifacts that may be in your projects if the builder is selected for a profile.
