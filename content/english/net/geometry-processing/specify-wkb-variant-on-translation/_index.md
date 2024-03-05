---
title: Specify WKB Variant on Translation
linktitle: Specify WKB Variant on Translation
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 18
url: /net/geometry-processing/specify-wkb-variant-on-translation/
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
    class SpecifyWkbVariantOnTranslation
    {
        public static void Run()
        {
            //ExStart: SpecifyWkbVariantOnTranslation
            IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
            byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
            File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
            //ExEnd: SpecifyWkbVariantOnTranslation
        }
    }
}

```
