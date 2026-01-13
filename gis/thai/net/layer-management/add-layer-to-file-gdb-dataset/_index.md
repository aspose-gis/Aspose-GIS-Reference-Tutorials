---
date: 2026-01-13
description: เรียนรู้วิธีเพิ่มเลเยอร์ลงในชุดข้อมูล File GDB ด้วย Aspose.GIS พร้อมการสนับสนุนระบบพิกัดเชิงพื้นที่
  WGS84 ทำตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อเพิ่มเลเยอร์ลงใน GDB ด้วย .NET.
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: การอ้างอิงเชิงพื้นที่ WGS84 – เพิ่มเลเยอร์ไปยัง GDB ด้วย Aspose.GIS
url: /th/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# spatial reference wgs84 – เพิ่มเลเยอร์ไปยัง GDB ด้วย Aspose.GIS

## Introduction
พร้อมที่จะเร่งกระบวนการทำงาน GIS ของคุณด้วย Aspose.GIS for .NET หรือยัง? ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีเพิ่มเลเยอร์ไปยังชุดข้อมูล File GDB** พร้อมทำงานกับระบบพิกัด **spatial reference wgs84** เราจะเดินผ่านแต่ละขั้นตอน ตั้งแต่การเตรียมโฟลเดอร์ข้อมูลของคุณจนถึงการตรวจสอบเลเยอร์ที่สร้างใหม่ เพื่อให้คุณสามารถจัดการข้อมูลเชิงพื้นที่ได้อย่างมั่นใจ

## Quick Answers
- **ระบบพิกัดหลักที่ใช้คืออะไร?** spatial reference wgs84 (WGS 84)  
- **ไลบรารีใดให้ API นี้?** Aspose.GIS for .NET  
- **ต้องการไลเซนส์สำหรับการทดสอบหรือไม่?** ใช่ – มีไลเซนส์ชั่วคราวของ Aspose ให้ใช้  
- **สามารถเพิ่มแอตทริบิวต์ให้กับเลเยอร์ใหม่ได้หรือไม่?** แน่นอน คุณสามารถกำหนดแอตทริบิวต์ของฟีเจอร์ได้ตามต้องการ  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6

## What is spatial reference wgs84?
spatial reference wgs84 (World Geodetic System 1984) เป็นระบบพิกัดเชิงภูมิศาสตร์ที่ใช้กันอย่างแพร่หลายที่สุด มันกำหนดค่าละติจูดและลองจิจูดเป็นหน่วยองศาและทำหน้าที่เป็น CRS เริ่มต้นสำหรับชุดข้อมูล GIS จำนวนมาก รวมถึงชุดข้อมูลที่เราจะสร้างในคู่มือนี้

## Why use Aspose.GIS to add a layer?
- **ไม่มีการพึ่งพาภายนอก:** ทำงานได้ทันทีด้วยโค้ด .NET แท้ ๆ  
- **ควบคุมสคีม่าได้เต็มที่:** คุณสามารถกำหนดแอตทริบิวต์และประเภทเรขาคณิตที่กำหนดเองได้  
- **ข้ามแพลตฟอร์ม:** รองรับ Windows, Linux และ macOS  
- **ไลเซนส์ที่มั่นคง:** ไลเซนส์ชั่วคราวช่วยให้คุณประเมินผลได้อย่างรวดเร็วก่อนตัดสินใจ

## Prerequisites
ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

- Aspose.GIS for .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก [เอกสาร Aspose.GIS for .NET](https://reference.aspose.com/gis/net/)  
- Document Directory: สร้างโฟลเดอร์เฉพาะบนเครื่องของคุณเพื่อเก็บไฟล์ GIS

## Import Namespaces
เพิ่มคำสั่ง `using` ที่จำเป็นในโปรเจกต์ C# ของคุณเพื่อให้เข้าถึงคลาสของ Aspose.GIS ได้:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Copy Directory
เริ่มต้นโดยทำสำเนาโฟลเดอร์ที่มีชุดข้อมูล GDB ดั้งเดิม การมีสำเนาช่วยปกป้องข้อมูลต้นฉบับขณะคุณทำการทดลอง

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Step 2: Open Dataset and Verify Creation Capability
เปิดชุดข้อมูลที่คัดลอกใหม่และตรวจสอบว่ามันสามารถสร้างเลเยอร์ใหม่ได้หรือไม่ คุณควรเห็นค่า `CanCreateLayers` คืนค่า **True**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Step 3: Create and Populate a New Layer with spatial reference wgs84
ต่อไปเราจะสร้างเลเยอร์ชื่อ **data** และกำหนดระบบพิกัดเป็น **Wgs84** อย่างชัดเจน พร้อมเพิ่มแอตทริบิวต์ง่าย ๆ ชื่อ **Name** และแทรกฟีเจอร์จุดหนึ่งจุด

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## Step 4: Open and Validate the Added Layer
สุดท้ายเปิดเลเยอร์ที่คุณสร้างขึ้นและตรวจสอบเนื้อหา คอนโซลจะแสดงว่าเลเยอร์มีฟีเจอร์หนึ่งรายการและแอตทริบิวต์ **Name** ตรงกับค่าที่คุณตั้งไว้

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Common Issues & Tips
- **Incorrect path:** ตรวจสอบให้แน่ใจว่า `dataDir` ลงท้ายด้วยตัวคั่นเส้นทาง (`/` หรือ `\`) เพื่อให้สตริงที่ต่อกันเป็นเส้นทางไฟล์ที่ถูกต้อง  
- **License errors:** หากพบคำเตือนเกี่ยวกับไลเซนส์ ให้ใช้ไลเซนส์ชั่วคราวจากพอร์ทัลของ Aspose ก่อนรันโค้ด  
- **CRS mismatch:** เมื่อเปิดเลเยอร์ในเครื่องมือ GIS อื่น ให้ตรวจสอบว่าเครื่องมือนั้นรับรู้ระบบพิกัด WGS 84 (EPSG:4326) อย่างถูกต้อง

## Frequently Asked Questions
### Q: Can I use Aspose.GIS for .NET with other GIS libraries?
Aspose.GIS for .NET ถูกออกแบบให้ทำงานอิสระได้ แต่คุณสามารถผสานรวมกับไลบรารีอื่นเพื่อเพิ่มฟังก์ชันการทำงานได้

### Q: Is a temporary license available for testing purposes?
ใช่ คุณสามารถรับไลเซนส์ชั่วคราวได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อการทดสอบและประเมินผล

### Q: What spatial reference systems does Aspose.GIS for .NET support?
Aspose.GIS for .NET รองรับระบบพิกัดเชิงพื้นที่หลากหลาย ให้ความยืดหยุ่นในการจัดการข้อมูลภูมิศาสตร์

### Q: Can I contribute to the Aspose.GIS community?
แน่นอน! เข้าร่วมการสนทนาและแบ่งปันประสบการณ์ของคุณได้ที่ [ฟอรั่ม Aspose.GIS](https://forum.aspose.com/c/gis/33)

### Q: Where can I find detailed documentation for Aspose.GIS for .NET?
สำรวจเอกสารฉบับเต็มได้ที่ [ที่นี่](https://reference.aspose.com/gis/net/) เพื่อข้อมูลเชิงลึกเกี่ยวกับ Aspose.GIS for .NET

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS for .NET (latest stable version)  
**Author:** Aspose