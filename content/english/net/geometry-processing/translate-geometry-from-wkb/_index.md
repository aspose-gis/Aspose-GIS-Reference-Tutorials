---
title: Translate Geometry from WKB
linktitle: Translate Geometry from WKB
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 20
url: /net/geometry-processing/translate-geometry-from-wkb/
---

## Complete Source Code
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Aspose.GIS.Examples.CSharp.Geometries
{
    class TranslateGeometryFromWkb
    {
        public static void Run()
        {
            //ExStart: TranslateGeometryFromWkb
            string path = Path.Combine("Your Document Directory", "WkbFile.wkb");
            byte[] wkb = File.ReadAllBytes(path);
            IGeometry geometry = Geometry.FromBinary(wkb);
            Console.WriteLine(geometry.AsText()); // LINESTRING (1.2 3.4, 5.6 7.8)
            //ExEnd: TranslateGeometryFromWkb
        }
    }
}

```
