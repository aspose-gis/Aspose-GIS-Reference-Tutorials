---
title: Replace Polygons with Lines
linktitle: Replace Polygons with Lines
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 16
url: /net/geometry-processing/replace-polygons-with-lines/
---

## Complete Source Code
```csharp
using System;
using Aspose.Gis.Geometries;

namespace Aspose.GIS.Examples.CSharp.Geometries
{
    class ReplacePolygonsByLines
    {
        public static void Run()
        {
            //ExStart: ReplacePolygonsByLines
            {
                var srcGeometry = Geometry.FromText(@"GeometryCollection (POLYGON((1 2, 1 4, 3 4, 3 2)), Point (5 1))");
                var dstGeometry = srcGeometry.ReplacePolygonsByLines();
                Console.WriteLine($"source: {srcGeometry.AsText()}");
                Console.WriteLine($"result: {dstGeometry.AsText()}");
            }
            //ExEnd: ReplacePolygonsByLines
        }
    }
}
```
