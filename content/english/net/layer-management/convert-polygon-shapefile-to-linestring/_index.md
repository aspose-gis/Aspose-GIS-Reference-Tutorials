---
title: Convert Polygon Shapefile to Linestring
linktitle: Convert Polygon Shapefile to Linestring
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 18
url: /net/layer-management/convert-polygon-shapefile-to-linestring/
---

## Complete Source Code
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Aspose.GIS.Examples.CSharp.Layers
{
    class ConvertPolygonShapeFileToLineStringShapeFile
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory";
            //ExStart: ConvertPolygonShapeFileToLineStringShapeFile
            using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
            {
                using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
                {
                    foreach (Feature sourceFeature in source)
                    {
                        Polygon polygon = (Polygon)sourceFeature.Geometry;
                        LineString line = new LineString(polygon.ExteriorRing);
                        Feature destinationFeature = destination.ConstructFeature();
                        destinationFeature.Geometry = line;
                        destination.Add(destinationFeature);
                    }
                }
            }
            //ExEnd: ConvertPolygonShapeFileToLineStringShapeFile
        }
    }
}

```
