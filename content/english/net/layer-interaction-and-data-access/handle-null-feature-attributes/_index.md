---
title: Handle Null Feature Attributes
linktitle: Handle Null Feature Attributes
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 13
url: /net/layer-interaction-and-data-access/handle-null-feature-attributes/
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
    class GetValueOfNullFeatureAttribute
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory";

            //ExStart: GetValueOfNullFeatureAttribute
            using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
            {
                int index = 0;
                foreach (Feature feature in layer)
                {
                    DateTime? date = feature.GetValue<DateTime?>("dob");
                    Console.WriteLine("Feature #{0}", index);
                    Console.WriteLine("\tAttribute value present: {0}", date.HasValue);
                    if (date.HasValue)
                    {
                        Console.WriteLine("\tAttribute value: {0}", date.Value);
                    }
                    index++;
                }
            }
            //ExEnd: GetValueOfNullFeatureAttribute
        }
    }
}

```
