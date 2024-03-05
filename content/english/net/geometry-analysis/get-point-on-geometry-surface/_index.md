---
title: Get Point on Geometry Surface
linktitle: Get Point on Geometry Surface
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 25
url: /net/geometry-analysis/get-point-on-geometry-surface/
---

## Complete Source Code
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Aspose.GIS.Examples.CSharp.Geometries
{
    class GetPointOnSurface
    {
        public static void Run()
        {
            //ExStart: GetPointOnSurface
            var polygon = new Polygon();
            polygon.ExteriorRing = new LinearRing(new[]
            {
                new Point(0, 0),
                new Point(0, 1),
                new Point(1, 1),
                new Point(0, 0),
            });

            IPoint pointOnSurface = polygon.GetPointOnSurface();

            // point on surface is guaranteed to be inside a polygon.
            Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // True
            //ExEnd: GetPointOnSurface
        }
    }
}

```
