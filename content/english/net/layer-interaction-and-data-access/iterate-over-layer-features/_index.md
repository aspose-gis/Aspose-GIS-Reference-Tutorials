---
title: Iterate Over Layer Features
linktitle: Iterate Over Layer Features
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 21
url: /net/layer-interaction-and-data-access/iterate-over-layer-features/
---

## Complete Source Code
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Aspose.GIS.Examples.CSharp.Layers
{
    class IterateOverFeaturesInLayer
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory"; 

            //ExStart: IterateOverFeaturesInLayer
            using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
            {
                foreach (Feature feature in layer)
                {
                    Console.WriteLine(feature.Geometry.AsText());
                }
            }
            //ExEnd: IterateOverFeaturesInLayer
        }
    }
}

```
