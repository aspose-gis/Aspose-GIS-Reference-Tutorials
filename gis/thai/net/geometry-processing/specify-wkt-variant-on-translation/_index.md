---
date: 2026-09-15
description: เรียนรู้วิธีการกำหนดระบบพิกัด, ตั้งค่ารูปแบบ WKT และควบคุมความแม่นยำของทศนิยมเมื่อสร้างเรขาคณิตจุดใน
  C# ด้วย Aspose.GIS สำหรับ .NET.
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: ระบุรูปแบบ WKT ในการแปล
og_description: เรียนรู้วิธีการกำหนดระบบพิกัด, ตั้งค่ารูปแบบ WKT และควบคุมความแม่นยำของทศนิยมเมื่อสร้างเรขาคณิตจุดใน
  C# ด้วย Aspose.GIS สำหรับ .NET.
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: กำหนดระบบพิกัด, ตั้งค่ารูปแบบ WKT ด้วย Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: กำหนดระบบพิกัด, ตั้งค่ารูปแบบ WKT ด้วย Aspose.GIS
url: /th/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# กำหนดระบบพิกัด, ตั้งค่า WKT variant ด้วย Aspose.GIS

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **assign coordinate system**, เลือก WKT variant ที่เหมาะสม, และควบคุมความแม่นยำของทศนิยมเมื่อคุณ **create point geometry** ด้วย C# กับ Aspose.GIS สำหรับ .NET ไม่ว่าคุณจะสร้างบริการแผนที่, ทำการวิเคราะห์เชิงพื้นที่, หรือแลกเปลี่ยนข้อมูลระหว่างแพลตฟอร์ม GIS การตั้งค่าเหล่านี้รับประกันว่าผลลัพธ์ของคุณจะสามารถทำงานร่วมกันได้และอ่านง่าย มาดำเนินการตามขั้นตอนทีละขั้นตอนกัน

## คำตอบอย่างรวดเร็ว
- **“assign coordinate system” คืออะไร?** มันผูก geometry เข้ากับระบบอ้างอิงพิกัดเฉพาะ เช่น WGS‑84.  
- **WKT variants ที่รองรับมีอะไรบ้าง?** Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.  
- **ฉันจะควบคุมความแม่นยำของทศนิยมได้อย่างไร?** ใช้ enum `NumericFormat` (`General`, `RoundTrip`, `Flat`).  
- **ฉันต้องการไลเซนส์สำหรับ Aspose.GIS หรือไม่?** มีเวอร์ชันทดลองฟรี; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์.  
- **เวอร์ชัน .NET ที่เข้ากันได้มีอะไรบ้าง?** .NET Framework 4.0+ and .NET Core/5/6+.

## “assign coordinate system” คืออะไร?
การกำหนด spatial reference (หรือ spatial reference system, SRS) จะบอกซอฟต์แวร์ GIS ว่าจะตีความค่าพิกัดของ geometry อย่างไร โดยเชื่อมตัวเลขกับระบบพิกัดในโลกจริง เช่น WGS‑84. หากไม่มี SRS ตัวเลข latitude‑longitude ของจุดจะไม่มีความหมายในโลกจริง.

## ทำไมต้องควบคุม WKT variant และ numeric format?
เครื่องมือ GIS มากกว่า 30 ตัวคาดหวังไวยากรณ์ WKT เฉพาะ ดังนั้นการเลือก variant ที่เหมาะจึงช่วยป้องกันข้อผิดพลาดในการนำเข้า การตั้งค่า numeric format ลดเสียงรบกวนจากการปัดเศษและทำให้ผลลัพธ์กระชับ ซึ่งสำคัญมากเมื่อบันทึกหรือไฟล์ถูกประมวลผลโดยโปรแกรมอัตโนมัติ.

