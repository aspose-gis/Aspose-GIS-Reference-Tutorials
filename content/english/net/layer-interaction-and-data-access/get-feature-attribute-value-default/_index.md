---
title: Get Feature Attribute Value (Default)
linktitle: Get Feature Attribute Value (Default)
second_title: Aspose.GIS .NET API
description: Unlock the power of Aspose.GIS for .NET! Retrieve and manipulate feature attribute values effortlessly with this step-by-step guide. Download your trial now!
type: docs
weight: 14
url: /net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---
## Introduction
Welcome to the world of Aspose.GIS for .NET! In this comprehensive guide, we'll dive into the intricacies of retrieving feature attribute values using the powerful capabilities of Aspose.GIS. Whether you're a seasoned developer or just getting started, this tutorial will provide you with a step-by-step walkthrough, ensuring you harness the full potential of this remarkable tool.
## Prerequisites
Before we embark on this coding adventure, make sure you have the following prerequisites in place:
- A working knowledge of C# and .NET framework.
- Aspose.GIS for .NET installed. If not, download it from [here](https://releases.aspose.com/gis/net/).
- A code editor, such as Visual Studio, to follow along seamlessly.
## Import Namespaces
In your C# project, make sure to include the necessary namespaces:
```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Now, let's break down each example into a series of easy-to-follow steps.
## Example 1: Get Feature Attribute Value (Default)
### Step 1: Set up the Environment
Begin by defining the path to your documents directory:
```csharp
string dataDir = "Your Document Directory";
```
### Step 2: Create a GeoJson Layer
Create a GeoJson layer and define an attribute with default values:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### Step 3: Construct a Feature
Construct a feature using the defined attribute:
```csharp
    Feature feature = layer.ConstructFeature();
```
### Step 4: Retrieve Values
Retrieve attribute values with various scenarios:
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // value == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // value == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // value == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## Example 2: Setting Default Values
### Step 1: Create Another GeoJson Layer
Repeat the process with a different GeoJson layer and a double attribute:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### Step 2: Construct a Feature (Again)
```csharp
    Feature feature = layer.ConstructFeature();
```
### Step 3: Retrieve and Set Values
Retrieve and set attribute values, showcasing defaults:
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // value == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // value == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // value == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
Congratulations! You've successfully harnessed the power of Aspose.GIS for .NET in retrieving and manipulating feature attribute values.
## Conclusion
In this tutorial, we've explored the nuances of retrieving feature attribute values using Aspose.GIS for .NET. With its intuitive API and robust capabilities, Aspose.GIS opens up a world of possibilities for GIS development in .NET environments.
## Frequently Asked Questions
### Is Aspose.GIS compatible with .NET Core?
Yes, Aspose.GIS is fully compatible with .NET Core, providing cross-platform support.
### Can I use Aspose.GIS for commercial projects?
Absolutely! Aspose.GIS comes with a commercial license that allows you to use it in your commercial applications without any restrictions.
### Where can I find additional support and resources?
Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community support and explore the [documentation](https://reference.aspose.com/gis/net/) for in-depth information.
### Is there a free trial available?
Yes, you can explore Aspose.GIS with a free trial. Download it [here](https://releases.aspose.com/).
### How do I obtain a temporary license for testing purposes?
For temporary licenses, visit [here](https://purchase.aspose.com/temporary-license/).
