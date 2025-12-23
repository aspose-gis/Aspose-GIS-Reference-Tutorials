---
date: 2025-12-23
description: เรียนรู้วิธีแปลงเรขาคณิตเป็น WKT ด้วยตัวเลือกที่หลากหลาย ตั้งค่ารูปแบบตัวเลขและปรับความแม่นยำของทศนิยมโดยใช้
  Aspose.GIS สำหรับ .NET.
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: แปลงเรขาคณิตเป็นตัวเลือก WKT Variant ด้วย Aspose.GIS
url: /th/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง Geometry เป็นตัวเลือก Variant ของ WKT ด้วย Aspose.GIS

## บทนำ
ในแอปพลิเคชัน .NET สมัยใหม่, **การแปลง geometry เป็น WKT** เป็นขั้นตอนทั่วไปเมื่อคุณต้องการแลกเปลี่ยนข้อมูลเชิงพื้นที่กับระบบอื่นหรือเก็บไว้ในรูปแบบข้อความ. Aspose.GIS for .NET ทำให้การแปลงนี้เป็นเรื่องง่ายในขณะที่ให้คุณควบคุมเต็มที่เกี่ยวกับ WKT variant, numeric format, และ decimal precision. ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีการแปลง geometry เป็น WKT, เลือก variant ที่เหมาะสม, และปรับแต่งผลลัพธ์ให้ตรงตามความต้องการของโครงการของคุณอย่างแม่นยำ.

## คำตอบสั้น
- **“convert geometry to WKT” หมายถึงอะไร?** มันแปลงวัตถุเชิงเรขาคณิต (จุด, เส้น, โพลิกอน) ให้เป็นรูปแบบ Well‑Known Text.  
- **WKT variants ที่สนับสนุนมีอะไรบ้าง?** `Iso`, `SimpleFeatureAccessOutdated`, และ `ExtendedPostGis`.  
- **ฉันจะควบคุม decimal precision อย่างไร?** ใช้ตัวเลือก `NumericFormat` เช่น `General`, `RoundTrip`, หรือ `Flat`.  
- **ฉันต้องการไลเซนส์สำหรับการใช้งานจริงหรือไม่?** ใช่, จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานที่ไม่ใช่รุ่นทดลอง.  
- **เวอร์ชัน .NET ที่เข้ากันได้คืออะไร?** .NET Framework 4.0+ และ .NET 5/6/7.

## “convert geometry to WKT” คืออะไร?
การแปลง geometry เป็น WKT จะสร้างสตริงที่มนุษย์อ่านได้ซึ่งอธิบายวัตถุเชิงพื้นที่. รูปแบบนี้ได้รับการยอมรับอย่างกว้างขวางโดยเครื่องมือ GIS, ฐานข้อมูล, และเว็บเซอร์วิส, ทำให้เหมาะสำหรับการแลกเปลี่ยนข้อมูล.

## ทำไมต้องใช้ Aspose.GIS สำหรับการแปลงนี้?
- **Precision control** – เลือกจำนวนตำแหน่งทศนิยมที่ต้องการแสดง.  
- **Variant flexibility** – ตรงกับ dialect ของ WKT ที่ระบบปลายทางของคุณต้องการ.  
- **No external dependencies** – ไลบรารี .NET แท้, ไม่มีไบนารีเนทีฟ.

