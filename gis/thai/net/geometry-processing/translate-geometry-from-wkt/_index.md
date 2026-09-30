---
date: 2026-09-30
description: เรียนรู้วิธีแยกวิเคราะห์ WKT และนับจุดโดยใช้ Aspose.GIS สำหรับ .NET พร้อมคำแนะนำขั้นตอนต่อขั้นตอนในการแปลงเรขาคณิต
  WKT เป็นอ็อบเจกต์
keywords:
- how to parse wkt
- convert wkt geometry
- Aspose.GIS .NET
- count points from wkt
- .NET spatial analytics
lastmod: 2026-09-30
linktitle: แปลงเรขาคณิตจาก WKT
og_description: เรียนรู้วิธีแยกวิเคราะห์ WKT และนับจุดโดยใช้ Aspose.GIS สำหรับ .NET
  คู่มือนี้จะแสดงวิธีแปลงเรขาคณิต WKT เป็นอ็อบเจกต์เพื่อการวิเคราะห์เชิงพื้นที่อย่างรวดเร็ว
og_image_alt: 'Developer guide: parse WKT and count points with Aspose.GIS for .NET'
og_title: วิธีแยกวิเคราะห์ WKT และนับจุดด้วย Aspose.GIS สำหรับ .NET
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to parse WKT and count points using Aspose.GIS for .NET,
    with step‑by‑step guidance on converting WKT geometry to objects.
  headline: How to parse WKT and count points with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to parse WKT and count points using Aspose.GIS for .NET,
    with step‑by‑step guidance on converting WKT geometry to objects.
  name: How to parse WKT and count points with Aspose.GIS for .NET
  steps:
  - name: '**Aspose.GIS for .NET API** – download it from the Aspose.GIS for .NET
      download page: [Aspose.GIS for .NET download](https://releases.aspose.com/gis/net/).
      For other Aspose products see the general releases page: [Aspose releases](https://releases.aspose.com/).'
    text: '**Aspose.GIS for .NET API** – download it from the Aspose.GIS for .NET
      download page: [Aspose.GIS for .NET download](https://releases.aspose.com/gis/net/).
      For other Aspose products see the general releases page: [Aspose releases](https://releases.aspose.com/).'
  - name: A recent version of **Visual Studio** or any .NET‑compatible IDE.
    text: A recent version of **Visual Studio** or any .NET‑compatible IDE.
  - name: Basic knowledge of **C#** programming.
    text: Basic knowledge of **C#** programming.
  type: HowTo
- questions:
  - answer: Yes, you can. Aspose.GIS for .NET is licensed per developer, allowing
      unrestricted use in commercial applications.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, Aspose.GIS for .NET supports WKB, GeoJSON, Shapefile, and several
      raster formats, giving you flexibility when integrating with existing GIS pipelines.
    question: Does Aspose.GIS for .NET support other geometric formats besides WKT?
  - answer: 'Yes, you can get a free trial from the Aspose releases page: [Aspose
      free trial downloads](https://releases.aspose.com/).'
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: 'You can find the documentation in the Aspose.GIS .NET reference: [Aspose.GIS
      .NET documentation](https://reference.aspose.com/gis/net/).'
    question: Where can I find documentation for Aspose.GIS for .NET?
  - answer: 'You can get support from the Aspose.GIS forum: [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).'
    question: How can I get support for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- parse WKT
- Aspose.GIS
- .NET geometry processing
- spatial analytics
- count points
title: วิธีแยกวิเคราะห์ WKT และนับจุดด้วย Aspose.GIS สำหรับ .NET
url: /th/net/geometry-processing/translate-geometry-from-wkt/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแยกวิเคราะห์ WKT และนับจุดด้วย Aspose.GIS สำหรับ .NET

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีแยกวิเคราะห์ WKT** และนับจำนวนจุดที่มันมีโดยใช้ไลบรารี Aspose.GIS สำหรับ .NET ไม่ว่าคุณจะกำลังสร้างบริการแผนที่, ทำการวิเคราะห์เชิงพื้นที่, หรือเพียงแค่ต้องการตรวจสอบข้อมูลเรขาคณิต การแยกวิเคราะห์ WKT เป็นขั้นตอนแรกของกระบวนการทำงานเชิงภูมิศาสตร์ใด ๆ คุณยังจะได้เห็นวิธี **แปลงเรขาคณิต WKT** ให้เป็นอ็อบเจ็กต์ที่มีชนิดอย่างเข้มแข็ง เพื่อให้คุณสามารถสอบถาม, แก้ไข, และส่งออกข้อมูลภายในแอปพลิเคชัน C# 

## คำตอบสั้น
- **“วิธีแยกวิเคราะห์ WKT” หมายถึงอะไร?** หมายถึงการแปลงข้อความ Well‑Known Text ให้เป็นอ็อบเจ็กต์เรขาคณิตของ Aspose.GIS ที่คุณสามารถทำงานด้วยโปรแกรมได้.  
- **API ใดจัดการการแปลง WKT?** `Geometry.FromText` แยกวิเคราะห์สตริง WKT ที่ถูกต้องใด ๆ และคืนค่าชนิดเรขาคณิตที่เหมาะสม.  
- **ฉันต้องการไลเซนส์หรือไม่?** มีรุ่นทดลองฟรีให้ใช้ แต่ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET 5, .NET 6, .NET Core 3.1 และ .NET Framework 4.6+.  
- **วิธีนี้เร็วสำหรับชุดข้อมูลขนาดใหญ่หรือไม่?** ใช่ – ไลบรารีประมวลผลจุดหลายล้านจุดในหน่วยความจำด้วยค่าโอเวอร์เฮดที่เป็นเชิงเส้นย่อย.  

## WKT คืออะไร?
Well‑Known Text (WKT) คือรูปแบบข้อความธรรมดาสำหรับเรขาคณิตที่กำหนดโดย Open Geospatial Consortium (OGC) มันเข้ารหัสจุด, เส้น, โพลิกอนและคอลเลกชันในรูปแบบที่มนุษย์อ่านได้ เช่น `POINT (30 10)` หรือ `LINESTRING (30 10, 10 30, 40 40)`.

## ทำไมต้องแปลงเรขาคณิต WKT?
การแปลงเรขาคณิต WKT ทำให้คุณสามารถเปลี่ยนรูปแบบข้อความให้เป็นอ็อบเจ็กต์ของ Aspose.GIS ซึ่งทำให้คุณสามารถทำการสอบถามเชิงพื้นที่ (เช่น การตัดกัน, บัฟเฟอร์ ฯลฯ), แก้ไขพิกัดด้วยโปรแกรม, และส่งออกข้อมูลเป็นรูปแบบอื่น ๆ เช่น GeoJSON, Shapefile หรือ WKB การแปลงทำทั้งหมดในหน่วยความจำ, รองรับพิกัด 3‑D, และสามารถจัดการไฟล์ขนาดสูงสุดถึง 2 GB โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ ทำให้เหมาะกับสายการประมวลผลเชิงวิเคราะห์ที่มีอัตราการส่งผ่านสูง.

## วิธีแยกวิเคราะห์ WKT?
โหลดสตริง WKT ด้วย `Geometry.FromText`, แคสต์ผลลัพธ์เป็นอินเทอร์เฟซที่เหมาะสม (เช่น `ILineString`), แล้วใช้คุณสมบัติของเรขาคณิต—เช่น `Count`—เพื่อดึงจำนวนจุด รูปแบบสามขั้นตอนนี้ (แยกวิเคราะห์, แคสต์, สอบถาม) ทำงานกับประเภทเรขาคณิตใด ๆ ที่ Aspose.GIS รองรับ รวมถึง `POINT`, `LINESTRING Z`, `POLYGON` และ `GEOMETRYCOLLECTION`.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **Aspose.GIS for .NET API** – ดาวน์โหลดจากหน้า Aspose.GIS for .NET download page: [Aspose.GIS for .NET download](https://releases.aspose.com/gis/net/). สำหรับผลิตภัณฑ์ Aspose อื่น ๆ ดูหน้าการปล่อยทั่วไป: [Aspose releases](https://releases.aspose.com/).  
2. เวอร์ชันล่าสุดของ **Visual Studio** หรือ IDE ที่รองรับ .NET ใด ๆ.  
3. ความรู้พื้นฐานด้านการเขียนโปรแกรม **C#**.

## นำเข้าเนมสเปซ
ก่อนอื่น, นำเข้าเนมสเปซที่จำเป็นสำหรับการจัดการเรขาคณิต:

เนมสเปซ `Aspose.Gis` มีประเภทเรขาคณิตหลักทั้งหมด, ในขณะที่ `Aspose.Gis.Geometries` ให้การทำงานเชิงรูปธรรมที่คุณจะใช้.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: สร้าง LineString จาก WKT
คลาส `LineString` แสดงถึงคอลเลกชันของจุดที่เรียงลำดับกันเป็นเส้นต่อเนื่อง มันทำการทำงานตามอินเทอร์เฟซ `ILineString`, เปิดเผยเมธอดสำหรับการนับและจัดการจุด

แยกวิเคราะห์ข้อความ WKT และแคสต์ผลลัพธ์เป็น `ILineString`:

```csharp
ILineString line = (ILineString)Geometry.FromText("LINESTRING Z (0.1 0.2 0.3, 1 2 1, 12 23 2)");
```

> **เคล็ดลับ:** เมธอด `FromText` จะตรวจจับประเภทเรขาคณิตโดยอัตโนมัติ, ดังนั้นคุณสามารถแคสต์เป็นอินเทอร์เฟซที่เหมาะสม (`ILineString`, `IPolygon`, ฯลฯ).

## ขั้นตอนที่ 2: นับจำนวนจุดใน LineString
คุณสมบัติ `Count` คืนค่าจำนวนคู่พิกัดทั้งหมดที่เก็บไว้ในเรขาคณิต นี่เป็นวิธีรวดเร็วในการตรวจสอบว่าเรขาคณิตมีจำนวนจุดตามที่คาดหวังก่อนทำการดำเนินการเชิงพื้นที่ที่มีค่าใช้จ่ายสูงกว่า

ดึงจำนวนจุด:

```csharp
Console.WriteLine(line.Count); // Output: 3
```

คุณสมบัติ `Count` คืนค่าจำนวนคู่พิกัดทั้งหมด ซึ่งเป็นประโยชน์สำหรับการตรวจสอบหรือการวิเคราะห์.

## ปัญหาที่พบบ่อยและเคล็ดลับ
- **สตริง WKT ที่ไม่ถูกต้อง** – หาก WKT มีรูปแบบผิด, `Geometry.FromText` จะโยนข้อยกเว้น. ควรห่อการเรียกในบล็อก `try/catch` เพื่อจัดการข้อผิดพลาดอย่างราบรื่น.  
- **3D กับ 2D** – ตัวอย่างใช้ `LINESTRING Z` แบบ 3‑D. หากข้อมูลของคุณเป็น 2‑D, ให้ละเว้นคีย์เวิร์ด `Z`.  
- **คอลเลกชันขนาดใหญ่** – สำหรับชุดข้อมูลขนาดมหาศาล, พิจารณาการสตรีมข้อมูลหรือประมวลผลเป็นชุดเพื่อ ลดความกดดันของหน่วยความจำ. Aspose.GIS สามารถประมวลผลคอลเลกชันที่มีจุดมากกว่า 10 ล้านจุดโดยคงการใช้หน่วยความจำสูงสุดต่ำกว่า 500 MB.

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้ Aspose.GIS for .NET ในโครงการเชิงพาณิชย์ของฉันได้หรือไม่?**  
ตอบ: ใช่, คุณสามารถทำได้. Aspose.GIS for .NET มีไลเซนส์ต่อผู้พัฒนา, ให้การใช้โดยไม่มีข้อจำกัดในแอปพลิเคชันเชิงพาณิชย์.

**ถาม: Aspose.GIS for .NET รองรับรูปแบบเรขาคณิตอื่น ๆ นอกจาก WKT หรือไม่?**  
ตอบ: ใช่, Aspose.GIS for .NET รองรับ WKB, GeoJSON, Shapefile, และรูปแบบเรสเตอร์หลายแบบ, ให้ความยืดหยุ่นเมื่อผสานรวมกับสายงาน GIS ที่มีอยู่.

**ถาม: มีรุ่นทดลองฟรีสำหรับ Aspose.GIS for .NET หรือไม่?**  
ตอบ: มี, คุณสามารถรับรุ่นทดลองฟรีจากหน้าการปล่อยของ Aspose: [Aspose free trial downloads](https://releases.aspose.com/).

**ถาม: ฉันจะหาเอกสารสำหรับ Aspose.GIS for .NET ได้จากที่ไหน?**  
ตอบ: คุณสามารถหาเอกสารได้ใน Aspose.GIS .NET reference: [Aspose.GIS .NET documentation](https://reference.aspose.com/gis/net/).

**ถาม: ฉันจะขอรับการสนับสนุนสำหรับ Aspose.GIS for .NET ได้อย่างไร?**  
ตอบ: คุณสามารถรับการสนับสนุนจากฟอรั่ม Aspose.GIS: [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

---

**อัปเดตล่าสุด:** 2026-09-30  
**ทดสอบด้วย:** Aspose.GIS for .NET 24.11 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [แปลงเรขาคณิตเป็น Wkt](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [วิธีเพิ่มจุดและวนซ้ำเรขาคณิตใน .NET](/gis/net/geometry-processing/iterate-over-points-in-geometry/)
- [นับจุดในเรขาคณิต](/gis/net/geometry-creation/count-points-in-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}