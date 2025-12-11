---
date: 2025-12-11
description: เรียนรู้วิธีแปลงพิกัดเป็น DMS ด้วย Aspose.GIS สำหรับ .NET รวมตัวอย่าง
  C# การแปลงละติจูดและลองจิจูดด้วย C# และคู่มือขั้นตอนโดยละเอียด
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: แปลงพิกัดเป็น DMS ด้วย Aspose.GIS สำหรับ .NET
url: /th/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลงพิกัดเป็น DMS ด้วย Aspose.GIS

## บทนำ
ในบทแนะนำนี้ คุณจะได้เรียนรู้วิธี **แปลงพิกัดเป็น DMS** (องศา, นาที, วินาที) ด้วยไลบรารี Aspose.GIS ที่ทรงพลังสำหรับ .NET ไม่ว่าคุณจะต้องการ c# แปลงละติจูดลองจิจูด สำหรับแอปพลิเคชันแผนที่, สร้างสตริงตำแหน่งที่อ่านง่ายโดยมนุษย์, หรือเพียงแค่สำรวจรูปแบบพิกัดต่าง ๆ คู่มือนี้จะพาคุณผ่านทุกขั้นตอนด้วยคำอธิบายที่ชัดเจนและโค้ด C# ที่พร้อมรัน

## คำตอบสั้น ๆ
- **“แปลงพิกัดเป็น DMS” หมายถึงอะไร?** จะเปลี่ยนค่าละติจูด/ลองจิจูดเชิงตัวเลขให้เป็นรูปแบบองศา‑นาที‑วินาทีแบบดั้งเดิม  
- **ไลบรารีใดทำการแปลง?** Aspose.GIS for .NET มีคลาส `GeoConvert` พร้อมการสนับสนุนรูปแบบในตัว  
- **ต้องมีลิขสิทธิ์เพื่อทดลองหรือไม่?** มีรุ่นทดลองฟรี; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6+  
- **สามารถใช้โค้ดเดียวกันสำหรับรูปแบบอื่นได้หรือไม่?** ใช่ — เพียงเปลี่ยนค่า enum `PointFormats` (เช่น `DecimalDegrees`, `GeoRef`)  

## การแปลงพิกัดเป็น DMS คืออะไร?
การแปลงพิกัดเป็น DMS จะเขียนค่าละติจูดและลองจิจูดแบบทศนิยมให้เป็นรูปแบบเช่น `25°30'00"N 45°30'00"E` การแสดงผลแบบนี้เป็นที่นิยมในงานแผนที่, การนำทาง, และการแลกเปลี่ยนข้อมูล GIS

## ทำไมต้องใช้ Aspose.GIS สำหรับการแปลงพิกัด?
- **API ครบวงจร** – ไม่ต้องใช้ไลบรารีภายนอกหรือคณิตศาสตร์ซับซ้อน; Aspose.GIS จัดการการแปลงและการจัดรูปแบบภายใน  
- **ความแม่นยำสูง** – จัดการกรณีขอบเช่นค่าติดลบและตัวบ่งชี้ซีกโลกอย่างแม่นยำ  
- **ข้ามแพลตฟอร์ม** – ทำงานเดียวกันบน Windows, Linux, และ macOS .NET runtimes  
- **ขยายได้** – สลับระหว่าง DMS, decimal degrees, degree‑decimal‑minutes, และรูปแบบ GeoRef ได้อย่างง่ายดาย  

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามขั้นตอน ตรวจสอบว่าคุณมี:

