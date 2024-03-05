---
title: Get All Feature Attribute Values
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 15
url: /net/layer-interaction-and-data-access/get-all-feature-attribute-values/
---

## Complete Source Code
```csharp
using System;
using Aspose.Gis;

namespace Aspose.GIS.Examples.CSharp.Layers
{
    class GetValuesOfAFeatureAttribute
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory";

            //ExStart: GetValuesOfAFeatureAttribute
            using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
            {
                foreach (var feature in layer)
                {
                    // reads all the attributes into an array.
                    object[] all = new object[3];
                    feature.GetValues(all);
                    Console.WriteLine("all    : {0}, {1}, {2}", all);

                    // reads several the attributes into an array.
                    object[] several = new object[2];
                    feature.GetValues(several);
                    Console.WriteLine("several: {0}, {1}", several);

                    // reads the attributes as dump of objects.
                    var dump = feature.GetValuesDump();
                    Console.WriteLine("dump   : {0}, {1}, {2}", dump);

                    Console.WriteLine();
                }
            }
            //ExEnd: GetValuesOfAFeatureAttribute
        }
    }
}
```
