---
title: Convert GeoJSON to TopoJSON with Grouping
linktitle: Convert GeoJSON to TopoJSON with Grouping
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 13
url: /net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
---

## Complete Source Code
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;

namespace Aspose.GIS.Examples.CSharp.Conversion
{
    class ConvertGeoJsonToTopoJsonWithGroupingIntoObjects
    {
        public static void Run()
        {
            //ExStart: ConvertGeoJsonToTopoJsonWithGroupingIntoObjects
            string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
            var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";

            var options = new ConversionOptions
            {
                DestinationDriverOptions = new TopoJsonOptions
                {
                    // we set the attribute in GeoJSON layer by which we are going to group into objects
                    ObjectNameAttribute = "group",
                    // if value of "group" is unknown for some feature it should be placed into object with name "unnamed".
                    DefaultObjectName = "unnamed",
                }
            };

            VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
            //ExEnd: ConvertGeoJsonToTopoJsonWithGroupingIntoObjects
        }
    }
}

```
