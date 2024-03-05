---
title: Convert GeoJSON Layer to File GDB
linktitle: Convert GeoJSON Layer to File GDB
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 17
url: /net/layer-management/convert-geojson-layer-to-file-gdb/
---

## Complete Source Code
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Aspose.GIS_for.NET.Layers
{
    class ConvertGeoJsonLayerToLayerInFileGdbDataset
    {
        public static void Run()
        {
            //ExStart: ConvertGeoJsonLayerToLayerInFileGdbDataset
            var geoJsonPath = "Your Document Directory" + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
            using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
            {
                layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
                layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));

                Feature firstFeature = layer.ConstructFeature();
                firstFeature.Geometry = new Point(33.97, -118.25);
                firstFeature.SetValue("name", "John");
                firstFeature.SetValue("age", 23);
                layer.Add(firstFeature);

                Feature secondFeature = layer.ConstructFeature();
                secondFeature.Geometry = new Point(35.81, -96.28);
                secondFeature.SetValue("name", "Mary");
                secondFeature.SetValue("age", 54);
                layer.Add(secondFeature);
            }

            // --

            // -- copy test dataset, to avoid modification of test data.
            
            var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
            var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
            RunExamples.CopyDirectory(sourceFile, destinationFile);

            // --

            using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
            {
                using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
                using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
                {
                    fileGdbLayer.CopyAttributes(geoJsonLayer);
                    foreach (var feature in geoJsonLayer)
                    {
                        fileGdbLayer.Add(feature);
                    }
                }
            }
            //ExEnd: ConvertGeoJsonLayerToLayerInFileGdbDataset
        }
    }
}

```
