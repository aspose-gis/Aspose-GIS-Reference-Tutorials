---
title: Translate Geometry to WKT
linktitle: Translate Geometry to WKT
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 23
url: /net/geometry-processing/translate-geometry-to-wkt/
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
    class TranslateGeometryToWkt
    {
        public static void Run()
        {
            //ExStart: TranslateGeometryToWkt
            Point point = new Point(23.5732, 25.3421);
            Console.WriteLine(point.AsText()); // POINT (23.5732, 25.3421)
            //ExEnd: TranslateGeometryToWkt
        }
    }
}

```
