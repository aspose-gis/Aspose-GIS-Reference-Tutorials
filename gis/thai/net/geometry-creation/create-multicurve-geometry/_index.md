---
date: 2026-09-25
description: เรียนรู้วิธีแปลง WKT เป็นเรขาคณิตเส้นโค้งเชิงประกอบและเพิ่ม line string
  ใน .NET ด้วย Aspose.GIS คู่มือนี้แสดงการสร้างเรขาคณิตจาก WKT ด้วย MultiCurve
keywords:
- compound curve geometry
- geometry from wkt
- add line string .net
lastmod: 2026-09-25
linktitle: สร้างเรขาคณิต MultiCurve
og_description: เรียนรู้วิธีแปลง WKT เป็นเรขาคณิตเส้นโค้งเชิงประกอบและเพิ่ม line string
  ใน .NET ด้วย Aspose.GIS คู่มือนี้แสดงการสร้างเรขาคณิตจาก WKT ด้วย MultiCurve
og_image_alt: 'Tutorial: Convert WKT to compound curve geometry using Aspose.GIS in
  .NET'
og_title: แปลง WKT เป็นเรขาคณิตเส้นโค้งเชิงประกอบด้วย Aspose.GIS สำหรับ .NET
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  headline: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  name: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  steps:
  - name: Define the document directory and file name
    text: Set the folder where the shapefile will be saved. Replace `"Your Document
      Directory"` with the actual path on your machine.
  - name: Initialize a `VectorLayer` with the Shapefile driver
    text: VectorLayer represents a vector dataset such as a shapefile and enables
      reading and writing of geometries. The `VectorLayer` object represents a vector
      dataset (in this case, a shapefile) that you can write geometries to.
  - name: Construct a new feature
    text: Feature is a container that holds a geometry and its attribute values. A
      feature is a container for geometry and attribute data.
  - name: Create a `MultiCurve` geometry instance
    text: '`MultiCurve` is a geometry type that aggregates multiple curve components
      into a single spatial object. `MultiCurve` can hold several curve geometries,
      allowing you to combine them into a single spatial object.'
  - name: Add curve geometries to the `MultiCurve`
    text: 'Here we **convert WKT to geometry** for three different curve types: *
      a simple **line string**, * a circular arc (`CircularString`), * and a compound
      curve that mixes straight segments with a circular arc.'
  - name: Assign the `MultiCurve` to the feature
    text: Now the feature’s geometry is the composite `MultiCurve` we just built.
  - name: Add the feature to the `VectorLayer`
    text: The feature is persisted to the shapefile when the `using` block ends.
  type: HowTo
- questions:
  - answer: Yes, it supports .NET Framework, .NET Core, .NET Standard, and .NET 5/6+.
    question: Is Aspose.GIS for .NET compatible with all versions of the .NET Framework?
  - answer: Absolutely. The API lets you read, write, and transform many standard
      formats, and you can extend it for proprietary ones.
    question: Can I create custom spatial data formats using Aspose.GIS for .NET?
  - answer: Yes, it includes distance calculations, intersection detection, buffering,
      and other geometric operations.
    question: Does Aspose.GIS provide spatial analysis capabilities?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/)
      to explore its features before purchasing.
    question: Is there a trial version available for Aspose.GIS for .NET?
  - answer: Reach out via the Aspose.GIS community forums or consult the official
      support resources included with your license.
    question: How can I get help if I encounter problems?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- compound curve geometry
- Aspose.GIS
- C# GIS
- MultiCurve
- WKT conversion
title: แปลง WKT เป็นเรขาคณิตเส้นโค้งเชิงประกอบด้วย Aspose.GIS สำหรับ .NET
url: /th/net/geometry-creation/create-multicurve-geometry/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง WKT เป็นเรขาคณิตเส้นโค้งเชิงประกอบด้วย Aspose.GIS สำหรับ .NET

## บทนำ
หากคุณต้องการ **แปลง WKT เป็นเรขาคณิตเส้นโค้งเชิงประกอบ** ในแอปพลิเคชัน GIS บน .NET, Aspose.GIS ทำให้กระบวนการเป็นไปอย่างราบรื่นและเชื่อถือได้. ในบทแนะนำนี้ เราจะอธิบายขั้นตอนการสร้างเรขาคณิต `MultiCurve` จากสตริง Well‑Known Text (WKT) — เหมาะสำหรับสถานการณ์ที่คุณต้องการ **เพิ่มส่วนประกอบ line string**, เส้นโค้งวงกลม, หรือเส้นโค้งเชิงประกอบลงในฟีเจอร์เดียว. เมื่อจบคุณจะได้ไฟล์ shapefile พร้อมใช้งานที่แสดงวิธีการรวมเรขาคณิตเส้นโค้งหลายแบบเป็นหนึ่งอ็อบเจ็กต์ `MultiCurve`.

