---
title: Get Feature Attribute Value
linktitle: Get Feature Attribute Value
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 12
url: /net/layer-interaction-and-data-access/get-feature-attribute-value/
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
    class GetValueOfAFeatureAttribute
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory";

            //ExStart: GetValueOfAFeatureAttribute
            using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
            {
                for (int i = 0; i < layer.Count; i++)
                {
                    Feature feature = layer[i];
                    Console.WriteLine("Entry {0} information\n ========================", i);

                    // case 1
                    string nameValue = feature.GetValue<string>("name"); // attribute name is case-sensitive
                    int ageValue = feature.GetValue<int>("age");
                    string dobValue = feature.GetValue<DateTime>("dob").ToString();
                    Console.WriteLine("Attribute value for feature #{0} is: {1}, {2}", nameValue, ageValue, dobValue);

                    // case 2
                    var objName = feature.GetValue("name"); // attribute name is case-sensitive
                    var objAge = feature.GetValue("age");
                    var objDob = feature.GetValue("dob");
                    Console.WriteLine("Attribute object for feature #{0} is: {1}, {2}", objName, objAge, objDob);
                }
            }
            //ExEnd: GetValueOfAFeatureAttribute
        }
    }
}

```