## ข้อกำหนดเบื้องต้น
1. **Aspose.GIS for .NET** – ดาวน์โหลดและติดตั้งจาก [download page](https://releases.aspose.com/gis/net/).  
2. **Development Environment** – สภาพแวดล้อมการพัฒนา – เวอร์ชันล่าสุดของ Visual Studio หรือ VS Code พร้อม .NET SDK.  
3. **Basic C# knowledge** – ความรู้พื้นฐาน C# – ความคุ้นเคยกับคลาส, อ็อบเจกต์, และ .NET framework.

## นำเข้า Namespaces
ขั้นแรก, นำ Namespaces ที่จำเป็นเข้าสู่สโคป:

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## ขั้นตอนที่ 1: สร้างอ็อบเจกต์ Point
สร้าง `Point` ที่คุณจะ later **convert geometry to WKT**. จุดนี้รวม latitude, longitude, และค่า measure (M) ที่เป็นตัวเลือก:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## ขั้นตอนที่ 2: ตั้งค่า Spatial Reference System (SRS)
กำหนดระบบอ้างอิงเชิงพื้นที่เพื่อให้ผลลัพธ์ WKT รู้ว่าจะอ้างอิงระบบพิกัดใด. ที่นี่เราใช้ระบบ WGS84 ที่เป็นที่นิยม:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## ขั้นตอนที่ 3: ระบุ WKT Variant
**Choose the appropriate WKT variant when you convert geometry to WKT**. แต่ละ variant จะจัดรูปแบบผลลัพธ์แตกต่างกันเล็กน้อย:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## ขั้นตอนที่ 4: ควบคุม Numeric Format (ตั้ง Numeric Format & ปรับ Decimal Precision)
ปรับแต่งการแสดงผลตัวเลขของพิกัด. คลาส `NumericFormat` ให้คุณ **set numeric format** และ **adjust decimal precision** ให้เหมาะกับความต้องการของคุณ:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## ปัญหาทั่วไป & เคล็ดลับ
- **Missing M value** – หากคุณไม่ต้องการ measure, ให้ละเว้น property `M`; variant ISO จะลบออกโดยอัตโนมัติ.  
- **Unexpected precision** – ตรวจสอบให้แน่ใจว่าคุณใช้ `NumericFormat` ที่ถูกต้อง; `General` รักษาความแม่นยำแบบ double เต็ม, ส่วน `Flat` จะปัดเศษตามจำนวนตำแหน่งทศนิยมที่ระบุ.  
- **SRID not displayed** – เฉพาะ variant `ExtendedPostGis` จะใส่คำนำหน้า `SRID=` ในผลลัพธ์. เลือก variant นี้เมื่อระบบเป้าหมายของคุณต้องการ SRID.

## สรุป
โดยทำตามขั้นตอนเหล่านี้คุณจะรู้วิธี **convert geometry to WKT**, เลือก variant ที่เหมาะสม, และควบคุมผลลัพธ์ตัวเลขอย่างแม่นยำ. สิ่งนี้ทำให้คุณมีความยืดหยุ่นในการผสาน Aspose.GIS กับเวิร์กโฟลว์ GIS, ฐานข้อมูล, หรือเว็บเซอร์วิสใด ๆ ที่รับ WKT.

## คำถามที่พบบ่อย
### Aspose.GIS รองรับทุกเวอร์ชันของ .NET หรือไม่?
ใช่, Aspose.GIS รองรับ .NET Framework 4.0 ขึ้นไป.  

### ฉันสามารถใช้ Aspose.GIS สำหรับโครงการเชิงพาณิชย์ได้หรือไม่?
ใช่, Aspose.GIS สามารถใช้ได้ทั้งในโครงการส่วนบุคคลและเชิงพาณิชย์.  

### Aspose.GIS มีการสนับสนุนรูปแบบข้อมูลเชิงพื้นที่อื่นหรือไม่?
ใช่, Aspose.GIS รองรับรูปแบบข้อมูลเชิงพื้นที่หลากหลาย รวมถึง ESRI Shapefile, GeoJSON, และ KML.  

### มีรุ่นทดลองฟรีสำหรับ Aspose.GIS หรือไม่?
ใช่, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีของ Aspose.GIS ได้จาก [here](https://releases.aspose.com/).  

### ฉันจะขอความช่วยเหลือหรือสนับสนุนสำหรับ Aspose.GIS ได้จากที่ไหน?
คุณสามารถโพสต์คำถามหรือขอความช่วยเหลือจากชุมชน Aspose.GIS ได้ที่ [forum](https://forum.aspose.com/c/gis/33).

## คำถามที่พบบ่อย
**Q: How do I export a Geometry collection to a single WKT string?**  
A: Iterate over each geometry in the collection and concatenate their `AsText` results, optionally separating them with commas or newlines.  
**Q: Can I change the SRID without altering the coordinates?**  
A: Yes, set the `SpatialReferenceSystem` property to the desired SRID; the coordinate values remain unchanged.  
**Q: What happens if I use an unsupported WKT variant?**  
A: Aspose.GIS will throw an `ArgumentException`. Always validate the variant against `WktVariant` enum values.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}