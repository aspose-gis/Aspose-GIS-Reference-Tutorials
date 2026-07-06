---
date: 2026-04-09
description: เรียนรู้วิธีกำหนดระบบอ้างอิงเชิงพื้นที่และตั้งค่าความแม่นยำของทศนิยมเมื่อสร้างจุดใน
  C# ด้วย Aspose.GIS สำหรับ .NET ในแอปพลิเคชัน .NET ของคุณ.
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: ระบุรูปแบบ WKT ในการแปล
second_title: Aspose.GIS .NET API
title: กำหนดการอ้างอิงเชิงพื้นที่และตั้งค่า WKT Variant ด้วย Aspose.GIS
url: /th/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# กำหนดระบบอ้างอิงเชิงพื้นที่และตั้งค่าตัวแปร WKT ด้วย Aspose.GIS

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **assign spatial reference** ให้กับเรขาคณิตและควบคุมรูปแบบการแสดงผล WKT อย่างแม่นยำด้วย Aspose.GIS สำหรับ .NET ไม่ว่าคุณจะต้อง **create point C#** สำหรับการทำแผนที่ การวิเคราะห์ หรือการแลกเปลี่ยนข้อมูล การเลือกตัวแปร WKT ที่เหมาะสมและความแม่นยำของตัวเลขทำให้ข้อมูลเชิงพื้นที่ของคุณสามารถทำงานร่วมกันได้และอ่านง่าย มาดำเนินการตามขั้นตอนทีละขั้นตอนกันเถอะ.

## คำตอบสั้น
- **“assign spatial reference” หมายถึงอะไร?** มันผูกเรขาคณิตกับระบบพิกัดเฉพาะ เช่น WGS‑84.  
- **WKT variants ที่รองรับมีอะไรบ้าง?** Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.  
- **ฉันจะควบคุมความแม่นยำของทศนิยมได้อย่างไร?** ใช้ตัวเลือก `NumericFormat` เช่น `General`, `RoundTrip`, หรือ `Flat`.  
- **ฉันต้องการไลเซนส์หรือไม่?** มีรุ่นทดลองใช้งานฟรี; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **เวอร์ชัน .NET ที่เข้ากันได้มีอะไรบ้าง?** .NET Framework 4.0+ and .NET Core/5/6+.

## “assign spatial reference” คืออะไร?
การกำหนดระบบอ้างอิงเชิงพื้นที่ (หรือระบบอ้างอิงเชิงพื้นที่, SRS) บอกซอฟต์แวร์ GIS ว่าจะตีความค่าพิกัดของเรขาคณิตอย่างไร หากไม่มี SRS ตัวเลขละติจูด‑ลองจิจูดของจุดจะไม่มีความหมายในโลกจริง.

## ทำไมต้องควบคุมตัวแปร WKT และรูปแบบตัวเลข?
เครื่องมือ GIS ต่าง ๆ คาดหวังไวยากรณ์ WKT ที่แตกต่างกันเล็กน้อย การเลือกตัวแปรที่เหมาะสมช่วยให้การแลกเปลี่ยนข้อมูลเป็นไปอย่างราบรื่น ในขณะที่การตั้งค่าความแม่นยำของทศนิยมช่วยป้องกันข้อผิดพลาดจากการปัดเศษหรือจำนวนที่ยาวเกินไปซึ่งทำให้บันทึกและไฟล์แออัด.

