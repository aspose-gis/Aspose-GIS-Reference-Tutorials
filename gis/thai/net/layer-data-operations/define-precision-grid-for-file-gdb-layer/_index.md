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

## การแนะนำ
ในบทแนะนำนี้ไม่จำเป็นต้องเรียนรู้ **วิธีการตั้งค่า grid** สำหรับชั้น File Geodatabase (GDB) สำหรับ Aspose.GIS สำหรับ .NET เป็น precision grid ที่ **ตรวจสอบช่วงพิกัด** สามารถตรวจสอบพื้นที่ภายนอกของขอบเขตได้เสมอ ข้อมูลที่คุณ ** เพิ่มลงในชั้น** มีอย่างสม่ำเสมอและเชื่อถือได้มากขึ้นในขั้นตอนแรกๆ มีความสำคัญอย่างไรและแสดงวิธีการทำงานของปัญหาที่พบบ่อย

## คำตอบด่วน
- **“set grid” ในอะไร?** และจะต้องบันทึกพิกัดและช่วงที่ใช้ได้สำหรับชั้น GIS
- ** ทำไมต้องใช้ตารางที่แม่นยำ** ค้นหาตำแหน่งที่สำรวจและผู้เยี่ยมชม
- **ไลบรารีใดให้สำหรับสิ่งนี้?** Aspose.GIS สำหรับ .NET
- **ต้องมีลิขสิทธิ์หรือไม่?** มีรุ่นทดลองให้ใช้ได้; ต้องมีลิขสิทธิ์เรื่องนี้เป็นหลัก
- ** สามารถรองรับ .NET Core ได้หรือไม่** รองรับ, Aspose.GIS รองรับ .NET Framework และ .NET Core

## Precision Grid คืออะไร และเหตุใดจึงตั้งค่าไว้
ตารางที่แม่นยำคือชุดที่ต้องการ (จุดกำเนิด, ขนาดอื่นๆ) ที่บอกเครื่อง GIS ลาดเอียงและเก็บค่าตำแหน่งอย่างไร การตั้งค่าตาราง **ตรวจสอบช่วงพิกัด** จะต้องพยายามแทรกจุดที่อยู่นอกตารางจะทำให้เกิด — ช่วยให้ ** ตรวจสอบสถานการณ์ที่อยู่นอกขอบเขต** ได้ตั้งแต่ขั้นตอนการพัฒนา

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มดำเนินการตรวจสอบคุณจะต้องติดตั้งสิ่งต่อไปนี้แล้ว:

1. **Visual Studio** – ดาวน์โหลดล่าสุด (ชุมชน, มืออาชีพ หรือ องค์กร)
2. **Aspose.GIS สำหรับ .NET** – ดาวน์โหลดจาก [เว็บไซต์](https://releases.aspose.com/gis/net/)
3. **ความรู้พื้นฐาน C#** – คุณสามารถดูโปรเจกต์ของคุณได้ .NET

## นำเข้าเนมสเปซ
ก่อนอื่นให้ทำการนำเข้า namespace ที่จำเป็นสำหรับการทำงานกับ Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## วิธีการตั้งค่ากริดในไฟล์ GDB Layer
ต่อไปนี้เป็นคำแนะนำแบบขั้นตอนต่อขั้นตอนที่แสดงวิธีกำหนดค่า grid, สร้างชั้น, และ **เพิ่มฟีเจอร์ลงในชั้น** อย่างปลอดภัย

### ขั้นตอนที่ 1: สร้างชุดข้อมูล
เราจะเริ่มด้วยการสร้าง dataset File Geodatabase ใหม่ ซึ่งเป็นที่ที่ชั้นจะถูกจัดเก็บ

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### ขั้นตอนที่ 2: กำหนดตัวเลือกความแม่นยำของตารางกริด
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

### ขั้นตอนที่ 3: สร้างเลเยอร์ด้วยตารางกริด
ต่อไปเราจะสร้างชั้นใหม่ภายใน dataset โดยใช้ตัวเลือก grid ที่กำหนดไว้ เราจะใช้ระบบอ้างอิงเชิงพื้นที่ WGS84

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### ขั้นตอนที่ 4: เพิ่มฟีเจอร์ลงในเลเยอร์
เราจะสร้างฟีเจอร์จุดสองจุด จุดแรกอยู่ภายใน grid ส่วนจุดที่สองตั้งใจให้ตกนอกเพื่อสาธิต **วิธีจัดการกับข้อผิดพลาด out of range**

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### ขั้นตอนที่ 5: จัดการข้อผิดพลาดเมื่อเพิ่มฟีเจอร์ที่อยู่นอกช่วง
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

### ขั้นตอนที่ 6: ทำความสะอาด
คำสั่ง `using` จะปิดและทำลายชุดข้อมูลและเลเยอร์ที่ปราศจากทรัพยากรทั้งหมดถูกปล่อยคืน

## ปัญหาทั่วไปและแนวทางแก้ไข
| ปัญหา | ทำไมมันถึงเกิดขึ้น | แก้ไข |
|----------------------|----------------|-----|
| **ข้อยกเว้น: “ค่า X … อยู่นอกช่วงที่ถูกต้อง”** | ตำแหน่งอยู่นอกตารางความแม่นยำ | `XOrigin`, `YOrigin` หรือ `XYScale` พยายามหาข้อมูลของคุณ, หรือทำให้ข้อมูลเป็นจุดที่กำหนดให้ |
| **คุณสมบัติไม่ปรากฏในโปรแกรมดู GIS** | ชั้นไม่ได้บันทึกต้องใช้การอ้างอิงเชิงพื้นที่ ผิด | ดีเจ `SpatialReferenceSystem.Wgs84` CRS ของ viewer, และว่า `Dataset.Create` ทำงานได้สำเร็จ |
| **ค่า M ละเว้น** | `MScale` ตั้งเป็น 0 หรือค่าต่ำเกินไป | ตั้งค่า `MScale` เหมาะสม (เช่น `1e4`) เพื่อเก็บค่าวัด |

## คำถามที่พบบ่อย

**ถาม: กิน Aspose.GIS for .NET กับรูปแบบไฟล์ GIS อย่างอื่นก็ได้?**
ตอบ: เป็นไปได้, Aspose.GIS กับ Shapefile, GeoJSON, KML และรูปแบบอื่น ๆ ที่เกิดขึ้นมากมาย

**ถาม: Aspose.GIS สำหรับ .NET รองรับ .NET Core ได้หรือไม่**
A: แน่นอน. ไลบรารีทำงานได้กับ .NET Framework, .NET Core, และ .NET 5/6+

**Q: ลองทดสอบเชิงพื้นที่เช่น buffer หรือ intersection ก็ได้?**
A: ได้ API มีเมธสำหรับบัฟเฟอร์, ตัดกัน, และคำนวณระยะทาง

**Q: Aspose.GIS มีจุดแปลงพิกัดหรือไม่**
ตอบ: มี ไม่เคยแปลงเรขาคณิตมาก่อนระบบอ้างอิงเชิงพื้นที่ต่างด้วยเครื่องมือ reprojection ใน

**ถาม: มีรุ่นทดลองให้ดาวน์โหลดหรือไม่**
ตอบ: มี ดาวน์โหลดเรื่องราวดาวน์โหลดรุ่นทดลองฟรีจาก [เว็บไซต์](https://releases.aspose.com/gis/net/)

---

**อัปเดตล่าสุด:** 28-12-2025
**ทดสอบกับ:** Aspose.GIS 24.11 สำหรับ .NET
**ผู้เขียน:** สมมติ  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}