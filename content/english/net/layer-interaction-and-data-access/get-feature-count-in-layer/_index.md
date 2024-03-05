---
title: Get Feature Count in Layer
linktitle: Get Feature Count in Layer
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 10
url: /net/layer-interaction-and-data-access/get-feature-count-in-layer/
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
    class GetFeatureCountInLayer
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory" ;

            //ExStart: GetFeatureCountInLayer
            using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
            {
                Console.WriteLine("Total Features in this file: " + layer.Count);
            }
            //ExEnd: GetFeatureCountInLayer
        }
    }
}

```
