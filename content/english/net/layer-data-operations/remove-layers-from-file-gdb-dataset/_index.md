---
title: Remove Layers from File GDB Dataset
linktitle: Remove Layers from File GDB Dataset
second_title: Aspose.GIS .NET API
description: 
type: docs
weight: 17
url: /net/layer-data-operations/remove-layers-from-file-gdb-dataset/
---

## Complete Source Code
```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Aspose.GIS_for.NET.Layers
{
    class RemoveLayersFromFileGdbDataset
    {
        public static void Run()
        {
            //ExStart: RemoveLayersFromFileGdbDataset
            // -- copy test dataset, to avoid modification of test data.

            //var datasetPath = GetOutputPath(".gdb");
            var path = "Your Document Directory" + "ThreeLayers.gdb";
            var datasetPath = "Your Document Directory" + "RemoveLayersFromFileGdbDataset_out.gdb";
            RunExamples.CopyDirectory(path, datasetPath);

            // --

            using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
            {
                Console.WriteLine(dataset.CanRemoveLayers); // True

                Console.WriteLine(dataset.LayersCount); // 3

                // remove layer by index
                dataset.RemoveLayerAt(2);
                Console.WriteLine(dataset.LayersCount); // 2

                // remove layer by name
                dataset.RemoveLayer("layer1");
                Console.WriteLine(dataset.LayersCount); // 1
            }
            //ExEnd: RemoveLayersFromFileGdbDataset
        }
    }
}

```
