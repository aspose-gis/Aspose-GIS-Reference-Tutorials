---
title: Convert Shapefile to GeoJSON
linktitle: Convert Shapefile to GeoJSON
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 15
url: /net/geo-data-conversion/convert-shapefile-to-geojson/
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
    class ConvertShapeFileToGeoJSON
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory";
            string shapefilePath = dataDir + "InputShapeFile.shp";
            string jsonPath = dataDir + "output_out.json";

            //ExStart: ConvertShapeFileToGeoJSON
            VectorLayer.Convert(shapefilePath, Drivers.Shapefile, jsonPath, Drivers.GeoJson);
            //ExEnd: ConvertShapeFileToGeoJSON
        }
    }
}

```