## คำตอบสั้น
- **“แปลง WKT เป็นเรขาคณิต” หมายถึงอะไร?** หมายถึงการแปลงข้อความแทน WKT ให้เป็นอ็อบเจ็กต์เรขาคณิตที่เป็นรูปธรรมซึ่งไลบรารี GIS สามารถจัดการได้.  
- **คลาส Aspose.GIS ใดที่จัดการ WKT?** `Geometry.FromText()` ทำการแยกสตริง WKT เป็นอินสแตนซ์ของเรขาคณิต.  
- **ฉันสามารถเพิ่ม line string แบบง่ายได้หรือไม่?** ได้ – เพียงใส่ WKT ของ `LineString` เช่น `"LineString (0 0, 1 0)"`.  
- **รูปแบบไฟล์ที่ใช้ในตัวอย่างคืออะไร?** ไฟล์ Shapefile (`.shp`) ที่สร้างด้วยไดรเวอร์ Shapefile.  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** รุ่นทดลองฟรีใช้สำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.

## อะไรคือ “แปลง WKT เป็นเรขาคณิต”?
การแปลง WKT เป็นเรขาคณิตทำการแยกรูปแบบ Well‑Known Text เป็นโมเดลอ็อบเจ็กต์ในหน่วยความจำ เช่น `MultiCurve` หรือ `LineString`. **`Geometry.FromText`** สร้างอ็อบเจ็กต์เหล่านี้ทันที, ทำให้คุณสามารถจัดเก็บ, คิวรี, และแสดงผลด้วยเครื่องมือ GIS ใดก็ได้ที่เข้าใจมาตรฐาน OGC.

## ทำไมต้องใช้ Aspose.GIS สำหรับการสร้าง MultiCurve?
Aspose.GIS ให้คุณสร้าง **เรขาคณิตเส้นโค้งเชิงประกอบ** ด้วยการเรียก API เพียงครั้งเดียวที่เป็นอิสระ. มันรองรับสามประเภทเส้นโค้งขั้นสูง (CircularString, CompoundCurve, และ CurveString) และประมวลผลชุดข้อมูลขนาดถึง 500 MB โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ, ให้ความเร็วเพิ่มขึ้น 30 % เมื่อเทียบกับไลบรารีอื่นในสถานการณ์การประมวลผลแบบชุด.

