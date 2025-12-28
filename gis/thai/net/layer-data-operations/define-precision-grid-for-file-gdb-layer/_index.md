---
date: 2025-12-28
description: เรียนรู้วิธีตั้งค่า grid สำหรับเลเยอร์ File GDB โดยใช้ Aspose.GIS สำหรับ
  .NET รวมถึงการเพิ่มฟีเจอร์ลงในเลเยอร์และการตรวจสอบช่วงพิกัด
linktitle: Define Precision Grid for File GDB Layer
second_title: Aspose.GIS .NET API
title: วิธีตั้งค่า Grid สำหรับเลเยอร์ File GDB ใน Aspose.GIS
url: /th/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งค่า Grid สำหรับชั้น File GDB ใน Aspose.GIS

## Introduction
ในบทแนะนำนี้ คุณจะได้เรียนรู้ **วิธีตั้งค่า grid** สำหรับชั้น File Geodatabase (GDB) โดยใช้ Aspose.GIS สำหรับ .NET การตั้งค่า precision grid จะช่วยให้คุณ **ตรวจสอบช่วงพิกัด** ได้ ป้องกันข้อผิดพลาด out‑of‑range และทำให้ข้อมูลที่คุณ **เพิ่มฟีเจอร์ลงในชั้น** มีความแม่นยำและเชื่อถือได้ เราจะเดินผ่านแต่ละขั้นตอน อธิบายว่าการตั้งค่าเหล่านี้สำคัญอย่างไร และแสดงวิธีจัดการกับปัญหาที่พบบ่อย

## Quick Answers
- **“set grid” หมายถึงอะไร?** มันกำหนดความแม่นยำของพิกัดและช่วงที่ใช้ได้สำหรับชั้น GIS  
- **ทำไมต้องใช้ precision grid?** เพื่อปกป้องข้อมูลจากพิกัดที่ไม่ถูกต้องและเพิ่มประสิทธิภาพการจัดเก็บ  
- **ไลบรารีใดให้ฟีเจอร์นี้?** Aspose.GIS สำหรับ .NET  
- **ต้องมีลิขสิทธิ์หรือไม่?** มีรุ่นทดลองให้ใช้ได้; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **สามารถใช้กับ .NET Core ได้หรือไม่?** ใช่, Aspose.GIS รองรับ .NET Framework และ .NET Core  

## What is a Precision Grid and Why Set It?
Precision grid คือชุดพารามิเตอร์ (origin, scale ฯลฯ) ที่บอกเครื่อง GIS ว่าจะปัดและเก็บค่าพิกัดอย่างไร การกำหนด grid จะทำให้คุณ **ตรวจสอบช่วงพิกัด** โดยอัตโนมัติ และการพยายามแทรกจุดที่อยู่นอก grid จะทำให้เกิดข้อยกเว้น—ช่วยให้คุณ **จัดการกับสถานการณ์ out of range** ได้ตั้งแต่ขั้นตอนการพัฒนา

## Prerequisites
ก่อนเริ่มทำตามขั้นตอน โปรดตรวจสอบว่าคุณได้ติดตั้งสิ่งต่อไปนี้แล้ว:

