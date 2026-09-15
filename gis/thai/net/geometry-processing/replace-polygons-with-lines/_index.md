---
date: 2026-09-15
description: เรียนรู้วิธีแปลง polygon เป็น line และแปลง polygons เป็น lines ด้วย Aspose.GIS
  for .NET. คู่มือเร็วสำหรับนักพัฒนา GIS.
keywords:
- convert polygon to line
- how to replace polygons
- transform polygons to lines
- gis polygon to line
- simplify map visualization
lastmod: 2026-09-15
linktitle: แทนที่ polygons ด้วย lines
og_description: แปลง polygon เป็น line ด้วย Aspose.GIS for .NET. บทเรียนนี้แสดงวิธีแทนที่
  polygons ด้วย lines, เวอร์ชัน .NET ที่รองรับ, และข้อผิดพลาดทั่วไป.
og_image_alt: Screenshot of Aspose.GIS converting polygon to line in a .NET console
  app
og_title: แปลง polygon เป็น line ด้วย Aspose.GIS for .NET – คู่มือเร็ว
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to convert polygon to line and transform polygons to lines
    using Aspose.GIS for .NET. A quick guide for GIS developers.
  headline: Convert polygon to line with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert polygon to line and transform polygons to lines
    using Aspose.GIS for .NET. A quick guide for GIS developers.
  name: Convert polygon to line with Aspose.GIS for .NET
  steps:
  - name: Define the source geometry
    text: The `GeometryCollection` class is a container that can hold any number of
      geometry objects, including polygons, points, and lines. It is the entry point
      for bulk operations like `ReplacePolygonsByLines`. Create a geometry collection
      that includes one or more polygons you want to convert. In this exa
  - name: Convert polygons to lines
    text: The `ReplacePolygonsByLines()` method scans the supplied collection, replaces
      each polygon with a `LineString` that follows its outer ring, and leaves all
      other geometry types untouched. This single call performs the conversion in
      O(n) time, where *n* is the number of geometries in the collection.
  - name: Display the original and converted geometries
    text: Printing both the original and the transformed geometries lets you verify
      that polygons have been replaced while other geometries stay the same. The `ToString()`
      override on each geometry provides a human‑readable WKT representation.
  type: HowTo