## ข้อกำหนดเบื้องต้น
1. Aspose.GIS for .NET – ดาวน์โหลดจาก [หน้าดาวน์โหลด](https://releases.aspose.com/gis/net/).  
2. สภาพแวดล้อมการพัฒนา .NET (Visual Studio, VS Code, หรือ Rider).  
3. ความคุ้นเคยพื้นฐานกับ C# และ .NET framework.

## นำเข้า namespaces
ก่อนใช้คลาสใด ๆ ของ Aspose.GIS ให้ทำการนำเข้า namespaces ที่จำเป็น:

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

## วิธีกำหนดระบบพิกัดให้กับจุด?
โหลดอินสแตนซ์ `Point` แล้วแนบ spatial reference system (SRS) ด้วยคลาส `SpatialReference`. รูปแบบสองขั้นตอนนี้ทำให้ geometry มี metadata ของระบบพิกัดเมื่อส่งออก ซึ่งช่วยให้เครื่องมือ downstream สามารถตีความพิกัดได้อย่างถูกต้อง. คลาส `Point` แทนตำแหน่งเดียวที่กำหนดด้วยพิกัด X (longitude) และ Y (latitude).

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## ขั้นตอนที่ 2: กำหนด spatial reference system (SRS)
ตอนนี้เราจะ **assign spatial reference** ให้กับจุด. `SpatialReference` แสดงระบบอ้างอิงพิกัดที่ระบุด้วย SRID. ที่นี่เราใช้ระบบ WGS‑84 ที่ได้รับการสนับสนุนอย่างกว้างขวาง (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## ขั้นตอนที่ 3: ระบุ WKT variant ที่ต้องการ
เลือก WKT variant ที่ตรงกับแอปพลิเคชัน downstream ของคุณ:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## วิธีตั้งค่าความแม่นยำของทศนิยมสำหรับผลลัพธ์ WKT?
ควบคุมจำนวนตำแหน่งทศนิยมที่ปรากฏในสตริงสุดท้ายโดยใช้ enum `NumericFormat` ซึ่งกำหนดกฎการจัดรูปแบบเช่น `General`, `RoundTrip`, หรือ `Flat`. การเลือก `RoundTrip` จะรักษาความแม่นยำของพิกัดเต็มสำหรับสถานการณ์ round‑tripping, ส่วน `General` ให้การแสดงผลกระชับที่เหมาะกับงาน visualisation ส่วนใหญ่. enum `NumericFormat` ควบคุมวิธีการจัดรูปแบบตัวเลขพิกัดในผลลัพธ์ WKT.

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### ข้อผิดพลาดทั่วไป & เคล็ดลับ
- **Pitfall:** ลืมตั้งค่า SRS ก่อนเรียก `AsText` อาจทำให้ข้อมูล SRID หายไป.  
- **Tip:** ใช้ `NumericFormat.RoundTrip` เมื่อคุณต้องการการ round‑tripping ของพิกัดโดยไม่สูญเสียข้อมูล.  
- **Tip:** variant `Iso` เป็นที่พกพาที่สุด; เลือก `ExtendedPostGis` เฉพาะเมื่อคุณต้องการฝัง SRID.

## สรุป
คุณได้เรียนรู้วิธี **assign coordinate system**, เลือก WKT variant ที่เหมาะสม, และ **set decimal precision** เมื่อคุณ **create point geometry** ด้วย Aspose.GIS การควบคุมเหล่านี้ให้ความยืดหยุ่นในการตอบสนองความต้องการของเวิร์กโฟลว์ GIS ใด ๆ ตั้งแต่การ visualisation อย่างง่ายจนถึงการวิเคราะห์เชิงพื้นที่ที่ต้องการความแม่นยำสูง.

## คำถามที่พบบ่อย

**Q:** Aspose.GIS รองรับทุกเวอร์ชันของ .NET หรือไม่?  
**A:** ใช่, Aspose.GIS รองรับ .NET Framework 4.0 ขึ้นไป รวมถึง .NET Core/5/6.

**Q:** ฉันสามารถใช้ Aspose.GIS สำหรับโครงการเชิงพาณิชย์ได้หรือไม่?  
**A:** แน่นอน. จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์, แต่มีเวอร์ชันทดลองฟรีสำหรับการประเมิน.

**Q:** Aspose.GIS รองรับรูปแบบข้อมูลเชิงพื้นที่อื่น ๆ หรือไม่?  
**A:** ใช่, รองรับมากกว่า 30 รูปแบบ รวมถึง ESRI Shapefile, GeoJSON, KML, CSV, และอื่น ๆ อีกมาก.

**Q:** ฉันสามารถดาวน์โหลดเวอร์ชันทดลองฟรีได้จากที่ไหน?  
**A:** คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรีของ Aspose.GIS ได้จาก [หน้า Aspose.GIS ฟรีทดลองดาวน์โหลด](https://releases.aspose.com/).

**Q:** จะขอรับความช่วยเหลือเมื่อเจอปัญหาต้องทำอย่างไร?  
**A:** โพสต์คำถามของคุณใน [forum](https://forum.aspose.com/c/gis/33) ของชุมชน Aspose.GIS ที่ซึ่งทีมงาน Aspose และสมาชิกชุมชนสามารถให้ความช่วยเหลือได้.

---

**อัปเดตล่าสุด:** 2026-09-15  
**ทดสอบกับ:** Aspose.GIS for .NET (latest release)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [สร้าง Vector Layer และตั้งค่า Spatial Reference System ของมัน](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [วิธีแปลง Geometry เป็น WKT ด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [วิธีจำกัดความแม่นยำเมื่อเขียน Geometries ด้วย Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}