1. **Visual Studio** – เวอร์ชันล่าสุดใดก็ได้ (Community, Professional หรือ Enterprise)  
2. **Aspose.GIS for .NET** – ดาวน์โหลดจาก [website](https://releases.aspose.com/gis/net/)  
3. **ความรู้พื้นฐาน C#** – ควรคุ้นเคยกับการสร้างโปรเจกต์คอนโซล .NET  

## Import Namespaces
ก่อนอื่นให้ทำการนำเข้า namespace ที่จำเป็นสำหรับการทำงานกับ Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## How to Set Grid in a File GDB Layer
ต่อไปนี้เป็นคำแนะนำแบบขั้นตอนต่อขั้นตอนที่แสดงวิธีกำหนดค่า grid, สร้างชั้น, และ **เพิ่มฟีเจอร์ลงในชั้น** อย่างปลอดภัย

### Step 1: Create a Dataset
เราจะเริ่มด้วยการสร้าง dataset File Geodatabase ใหม่ ซึ่งเป็นที่ที่ชั้นจะถูกจัดเก็บ

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### Step 2: Define Precision Grid Options
ที่นี่เรากำหนดพารามิเตอร์ของ grid ปรับค่า origin และ scale ให้ตรงกับระบบพิกัดของโครงการของคุณ

```csharp
var options = new FileGdbOptions
{
    CoordinatePrecisionGrid = new FileGdbCoordinatePrecisionGrid
    {
        XOrigin = -400,
        YOrigin = -400,
        XYScale = 1e10,
        MOrigin = 0,
        MScale = 1e4,
    },
    EnsureValidCoordinatesRange = true,
};
```

*แฟล็ก `EnsureValidCoordinatesRange = true` บอก Aspose.GIS ให้ **ตรวจสอบช่วงพิกัด** สำหรับทุกฟีเจอร์ที่คุณเพิ่ม*

### Step 3: Create a Layer with the Grid
ต่อไปเราจะสร้างชั้นใหม่ภายใน dataset โดยใช้ตัวเลือก grid ที่กำหนดไว้ เราจะใช้ระบบอ้างอิงเชิงพื้นที่ WGS84

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### Step 4: Add Features to the Layer
เราจะสร้างฟีเจอร์จุดสองจุด จุดแรกอยู่ภายใน grid ส่วนจุดที่สองตั้งใจให้ตกนอกเพื่อสาธิต **วิธีจัดการกับข้อผิดพลาด out of range**

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### Step 5: Handle Exceptions When Adding Out‑of‑Range Features
การพยายามเพิ่มฟีเจอร์ที่สองจะทำให้เกิดข้อยกเว้นเพราะค่าพิกัด X (`-410`) อยู่นอก grid ที่กำหนด เราจะดักจับข้อยกเว้นและแสดงข้อความที่ชัดเจน

```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // X value -410 is out of valid range.
}
```

### Step 6: Clean Up
คำสั่ง `using` จะปิดและทำลาย dataset และ layer โดยอัตโนมัติ เพื่อให้แน่ใจว่าทรัพยากรทั้งหมดถูกปล่อยคืน

## Common Issues and Solutions
| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **Exception: “X value … is out of valid range.”** | พิกัดอยู่นอก precision grid | ปรับ `XOrigin`, `YOrigin` หรือ `XYScale` ให้ครอบคลุมข้อมูลของคุณ, หรือทำให้ข้อมูลอินพุตอยู่ในช่วงที่กำหนด |
| **Features not appearing in GIS viewer** | ชั้นไม่ได้บันทึกหรือใช้ spatial reference ผิด | ตรวจสอบว่า `SpatialReferenceSystem.Wgs84` ตรงกับ CRS ของ viewer, และว่า `Dataset.Create` ทำงานสำเร็จ |
| **M values ignored** | `MScale` ตั้งเป็น 0 หรือค่าต่ำเกินไป | ตั้งค่า `MScale` ที่เหมาะสม (เช่น `1e4`) เพื่อเก็บค่า measure |

## Frequently Asked Questions

**Q: สามารถใช้ Aspose.GIS for .NET กับรูปแบบไฟล์ GIS อื่นได้หรือไม่?**  
A: ใช่, Aspose.GIS รองรับ Shapefile, GeoJSON, KML และรูปแบบอื่น ๆ อีกหลายประเภท  

**Q: Aspose.GIS for .NET รองรับ .NET Core หรือไม่?**  
A: แน่นอน. ไลบรารีทำงานได้กับ .NET Framework, .NET Core, และ .NET 5/6+  

**Q: สามารถทำการดำเนินการเชิงพื้นที่ เช่น buffer หรือ intersection ได้หรือไม่?**  
A: ได้, API มีเมธอดสำหรับการ buffer, intersect, และคำนวณระยะทาง  

**Q: Aspose.GIS มีความสามารถในการแปลงพิกัดหรือไม่?**  
A: มี, คุณสามารถแปลง geometry ระหว่างระบบอ้างอิงเชิงพื้นที่ต่าง ๆ ด้วยเครื่องมือ reprojection ในตัว  

**Q: มีรุ่นทดลองให้ดาวน์โหลดหรือไม่?**  
A: มี, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีจาก [website](https://releases.aspose.com/gis/net/)  

---

**Last Updated:** 2025-12-28  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}