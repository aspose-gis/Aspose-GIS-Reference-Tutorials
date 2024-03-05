---
title: Crop Layer Features
linktitle: Crop Layer Features
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 19
url: /net/layer-management/crop-layer-features/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;

namespace Aspose.GIS.Examples.CSharp.Layers
{
    public static class CropLayer
    {
        public static void Run()
        {
            CropRaster();
        }

        private static void CropRaster()
        {
            Console.WriteLine($"== Start Demo: {nameof(CropRaster)}");
            // ExStart: CropRaster
            string filesPath = "Your Document Directory";
            using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
            using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
            {
                // read and print raster
                var cellSize = warped.CellSize;
                var extent = warped.GetExtent();
                var spatialRefSys = warped.SpatialReferenceSystem;
                var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
                var bounds = warped.Bounds;

                Console.WriteLine($"cellSize: {cellSize}");
                Console.WriteLine($"source extent: {layer.GetExtent()}");
                Console.WriteLine($"target extent: {extent}");
                Console.WriteLine($"spatialRefSys: {code}");
                Console.WriteLine($"bounds: {bounds}");
            }
            // ExEnd: CropRaster
        }
    }
}
```
