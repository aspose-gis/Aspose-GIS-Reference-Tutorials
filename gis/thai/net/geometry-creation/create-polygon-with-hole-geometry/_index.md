---
date: 2026-09-05
description: เรียนรู้วิธีสร้างวงแหวนภายในของ polygon ที่มีรูโดยใช้ Aspose.GIS สำหรับ
  .NET คู่มือนี้จะแสดงวิธีเพิ่มรูใน polygon และทำงานกับข้อมูล
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: สร้าง Polygon พร้อม Geometry ที่มีรู
og_description: เรียนรู้วิธีสร้างวงแหวนภายในของ polygon ที่มีรูโดยใช้ Aspose.GIS สำหรับ
  .NET คู่มือนี้จะแสดงวิธีเพิ่มรูใน polygon และทำงานกับข้อมูล
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: สร้างวงแหวนภายในของ polygon ที่มีรูโดยใช้ Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: สร้างวงแหวนภายในของ polygon ที่มีรูโดยใช้ Aspose.GIS
url: /th/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างวงแหวนภายในของโพลิกอนที่มีรูโดยใช้ Aspose.GIS

## บทนำ
ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **create a polygon interior ring** ที่มีรูโดยใช้ Aspose.GIS สำหรับ .NET ไม่ว่าคุณจะกำลังสร้างแอปพลิเคชันแผนที่, ทำการวิเคราะห์เชิงพื้นที่, หรือเตรียมข้อมูลสำหรับบริการ GIS การฝังรูภายในโพลิกอนเป็นทักษะพื้นฐาน เราจะเดินผ่านขั้นตอนทั้งหมด—from setting up the development environment to generating a valid polygon object that can be saved to any supported geospatial format.

## คำตอบอย่างรวดเร็ว
- **What does “create polygon with hole” mean?** หมายความว่าการสร้างโพลิกอนที่มีหนึ่งหรือหลายวงแหวนภายใน (รู) ซึ่งจะไม่รวมในพื้นที่  
- **Which library handles this?** Aspose.GIS for .NET ให้การสนับสนุนเต็มรูปแบบสำหรับวงแหวนภายนอกและภายใน  
- **Do I need a license?** การทดลองใช้ฟรีทำงานได้สำหรับการพัฒนา; จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานจริง  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **How long does it take?** โดยทั่วไปใช้เวลาน้อยกว่า 10 minutes สำหรับการดำเนินการและทดสอบ  

## วิธีเพิ่มรูในโพลิกอนโดยใช้ Aspose.GIS
โหลดสภาพแวดล้อม GIS ของคุณ, กำหนดวงแหวนภายนอก, จากนั้นแนบหนึ่งหรือหลายวงแหวนภายใน Aspose.GIS จะจัดแนววงแหวนโดยอัตโนมัติและตรวจสอบความถูกต้องของรูปทรง, ดังนั้นคุณสามารถมุ่งเน้นที่พิกัดที่แสดงถึงช่องว่างที่ต้องการได้

## วงแหวนภายในของโพลิกอนคืออะไร?
A **polygon interior ring** คือขอบเขตภายในที่ลบพื้นที่ออกจากรูปร่างภายนอกของโพลิกอน.  
คุณสร้างมันโดยกำหนดลำดับจุดปิดที่ Aspose.GIS พิจารณาเป็นรู, ซึ่งจะถูกตัดออกเมื่อคำนวณพื้นที่หรือแสดงรูปร่าง

## ทำไมต้องสร้างวงแหวนภายในของโพลิกอนโดยใช้ Aspose.GIS?
Aspose.GIS ตรวจสอบและแก้ไขการจัดแนวของวงแหวนภายในเวลาไม่ถึง 5 ms สำหรับโพลิกอนที่มีประมาณ 200 จุด, ทำให้ไม่ต้องเขียนโค้ดตรวจสอบเอง นอกจากนี้ยังรองรับ **30+ geospatial file formats** (Shapefile, GeoJSON, GML, KML, ฯลฯ) และสามารถประมวลผลโพลิกอนที่มีจุดสูงสุดถึง 10,000 จุดโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ, ให้คุณได้ทั้งความเร็วและความสามารถในการขยาย

## สถานการณ์การใช้งานจริงสำหรับโพลิกอนที่มีรู
1. **Land parcel with an internal lake** – ทะเลสาบภายในแปลงที่ดินถูกจำลองเป็นรูเพื่อไม่ให้นับเป็นส่วนของพื้นที่แปลง  
2. **Building footprints with courtyards** – ลานกลางอาคารถูกตัดออกจากรอยเท้าอาคาร  
3. **Protected zones inside a larger conservation area** – คุณสามารถตัดส่วนที่จำกัดออกได้โดยไม่ต้องสร้างเลเยอร์แยก  

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:
1. Aspose.GIS for .NET Library: คุณสามารถดาวน์โหลดได้จาก **Aspose.GIS for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).  
2. Development Environment: ตรวจสอบว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาพร้อม Visual Studio หรือ IDE .NET อื่นใดที่ติดตั้งแล้ว  

## นำเข้า namespace
Namespace `Aspose.Gis` มีประเภทเรขาคณิตทั้งหมดที่คุณต้องการ รวมถึง `Polygon`, `LinearRing` และเมธอดช่วยเหลือสำหรับการตรวจสอบความถูกต้อง

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

ตอนนี้, เรามาเริ่มสร้างเรขาคณิตโพลิกอนที่มีรูโดยใช้ Aspose.GIS สำหรับ .NET

