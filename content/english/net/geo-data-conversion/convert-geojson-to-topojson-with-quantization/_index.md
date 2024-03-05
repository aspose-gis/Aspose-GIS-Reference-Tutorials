---
title: Convert GeoJSON to TopoJSON with Quantization
linktitle: Convert GeoJSON to TopoJSON with Quantization
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 14
url: /net/geo-data-conversion/convert-geojson-to-topojson-with-quantization/
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
    class ConvertGeoJsonToTopoJsonWithQuantization
    {
        public static void Run()
        {
            //ExStart: ConvertGeoJsonToTopoJsonWithQuantization
            // convert GeoJSON to TopoJSON with quantization - transforming doubles to integers
            // to reduce file size.

            string SampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
            var outputFilePath = "Your Document Directory" + "convertedSampleWithQuantization_out.topojson";

            var options = new ConversionOptions
            {
                DestinationDriverOptions = new TopoJsonOptions
                {
                    // There are two ways to set quantization parameters - with Transform property or
                    // with quantization number. Here we specify quantization number.
                    // Quantization number specifies number of expressible values per dimension in a result
                    // coordinates.
                    QuantizationNumber = 100_000,

                    // Alternatively, 'Transform' property can be set (but not simultaneously with quantization number).
                    // Refer to TopoJSON specification for more details on transform object and quantization.
                    //
                    // Transform = new TopoJsonTransform(
                    //     xTranslate: 0,
                    //     yTranslate: 0,
                    //     xScale: 0.0001000010000100001,
                    //     yScale: 0.0001000010000100001),
                }
            };

            VectorLayer.Convert(SampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
            //ExEnd: ConvertGeoJsonToTopoJsonWithQuantization
        }
    }
}

```
