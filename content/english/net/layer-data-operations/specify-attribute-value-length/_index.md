---
title: Specify Attribute Value Length
linktitle: Specify Attribute Value Length
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 18
url: /net/layer-data-operations/specify-attribute-value-length/
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
    class SpecifyAttributeValueLength
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory";
            //ExStart: SpecifyAttributeValueLength
            using (VectorLayer layer = VectorLayer.Create(dataDir + "SpecifyAttributeValueLength_out.shp", Drivers.Shapefile))
            {
                // add attributes before adding features
                FeatureAttribute attribute = new FeatureAttribute("wide", AttributeDataType.String);
                attribute.Width = 120;
                layer.Attributes.Add(attribute);

                Feature feature = layer.ConstructFeature();
                feature.SetValue("wide", "this string can be up to 120 characters long now.");
                layer.Add(feature);
            }
            //ExEnd: SpecifyAttributeValueLength
        }
    }
}

```
