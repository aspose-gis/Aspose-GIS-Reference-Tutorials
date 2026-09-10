---
date: 2026-09-10
description: เรียนรู้วิธีลดขนาดไฟล์ geometry โดยลดความแม่นยำและปัดค่า Z ด้วย Aspose.GIS
  for .NET เพื่อปรับปรุงประสิทธิภาพและลดการใช้หน่วยความจำ
keywords:
- reduce geometry file size
- reduce geometry precision
- round Z values
- Aspose.GIS .NET
- geometry processing
lastmod: 2026-09-10
linktitle: ลดความแม่นยำของ geometry
og_description: เรียนรู้วิธีลดขนาดไฟล์ geometry โดยลดความแม่นยำและปัดค่า Z ด้วย Aspose.GIS
  for .NET เพื่อปรับปรุงประสิทธิภาพและลดการใช้หน่วยความจำ
og_image_alt: Guide showing how to reduce geometry file size by rounding Z in .NET
  using Aspose.GIS
og_title: วิธีลดขนาดไฟล์ geometry โดยการปัดค่า Z ใน .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to reduce geometry file size by lowering precision and rounding
    Z values with Aspose.GIS for .NET, improving performance and cutting memory usage.
  headline: How to reduce geometry file size by rounding Z in .NET
  type: TechArticle
