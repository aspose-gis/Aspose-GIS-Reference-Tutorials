---
date: 2026-08-18
description: แปลงองศาทศนิยมเป็น dms ด้วย Aspose.GIS for .NET คู่มือ C# ทีละขั้นตอนนี้แสดงวิธีแปลง
  latitude/longitude, องศาทศนิยมเป็น dms และอื่น ๆ อีกมาก
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: แปลงพิกัด
og_description: การแปลงองศาทศนิยมเป็น dms ง่ายขึ้นด้วย Aspose.GIS for .NET เรียนรู้การแปลงค่า
  latitude‑longitude ให้เป็นรูปแบบ DMS ในหน่วยนาที
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: แปลงองศาทศนิยมเป็น dms ด้วย Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: วิธีแปลงองศาทศนิยมเป็น dms ด้วย Aspose.GIS for .NET
url: /th/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแปลงองศาทศนิยมเป็น DMS ด้วย Aspose.GIS

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีแปลงองศาทศนิยมเป็น DMS** ด้วยไลบรารีที่ทรงพลังของ Aspose.GIS สำหรับ .NET ไม่ว่าคุณจะต้องการ **c# convert lat long**, สร้างสตริงตำแหน่งที่อ่านง่ายสำหรับรายงาน, หรือเพียงแค่สำรวจรูปแบบพิกัดต่าง ๆ คู่มือนี้จะพาคุณผ่านทุกขั้นตอนด้วยคำอธิบายที่ชัดเจนและโค้ดสแนป C# ที่พร้อมใช้งาน

## คำตอบอย่างรวดเร็ว
- **การแปลงพิกัดเป็น DMS หมายถึงอะไร?** มันแปลงค่าตำแหน่งละติจูด/ลองจิจูดเชิงตัวเลขให้เป็นรูปแบบองศา‑นาที‑วินาทีแบบดั้งเดิม.  
- **ไลบรารีใดที่จัดการการแปลง?** Aspose.GIS สำหรับ .NET มีคลาส `GeoConvert` พร้อมการสนับสนุนรูปแบบในตัว.  
- **ต้องมีลิขสิทธิ์เพื่อทดลองใช้งานหรือไม่?** มีรุ่นทดลองฟรี; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6+.  
- **สามารถใช้โค้ดเดียวกันสำหรับรูปแบบอื่นได้หรือไม่?** ได้ — เพียงเปลี่ยนค่า enum `PointFormats` (เช่น `DecimalDegrees`, `GeoRef`).  

## การแปลงพิกัดเป็น DMS คืออะไร?
การแปลงพิกัดเป็น DMS จะเขียนค่าละติจูดและลองจิจูดเชิงทศนิยมใหม่เป็นรูปแบบเช่น `25°30'00"N 45°30'00"E`. กระบวนการจะแยกแต่ละองศาทศนิยมเป็นองศาเต็ม, นาที (หนึ่งหกสิบขององศา), และวินาที (หนึ่งหกสิบของนาที) แล้วต่อท้ายด้วยตัวบ่งชี้ซีกโลกที่เหมาะสม (N, S, E, W). รูปแบบที่อ่านง่ายนี้มีความสำคัญสำหรับชุดข้อมูลเก่าหลายชุดและสำหรับการสื่อสารตำแหน่งที่แม่นยำโดยไม่ต้องพึ่งพาการเขียนเป็นทศนิยม.

## ทำไมต้องใช้ Aspose.GIS สำหรับการแปลงพิกัด?
Aspose.GIS รองรับ **รูปแบบการนำเข้าและส่งออกกว่า 50 แบบ** และสามารถประมวลผลไฟล์ GIS ขนาดหลายร้อยหน้าโดยไม่ต้องโหลดชุดข้อมูลทั้งหมดเข้าสู่หน่วยความจำ API ให้ความแม่นยำระดับซับมิลลิเมตรสำหรับกรณีขอบเช่นค่าติดลบและตัวบ่งชี้ซีกโลก และทำงานอย่างสม่ำเสมอบน Windows, Linux, และ macOS runtime ของ .NET.

