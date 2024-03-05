---
title: Convert GeoJSON to TopoJSON with Specific Object Name
linktitle: Convert GeoJSON to TopoJSON with Specific Object Name
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 12
url: /net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/
---

## Complete Source Code
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Aspose.GIS.Examples.CSharp.Conversion
{
    class ConvertGeoJsonToTopoJsonAndSpecifyObjectName
    {
        public static void Run()
        {
            //ExStart: ConvertGeoJsonToTopoJsonAndSpecifyObjectName
            string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
            var outputFilePath = "Your Document Directory" + "convertedSampleWithObjectName_out.topojson";

            var options = new ConversionOptions
            {
                DestinationDriverOptions = new TopoJsonOptions
                {
                    // specify the name of the object where features should be written
                    DefaultObjectName = "name_of_the_object",
                }
            };
            VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
            //ExEnd: ConvertGeoJsonToTopoJsonAndSpecifyObjectName
        }
    }
}

```