## ขั้นตอนที่ 1: สร้างอ็อบเจกต์โพลิกอน
`Polygon` คือประเภทเรขาคณิตของ Aspose.GIS ที่แสดงโพลิกอนแบบระนาบพร้อมวงแหวนภายในแบบเลือกได้ เราเริ่มโดยสร้างอ็อบเจกต์ `Polygon` ว่างที่ภายหลังจะเก็บทั้งวงแหวนภายนอกและภายใน

```csharp
Polygon polygon = new Polygon();
```

## ขั้นตอนที่ 2: กำหนดวงแหวนภายนอก
`LinearRing` คือคลาสที่ใช้สำหรับขอบเขตภายนอกและภายใน วงแหวนภายนอกกำหนดขอบเขตภายนอกของโพลิกอน เพิ่มจุดตามลำดับตามเข็มนาฬิกาเพื่อสร้างรูปแบบปิด

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## ขั้นตอนที่ 3: กำหนดวงแหวนภายใน (รู)
`LinearRing` ยังเป็นตัวแทนของวงแหวนภายใน วงแหวนภายในคือ **hole** ที่จะถูกตัดออกจากพื้นที่ของโพลิกอน จุดมักจะถูกเพิ่มในลำดับทวนเข็มนาฬิกา, แต่ Aspose.GIS จัดการการจัดแนวโดยอัตโนมัติ

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## ขั้นตอนที่ 4: กำหนดวงแหวนภายนอกและเพิ่มวงแหวนภายในลงในโพลิกอน
เมธอด `AddInteriorRing` จะผูกหนึ่งหรือหลายวงแหวนภายในเข้ากับ `Polygon` เรียกใช้หลังจากตั้งค่า `ExteriorRing`; คุณสามารถเรียกซ้ำเพื่อเพิ่มหลายรูได้

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## เคล็ดลับและแนวทางปฏิบัติที่ดีที่สุด
- **Orientation matters for readability** – แม้ว่า Aspose.GIS จะปรับการจัดแนวอัตโนมัติ, การเก็บวงแหวนภายนอกตามเข็มนาฬิกาและวงแหวนภายในทวนเข็มนาฬิกาจะทำให้เรขาคณิตตรวจสอบได้ง่ายในโปรแกรม GIS  
- **Close each ring** – ปิดแต่ละวงแหวน – ควรทำซ้ำพิกัดแรกเป็นจุดสุดท้ายเสมอ; นี้รับประกันรูปแบบปิดที่ถูกต้อง  
- **Validate after creation** – ตรวจสอบหลังการสร้าง – คุณสามารถเรียก `polygon.IsValid` เพื่อให้แน่ใจว่าเรขาคณิตสอดคล้องกับมาตรฐาน OGC ก่อนบันทึก  

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| รูไม่แสดงใน GIS viewer | การจัดแนวของวงแหวนภายในกลับด้าน | ตรวจสอบให้แน่ใจว่าจุดถูกเพิ่มในทิศทางตรงกันข้ามกับวงแหวนภายนอก (ทวนเข็มนาฬิกา). |
| ข้อผิดพลาดโพลิกอนไม่ถูกต้อง | วงแหวนไม่ปิด (จุดแรก ≠ จุดสุดท้าย) | ทำซ้ำจุดแรกเป็นจุดสุดท้ายในแต่ละวงแหวน (ตามที่แสดงด้านบน). |
| เรขาคณิตว่างโดยไม่คาดคิด | ลืมกำหนด `ExteriorRing` ก่อนเพิ่มวงแหวนภายใน | ตั้งค่า `polygon.ExteriorRing` ก่อน, จากนั้นเรียก `AddInteriorRing`. |

## คำถามที่พบบ่อย
### 1. Aspose.GIS คืออะไร?
Aspose.GIS เป็นไลบรารี .NET ที่ช่วยให้นักพัฒนาสามารถทำงานกับข้อมูลเชิงพื้นที่, สามารถสร้าง, อ่าน, และจัดการรูปแบบไฟล์เชิงพื้นที่ต่าง ๆ

### 2. ฉันสามารถใช้ Aspose.GIS สำหรับโครงการเชิงพาณิชย์ได้หรือไม่?
ได้, คุณสามารถใช้ Aspose.GIS สำหรับโครงการส่วนบุคคลและเชิงพาณิชย์โดยการซื้อใบอนุญาต เยี่ยมชม **Aspose.GIS purchase page**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)) เพื่อดูรายละเอียดเพิ่มเติม.

### 3. มีการทดลองใช้ฟรีสำหรับ Aspose.GIS หรือไม่?
ได้, คุณสามารถใช้การทดลองฟรีของ Aspose.GIS จาก **Aspose.GIS free trial download page**([https://releases.aspose.com/](https://releases.aspose.com/)).

### 4. ฉันสามารถหาการสนับสนุนสำหรับ Aspose.GIS ได้ที่ไหน?
คุณสามารถหาการสนับสนุนสำหรับ Aspose.GIS ได้ที่ [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### 5. ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS ได้อย่างไร?
คุณสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS ได้จาก **Aspose.GIS temporary license page**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)).

---

**อัปเดตล่าสุด:** 2026-09-05  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [วิธีสร้างเรขาคณิตโพลิกอนด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [เรียนรู้วิธีสร้างเรขาคณิต MultiPolygon ด้วย Aspose.GIS](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [แปลงโพลิกอนเป็นเส้นด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}