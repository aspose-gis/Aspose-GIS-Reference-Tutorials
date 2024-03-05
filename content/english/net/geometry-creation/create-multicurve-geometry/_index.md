---
title: Create MultiCurve Geometry
linktitle: Create MultiCurve Geometry
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 17
url: /net/geometry-creation/create-multicurve-geometry/
---

## Complete Source Code
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Aspose.GIS.Examples.CSharp.Geometries
{
    class CreateMultiCurve
    {
        public static void Run()
        {
            //ExStart: CreateMultiCurve
            string path = "Your Document Directory" + "CreateMultiCurve_out.shp";
            using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
            {
                var feature = layer.ConstructFeature();
                var multiCurve = new MultiCurve();
                multiCurve.Add(Geometry.FromText("LineString (0 0, 1 0)"));
                multiCurve.Add(Geometry.FromText("CircularString (2 2, 3 3, 4 2)"));
                multiCurve.Add(Geometry.FromText("CompoundCurve ((0 1, 0 0), CircularString (0 0, 3 3, 6 0))"));
                feature.Geometry = multiCurve;

                layer.Add(feature);
            }
            //ExEnd: CreateMultiCurve
        }
    }
}

```