## ข้อกำหนดเบื้องต้น
1. **ความรู้พื้นฐานของ C#** – ความคุ้นเคยกับตัวแปร, การเรียกเมธอด, และการแสดงผลบนคอนโซล.  
2. **Aspose.GIS ติดตั้งแล้ว** – ดาวน์โหลดแพคเกจล่าสุดจาก [Aspose.GIS website](https://releases.aspose.com/gis/net/). คุณยังสามารถสำรวจไซต์หลักของการปล่อย Aspose ได้ที่ [Aspose releases website](https://releases.aspose.com/).  

## นำเข้าเนมสเปซ
ก่อนอื่น ให้นำเข้าเนมสเปซที่จำเป็นสำหรับการทำงาน GIS:

ส่วนการนำเข้าเนมสเปซยังคงไม่เปลี่ยนแปลง.

## คู่มือทีละขั้นตอน

### คลาส GeoConvert คืออะไร?
คลาส `GeoConvert` ให้เมธอดแบบสแตติกสำหรับการแปลงระหว่างรูปแบบพิกัดต่าง ๆ เช่น องศาทศนิยม, DMS, และ GeoRef. มันมีโอเวอร์โหลดที่รับค่าตัวเลขดิบหรืออ็อบเจ็กต์ `Point` และคืนค่าสตริงที่จัดรูปแบบหรืออ็อบเจ็กต์ `Point` ใหม่. ด้วยการจัดการกรณีขอบเช่นพิกัดติดลบและการปัดเศษ, คลาสนี้รับประกันว่าผลลัพธ์สอดคล้องกับมาตรฐาน GIS, ทำให้การรวมเข้ากับแอปพลิเคชันแมปปิ้ง .NET ใด ๆ ง่ายขึ้น.

### ขั้นตอนที่ 1: เริ่มกระบวนการแปลง
เราพิมพ์ข้อความทักทายเพื่อให้คุณทราบว่าการสาธิตได้เริ่มต้นแล้ว.

```csharp
using System;
using Aspose.Gis;
```

### ขั้นตอนที่ 2: แปลงเป็นองศาทศนิยม
แม้เป้าหมายสุดท้ายจะเป็น DMS, เราเริ่มด้วยการแสดงการแสดงผลแบบทศนิยมเดิม. สิ่งนี้ยังแสดงเส้นทาง **decimal degrees to dms** ที่คุณจะทำตามต่อไป.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### ขั้นตอนที่ 3: แปลงเป็นองศาและนาทีทศนิยม
รูปแบบนี้ (`DD°MM.m'`) เป็นขั้นตอนกลางที่พบบ่อยเมื่อคุณต้องการ **convert lat long degree minutes**.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### ขั้นตอนที่ 4: แปลงเป็นองศานาทีวินาที (DMS)
นี่คือหัวใจของบทแนะนำของเรา—**convert coordinates to dms**.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### ขั้นตอนที่ 5: แปลงเป็น GeoRef
เพื่อความครบถ้วน เรายังสาธิตรูปแบบ `GeoRef` ซึ่งมีประโยชน์ในกระบวนการประมวลผลภาพถ่ายจากระยะไกล.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## ปัญหาทั่วไปและวิธีแก้
- **ตัวอักษรซีกโลกไม่ถูกต้อง** – ตรวจสอบว่าคุณส่งค่าบวกสำหรับเหนือ/ตะวันออกและค่าลบสำหรับใต้/ตะวันตก; API จะเพิ่ม suffix ที่ถูกต้องโดยอัตโนมัติ.  
- **ผลลัพธ์เป็นค่าว่างโดยไม่คาดคิด** – ตรวจสอบว่าอ้างอิง assembly `Aspose.Gis` อย่างถูกต้องและโครงการตั้งเป้าหมายเป็นเวอร์ชัน .NET ที่รองรับ.  
- **ไม่พบลิขสิทธิ์** – วางไฟล์ลิขสิทธิ์ของคุณในโฟลเดอร์รากของแอปพลิเคชันหรือกำหนดโปรแกรมโดยใช้ `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.

## คำถามที่พบบ่อย

**Q: Aspose.GIS รองรับภาษาโปรแกรมอื่นหรือไม่?**  
A: Aspose.GIS มุ่งเป้าไปที่นักพัฒนา .NET เป็นหลัก, แต่มีเวอร์ชัน Java ให้ใช้งานด้วย.

**Q: ฉันสามารถทดลองใช้ Aspose.GIS ก่อนซื้อได้หรือไม่?**  
A: ได้, คุณสามารถเข้าถึงรุ่นทดลองฟรีของ Aspose.GIS จาก [website](https://releases.aspose.com/).

**Q: ฉันจะขอรับการสนับสนุนสำหรับ Aspose.GIS ได้อย่างไร?**  
A: คุณสามารถขอความช่วยเหลือจากฟอรั่มชุมชน Aspose.GIS [ที่นี่](https://forum.aspose.com/c/gis/33).

**Q: มีลิขสิทธิ์ชั่วคราวสำหรับ Aspose.GIS หรือไม่?**  
A: มี, สามารถขอรับลิขสิทธิ์ชั่วคราวได้จาก [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: ฉันสามารถซื้อ Aspose.GIS ได้จากที่ไหน?**  
A: คุณสามารถซื้อ Aspose.GIS ได้จาก [purchase page](https://purchase.aspose.com/buy).

## สรุป
โดยทำตามขั้นตอนเหล่านี้ คุณจะรู้วิธี **convert decimal degrees to dms** และรูปแบบ GIS ที่พบบ่อยอื่น ๆ ด้วย Aspose.GIS สำหรับ .NET ความสามารถนี้ทำให้คุณสามารถรวมสตริงตำแหน่งที่อ่านง่ายเข้าไปในแอปพลิเคชันแผนที่, รายงาน, หรือกระบวนการข้อมูลเชิงพื้นที่ใด ๆ ได้อย่างราบรื่น อย่าลังเลที่จะทดลองค่าละติจูด/ลองจิจูดต่าง ๆ และสำรวจรูปแบบอื่น ๆ ที่คลาส `GeoConvert` มีให้.

**อัปเดตล่าสุด:** 2026-08-18  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## บทแนะนำที่เกี่ยวข้อง

- [วิธีสร้างจุดเรขาคณิตและรับประเภทเรขาคณิตด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-analysis/get-geometry-type/)
- [วิธีแปลง GeoJSON – Aspose.GIS สำหรับ .NET](/gis/net/geo-data-conversion/)
- [สร้าง MultiPoint Geometry .NET ด้วย Aspose.GIS](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}