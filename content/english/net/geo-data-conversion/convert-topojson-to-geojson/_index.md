---
title: Convert TopoJSON to GeoJSON
linktitle: Convert TopoJSON to GeoJSON
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 16
url: /net/geo-data-conversion/convert-topojson-to-geojson/
---

## Complete Source Code
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Aspose.GIS.Examples.CSharp.Conversion
{
    class ConvertTopoJsonToGeoJson
    {
        public static void Run()
        {
            //ExStart: ConvertTopoJsonToGeoJson
            var sampleTopoJsonPath = "Your Document Directory" + "sample.topojson";
            var outputFilePath = "Your Document Directory" + "convertedSample_out.geojson";
            VectorLayer.Convert(sampleTopoJsonPath, Drivers.TopoJson, outputFilePath, Drivers.GeoJson);
            //ExEnd: ConvertTopoJsonToGeoJson
        }
    }
}

```
