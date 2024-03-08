---
title: Create New Shapefile
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
description: Learn how to create a new shapefile using Aspose.GIS for .NET. Follow our step-by-step guide and unlock the power of spatial data manipulation.
type: docs
weight: 12
url: /net/layer-management/create-new-shapefile/
---
## Introduction
If you're delving into geographic information systems (GIS) development with .NET, Aspose.GIS is your go-to solution. This powerful library empowers developers to work seamlessly with spatial data, and in this tutorial, we'll guide you through the process of creating a new shapefile using Aspose.GIS for .NET.
## Prerequisites
Before we jump into the tutorial, make sure you have the following prerequisites in place:
- Basic understanding of C# programming language.
- Visual Studio installed on your machine.
- Aspose.GIS for .NET library. You can download it [here](https://releases.aspose.com/gis/net/).
## Import Namespaces
Start by importing the necessary namespaces to leverage the functionality of Aspose.GIS:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Step 1: Set Up Your Project
Begin by creating a new C# project in Visual Studio and include the Aspose.GIS library.
## Step 2: Define the Document Directory
```csharp
string dataDir = "Your Document Directory";
```
Replace "Your Document Directory" with the actual path where you want to save your new shapefile.
## Step 3: Create a VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
This code segment sets up the vector layer and defines attributes for your features.
## Step 4: Add Features
### Case 1: Sets Values Individually
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
### Case 2: Sets New Values for All Attributes
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## Conclusion
Congratulations! You've successfully created a new shapefile using Aspose.GIS for .NET. This tutorial covered the basics of setting up your project, defining attributes, and adding features. As you explore further, refer to the [documentation](https://reference.aspose.com/gis/net/) for advanced features and functionalities.
## Frequently Asked Questions
### Q: Can I use Aspose.GIS with other programming languages?
Aspose.GIS primarily supports .NET, but there are versions available for Java as well.
### Q: Is there a free trial available?
Yes, you can access the free trial [here](https://releases.aspose.com/).
### Q: Where can I find support for Aspose.GIS?
Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community support and discussions.
### Q: How can I obtain a temporary license?
Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
### Q: Where can I purchase Aspose.GIS for .NET?
You can buy the library [here](https://purchase.aspose.com/buy).
