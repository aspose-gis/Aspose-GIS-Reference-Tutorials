---
title: Convert GeoJSON to TopoJSON
linktitle: Convert GeoJSON to TopoJSON
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 11
url: /net/geo-data-conversion/convert-geojson-to-topojson/
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
    class ConvertGeoJsonToTopoJson
    {
        public static void Run()
        {
            //ExStart: ConvertGeoJsonToTopoJson
            string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
            var outputFilePath = "Your Document Directory" + "convertedSample_out.topojson";
            VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson);
            //ExEnd: ConvertGeoJsonToTopoJson
        }
    }
}

```
