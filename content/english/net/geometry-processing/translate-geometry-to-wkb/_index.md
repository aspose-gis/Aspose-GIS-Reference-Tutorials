---
title: Translate Geometry to WKB
linktitle: Translate Geometry to WKB
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 22
url: /net/geometry-processing/translate-geometry-to-wkb/
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
    class TranslateGeometryToWkb
    {
        public static void Run()
        {
            //ExStart: TranslateGeometryToWkb
            IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
            byte[] wkb = geometry.AsBinary();
            //File.WriteAllBytes(Path.Combine(TestConfiguration.TestOutputPath, "file.wkb"), wkb);
            File.WriteAllBytes(Path.Combine("Your Document Directory", "WkbFile.wkb"), wkb);
            //ExEnd: TranslateGeometryToWkb
        }
    }
}

```