## ข้อกำหนดเบื้องต้น
1. Aspose.GIS for .NET – ดาวน์โหลดจาก [หน้าดาวน์โหลด](https://releases.aspose.com/gis/net/).  
2. สภาพแวดล้อมการพัฒนา .NET (Visual Studio, VS Code, หรือ Rider).  
3. ความคุ้นเคยพื้นฐานกับ C# และ .NET framework.

## นำเข้า Namespaces
ก่อนใช้คลาส Aspose.GIS ใด ๆ ให้ทำการนำเข้า Namespaces ที่จำเป็น:

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

## ขั้นตอนที่ 1: สร้างอ็อบเจ็กต์ Point (create point C#)
เราจะเริ่มโดยสร้าง `Point` พร้อมค่าละติจูด, ลองจิจูด, และค่ามาตรการ (M) ที่เป็นตัวเลือก:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## ขั้นตอนที่ 2: กำหนดระบบอ้างอิงเชิงพื้นที่ (SRS)
ตอนนี้เราจะ **assign spatial reference** ให้กับจุดนี้ เราใช้ระบบ WGS‑84 ที่ได้รับการสนับสนุนอย่างกว้างขวาง (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## ขั้นตอนที่ 3: ระบุตัวแปร WKT ที่ต้องการ
เลือกตัวแปร WKT ที่ตรงกับแอปพลิเคชัน downstream ของคุณ:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## ขั้นตอนที่ 4: ตั้งค่าความแม่นยำของทศนิยมสำหรับผลลัพธ์ WKT
ควบคุมจำนวนตัวเลขที่ปรากฏในสตริงสุดท้ายโดยใช้ `NumericFormat`:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ข้อผิดพลาด:** การลืมตั้งค่า SRS ก่อนเรียก `AsText` อาจทำให้ข้อมูล SRID หายไป.  
- **เคล็ดลับ:** ใช้ `NumericFormat.RoundTrip` เมื่อคุณต้องการการแปลงพิกัดแบบไม่มีการสูญเสีย.  
- **เคล็ดลับ:** ตัวแปร `Iso` เป็นที่พกพาที่สุด; เลือก `ExtendedPostGis` เฉพาะเมื่อคุณต้องการฝัง SRID.

## สรุป
ตอนนี้คุณรู้วิธี **assign spatial reference**, เลือกตัวแปร WKT ที่เหมาะสม, และ **set decimal precision** เมื่อคุณ **create point C#** ด้วย Aspose.GIS การควบคุมเหล่านี้ให้ความยืดหยุ่นในการตอบสนองความต้องการที่แม่นยำของกระบวนการ GIS ใด ๆ ตั้งแต่การแสดงผลอย่างง่ายจนถึงการวิเคราะห์เชิงพื้นที่ความแม่นยำสูง.

## คำถามที่พบบ่อย

**Q:** Aspose.GIS รองรับทุกเวอร์ชันของ .NET หรือไม่?  
**A:** ใช่, Aspose.GIS รองรับ .NET Framework 4.0 ขึ้นไป รวมถึง .NET Core/5/6.

**Q:** ฉันสามารถใช้ Aspose.GIS สำหรับโครงการเชิงพาณิชย์ได้หรือไม่?  
**A:** แน่นอน. จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์, แต่มีรุ่นทดลองฟรีสำหรับการประเมิน.

**Q:** Aspose.GIS รองรับรูปแบบข้อมูลเชิงพื้นที่อื่น ๆ หรือไม่?  
**A:** ใช่, มันทำงานร่วมกับ ESRI Shapefile, GeoJSON, KML, และรูปแบบอื่น ๆ อีกมากมาย.

**Q:** ฉันสามารถดาวน์โหลดรุ่นทดลองฟรีได้จากที่ไหน?  
**A:** คุณสามารถดาวน์โหลดรุ่นทดลองฟรีของ Aspose.GIS ได้จาก [ที่นี่](https://releases.aspose.com/).

**Q:** ฉันจะขอความช่วยเหลือเมื่อเจอปัญหาได้อย่างไร?  
**A:** โพสต์คำถามของคุณใน [forum](https://forum.aspose.com/c/gis/33) ของชุมชน Aspose.GIS ที่ซึ่งทั้งทีมงาน Aspose และสมาชิกชุมชนสามารถช่วยเหลือได้.

---

**อัปเดตล่าสุด:** 2026-04-09  
**ทดสอบกับ:** Aspose.GIS for .NET (latest release)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}