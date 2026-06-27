---
date: 2026-06-05
description: เรียนรู้วิธีทำการวิเคราะห์การทับซ้อนเชิงพื้นที่, ค้นหาโพลิกอนที่ตัดกันและตรวจจับโพลิกอนที่ทับซ้อนด้วย
  Aspose.GIS for .NET. คู่มือขั้นตอนต่อขั้นตอนสำหรับนักพัฒนา.
keywords:
- spatial overlap analysis
- find intersecting polygons
- detect overlapping polygons
- how to check overlap
- real-time overlap detection
linktitle: ตรวจสอบการทับซ้อนของรูปทรงเรขาคณิต
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to perform spatial overlap analysis, find intersecting polygons
    and detect overlapping polygons with Aspose.GIS for .NET. Step‑by‑step guide for
    developers.
  headline: How to Perform Spatial Overlap Analysis of Geometries with Aspose.GIS
    for .NET
  type: TechArticle
- questions:
  - answer: '`Geometry.Overlaps(otherGeometry)`'
    question: What is the primary method?
  - answer: A free trial works for development; a license is required for production.
    question: Do I need a license for testing?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Which .NET versions are supported?
  - answer: Roughly 5‑10 minutes for a basic overlap check.
    question: How long does the implementation take?
  - answer: Yes—Aspose.GIS integrates smoothly with most .NET GIS stacks.
    question: Can I use this with other GIS libraries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: วิธีการทำการวิเคราะห์การทับซ้อนเชิงพื้นที่ของรูปทรงเรขาคณิตด้วย Aspose.GIS
  for .NET
url: /th/net/geometry-analysis/check-geometries-overlap/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การวิเคราะห์การทับซ้อนเชิงพื้นที่ของรูปทรงเรขาคณิตด้วย Aspose.GIS

## บทนำ

หากคุณต้องการ **ตรวจสอบการทับซ้อน** ระหว่างสองฟีเจอร์เชิงพื้นที่ Aspose.GIS สำหรับ .NET จะมอบ API ที่สะอาด ปลอดภัยต่อประเภทข้อมูล ซึ่งทำงานหนักให้คุณ การทำ **การวิเคราะห์การทับซ้อนเชิงพื้นที่** เป็นความต้องการที่พบบ่อยเมื่อสร้างเครื่องมือกำหนดเส้นทาง, ตัวตรวจสอบการใช้ที่ดิน, หรือยูทิลิตี้ GIS ใด ๆ ที่ต้องเข้าใจว่ารูปทรงเรขาคณิตทำงานร่วมกันอย่างไร ในบทเรียนนี้เราจะเดินผ่านข้อกำหนดเบื้องต้น, การอธิบายโค้ด, และเคล็ดลับเชิงปฏิบัติ เพื่อให้คุณสามารถตรวจจับพอลิกอนและรูปทรงเรขาคณิตอื่น ๆ ที่ทับซ้อนกันในโครงการของคุณได้อย่างมั่นใจ

## คำตอบสั้น
- **วิธีหลักคืออะไร?** `Geometry.Overlaps(otherGeometry)`  
- **ต้องใช้ไลเซนส์สำหรับการทดสอบหรือไม่?** ทดลองใช้ฟรีทำงานได้สำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์สำหรับการผลิต  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+  
- **ใช้เวลานานเท่าไหร่ในการทำงาน?** ประมาณ 5‑10 นาทีสำหรับการตรวจสอบการทับซ้อนพื้นฐาน  
- **สามารถใช้ร่วมกับไลบรารี GIS อื่นได้หรือไม่?** ใช่—Aspose.GIS ผสานรวมได้อย่างราบรื่นกับสแตก GIS ของ .NET ส่วนใหญ่

## การวิเคราะห์การทับซ้อนเชิงพื้นที่คืออะไร?
พรีดิเชต `Overlaps` ปฏิบัติตามคำนิยามของ OGC (Open Geospatial Consortium) และคืนค่า **true** เฉพาะเมื่อสองรูปทรงเรขาคณิตมีจุดภายในร่วมกันโดยไม่มีรูปทรงใดรูปทรงหนึ่งครอบคลุมอีกรูปทรงหนึ่งทั้งหมด กล่าวคือ รูปร่างตัดกัน *ภายใน* แต่ไม่ได้ล้อมรอบกันอย่างเต็มที่

