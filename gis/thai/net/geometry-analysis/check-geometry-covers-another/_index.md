---
date: 2026-08-03
description: เรียนรู้วิธีสร้าง linestring c# ด้วย Aspose.GIS สำหรับ .NET, เพิ่มจุดลงใน
  linestring, และทำการตรวจสอบจุดบนเส้นโดยใช้วิธี covers.
keywords:
- create linestring c#
- point on line check
- add points to linestring
- use covers method
lastmod: 2026-08-03
linktitle: สร้าง linestring c# – ตรวจสอบว่า geometry ครอบคลุมอีกรูปหนึ่ง
og_description: สร้าง linestring c# และตรวจสอบจุดบนเส้นโดยใช้วิธี Aspose.GIS covers.
  เรียนรู้การตรวจสอบ geometry อย่างแม่นยำสำหรับแอปพลิเคชัน .NET (150‑160 ตัวอักษร)
og_image_alt: Developer guide showing linestring creation and covers check in C# with
  Aspose.GIS
og_title: สร้าง linestring c# – ตรวจสอบว่า geometry ครอบคลุมอีกรูปหนึ่ง (50‑60 ตัวอักษร)
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  headline: Create linestring c# – Check geometry covers another
  type: TechArticle
- description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  name: Create linestring c# – Check geometry covers another
  steps:
  - name: create a linestring object
    text: The `LineString` class represents a sequence of points connected by straight
      line segments in a two‑dimensional plane. Here, we instantiate a new `LineString`
      object, which represents a sequence of connected line segments in a two‑dimensional
      space.
  - name: add points to linestring
    text: '`AddPoint` appends a coordinate pair to the end of the `LineString` collection,
      preserving the order of insertion. We **add points to linestring** using the
      `AddPoint` method. In this example, we add two points: (0, 0) and (1, 1), forming
      a simple diagonal line segment.'
  - name: create a point object
    text: The `Point` class models a single location in a two‑dimensional coordinate
      system. Instantiate a `Point` object representing a single point in a two‑dimensional
      space. Here, we create a point at coordinates (0, 0).
  - name: perform a point on line check – does the line cover the point?
    text: '`Covers` determines whether the first geometry completely contains the
      second geometry, returning true only when every point of the second geometry
      lies inside the first. Use the `Covers` method to check if the line covers the
      point. In this case, it returns `True` because the point (0, 0) lies exac'
  - name: verify the reverse relationship – is the point covered by the line?
    text: '`CoveredBy` is the inverse of `Covers`; it returns true when the invoking
      geometry is entirely inside the target geometry. Similarly, use the `CoveredBy`
      method to check if the point is covered by the line. Since the point (0, 0)
      lies on the line, it also returns `True`.'
  type: HowTo
