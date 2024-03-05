---
title: Check Geometry Covers Another
linktitle: Check Geometry Covers Another
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 15
url: /net/geometry-analysis/check-geometry-covers-another/
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
    class DetermineIfOneGeometryCoversAnother
    {
        public static void Run()
        {
            //ExStart: DetermineIfOneGeometryCoversAnother
            var line = new LineString();
            line.AddPoint(0, 0);
            line.AddPoint(1, 1);

            var point = new Point(0, 0);
            Console.WriteLine(line.Covers(point));    // True
            Console.WriteLine(point.CoveredBy(line)); // True
            //ExEnd: DetermineIfOneGeometryCoversAnother
        }
    }
}

```