1. **ความรู้พื้นฐานของ C#** – คุ้นเคยกับตัวแปร, การเรียกเมธอด, และการแสดงผลบนคอนโซล  
2. **ติดตั้ง Aspose.GIS** – ดาวน์โหลดแพคเกจล่าสุดจาก [Aspose.GIS website](https://releases.aspose.com/gis/net/)  

## นำเข้า Namespaces
เริ่มต้นด้วยการนำเข้า namespace ที่จำเป็นสำหรับการทำงาน GIS:

```csharp
using System;
using Aspose.Gis;
```

## คู่มือขั้นตอนโดยละเอียด

### ขั้นตอนที่ 1: เริ่มกระบวนการแปลง
เราจะแสดงข้อความต้อนรับเพื่อให้คุณทราบว่าการสาธิตได้เริ่มต้นแล้ว

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### ขั้นตอนที่ 2: แปลงเป็น Decimal Degrees  
แม้เป้าหมายสุดท้ายจะเป็น DMS เราจะเริ่มด้วยการแสดงค่าทศนิยมเดิมก่อน

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### ขั้นตอนที่ 3: แปลงเป็น Degree Decimal Minutes  
รูปแบบนี้ (`DD°MM.m'`) เป็นขั้นตอนกลางที่นิยมเมื่อคุณต้องการ *convert lat long degree minutes*

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### ขั้นตอนที่ 4: แปลงเป็น Degree Minutes Seconds (DMS)  
นี่คือหัวใจของบทแนะนำ — **แปลงพิกัดเป็น DMS**

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### ขั้นตอนที่ 5: แปลงเป็น GeoRef  
เพื่อความครบถ้วน เราจะสาธิตรูปแบบ `GeoRef` ที่เป็นประโยชน์ในกระบวนการประมวลผลภาพถ่ายจากระยะไกล

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## ปัญหาที่พบบ่อยและวิธีแก้
- **ตัวอักษรซีกโลกไม่ถูกต้อง** – ตรวจสอบให้แน่ใจว่าคุณส่งค่าบวกสำหรับเหนือ/ตะวันออกและค่าลบสำหรับใต้/ตะวันตก; API จะเพิ่ม suffix ที่ถูกต้องโดยอัตโนมัติ  
- **ผลลัพธ์เป็นค่าว่าง** – ตรวจสอบว่า assembly `Aspose.Gis` ถูกอ้างอิงอย่างถูกต้องและโปรเจกต์ตั้งเป้าหมายเป็นเวอร์ชัน .NET ที่รองรับ  
- **ไม่พบลิขสิทธิ์** – วางไฟล์ลิขสิทธิ์ไว้ที่โฟลเดอร์รากของแอปพลิเคชันหรือกำหนดโปรแกรมmatically ด้วย `License license = new License(); license.SetLicense("Aspose.GIS.lic");`  

## คำถามที่พบบ่อย

**Q: Aspose.GIS รองรับภาษาโปรแกรมอื่นหรือไม่?**  
A: Aspose.GIS มุ่งเน้นที่นักพัฒนา .NET เป็นหลัก แต่ยังมีเวอร์ชัน Java ให้ใช้ด้วย  

**Q: สามารถทดลองใช้ Aspose.GIS ก่อนซื้อได้หรือไม่?**  
A: ใช่ คุณสามารถเข้าถึงรุ่นทดลองฟรีของ Aspose.GIS จาก [website](https://releases.aspose.com/)  

**Q: จะขอรับการสนับสนุนสำหรับ Aspose.GIS ได้อย่างไร?**  
A: คุณสามารถขอความช่วยเหลือจากฟอรั่มชุมชน Aspose.GIS [ที่นี่](https://forum.aspose.com/c/gis/33)  

**Q: มีลิขสิทธิ์ชั่วคราวสำหรับ Aspose.GIS หรือไม่?**  
A: มี สามารถขอรับลิขสิทธิ์ชั่วคราวได้จาก [temporary license page](https://purchase.aspose.com/temporary-license/)  

**Q: จะซื้อ Aspose.GIS ได้จากที่ไหน?**  
A: คุณสามารถซื้อ Aspose.GIS ได้จาก [purchase page](https://purchase.aspose.com/buy)  

## สรุป
โดยทำตามขั้นตอนเหล่านี้ คุณจะรู้วิธี **แปลงพิกัดเป็น DMS** และรูปแบบ GIS ที่พบบ่อยอื่น ๆ ด้วย Aspose.GIS สำหรับ .NET ความสามารถนี้ช่วยให้คุณผสานสตริงตำแหน่งที่อ่านง่ายเข้ากับแอปพลิเคชันแผนที่, รายงาน, หรือเวิร์กโฟลว์ข้อมูลเชิงพื้นที่ใด ๆ ได้อย่างราบรื่น อย่าลังเลที่จะทดลองค่าละติจูด/ลองจิจูดต่าง ๆ และสำรวจรูปแบบอื่น ๆ ที่คลาส `GeoConvert` มีให้

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}