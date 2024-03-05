---
title: Read Features from MapInfo Tab
linktitle: Read Features from MapInfo Tab
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 12
url: /net/layer-data-operations/read-features-from-mapinfo-tab/
---

## Complete Source Code
```csharp
using Aspose.Gis;
using System;
using System.IO;

namespace Aspose.GIS.Examples.CSharp.Layers
{
    class ReadFeaturesFromMapInfoTab
    {
        public static void Run()
        {
            //ExStart: ReadFeaturesFromMapInfoTab
            string TestDataPath = "Your Document Directory";
            using (var layer = Drivers.MapInfoTab.OpenLayer(Path.Combine(TestDataPath, "data.tab")))
            {
                Console.WriteLine($"Number of features is {layer.Count}.");

                var lastGeometry = layer[layer.Count - 1].Geometry;
                Console.WriteLine($"Last geometry is {lastGeometry.AsText()}.");

                foreach (Feature feature in layer)
                {
                    Console.WriteLine(feature.Geometry.AsText());
                }
            }
            //ExEnd: ReadFeaturesFromMapInfoTab
        }
    }
}

```