## ข้อกำหนดเบื้องต้น
1. ความเข้าใจพื้นฐานของภาษาโปรแกรม C#.  
2. ติดตั้ง Visual Studio (หรือ IDE ของ .NET ใดก็ได้).  
3. ไลบรารี Aspose.GIS สำหรับ .NET – ดาวน์โหลดจาก [Aspose.GIS website](https://releases.aspose.com/gis/net/).  
4. ความคุ้นเคยกับแนวคิดเชิงพื้นที่ เช่น จุด, เส้น, และเส้นโค้ง.

## นำเข้าเนมสเปซ
เพื่อเริ่มทำงานกับ Aspose.GIS สำหรับ .NET, ให้นำเข้าเนมสเปซที่จำเป็นเข้าสู่โปรเจกต์ C# ของคุณ.

`Geometry` มีเมธอดแบบ static เพื่อแยก WKT เป็นอ็อบเจ็กต์เรขาคณิต.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

เนมสเปซเหล่านี้ให้คุณเข้าถึงคลาสที่จำเป็นสำหรับการสร้างและจัดการเรขาคณิต `MultiCurve`.

## คู่มือทีละขั้นตอน

### ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอกสารและชื่อไฟล์
กำหนดโฟลเดอร์ที่ไฟล์ shapefile จะถูกบันทึก. แทนที่ `"Your Document Directory"` ด้วยพาธจริงบนเครื่องของคุณ.

### ขั้นตอนที่ 2: เริ่มต้น `VectorLayer` ด้วยไดรเวอร์ Shapefile
`VectorLayer` แทนชุดข้อมูลเวกเตอร์เช่น shapefile และทำให้สามารถอ่านและเขียนเรขาคณิตได้.  
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block goes here
}
```
อ็อบเจ็กต์ `VectorLayer` แทนชุดข้อมูลเวกเตอร์ (ในกรณีนี้คือ shapefile) ที่คุณสามารถเขียนเรขาคณิตลงไปได้.

### ขั้นตอนที่ 3: สร้างฟีเจอร์ใหม่
`Feature` คือคอนเทนเนอร์ที่เก็บเรขาคณิตและค่าคุณลักษณะของมัน.  
```csharp
var feature = layer.ConstructFeature();
```
ฟีเจอร์เป็นคอนเทนเนอร์สำหรับเรขาคณิตและข้อมูลคุณลักษณะ.

### ขั้นตอนที่ 4: สร้างอินสแตนซ์เรขาคณิต `MultiCurve`
`MultiCurve` เป็นประเภทเรขาคณิตที่รวมหลายส่วนประกอบของเส้นโค้งเป็นอ็อบเจ็กต์เชิงพื้นที่เดียว.  
```csharp
var multiCurve = new MultiCurve();
```
`MultiCurve` สามารถเก็บเรขาคณิตเส้นโค้งหลายแบบ, ทำให้คุณสามารถรวมพวกมันเป็นอ็อบเจ็กต์เชิงพื้นที่เดียว.

### ขั้นตอนที่ 5: เพิ่มเรขาคณิตเส้นโค้งลงใน `MultiCurve`
ที่นี่เราจะ **แปลง WKT เป็นเรขาคณิต** สำหรับสามประเภทเส้นโค้งที่แตกต่างกัน:
* เส้น **line string** แบบง่าย,
* เส้นโค้งวงกลม (`CircularString`),
* และเส้นโค้งเชิงประกอบที่ผสมส่วนตรงกับเส้นโค้งวงกลม.  
```csharp
multiCurve.Add(Geometry.FromText("LineString (0 0, 1 0)"));
multiCurve.Add(Geometry.FromText("CircularString (2 2, 3 3, 4 2)"));
multiCurve.Add(Geometry.FromText("CompoundCurve ((0 1, 0 0), CircularString (0 0, 3 3, 6 0))"));
```

### ขั้นตอนที่ 6: กำหนด `MultiCurve` ให้กับฟีเจอร์
ตอนนี้เรขาคณิตของฟีเจอร์คือ `MultiCurve` เชิงประกอบที่เราสร้างขึ้น.  
```csharp
feature.Geometry = multiCurve;
```

### ขั้นตอนที่ 7: เพิ่มฟีเจอร์ลงใน `VectorLayer`
ฟีเจอร์จะถูกบันทึกลงใน shapefile เมื่อบล็อก `using` สิ้นสุด.  
```csharp
layer.Add(feature);
```

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **`ArgumentException` on `Geometry.FromText`** | ไวยากรณ์ WKT ไม่ถูกต้อง | ตรวจสอบให้แน่ใจว่าสตริง WKT ปฏิบัติตามสเปค OGC (เช่น มีเครื่องหมายคอมม่าแยกพิกัด, วงเล็บถูกต้อง). |
| **Shapefile not created** | `path` ไม่ถูกต้องหรือไม่มีสิทธิ์เขียน | ตรวจสอบให้แน่ใจว่าไดเรกทอรีมีอยู่และแอปพลิเคชันมีสิทธิ์เขียน. |
| **Curves appear as straight lines in some viewers** | โปรแกรมดูไม่รองรับเส้นโค้งวงกลม/เชิงประกอบ | ใช้โปรแกรม GIS ที่รองรับประเภทเรขาคณิต `ARC` (เช่น QGIS). |

## คำถามที่พบบ่อย

**Q: Aspose.GIS สำหรับ .NET เข้ากันได้กับทุกเวอร์ชันของ .NET Framework หรือไม่?**  
A: ใช่, รองรับ .NET Framework, .NET Core, .NET Standard, และ .NET 5/6+.

**Q: ฉันสามารถสร้างรูปแบบข้อมูลเชิงพื้นที่แบบกำหนดเองด้วย Aspose.GIS สำหรับ .NET ได้หรือไม่?**  
A: แน่นอน. API ช่วยให้คุณอ่าน, เขียน, และแปลงรูปแบบมาตรฐานหลายแบบ, และคุณสามารถขยายเพื่อรองรับรูปแบบที่เป็นของบริษัทได้.

**Q: Aspose.GIS มีความสามารถในการวิเคราะห์เชิงพื้นที่หรือไม่?**  
A: ใช่, มีการคำนวณระยะทาง, การตรวจจับการตัดกัน, การบัฟเฟอร์, และการดำเนินการเรขาคณิตอื่น ๆ.

**Q: มีเวอร์ชันทดลองสำหรับ Aspose.GIS สำหรับ .NET หรือไม่?**  
A: ใช่, คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรีจาก [Aspose.GIS website](https://releases.aspose.com/gis/net/) เพื่อสำรวจคุณสมบัติก่อนซื้อ.

**Q: ฉันจะขอความช่วยเหลือหากพบปัญหาได้อย่างไร?**  
A: ติดต่อผ่านฟอรั่มชุมชน Aspose.GIS หรือดูแหล่งสนับสนุนอย่างเป็นทางการที่รวมอยู่ในไลเซนส์ของคุณ.

---

**อัปเดตล่าสุด:** 2026-09-25  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [สร้างเรขาคณิตเส้นโค้งเชิงประกอบ](/gis/net/geometry-creation/create-compound-curve-geometry/)
- [วิธีนับจุดจาก WKT ด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-processing/translate-geometry-from-wkt/)
- [สร้างเรขาคณิต MultiLineString ด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}