## ทำไมต้องเลือก Aspose.GIS สำหรับการตรวจจับการทับซ้อน?
Aspose.GIS รองรับ **รูปทรงเรขาคณิตกว่า 30 ประเภท** และสามารถประมวลผล **ไฟล์หลายกิกะไบต์** โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ ให้การตอบสนองระดับมิลลิวินาทีสำหรับคู่พอลิกอนทั่วไป การออกแบบที่ไม่มีการพึ่งพาอื่นใด, การสนับสนุนข้ามแพลตฟอร์ม .NET Core, และพรีดิเชตที่สอดคล้องกับ OGC ทำให้เป็นตัวเลือกที่เชื่อถือได้สำหรับการตรวจจับการทับซ้อนแบบเรียลไทม์ในระบบผลิต

## ข้อกำหนดเบื้องต้น
- **พื้นฐาน C#** – ความคุ้นเคยกับคลาส, เมธอด, และการแสดงผลบนคอนโซล  
- **Aspose.GIS สำหรับ .NET** – ดาวน์โหลดและติดตั้งจากเว็บไซต์ทางการ [ที่นี่](https://releases.aspose.com/gis/net/) หรือจากหน้ารีลีสทั่วไป [ที่นี่](https://releases.aspose.com/)  
- **IDE** – Visual Studio, Rider, หรือ VS Code พร้อมส่วนขยาย C#

## นำเข้า Namespaces
เพิ่มคำสั่ง `using` ที่จำเป็นเพื่อให้โค้ดของคุณเข้าถึงประเภทเรขาคณิตของ Aspose.GIS

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: กำหนดรูปทรงเรขาคณิตที่ต้องการเปรียบเทียบ
`LineString` เป็นประเภทเรขาคณิตที่แทนชุดจุดเชื่อมต่อกันเป็นเส้นตรง เราจะเริ่มด้วยสองอ็อบเจกต์ `LineString` ที่มีจุดปลายร่วมกันแต่ **ไม่** ทับซ้อนกัน

```csharp
var geometry1 = new LineString();
geometry1.AddPoint(0, 0);
geometry1.AddPoint(0, 2);

var geometry2 = new LineString();
geometry2.AddPoint(0, 2);
geometry2.AddPoint(0, 3);
```

## ขั้นตอนที่ 2: ใช้เมธอด `Overlaps` – การตรวจสอบครั้งแรก
`Geometry.Overlaps` เป็นพรีดิเชตที่สอดคล้องกับ OGC ซึ่งคืนค่า true เมื่อสองรูปทรงเรขาคณิตมีจุดภายในร่วมกันโดยไม่มีรูปทรงใดรูปทรงหนึ่งครอบคลุมอีกรูปทรงหนึ่ง เมธอดนี้คืนค่า `false` เนื่องจากเส้นเพียงแตะกันที่จุดเดียว

```csharp
Console.WriteLine(geometry1.Overlaps(geometry2)); // Output: False
```

## ขั้นตอนที่ 3: สร้างรูปทรงเรขาคณิตอื่นที่ทับซ้อนจริง ๆ
ต่อไปเราจะสร้างเส้นที่สามที่วิ่งผ่านภายในของ `geometry1` ทำให้เกิดการตัดกันภายในอย่างแน่นอน

```csharp
var geometry3 = new LineString();
geometry3.AddPoint(0, 1);
geometry3.AddPoint(0, 3);
```

## ขั้นตอนที่ 4: ตรวจสอบการทับซ้อนอีกครั้ง – ครั้งนี้ควรเป็น true
การเรียก `Overlaps` เดียวกันบนคู่ใหม่จะคืนค่า `true` ยืนยันว่ารูปทรงเรขาคณิตทับซ้อนกันจริง

```csharp
Console.WriteLine(geometry1.Overlaps(geometry3)); // Output: True
```

## วิธีตรวจจับการทับซ้อนในกรณีที่ซับซ้อนกว่า?
โหลดพอลิกอนหรืออ็อบเจกต์หลายรูปทรงของคุณและเรียกพรีดิเชต `Overlaps` เดียวกัน; API จะเลือกอัลกอริทึมที่เหมาะสมโดยอัตโนมัติสำหรับแต่ละประเภทรูปทรง `SpatialReference` เป็นโครงสร้างที่ให้คุณกำหนดค่าความทนทานแบบกำหนดเองสำหรับการดำเนินการเรขาคณิต วิธีนี้ทำงานได้กับชุดข้อมูลขนาดใหญ่, ทำให้สามารถตรวจจับการทับซ้อนแบบเรียลไทม์ได้ทั่วพันธุ์ฟีเจอร์

## ปัญหาที่พบบ่อยและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|---------|
| **คืนค่า `false` เสมอ** | รูปทรงเรขาคณิตเพียงแตะกัน (แชร์ขอบ) ไม่ได้ทับซ้อน | ใช้ `Intersects` สำหรับจุดที่แชร์, หรือปรับพิกัดให้ภายในตัดกัน |
| **เกิดข้อยกเว้นเมื่อทำงานกับชุดข้อมูลขนาดใหญ่** | ความกดดันหน่วยความจำเมื่อโหลดรูปทรงหลายรูปพร้อมกัน | ประมวลผลรูปทรงเป็นชุดหรือใช้ `GeometryCollection` พร้อมสตรีมมิ่ง |
| **คืนค่า `true` ที่ไม่คาดคิดสำหรับพอลิกอน** | พื้นในของพอลิกอนตัดกันแต่แชร์ขอบ | ตรวจสอบว่าคุณต้องการคำนิยาม *overlaps* ของ OGC จริงหรือไม่; หากไม่, ใช้ `Crosses` หรือ `Touches` |

## คำถามที่พบบ่อย

**Q1: สามารถใช้ Aspose.GIS สำหรับ .NET ร่วมกับไลบรารี .NET อื่นได้หรือไม่?**  
A1: ใช่, Aspose.GIS สำหรับ .NET ผสานรวมอย่างราบรื่นกับไลบรารี .NET อื่น ๆ, เพิ่มความสามารถโดยไม่มีอุปสรรค

**Q2: มีการทดลองใช้ฟรีสำหรับ Aspose.GIS สำหรับ .NET หรือไม่?**  
A2: มี, คุณสามารถเข้าถึงการทดลองใช้ฟรีของ Aspose.GIS สำหรับ .NET จาก [ที่นี่](https://releases.aspose.com/)

**Q3: จะหาเอกสารสำหรับ Aspose.GIS สำหรับ .NET ได้จากที่ไหน?**  
A3: เอกสารครบถ้วนสำหรับ Aspose.GIS สำหรับ .NET มีให้ที่ [ที่นี่](https://reference.aspose.com/gis/net/)

**Q4: จะขอไลเซนส์ชั่วคราวสำหรับ Aspose.GIS สำหรับ .NET ได้อย่างไร?**  
A4: คุณสามารถรับไลเซนส์ชั่วคราวสำหรับ Aspose.GIS สำหรับ .NET จาก [ที่นี่](https://purchase.aspose.com/temporary-license/)

**Q5: จะขอรับการสนับสนุนสำหรับ Aspose.GIS สำหรับ .NET ได้จากที่ไหน?**  
A5: สำหรับความช่วยเหลือหรือคำถามใด ๆ, เยี่ยมชมฟอรั่ม Aspose.GIS ที่ [ที่นี่](https://forum.aspose.com/c/gis/33)

{{< blocks/products/products-backtop-button >}}

## บทเรียนที่เกี่ยวข้อง

- [GIS Overlay Analysis - How to Perform Overlay Operations with Aspose.GIS for .NET](/gis/net/geometry-analysis/find-geometry-overlays/)
- [Create Polygon Geometry C# and Check Intersection with Aspose.GIS for .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Network Routing Check: Touching Geometries with Aspose.GIS](/gis/net/geometry-analysis/check-geometries-touching/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

--- 

**อัปเดตล่าสุด:** 2026-06-05  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose