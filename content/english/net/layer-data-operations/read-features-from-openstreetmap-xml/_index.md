---
title: Read Features from OpenStreetMap XML
linktitle: Read Features from OpenStreetMap XML
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 13
url: /net/layer-data-operations/read-features-from-openstreetmap-xml/
---

## Complete Source Code
```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Aspose.GIS_for.NET.Layers
{
    class ReadFeaturesFromOSMXML
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory";

            //ExStart: ReadFeaturesFromOSMXML
            using (var layer = Drivers.OsmXml.OpenLayer(dataDir + "fountain.osm"))
            {
                // get feratures count
                int count = layer.Count;

                Console.WriteLine("Layer count: " + count);
                // get feature at index 2
                Feature featureAtIndex2 = layer[2];

                // iterate through all features.
                foreach (Feature feature in layer)
                {
                    // handle feature
                    Console.WriteLine(feature.Geometry.AsText());
                }
            }
            //ExEnd: ReadFeaturesFromOSMXML
        }
    }
}

```
