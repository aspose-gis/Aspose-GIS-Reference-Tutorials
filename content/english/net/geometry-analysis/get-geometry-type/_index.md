---
title: Get Geometry Type
linktitle: Get Geometry Type
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 23
url: /net/geometry-analysis/get-geometry-type/
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
    class GetGeometryType
    {
        public static void Run()
        {
            //ExStart: GetGeometryType
            Point point = new Point(40.7128, -74.006);

            GeometryType geometryType = point.GeometryType;

            Console.WriteLine(geometryType); // Point
            //ExEnd: GetGeometryType
        }
    }
}

```
