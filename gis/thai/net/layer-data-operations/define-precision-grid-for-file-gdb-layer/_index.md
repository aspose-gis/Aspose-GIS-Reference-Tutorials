---
date: 2026-04-24
description: เรียนรู้วิธีสร้างไฟล์จีโอเดต้าเบสและตั้งค่า precision grid สำหรับเลเยอร์
  File GDB ด้วย Aspose.GIS for .NET รวมถึงการเพิ่มฟีเจอร์ลงในเลเยอร์และการตรวจสอบช่วงพิกัด.
keywords:
- create file geodatabase
- handle out of range
- add features layer
- configure coordinate grid
- validate coordinate range
linktitle: กำหนดกริดความแม่นยำสำหรับชั้นไฟล์ GDB
second_title: Aspose.GIS .NET API
title: สร้างไฟล์ Geodatabase และตั้งค่า Grid สำหรับชั้น GDB (Aspose.GIS)
url: /th/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตั้งค่า Grid สำหรับเลเยอร์ File GDB ใน Aspose.GIS

## บทนำ
ในบทเรียนนี้คุณจะ **สร้างไฟล์ geodatabase** และเรียนรู้วิธี **ตั้งค่า grid** สำหรับเลเยอร์ File Geodatabase (GDB) ด้วย Aspose.GIS สำหรับ .NET การกำหนด precision grid ช่วยให้คุณ **ตรวจสอบช่วงพิกัด** ป้องกันข้อผิดพลาด out‑of‑range และรับประกันว่าการดำเนินการ **เพิ่มฟีเจอร์ลงในเลเยอร์** จะเก็บข้อมูลอย่างแม่นยำ เราจะเดินผ่านทุกขั้นตอน อธิบายว่าการตั้งค่าแต่ละอย่างสำคัญอย่างไร และแสดงวิธี **จัดการกับสถานการณ์ out of range** อย่างราบรื่น

## คำตอบสั้น
- **“set grid” หมายถึงอะไร?** มันกำหนดความแม่นยำของพิกัดและช่วงที่ถูกต้องสำหรับเลเยอร์ GIS.  
- **ทำไมต้องใช้ precision grid?** มันปกป้องข้อมูลของคุณจากพิกัดที่ไม่ถูกต้องและเพิ่มประสิทธิภาพการจัดเก็บ.  
- **ไลบรารีใดให้คุณสมบัตินี้?** Aspose.GIS for .NET.  
- **ฉันต้องมีลิขสิทธิ์หรือไม่?** มีรุ่นทดลองให้ใช้; จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **ฉันสามารถใช้กับ .NET Core ได้หรือไม่?** ใช่, Aspose.GIS รองรับ .NET Framework และ .NET Core.

## Precision Grid คืออะไรและทำไมต้องตั้งค่า?
Precision grid คือชุดพารามิเตอร์ (origin, scale, ฯลฯ) ที่บอกเครื่อง GIS ว่าจะปัดและเก็บค่าพิกัดอย่างไร โดยการกำหนด grid คุณจะ **ตรวจสอบช่วงพิกัด** โดยอัตโนมัติ และการพยายามแทรกจุดที่อยู่นอก grid จะทำให้เกิด exception—ช่วยให้คุณ **จัดการกับสถานการณ์ out of range** ได้ตั้งแต่ขั้นตอนการพัฒนา

## ทำไมต้องสร้าง File Geodatabase พร้อม Precision Grid?
การสร้างไฟล์ geodatabase ให้คุณมีคอนเทนเนอร์พกพาและประสิทธิภาพสูงสำหรับข้อมูลเวกเตอร์ การเพิ่ม precision grid ตั้งแต่ขั้นตอนการสร้างทำให้:

- **คุณภาพข้อมูลที่สม่ำเสมอ** – ทุกฟีเจอร์เคารพความแม่นยำเชิงตัวเลขเดียวกัน.  
- **การทำดัชนีที่เร็วขึ้น** – เอนจินสามารถจัดเก็บพิกัดได้อย่างมีประสิทธิภาพมากขึ้น.  
- **การตรวจจับข้อผิดพลาดตั้งแต่ต้น** – พิกัดที่อยู่นอกช่วงจะถูกจับก่อนที่จะทำให้ชุดข้อมูลเสียหาย.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามขั้นตอนต่อไปนี้ให้แน่ใจว่าคุณได้ติดตั้งสิ่งต่อไปนี้แล้ว:

1. **Visual Studio** – เวอร์ชันล่าสุดใดก็ได้ (Community, Professional, หรือ Enterprise).  
2. **Aspose.GIS for .NET** – ดาวน์โหลดจาก [website](https://releases.aspose.com/gis/net/).  
3. **ความรู้พื้นฐาน C#** – คุณควรคุ้นเคยกับการสร้างโปรเจกต์คอนโซล .NET.

## กรณีการใช้งานทั่วไป
- **การเก็บข้อมูลภาคสนาม** ที่อุปกรณ์ GPS อาจสร้างพิกัดที่อยู่นอกขอบเขตเล็กน้อย.  
- **การย้ายข้อมูล** จากระบบเก่าที่ใช้ความแม่นยำของพิกัดต่างกัน.  
- **สายงาน ETL อัตโนมัติ** ที่ต้องบังคับให้มีความสมบูรณ์ของข้อมูลเชิงพื้นที่ก่อนโหลดข้อมูลเข้าสู่ฐานข้อมูล GIS.

## นำเข้า Namespaces
ก่อนอื่นให้นำเข้า namespaces ที่จำเป็นสำหรับการทำงานกับ Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## วิธีกำหนดค่า Coordinate Grid ในเลเยอร์ File GDB
ต่อไปนี้เป็นคำแนะนำแบบขั้นตอนต่อขั้นตอนที่แสดงวิธีกำหนดค่า grid, สร้างเลเยอร์, และ **เพิ่มฟีเจอร์ลงในเลเยอร์** อย่างปลอดภัย

### ขั้นตอนที่ 1: สร้าง Dataset
เราจะเริ่มด้วยการสร้าง File Geodatabase dataset ใหม่ ซึ่งเป็นที่ที่เลเยอร์จะอยู่

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### ขั้นตอนที่ 2: กำหนด Precision Grid Options
ที่นี่เรากำหนดพารามิเตอร์ของ grid ปรับ origin และ scale ให้ตรงกับระบบพิกัดของโครงการของคุณ

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

*ฟลัก `EnsureValidCoordinatesRange = true` บอก Aspose.GIS ให้ **ตรวจสอบช่วงพิกัด** สำหรับทุกฟีเจอร์ที่คุณเพิ่ม.*

### ขั้นตอนที่ 3: สร้างเลเยอร์พร้อม Grid
ตอนนี้เราจะสร้างเลเยอร์ใหม่ภายใน dataset โดยใช้ตัวเลือก grid ที่กำหนดไว้ เราจะใช้ระบบอ้างอิงเชิงพื้นที่ WGS84

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### ขั้นตอนที่ 4: เพิ่ม Features ไปยังเลเยอร์
เราจะสร้างฟีเจอร์จุดสองจุด จุดแรกอยู่ภายใน grid ส่วนจุดที่สองตั้งใจให้อยู่นอกเพื่อสาธิต **วิธีจัดการกับข้อผิดพลาด out of range**

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### ขั้นตอนที่ 5: จัดการ Exceptions เมื่อเพิ่ม Features ที่อยู่นอกช่วง
การพยายามเพิ่มฟีเจอร์ที่สองจะทำให้เกิด exception เนื่องจากพิกัด X (`-410`) อยู่นอก grid ที่กำหนด เราจับ exception และแสดงข้อความที่ชัดเจน

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

### ขั้นตอนที่ 6: ทำความสะอาด
คำสั่ง `using` จะปิดและทำลาย dataset และ layer โดยอัตโนมัติ เพื่อให้แน่ใจว่าทรัพยากรทั้งหมดถูกปล่อยคืน

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| **Exception: “X value … is out of valid range.”** | พิกัดอยู่นอก precision grid. | ปรับ `XOrigin`, `YOrigin`, หรือ `XYScale` ให้ครอบคลุมข้อมูลของคุณ, หรือให้แน่ใจว่าข้อมูลเข้าอยู่ในช่วงที่กำหนด. |
| **Features not appearing in GIS viewer** | เลเยอร์ไม่ได้บันทึกหรือ spatial reference ผิด. | ตรวจสอบว่า `SpatialReferenceSystem.Wgs84` ตรงกับ CRS ของ viewer, และ `Dataset.Create` สำเร็จ. |
| **M values ignored** | `MScale` ตั้งเป็น 0 หรือค่าต่ำเกินไป. | ตั้งค่า `MScale` ที่เหมาะสม (เช่น `1e4`) เพื่อเก็บค่า measure. |

## เคล็ดลับการแก้ไขปัญหา
- **ตรวจสอบขอบเขตของ grid อีกครั้ง** ก่อนโหลดข้อมูลจำนวนมาก; การพิมพ์ผิดเล็กน้อยใน `XOrigin` อาจทำให้หลายแถวถูกปฏิเสธ.  
- **บันทึกข้อความ exception** (ตามที่แสดงในบล็อก try‑catch) ลงไฟล์เมื่อประมวลผลการนำเข้าที่อัตโนมัติ; จะทำให้ง่ายต่อการสังเกตรูปแบบของข้อมูลที่อยู่นอกช่วง.  
- **ใช้ `EnsureValidCoordinatesRange = false` เฉพาะกับแหล่งข้อมูลที่เชื่อถือได้** – การปิดจะข้ามการตรวจสอบและอาจทำให้รูปทรงเสียหาย.

## คำถามที่พบบ่อย

**Q: สามารถใช้ Aspose.GIS for .NET กับรูปแบบไฟล์ GIS อื่นได้หรือไม่?**  
A: ใช่, Aspose.GIS รองรับ Shapefile, GeoJSON, KML, และรูปแบบอื่น ๆ อีกมากมาย.

**Q: Aspose.GIS for .NET เข้ากันได้กับ .NET Core หรือไม่?**  
A: แน่นอน. ไลบรารีทำงานกับ .NET Framework, .NET Core, และ .NET 5/6+.

**Q: สามารถทำการดำเนินการเชิงพื้นที่เช่น buffering หรือ intersection ได้หรือไม่?**  
A: ใช่, API มีเมธอดสำหรับ buffering, intersecting, และคำนวณระยะทาง.

**Q: Aspose.GIS มีความสามารถในการแปลงพิกัดหรือไม่?**  
A: ใช่, คุณสามารถแปลงรูปทรงระหว่างระบบอ้างอิงเชิงพื้นที่ต่าง ๆ ด้วยเครื่องมือ reprojection ในตัว.

**Q: มีรุ่นทดลองให้ดาวน์โหลดหรือไม่?**  
A: มี, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีจาก [website](https://releases.aspose.com/gis/net/).

---

**อัปเดตล่าสุด:** 2026-04-24  
**ทดสอบกับ:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}