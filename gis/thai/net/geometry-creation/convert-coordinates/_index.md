---
date: 2026-02-13
description: เรียนรู้วิธีแปลงพิกัดเป็น DMS ด้วย Aspose.GIS สำหรับ .NET คู่มือ C# ขั้นตอนต่อขั้นตอนนี้แสดงการแปลงละติจูดและลองจิจูด,
  องศาทศนิยมเป็น DMS และอื่น ๆ อีกมาก
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: วิธีแปลงพิกัดเป็น DMS ด้วย Aspose.GIS สำหรับ .NET
url: /th/net/geometry-creation/convert-coordinates/
weight: 25
---

 -> "**ผู้เขียน:** Aspose"

Then closing shortcodes.

Also need to keep the backtop button shortcode unchanged.

Now produce final content with all translations.

Check for any leftover English text: In bullet list we kept technical terms like "All‑in‑one API" etc. That's okay.

Make sure we didn't translate code block placeholders.

Now craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแปลงพิกัดเป็น DMS ด้วย Aspose.GIS

## บทนำ
ในบทแนะนำนี้ คุณจะได้เรียนรู้ **วิธีแปลงพิกัด** เป็น DMS (องศา, นาที, วินาที) ด้วยไลบรารี Aspose.GIS ที่ทรงพลังสำหรับ .NET ไม่ว่าคุณจะต้องการ **c# convert lat long**, สร้างสตริงตำแหน่งที่อ่านได้โดยมนุษย์, หรือเพียงแค่สำรวจรูปแบบพิกัดต่าง ๆ คู่มือนี้จะพาคุณผ่านทุกขั้นตอนด้วยคำอธิบายที่ชัดเจนและโค้ด C# ที่พร้อมรัน

## คำตอบด่วน
- **“convert coordinates to DMS” หมายถึงอะไร?** มันแปลงค่าละติจูด/ลองจิจูดเชิงตัวเลขให้เป็นรูปแบบองศา‑นาที‑วินาทีแบบดั้งเดิม  
- **ไลบรารีใดที่จัดการการแปลง?** Aspose.GIS สำหรับ .NET มีคลาส `GeoConvert` พร้อมการสนับสนุนรูปแบบในตัว  
- **ต้องใช้ลิขสิทธิ์เพื่อทดลองหรือไม่?** มีการทดลองใช้ฟรี; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6+.  
- **สามารถใช้โค้ดเดียวกันสำหรับรูปแบบอื่นได้หรือไม่?** ได้—เพียงเปลี่ยนค่า enum `PointFormats` (เช่น `DecimalDegrees`, `GeoRef`).  

## วิธีแปลงพิกัดเป็น DMS
ก่อนจะลงลึกในโค้ด เรามาทำความเข้าใจกันว่าทำไม DMS ยังคงมีคุณค่า นักทำแผนที่, นักบิน, และผู้ให้บริการข้อมูล GIS จำนวนมากพึ่งพา DMS เนื่องจากเป็นมิตรต่อผู้ใช้และสอดคล้องกับแผนที่แบบดั้งเดิม Aspose.GIS กำจัดความจำเป็นในการคำนวณด้วยมือ ทำให้คุณสามารถมุ่งเน้นที่ตรรกะของแอปพลิเคชันของคุณได้

## การแปลงพิกัดเป็น DMS คืออะไร?
การแปลงพิกัดเป็น DMS จะเขียนค่าละติจูดและลองจิจูดแบบทศนิยมใหม่เป็นรูปแบบเช่น `25°30'00"N 45°30'00"E`. การแสดงผลนี้ถูกใช้กันอย่างแพร่หลายในงานทำแผนที่, การนำทาง, และการแลกเปลี่ยนข้อมูล GIS

## ทำไมต้องใช้ Aspose.GIS สำหรับการแปลงพิกัด?
- **All‑in‑one API** – ไม่ต้องใช้ไลบรารีภายนอกหรือคณิตศาสตร์ซับซ้อน; Aspose.GIS จัดการการแยกวิเคราะห์และการจัดรูปแบบภายใน  
- **High accuracy** – จัดการกรณีขอบอย่างแม่นยำ เช่น ค่าติดลบและตัวบ่งชี้ซีกโลก  
- **Cross‑platform** – ทำงานเช่นเดียวกันบน Windows, Linux, และ macOS runtime ของ .NET  
- **Extensible** – สามารถสลับระหว่างรูปแบบ DMS, decimal degrees, degree‑decimal‑minutes, และ GeoRef ได้อย่างง่ายดาย  

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน ให้แน่ใจว่าคุณมี:

1. **Basic knowledge of C#** – ความคุ้นเคยกับตัวแปร, การเรียกเมธอด, และการแสดงผลบนคอนโซล.  
2. **Aspose.GIS installed** – ดาวน์โหลดแพคเกจล่าสุดจาก [เว็บไซต์ Aspose.GIS](https://releases.aspose.com/gis/net/).  

## นำเข้า Namespaces
แรกเริ่ม ให้นำเข้า namespaces ที่จำเป็นสำหรับการทำงาน GIS:

```csharp
using System;
using Aspose.Gis;
```

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: เริ่มกระบวนการแปลง
เราจะแสดงข้อความเป็นมิตรเพื่อให้คุณทราบว่าการสาธิตได้เริ่มต้นแล้ว

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### ขั้นตอนที่ 2: แปลงเป็น Decimal Degrees
แม้ว่าจุดมุ่งหมายสุดท้ายคือ DMS เราเริ่มด้วยการแสดงการแทนค่าทศนิยมเดิม ซึ่งยังเป็นการสาธิตเส้นทาง **decimal degrees to dms** ที่คุณจะตามต่อในภายหลัง

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### ขั้นตอนที่ 3: แปลงเป็น Degree Decimal Minutes
รูปแบบนี้ (`DD°MM.m'`) เป็นขั้นตอนกลางที่พบบ่อยเมื่อคุณต้องการ *convert lat long degree minutes*.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### ขั้นตอนที่ 4: แปลงเป็น Degree Minutes Seconds (DMS)
นี่คือหัวใจของบทแนะนำของเรา—**convert coordinates to DMS**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### ขั้นตอนที่ 5: แปลงเป็น GeoRef
เพื่อความครบถ้วน เรายังสาธิตรูปแบบ `GeoRef` ซึ่งมีประโยชน์ในกระบวนการทำงานด้านการสำรวจระยะไกล

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## ปัญหาที่พบบ่อยและวิธีแก้
- **Incorrect hemisphere letters** – ตรวจสอบให้แน่ใจว่าคุณส่งค่าบวกสำหรับเหนือ/ตะวันออกและค่าลบสำหรับใต้/ตะวันตก; API จะเพิ่ม suffix ที่ถูกต้องโดยอัตโนมัติ  
- **Unexpected blank output** – ตรวจสอบว่า assembly `Aspose.Gis` ถูกอ้างอิงอย่างถูกต้องและโครงการตั้งเป้าหมายเป็นเวอร์ชัน .NET ที่รองรับ  
- **License not found** – วางไฟล์ลิขสิทธิ์ของคุณในโฟลเดอร์รากของแอปพลิเคชันหรือกำหนดโปรแกรมmatically ด้วย `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.  

## คำถามที่พบบ่อย

**Q: Aspose.GIS รองรับภาษาโปรแกรมอื่นหรือไม่?**  
A: Aspose.GIS มุ่งเป้าเป็นหลักไปยังนักพัฒนา .NET แต่ก็มีเวอร์ชัน Java ให้ใช้ด้วย  

**Q: ฉันสามารถทดลองใช้ Aspose.GIS ก่อนซื้อได้หรือไม่?**  
A: ได้, คุณสามารถเข้าถึงการทดลองใช้ฟรีของ Aspose.GIS จาก [เว็บไซต์](https://releases.aspose.com/).  

**Q: ฉันจะขอรับการสนับสนุนสำหรับ Aspose.GIS ได้อย่างไร?**  
A: คุณสามารถขอความช่วยเหลือจากฟอรั่มชุมชน Aspose.GIS [ที่นี่](https://forum.aspose.com/c/gis/33).  

**Q: มีลิขสิทธิ์ชั่วคราวสำหรับ Aspose.GIS หรือไม่?**  
A: มี, สามารถรับลิขสิทธิ์ชั่วคราวได้จาก [หน้าลิขสิทธิ์ชั่วคราว](https://purchase.aspose.com/temporary-license/).  

**Q: ฉันสามารถซื้อ Aspose.GIS ได้จากที่ไหน?**  
A: คุณสามารถซื้อ Aspose.GIS ได้จาก [หน้าเพจการซื้อ](https://purchase.aspose.com/buy).  

## สรุป
โดยทำตามขั้นตอนเหล่านี้ คุณจะรู้วิธี **convert coordinates to DMS** และรูปแบบ GIS ที่พบบ่อยอื่น ๆ ด้วย Aspose.GIS สำหรับ .NET ความสามารถนี้ทำให้คุณสามารถผสานสตริงตำแหน่งที่อ่านได้โดยมนุษย์เข้าไปในแอปพลิเคชันแผนที่, รายงาน, หรือกระบวนการทำงานข้อมูลเชิงพื้นที่ใด ๆ ได้อย่างราบรื่น อย่าลังเลที่จะทดลองค่าละติจูด/ลองจิจูดต่าง ๆ และสำรวจรูปแบบอื่น ๆ ที่คลาส `GeoConvert` มีให้

---

**อัปเดตล่าสุด:** 2026-02-13  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}