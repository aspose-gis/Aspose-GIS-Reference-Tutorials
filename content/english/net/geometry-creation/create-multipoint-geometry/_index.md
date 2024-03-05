---
title: Create MultiPoint Geometry
linktitle: Create MultiPoint Geometry
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 14
url: /net/geometry-creation/create-multipoint-geometry/
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
    class CreateMultiPoint
    {
        public static void Run()
        {
            //ExStart: CreateMultiPoint
            MultiPoint multipoint = new MultiPoint();
            multipoint.Add(new Point(1, 2));
            multipoint.Add(new Point(3, 4));
            //ExEnd: CreateMultiPoint
        }
    }
}

```
