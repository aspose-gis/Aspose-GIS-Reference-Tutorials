---
title: Read Object ID from File GDB Layer
linktitle: Read Object ID from File GDB Layer
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 16
url: /net/layer-data-operations/read-object-id-from-file-gdb-layer/
---

## Complete Source Code
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Aspose.GIS.Examples.CSharp.Layers
{
    class ReadObjectIdFromFileGdbLayer
    {
        public static void Run()
        {
            string dataDir = "Your Document Directory";
            string path = dataDir + "test.gdb";
            //ExStart: ReadObjectIdFromFileGdbLayer
            using (var dataset = Dataset.Open(path, Drivers.FileGdb))
            using (var layer = dataset.OpenLayer("layer"))
            {
                foreach (var feature in layer)
                {
                    Console.WriteLine(feature.GetValue<int>("OBJECTID"));
                }
            }
            //ExEnd: ReadObjectIdFromFileGdbLayer
        }
    }
}

```
