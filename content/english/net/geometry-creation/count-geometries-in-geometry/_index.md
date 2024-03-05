---
title: Count Geometries in Geometry
linktitle: Count Geometries in Geometry
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 23
url: /net/geometry-creation/count-geometries-in-geometry/
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
    class CountGeometriesInGeometry
    {
        public static void Run()
        {
            //ExStart: CountGeometriesInGeometry
            Point point = new Point(40.7128, -74.006);

            LineString line = new LineString();
            line.AddPoint(78.65, -32.65);
            line.AddPoint(-98.65, 12.65);

            GeometryCollection geometryCollection = new GeometryCollection();
            geometryCollection.Add(point);
            geometryCollection.Add(line);

            int geometriesCount = geometryCollection.Count;
            Console.WriteLine(geometriesCount); // 2
            //ExEnd: CountGeometriesInGeometry
        }
    }
}

```
