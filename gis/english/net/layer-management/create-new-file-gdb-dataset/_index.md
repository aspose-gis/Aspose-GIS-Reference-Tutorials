---
title: Create New File GDB Dataset
linktitle: Create New File GDB Dataset
second_title: Aspose.GIS .NET API
description: Explore Aspose.GIS for .NET to effortlessly create and manage GIS datasets. Download now for seamless geospatial development. #Aspose #GIS
weight: 10
url: /net/layer-management/create-new-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create New File GDB Dataset

## Introduction
In the realm of geospatial development, Aspose.GIS for .NET stands out as a powerful toolkit for managing and manipulating Geographic Information System (GIS) data. Whether you're a seasoned developer or just starting your journey into GIS, this tutorial will walk you through the process of creating a new File Geodatabase (GDB) dataset using Aspose.GIS for .NET.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites in place:
- Aspose.GIS for .NET: Make sure you have the Aspose.GIS for .NET library installed. You can download it from the [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).
- Development Environment: Set up your development environment with a compatible IDE, such as Visual Studio, and have a basic understanding of .NET programming.
- Document Directory: Replace "Your Document Directory" in the code snippet with the appropriate path where you want to store your GDB dataset.
- Familiarity with C#: This tutorial assumes you are familiar with C# programming language.
## Import Namespaces
In the initial steps, import the necessary namespaces to leverage Aspose.GIS functionality in your .NET application:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Step 1: Create a New File GDB Dataset
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Output: 0
    // Continue with subsequent steps...
}
```
Explanation: In this step, we create a new GDB dataset using the `Dataset.Create` method. We specify the path and the driver (FileGdb) to create a File Geodatabase. The console output displays the initial layer count, which is zero at this point.
## Step 2: Create and Populate Layer_1
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
Explanation: This step involves creating a layer named "layer_1" within the dataset. It defines an attribute named "value" of integer type and populates the layer with ten features, each having a point geometry.
## Step 3: Create and Populate Layer_2
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Explanation: Here, we create a second layer named "layer_2" and add a single feature with a line string geometry.
## Step 4: Check the Updated Layers Count
```csharp
Console.WriteLine(dataset.LayersCount); // Output: 2
```
Explanation: Finally, we check the updated layers count after adding the two layers. In this case, the output should be 2.
## Conclusion
Congratulations! You've successfully created a new File GDB dataset and populated it with layers using Aspose.GIS for .NET. This tutorial provides a foundational understanding of working with geospatial data in a .NET environment.
## Frequently Asked Questions
### Q: Can I use Aspose.GIS for .NET with other GIS libraries?
Aspose.GIS for .NET is a standalone toolkit; however, you can integrate it with other .NET libraries to enhance functionality.
### Q: Is there a community forum for Aspose.GIS support?
Yes, you can find support and discussions on the [Aspose.GIS Forum](https://forum.aspose.com/c/gis/33).
### Q: How can I obtain a temporary license for Aspose.GIS?
Visit the [Temporary License](https://purchase.aspose.com/temporary-license/) page for information on obtaining a temporary license.
### Q: Are there additional examples and documentation available?
Explore the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/) for more examples and detailed information.
### Q: Where can I purchase Aspose.GIS for .NET?
You can purchase Aspose.GIS for .NET on the [purchase page](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