- questions:
  - answer: Yes, you can use Aspose.GIS for .NET in both commercial and non‑commercial
      projects after obtaining the appropriate license.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, Aspose.GIS for .NET is compatible with both .NET Framework and .NET
      Core environments.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Yes, Aspose.GIS for .NET supports a wide range of GIS formats including
      Shapefile, GeoJSON, KML, and more.
    question: Does Aspose.GIS for .NET support various GIS formats?
  - answer: Aspose.GIS for .NET is a proprietary library developed by Aspose, so external
      contributions are not accepted. However, you can provide feedback and suggestions
      to improve the library.
    question: Can I contribute to the development of Aspose.GIS for .NET?
  - answer: Updates for Aspose.GIS for .NET are released regularly to introduce new
      features, enhancements, and bug fixes. Check the [website](https://releases.aspose.com/gis/net/)
      for the latest releases.
    question: How often are updates released for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create linestring
- Aspose.GIS
- C# geometry analysis
title: สร้าง linestring c# – ตรวจสอบว่า geometry ครอบคลุมอีกรูปหนึ่ง
url: /th/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตรวจสอบว่าเรขาคณิตครอบคลุมอีกอันหนึ่ง

## บทนำ
ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีสร้าง linestring c#** ด้วย Aspose.GIS สำหรับ .NET, เพิ่มจุดลงใน linestring, และทำการตรวจสอบ **จุดบนเส้น** อย่างเชื่อถือได้ด้วยเมธอด `Covers` และ `CoveredBy` ไม่ว่าคุณจะกำลังสร้างเครื่องมือแผนที่, ทำการวิเคราะห์เชิงพื้นที่, หรือเพียงต้องการตรวจสอบความสัมพันธ์เชิงเรขาคณิต การเชี่ยวชาญในขั้นตอนเหล่านี้จะทำให้แอปพลิเคชันของคุณมีความแม่นยำที่ต้องการ

## คำตอบอย่างรวดเร็ว
- **อะไรหมายถึง “create linestring c#”?** หมายถึงการสร้างอ็อบเจกต์เรขาคณิต `LineString` และเติมข้อมูลจุดพิกัดลงไป  
- **เมธอดใดตรวจสอบว่าจุดอยู่บนเส้น?** ใช้เมธอด `Covers` บน `LineString` หรือ `CoveredBy` บน `Point`  
- **ฉันต้องมีใบอนุญาตเพื่อรันตัวอย่างหรือไม่?** ใบอนุญาตชั่วคราวใช้ได้สำหรับการประเมิน; ต้องมีใบอนุญาตเต็มสำหรับการใช้งานจริง  
- **สามารถใช้กับ .NET Core ได้หรือไม่?** ใช่, Aspose.GIS รองรับ .NET Framework และ .NET Core  
- **ฉันสามารถเพิ่มจุดลงใน linestring ได้กี่จุด?** ไม่มีขีดจำกัดที่แน่นอน; คุณสามารถเพิ่มจุดได้ตามต้องการสำหรับการวิเคราะห์เชิงพื้นที่ของคุณ  

## อะไรคือการสร้าง linestring c#?
`LineString` คือรูปทรงเรขาคณิตที่ประกอบด้วยรายการจุดที่เรียงลำดับกันโดยเชื่อมต่อด้วยเส้นตรง ใน C# คุณสร้างโดยการสร้างอ็อบเจกต์ `LineString` จากเนมสเปซ `Aspose.Gis.Geometries` แล้ว **เพิ่มจุดลงใน linestring** ด้วยเมธอด `AddPoint` อ็อบเจกต์นี้เป็นพื้นฐานสำหรับการวิเคราะห์เชิงเส้นใด ๆ เช่น การทำแผนที่เส้นทางหรือการติดตามเครือข่าย

## ทำไมต้องใช้ Aspose.GIS สำหรับการตรวจสอบจุดบนเส้น?
`Covers` เป็นเมธอดเชิงพื้นที่ที่คืนค่า true เมื่อเรขาคณิตแรกครอบคลุมเรขาคณิตที่สองอย่างสมบูรณ์  
Aspose.GIS ให้การทำงานเชิงกำหนดและความแม่นยำสูงของเมธอดเชิงพื้นที่ รองรับรูปแบบ GIS มากกว่า 50 รูปแบบ, สามารถจัดการเครือข่ายเส้นหลายร้อยกิโลเมตรโดยไม่ต้องโหลดข้อมูลทั้งหมดเข้าสู่หน่วยความจำ, และทำงานบน .NET Framework, .NET Core, และ .NET 5/6+ การใช้เมธอด `Covers` ของ Aspose.GIS รับประกันว่าข้อผิดพลาดการปัดเศษของเลขทศนิยมจะถูกคำนึงถึง ทำให้ได้ผลลัพธ์การตรวจสอบจุดบนเส้นที่เชื่อถือได้แม้ในสถานการณ์องค์กรที่ต้องการความแม่นยำสูง

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มใช้ Aspose.GIS สำหรับ .NET โปรดตรวจสอบว่าคุณได้เตรียมสิ่งต่อไปนี้เรียบร้อยแล้ว:

### 1. ติดตั้ง Visual Studio
ตรวจสอบว่าคุณได้ติดตั้ง Visual Studio บนระบบของคุณแล้ว Aspose.GIS สำหรับ .NET ผสานรวมอย่างราบรื่นกับ Visual Studio ทำให้การพัฒนาง่ายและสะดวก

### 2. รับ Aspose.GIS สำหรับ .NET
ดาวน์โหลดไลบรารี Aspose.GIS สำหรับ .NET จาก [website](https://releases.aspose.com/gis/net/) คุณสามารถดาวน์โหลดไลบรารีโดยตรงหรือใช้ผู้จัดการแพ็กเกจเช่น NuGet เพื่อติดตั้งในโปรเจกต์ของคุณ

### 3. ความคุ้นเคยกับ .NET Framework
ความรู้พื้นฐานเกี่ยวกับ .NET Framework และภาษาโปรแกรม C# เป็นสิ่งจำเป็นเพื่อใช้ Aspose.GIS สำหรับ .NET อย่างมีประสิทธิภาพ

### 4. เข้าถึงเอกสารและการสนับสนุน
อ้างอิงที่ [documentation](https://reference.aspose.com/gis/net/) เพื่อดูข้อมูลรายละเอียดเกี่ยวกับ API และฟังก์ชันของ Aspose.GIS หากคุณพบปัญหาหรือมีคำถาม สามารถใช้ [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อขอความช่วยเหลือ

### 5. ตัวเลือก: ใบอนุญาตชั่วคราว
หากคุณกำลังสำรวจ Aspose.GIS สำหรับ .NET คุณสามารถรับใบอนุญาตชั่วคราวจาก [temporary license page](https://purchase.aspose.com/temporary-license/) เพื่อประเมินคุณสมบัติต่าง ๆ ของไลบรารี

## นำเข้าเนมสเปซ
ก่อนใช้ Aspose.GIS สำหรับ .NET ในโปรเจกต์ของคุณ คุณต้องนำเข้าเนมสเปซที่จำเป็น:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

ตอนนี้เราจะอธิบายตัวอย่างที่ให้มาเป็นหลายขั้นตอนเพื่อทำความเข้าใจวิธี **ตรวจสอบว่าเรขาคณิตหนึ่งครอบคลุมอีกอันหนึ่ง** ด้วย Aspose.GIS สำหรับ .NET

## วิธีสร้าง linestring c# – คู่มือขั้นตอน
โหลดโปรเจกต์ของคุณ, นำเข้าเนมสเปซที่ต้องการ, แล้วทำตามห้าขั้นตอนสั้น ๆ ด้านล่าง ในไม่กี่บรรทัดของโค้ดคุณจะได้อ็อบเจกต์ `LineString`, อ็อบเจกต์ `Point`, และการตรวจสอบแบบบูลีนสองค่าเพื่อบอกว่าเส้นครอบคลุมจุดหรือไม่และจุดถูกเส้นครอบคลุมหรือไม่

### ขั้นตอนที่ 1: สร้างอ็อบเจกต์ linestring
คลาส `LineString` แสดงถึงลำดับของจุดที่เชื่อมต่อด้วยเส้นตรงในระนาบสองมิติ  
```csharp
var line = new LineString();
```
ที่นี่เราสร้างอ็อบเจกต์ `LineString` ใหม่ ซึ่งเป็นลำดับของเส้นเชื่อมต่อในพื้นที่สองมิติ

### ขั้นตอนที่ 2: เพิ่มจุดลงใน linestring
`AddPoint` เพิ่มคู่พิกัดไปยังท้ายคอลเลกชัน `LineString` โดยคงลำดับการแทรกไว้  
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
เร **เพิ่มจุดลงใน linestring** ด้วยเมธอด `AddPoint` ในตัวอย่างนี้เราเพิ่มสองจุด: (0, 0) และ (1, 1) สร้างเส้นทแยงมุมง่าย ๆ

### ขั้นตอนที่ 3: สร้างอ็อบเจกต์ point
คลาส `Point` แสดงตำแหน่งเดียวในระบบพิกัดสองมิติ  
```csharp
var point = new Point(0, 0);
```
สร้างอ็อบเจกต์ `Point` ที่แทนตำแหน่งเดียวในพื้นที่สองมิติ ที่นี่เราสร้างจุดที่พิกัด (0, 0)

### ขั้นตอนที่ 4: ทำการตรวจสอบจุดบนเส้น – เส้นครอบคลุมจุดหรือไม่?
`Covers` กำหนดว่าเรขาคณิตแรกครอบคลุมเรขาคณิตที่สองอย่างสมบูรณ์ คืนค่า true เฉพาะเมื่อทุกจุดของเรขาคณิตที่สองอยู่ภายในเรขาคณิตแรก  
```csharp
Console.WriteLine(line.Covers(point));    // True
```
ใช้เมธอด `Covers` เพื่อตรวจสอบว่าเส้นครอบคลุมจุดหรือไม่ ในกรณีนี้มันคืนค่า `True` เนื่องจากจุด (0, 0) อยู่บนเส้นอย่างแม่นยำ

### ขั้นตอนที่ 5: ตรวจสอบความสัมพันธ์ย้อนกลับ – จุดถูกเส้นครอบคลุมหรือไม่?
`CoveredBy` เป็นการกลับด้านของ `Covers`; คืนค่า true เมื่อเรขาคณิตที่เรียกใช้อยู่ภายในเรขาคณิตเป้าหมายทั้งหมด  
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
เช่นเดียวกัน ใช้เมธอด `CoveredBy` เพื่อตรวจสอบว่าจุดถูกเส้นครอบคลุมหรือไม่ เนื่องจากจุด (0, 0) อยู่บนเส้น มันก็คืนค่า `True` ด้วยเช่นกัน

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| `line.Covers(point)` คืนค่า `False` แม้ว่าจุดดูเหมือนอยู่บนเส้น | พิกัดของจุดไม่ตรงกันอย่างสมบูรณ์เนื่องจากความแม่นยำของเลขทศนิยม | ใช้ `Math.Round` กับพิกัดหรือใช้การตรวจสอบด้วยความคลาดเคลื่อนโดย `line.Distance(point) < epsilon` |
| ขาด `using Aspose.Gis.Geometries;` | ไม่ได้นำเข้าเนมสเปซ ทำให้เกิดข้อผิดพลาดในการคอมไพล์ | ตรวจสอบให้มีคำสั่ง import อยู่ (ดูส่วน **นำเข้าเนมสเปซ**) |
| ข้อยกเว้นใบอนุญาตขณะรันไทม์ | ไม่มีใบอนุญาตที่ถูกต้องโหลดสำหรับการใช้งานจริง | โหลดใบอนุญาตชั่วคราวหรือเต็มโดยใช้ `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## คำถามที่พบบ่อย

**Q: สามารถใช้ Aspose.GIS สำหรับ .NET ในโครงการเชิงพาณิชย์ของฉันได้หรือไม่?**  
A: ใช่, คุณสามารถใช้ Aspose.GIS สำหรับ .NET ทั้งในโครงการเชิงพาณิชย์และไม่เชิงพาณิชย์หลังจากได้ใบอนุญาตที่เหมาะสม

**Q: Aspose.GIS สำหรับ .NET รองรับ .NET Core หรือไม่?**  
A: ใช่, Aspose.GIS สำหรับ .NET รองรับทั้งสภาพแวดล้อม .NET Framework และ .NET Core

**Q: Aspose.GIS สำหรับ .NET รองรับรูปแบบ GIS ต่าง ๆ หรือไม่?**  
A: ใช่, Aspose.GIS สำหรับ .NET รองรับรูปแบบ GIS หลากหลายรวมถึง Shapefile, GeoJSON, KML และอื่น ๆ

**Q: ฉันสามารถมีส่วนร่วมในการพัฒนา Aspose.GIS สำหรับ .NET ได้หรือไม่?**  
A: Aspose.GIS สำหรับ .NET เป็นไลบรารีเชิงพาณิชย์ที่พัฒนาโดย Aspose จึงไม่รับการมีส่วนร่วมจากภายนอก อย่างไรก็ตามคุณสามารถให้ข้อเสนอแนะและแนวคิดเพื่อปรับปรุงไลบรารีได้

**Q: การอัปเดตของ Aspose.GIS สำหรับ .NET มีความถี่แค่ไหน?**  
A: การอัปเดตของ Aspose.GIS สำหรับ .NET มีการปล่อยอย่างสม่ำเสมอเพื่อแนะนำฟีเจอร์ใหม่, การปรับปรุง, และการแก้ไขบั๊ก ตรวจสอบที่ [website](https://releases.aspose.com/gis/net/) สำหรับรุ่นล่าสุด

## สรุป
โดยทำตามขั้นตอนข้างต้น คุณจะรู้วิธี **สร้าง linestring c#**, **เพิ่มจุดลงใน linestring**, และทำการตรวจสอบ **จุดบนเส้น** อย่างเชื่อถือได้ด้วยเมธอด `Covers` และ `CoveredBy` ความสามารถนี้ช่วยเพิ่มฟีเจอร์การวิเคราะห์เชิงพื้นที่ของซอฟต์แวร์ของคุณและเปิดประตูสู่การดำเนินการ GIS ขั้นสูงเช่นการตรวจสอบเส้นทาง, การตรวจสอบโทโพโลยีเครือข่าย, และการค้นหาใกล้เคียง

---

**อัปเดตล่าสุด:** 2026-08-03  
**ทดสอบด้วย:** Aspose.GIS for .NET (latest release)  
**ผู้เขียน:** Aspose

{{< blocks/products/products-backtop-button >}}

## บทเรียนที่เกี่ยวข้อง

- [เรียนรู้วิธีสร้างเรขาคณิต LineString ด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [วิธีเพิ่ม Point ลงใน LineString และแปลงเรขาคณิตเป็นรูปแบบที่แก้ไขได้ด้วย Aspose.GIS](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [point inside polygon c# – ตรวจสอบว่า Geometry มีอีกอันหนึ่ง](/gis/net/geometry-analysis/check-geometry-contains-another/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}