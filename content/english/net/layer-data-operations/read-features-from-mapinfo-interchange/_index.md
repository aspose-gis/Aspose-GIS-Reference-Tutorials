---
title: Read Features from MapInfo Interchange
linktitle: Read Features from MapInfo Interchange
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 11
url: /net/layer-data-operations/read-features-from-mapinfo-interchange/
---

## Complete Source Code
```csharp
using Aspose.Gis;
using System;
using System.IO;

namespace Aspose.GIS.Examples.CSharp.Layers
{
    class ReadFeaturesFromMapInfoInterchange
    {
        public static void Run()
        {
            //ExStart: ReadFeaturesFromMapInfoInterchange
            string dataDir = "Your Document Directory";
            using (var layer = Drivers.MapInfoInterchange.OpenLayer(Path.Combine(dataDir, "data.mif")))
            {
                Console.WriteLine($"Number of features is {layer.Count}.");

                var lastGeometry = layer[layer.Count - 1].Geometry;
                Console.WriteLine($"Last geometry is {lastGeometry.AsText()}.");

                foreach (Feature feature in layer)
                {
                    Console.WriteLine(feature.Geometry.AsText());
                }
            }
            //ExEnd: ReadFeaturesFromMapInfoInterchange
        }
    }
}

```