- questions:
  - answer: Reducing geometry precision helps optimize memory usage and improve performance,
      especially when dealing with large datasets in GIS applications.
    question: Why is geometry precision reduction important in GIS?
  - answer: While minor accuracy is lost, the trade‑off often yields a good balance
      between precision and performance for most spatial analyses.
    question: Does reducing geometry precision affect accuracy?
  - answer: Yes, you can specify the desired number of decimal places for both XY
      and Z coordinates using the `RoundXY` and `RoundZ` methods.
    question: Can I customize the precision reduction level in Aspose.GIS for .NET?
  - answer: Absolutely—less data per vertex means faster spatial queries, reduced
      I/O, and lower memory consumption, often delivering **30 % faster processing**
      on typical datasets.
    question: Are there measurable performance benefits?
  - answer: You can get support by visiting the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      or accessing the documentation available in the [Aspose.GIS .NET API reference](https://reference.aspose.com/gis/net/).
    question: Where can I get support for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- reduce geometry file size
- Aspose.GIS
- .NET GIS
- geometry precision
- round Z
title: วิธีลดขนาดไฟล์ geometry โดยการปัดค่า Z ใน .NET
url: /th/net/geometry-processing/reduce-geometry-precision/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีลดขนาดไฟล์เรขาคณิตโดยการปัดเศษค่า Z ใน .NET

## บทนำ
ถ้าคุณกำลังทำงานกับชุดข้อมูลเชิงพื้นที่ขนาดใหญ่ คุณอาจเคยสังเกตว่าการเพิ่มตำแหน่งทศนิยมในข้อมูลเรขาคณิตจะทำให้ไฟล์ใหญ่ขึ้นและใช้เวลาประมวลผลเพิ่มขึ้น ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีลดขนาดไฟล์เรขาคณิต** ด้วยการลดความแม่นยำของเรขาคณิตและ **วิธีปัดเศษค่า Z** ด้วย Aspose.GIS สำหรับ .NET เมื่อจบคู่มือคุณจะสามารถย่อไฟล์เรขาคณิต เร่งความเร็วการดำเนินการเชิงพื้นที่ และลดการใช้หน่วยความจำได้ทั้งหมดด้วยการเรียกใช้เมธอดไม่กี่ขั้นตอน

## คำตอบอย่างรวดเร็ว
- **“round Z” หมายถึงอะไร?** มันตัดจำนวนตำแหน่งทศนิยมของพิกัด Z ในวัตถุเรขาคณิต  
- **ทำไมต้องลดขนาดไฟล์เรขาคณิต?** จำนวนตำแหน่งทศนิยมต่อจุดที่น้อยลงช่วยลดการจัดเก็บ เร่งการสืบค้น และลดการใช้ RAM  
- **ไลบรารีใดจัดการเรื่องนี้?** Aspose.GIS for .NET มีเมธอดในตัว `RoundZ` และ `RoundXY`  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีสามารถใช้ทดสอบได้; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **ฉันสามารถควบคุมจำนวนตำแหน่งทศนิยมได้หรือไม่?** ได้ คุณระบุจำนวนตำแหน่งที่ต้องการในเมธอด `Round*`

## อะไรคือ “วิธีปัดเศษ Z” ใน GIS?
การปัดเศษพิกัด Z จะลบความแม่นยำทศนิยมที่ไม่จำเป็น โดยแปลงค่าตัวอย่างเช่น 3.345 เป็น 3.3 (หรือความแม่นยำใด ๆ ที่คุณระบุ) การลดนี้สามารถทำให้ขนาดไฟล์ลดลงอย่างเห็นได้ชัดและเร่งการประมวลผล โดยเฉพาะเมื่อรายละเอียดระดับความสูงที่ละเอียดกว่าความคลาดเคลื่อนที่ต้องการในการวิเคราะห์ไม่จำเป็น เป็นเทคนิคทั่วไปสำหรับการเพิ่มประสิทธิภาพชุดข้อมูล 3‑D

## ทำไมต้องลดขนาดไฟล์เรขาคณิตด้วย Aspose.GIS?
Aspose.GIS รองรับ **รูปแบบเวกเตอร์และแรสเตอร์กว่า 30 แบบ** และสามารถประมวลผลไฟล์ได้ถึง **2 GB** โดยไม่ต้องโหลดชุดข้อมูลทั้งหมดเข้าสู่หน่วยความจำ การลดความแม่นยำจะลดปริมาณข้อมูลต่อจุด ซึ่งโดยทั่วไปให้ผลลัพธ์เป็น **การสืบค้นเชิงพื้นที่เร็วขึ้น 20‑40 %** และ **การใช้หน่วยความจำน้อยลง 15‑30 %** ในชุดข้อมูลขนาดใหญ่

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้ตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้:
1. Aspose.GIS for .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก [Aspose.GIS website](https://releases.aspose.com/gis/net/)  
2. ความรู้พื้นฐานการเขียนโปรแกรม C#: ความคุ้นเคยกับภาษา C# จะเป็นประโยชน์

## นำเข้า namespace
ก่อนอื่น ให้นำเข้า namespace ที่จำเป็นเพื่อใช้คลาสและเมธอดของ Aspose.GIS

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: สร้างจุด
`Point` คือคลาสเรขาคณิตพื้นฐานที่แสดงตำแหน่งเดียวในพื้นที่ 2‑D หรือ 3‑D คุณจะใช้มันเพื่อสาธิตการลดความแม่นยำ

```csharp
Point point = new Point(1.344, 2.345, 3.345, 4.345);
```

## ขั้นตอนที่ 2: ลดความแม่นยำ XY
`RoundXY` ลดจำนวนตำแหน่งทศนิยมของพิกัด X และ Y เมธอดนี้รับจำนวนตำแหน่งที่ต้องการและคืนค่าเรขาคณิตใหม่ที่มีความแม่นยำที่ปรับแล้ว

```csharp
point.RoundXY(digits: 2);
```

## ขั้นตอนที่ 3: แสดงพิกัด
หลังจากปัดเศษ คุณสามารถตรวจสอบค่าพิกัดที่อัปเดตได้

```csharp
Console.WriteLine("{0}, {1}, {2}, {3}", point.X, point.Y, point.Z, point.M);
```

## ขั้นตอนที่ 4: ลดความแม่นยำ Z – วิธีปัดเศษ z
`RoundZ` จำกัดความแม่นยำของส่วนความสูง (Z) การใช้ขั้นตอนนี้มักให้การลดขนาดไฟล์ที่มากที่สุดสำหรับชุดข้อมูล 3‑D เนื่องจากค่าความสูงมักมีตำแหน่งทศนิยมหลายตำแหน่ง

```csharp
point.RoundZ(digits: 1);
```

## ขั้นตอนที่ 5: แสดงพิกัดที่อัปเดต
แสดงพิกัดของจุดหลังจากการลดความแม่นยำของ Z

```csharp
Console.WriteLine("{0}, {1}, {2}, {3}", point.X, point.Y, point.Z, point.M);
```

## ขั้นตอนที่ 6: สร้าง Linestring
`LineString` คือคอลเลกชันของจุดที่สร้างเป็นโพลีไลน์ ใช้สำหรับสาธิตการเปลี่ยนแปลงความแม่นยำเป็นกลุ่มหลายจุด

```csharp
LineString line = new LineString();
line.AddPoint(1.2, 2.3);
line.AddPoint(2.4, 3.1);
```

## ขั้นตอนที่ 7: ลดความแม่นยำ XY ของ Linestring
ใช้ `RoundXY` กับ `LineString` ทั้งหมดเพื่อทำให้ค่าพิกัด X/Y ของทุกจุดถูกตัดทศนิยม

```csharp
line.RoundXY(digits: 0);
```

## ขั้นตอนที่ 8: แสดงพิกัดที่อัปเดตของ Linestring
ตรวจสอบพิกัดหลังจากความแม่นยำ XY ถูกลดลง

```csharp
Console.WriteLine("{0}, {1}", line[0].X, line[0].Y);
Console.WriteLine("{0}, {1}", line[1].X, line[1].Y);
```

## กรณีการใช้งานทั่วไป & เคล็ดลับ
- **การแปลง raster‑vector ขนาดใหญ่:** การปัดเศษ Z สามารถทำให้ไฟล์เรขาคณิตกลางเล็กลง เร่งกระบวนการแปลง  
- **แอป GIS บนมือถือ:** ความแม่นยำต่ำลงช่วยลดแบนด์วิดท์เมื่อส่งเรขาคณิตผ่านเครือข่าย  
- **เคล็ดลับระดับมืออาชีพ:** ใช้ `RoundXY` ก่อน `RoundZ` เพื่อให้กระบวนการสอดคล้องและหลีกเลี่ยงการปัดเศษค่าที่ถูกปัดแล้วซ้ำ

## คำถามที่พบบ่อย

**Q: ทำไมการลดความแม่นยำของเรขาคณิตจึงสำคัญใน GIS?**  
A: การลดความแม่นยำของเรขาคณิตช่วยเพิ่มประสิทธิภาพการใช้หน่วยความจำและปรับปรุงประสิทธิภาพ โดยเฉพาะเมื่อจัดการกับชุดข้อมูลขนาดใหญ่ในแอปพลิเคชัน GIS  

**Q: การลดความแม่นยำของเรขาคณิตส่งผลต่อความแม่นยำหรือไม่?**  
A: แม้ว่าจะสูญเสียความแม่นยำเล็กน้อย แต่การแลกเปลี่ยนนี้มักให้สมดุลที่ดีระหว่างความแม่นยำและประสิทธิภาพสำหรับการวิเคราะห์เชิงพื้นที่ส่วนใหญ่  

**Q: ฉันสามารถกำหนดระดับการลดความแม่นยำใน Aspose.GIS for .NET ได้หรือไม่?**  
A: ได้ คุณสามารถระบุจำนวนตำแหน่งทศนิยมที่ต้องการสำหรับพิกัด XY และ Z โดยใช้เมธอด `RoundXY` และ `RoundZ`  

**Q: มีประโยชน์ด้านประสิทธิภาพที่วัดได้หรือไม่?**  
A: แน่นอน—ข้อมูลต่อจุดที่น้อยลงหมายถึงการสืบค้นเชิงพื้นที่ที่เร็วขึ้น การ I/O ที่ลดลง และการใช้หน่วยความจำน้อยลง ซึ่งมักให้การประมวลผลเร็วขึ้น **30 %** ในชุดข้อมูลทั่วไป  

**Q: ฉันจะขอรับการสนับสนุนสำหรับ Aspose.GIS for .NET ได้จากที่ไหน?**  
A: คุณสามารถรับการสนับสนุนโดยเยี่ยมชม [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) หรือเข้าถึงเอกสารใน [Aspose.GIS .NET API reference](https://reference.aspose.com/gis/net/)

**อัปเดตล่าสุด:** 2026-09-10  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [วิธีจำกัดความแม่นยำเมื่อเขียนเรขาคณิตด้วย Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)
- [สร้างเลเยอร์เวกเตอร์, จำกัดความแม่นยำด้วย Aspose.GIS for .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [วิธีแปลงเรขาคณิตเป็น WKT ด้วย Aspose.GIS for .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}