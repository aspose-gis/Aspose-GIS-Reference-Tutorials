---
title: Create LineString Geometry
linktitle: Create LineString Geometry
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 11
url: /net/geometry-creation/create-linestring-geometry/
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
    class CreateLineString
    {
        public static void Run()
        {
            //ExStart: CreateLineString
            LineString line = new LineString();

            line.AddPoint(78.65, -32.65);

            line.AddPoint(-98.65, 12.65);
            //ExEnd: CreateLineString
        }
    }
}

```
