---
title: Add Layer to File GDB Dataset
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 16
url: /net/layer-management/add-layer-to-file-gdb-dataset/
---

## Complete Source Code
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Aspose.GIS_for.NET.Layers
{
    class AddLayerToFileGdbDataset
    {
        public static void Run()
        {
            //ExStart: AddLayerToFileGdbDataset
            // -- copy test dataset, to avoid modification of test data.

            var path = "Your Document Directory" + "ThreeLayers.gdb";
            var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
            RunExamples.CopyDirectory(path, datasetPath);

            // --

            using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
            {
                Console.WriteLine(dataset.CanCreateLayers); // True

                using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
                {
                    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
                    var feature = layer.ConstructFeature();
                    feature.SetValue("Name", "Name_1");
                    feature.Geometry = new Point(12.21, 23.123, 20, -200);
                    layer.Add(feature);
                }

                using (var layer = dataset.OpenLayer("data"))
                {
                    Console.WriteLine(layer.Count); // 1
                    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
                }
            }
            //ExEnd: AddLayerToFileGdbDataset
        }
    }
}

```