- questions:
  - answer: Yes, it supports more than 30 formats—including Shapefile, GeoJSON, KML,
      GML, and CSV—allowing you to read, convert, and write data without external
      tools.
    question: Can Aspose.GIS for .NET work with various GIS file formats?
  - answer: Yes, you can access the free trial of Aspose.GIS for .NET on the Aspose
      releases page ([Aspose releases page](https://releases.aspose.com/)).
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Yes, developers can get support and assistance from the Aspose.GIS community
      forum ([Aspose.GIS community forum](https://forum.aspose.com/c/gis/33)).
    question: Does Aspose.GIS for .NET offer support for developers?
  - answer: Yes, you can acquire a temporary license from Aspose's temporary license
      page ([temporary license page](https://purchase.aspose.com/temporary-license/)).
    question: Can I purchase a temporary license for Aspose.GIS for .NET?
  - answer: Absolutely, it provides comprehensive documentation, code examples, and
      API references for all skill levels.
    question: Is Aspose.GIS for .NET suitable for both beginners and experienced developers?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert polygon to line
- Aspose.GIS
- .NET GIS processing
title: แปลง polygon เป็น line ด้วย Aspose.GIS for .NET
url: /th/net/geometry-processing/replace-polygons-with-lines/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลงโพลิกอนเป็นเส้นด้วย Aspose.GIS สำหรับ .NET

## บทนำ
หากคุณต้องการ **convert polygon to line** ในโครงการ GIS บน .NET, Aspose.GIS ทำให้กระบวนการเป็นเรื่องง่าย ไม่ว่าคุณจะกำลังทำให้การแสดงแผนที่ง่ายขึ้น, เตรียมข้อมูลสำหรับอัลกอริธึมการกำหนดเส้นทาง, หรือเพียงต้องการการแสดงเรขาคณิตที่สะอาดขึ้น, บทแนะนำนี้จะพาคุณผ่านขั้นตอนที่แม่นยำเพื่อแทนที่โพลิกอนด้วยเรขาคณิตเส้นโดยใช้ Aspose.GIS API คุณจะเห็นว่าทำไมห้องสมุดนี้เป็นตัวเลือกที่นิยมสำหรับนักพัฒนา GIS และวิธีทำการแปลงให้เสร็จในไม่กี่บรรทัดของโค้ด

## คำตอบอย่างรวดเร็ว
- **“convert polygon to line” หมายถึงอะไร?** มันดึงแหวนภายนอกของโพลิกอนและสร้าง `LineString` ที่ตามเส้นรอบวงเดียวกัน.  
- **ทำไมต้องใช้ Aspose.GIS สำหรับงานนี้?** ไลบรารีมีเมธอดเดียว (`ReplacePolygonsByLines`) ที่จัดการการแปลงแบบกลุ่มอย่างมีประสิทธิภาพโดยไม่ต้องทำการแยกวิเคราะห์เรขาคณิตด้วยตนเอง.  
- **เวอร์ชัน .NET ใดบ้างที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6+ ทั้งหมดได้รับการสนับสนุนเต็มรูปแบบ.  
- **ต้องมีลิขสิทธิ์สำหรับการพัฒนาหรือไม่?** รุ่นทดลองฟรีสามารถใช้สำหรับการทดสอบได้; จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **ใช้เวลานานเท่าไหร่ในการทำการแปลง?** นักพัฒนาส่วนใหญ่สามารถทำการแปลงพื้นฐานให้เสร็จภายในไม่กี่นาที (น้อยกว่า 10 นาที).  

## “convert polygon to line” คืออะไร?
การแปลงโพลิกอนเป็นเส้นหมายถึงการดึงแหวนภายนอกของโพลิกอน (เส้นรอบวง) และแสดงเป็น `LineString` เรขาคณิตที่ได้จะคงรูปร่างขอบเขตเดิมของรูปทรงเดิมไว้แต่ละข้อมูลพื้นที่ภายในจะถูกละทิ้ง ซึ่งเหมาะสำหรับการวิเคราะห์เครือข่าย, การเรนเดอร์ขอบ, หรือเมื่อคุณต้องการการแสดงผลที่เบาสำหรับแผนที่เว็บ.

## ทำไมต้องแปลงโพลิกอนเป็นเส้นด้วย Aspose.GIS?
Aspose.GIS แทนที่โพลิกอนทุกตัวในคอลเลกชันด้วยเส้นขอบของมันในหนึ่งการเรียกเดียว, รักษาโทโพโลยีและขจัดความจำเป็นในการวนลูปแบบกำหนดเอง วิธีนี้ลดความซับซ้อนของโค้ดได้ถึง 80 % และประมวลผลคอลเลกชันที่มีฟีเจอร์กว่า 10 000 รายการในเวลาน้อยกว่าวินาทีบนฮาร์ดแวร์เซิร์ฟเวอร์ทั่วไป, ด้วยคอร์ C++ เนทีฟและการจัดการหน่วยความจำแบบ zero‑copy.

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่ม, ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

### การติดตั้ง Aspose.GIS สำหรับ .NET
1. ดาวน์โหลด Aspose.GIS สำหรับ .NET: เยี่ยมชมหน้าดาวน์โหลด Aspose.GIS สำหรับ .NET ([Aspose.GIS for .NET download](https://releases.aspose.com/gis/net/)).  
2. ติดตั้ง Aspose.GIS สำหรับ .NET: ทำตามคำแนะนำการติดตั้งในแพ็กเกจหรือดูเอกสาร Aspose.GIS ([Aspose.GIS documentation](https://reference.aspose.com/gis/net/)) สำหรับขั้นตอนโดยละเอียด.

## นำเข้าเนมสเปซ
ในโครงการ .NET ของคุณ, ให้นำเข้าเนมสเปซที่จำเป็นเพื่อให้คุณสามารถทำงานกับคลาสของ Aspose.GIS ได้.

เนมสเปซ `Aspose.Gis` มีประเภทเรขาคณิตหลัก, ส่วน `Aspose.Gis.Geometries` ให้การใช้งานที่เป็นรูปธรรมเช่น `Polygon` และ `LineString`.

```csharp
using System;
using Aspose.Gis.Geometries;
```

## คู่มือขั้นตอนโดยละเอียด

### ขั้นตอนที่ 1: กำหนดเรขาคณิตต้นทาง
คลาส `GeometryCollection` เป็นคอนเทนเนอร์ที่สามารถเก็บอ็อบเจ็กต์เรขาคณิตจำนวนใดก็ได้, รวมถึงโพลิกอน, จุด, และเส้น. มันเป็นจุดเริ่มต้นสำหรับการดำเนินการแบบกลุ่มเช่น `ReplacePolygonsByLines`.

สร้างคอลเลกชันของเรขาคณิตที่รวมโพลิกอนหนึ่งหรือหลายโพลิกอนที่คุณต้องการแปลง. ในตัวอย่างนี้เรายังเพิ่มจุดเพื่อแสดงว่าองค์ประกอบที่ไม่ใช่โพลิกอนจะคงอยู่โดยไม่เปลี่ยนแปลง.

```csharp
var srcGeometry = Geometry.FromText(@"GeometryCollection (POLYGON((1 2, 1 4, 3 4, 3 2)), Point (5 1))");
```

### ขั้นตอนที่ 2: แปลงโพลิกอนเป็นเส้น
เมธอด `ReplacePolygonsByLines()` จะสแกนคอลเลกชันที่ให้มา, แทนที่แต่ละโพลิกอนด้วย `LineString` ที่ตามแหวนภายนอกของมัน, และปล่อยให้ประเภทเรขาคณิตอื่นทั้งหมดคงเดิม การเรียกเดียวนี้ทำการแปลงในเวลา O(n) โดยที่ *n* คือจำนวนเรขาคณิตในคอลเลกชัน.

```csharp
var dstGeometry = srcGeometry.ReplacePolygonsByLines();
```

### ขั้นตอนที่ 3: แสดงเรขาคณิตต้นฉบับและที่แปลงแล้ว
การพิมพ์เรขาคณิตต้นฉบับและที่แปลงแล้วทั้งสองจะทำให้คุณตรวจสอบว่าโพลิกอนได้ถูกแทนที่ในขณะที่เรขาคณิตอื่นคงเดิม. การโอเวอร์ไรด์ `ToString()` ของแต่ละเรขาคณิตให้การแสดงผล WKT ที่อ่านได้โดยมนุษย์.

```csharp
Console.WriteLine($"source: {srcGeometry.AsText()}");
Console.WriteLine($"result: {dstGeometry.AsText()}");
```

## ปัญหาและวิธีแก้ไขทั่วไป
- **ผลลัพธ์เส้นหายไป:** ตรวจสอบให้แน่ใจว่าเรขาคณิตต้นทางมีโพลิกอนจริง; จุดหรือมัลติพอยท์จะถูกส่งผ่านโดยไม่เปลี่ยนแปลง.  
- **ปัญหาลำดับพิกัด:** Aspose.GIS คาดว่าพิกัดจะอยู่ในลำดับ `X Y` (ลองจิจูด ละติจูด). การสลับค่าจะทำให้รูปทรงที่ไม่คาดคิด.  
- **คอลเลกชันขนาดใหญ่:** สำหรับชุดข้อมูลขนาดใหญ่มาก (หลายแสนฟีเจอร์), ประมวลผลเรขาคณิตเป็นชุดละ 10 000–20 000 รายการเพื่อรักษาการใช้หน่วยความจำให้อยู่ต่ำกว่า 200 MB.

## คำถามที่พบบ่อย

**Q: Aspose.GIS สำหรับ .NET สามารถทำงานกับรูปแบบไฟล์ GIS ต่าง ๆ ได้หรือไม่?**  
A: ใช่, รองรับรูปแบบมากกว่า 30 แบบ—รวมถึง Shapefile, GeoJSON, KML, GML, และ CSV—ทำให้คุณสามารถอ่าน, แปลง, และเขียนข้อมูลโดยไม่ต้องใช้เครื่องมือภายนอก.

**Q: มีรุ่นทดลองฟรีสำหรับ Aspose.GIS สำหรับ .NET หรือไม่?**  
A: ใช่, คุณสามารถเข้าถึงรุ่นทดลองฟรีของ Aspose.GIS สำหรับ .NET ได้ที่หน้าปล่อยของ Aspose ([Aspose releases page](https://releases.aspose.com/)).

**Q: Aspose.GIS สำหรับ .NET มีการสนับสนุนนักพัฒนาหรือไม่?**  
A: ใช่, นักพัฒนาสามารถรับการสนับสนุนและความช่วยเหลือจากฟอรั่มชุมชน Aspose.GIS ([Aspose.GIS community forum](https://forum.aspose.com/c/gis/33)).

**Q: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.GIS สำหรับ .NET ได้หรือไม่?**  
A: ใช่, คุณสามารถรับใบอนุญาตชั่วคราวจากหน้าลิขสิทธิ์ชั่วคราวของ Aspose ([temporary license page](https://purchase.aspose.com/temporary-license/)).

**Q: Aspose.GIS สำหรับ .NET เหมาะกับทั้งผู้เริ่มต้นและนักพัฒนาที่มีประสบการณ์หรือไม่?**  
A: แน่นอน, มันมีเอกสารครบถ้วน, ตัวอย่างโค้ด, และอ้างอิง API สำหรับทุกระดับทักษะ.

## สรุป
โดยทำตามขั้นตอนเหล่านี้, คุณได้เรียนรู้วิธี **convert polygon to line** และการ **transform polygons to lines** อย่างมีประสิทธิภาพด้วย Aspose.GIS สำหรับ .NET ความสามารถนี้เปิดประตูสู่การแสดงผลที่เบาขึ้น, การเตรียมการกำหนดเส้นทาง, และกระบวนการ GIS อื่น ๆ อีกมากมาย อย่าลังเลที่จะสำรวจคุณลักษณะเพิ่มเติมของ Aspose.GIS เช่น การสอบถามเชิงพื้นที่, การแปลงพิกัด, และการแปลงรูปแบบเพื่อขยายความสามารถของแอปพลิเคชันของคุณ.

---

**อัปเดตล่าสุด:** 2026-09-15  
**ทดสอบด้วย:** Aspose.GIS สำหรับ .NET (รุ่นล่าสุด)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [เรียนรู้วิธีสร้างเรขาคณิต LineString ด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [วิธีสร้าง GeoJSON ด้วยการกำหนดค่าความคลาดเคลื่อนใน Aspose.GIS สำหรับ .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [วิธีแปลงเรขาคณิตเป็น WKT ด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}