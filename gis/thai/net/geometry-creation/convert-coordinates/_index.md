---
title: ประสานงานการแปลงด้วย Aspose.GIS
linktitle: แปลงพิกัด
second_title: Aspose.GIS .NET API
description: เรียนรู้วิธีแปลงพิกัดด้วย Aspose.GIS สำหรับ .NET มีคำแนะนำทีละขั้นตอน ข้อกำหนดเบื้องต้น และคำถามที่พบบ่อย
type: docs
weight: 25
url: /th/net/geometry-creation/convert-coordinates/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกเข้าไปในโลกของระบบสารสนเทศทางภูมิศาสตร์ (GIS) โดยใช้ไลบรารี Aspose.GIS อันทรงพลังสำหรับ .NET Aspose.GIS เป็นชุดเครื่องมือที่ครอบคลุมที่ช่วยให้นักพัฒนาสามารถทำงานกับข้อมูลเชิงพื้นที่ได้อย่างง่ายดาย ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการใช้ Aspose.GIS เพื่อแปลงพิกัดอย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. ความรู้พื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# เป็นสิ่งสำคัญในการทำความเข้าใจและนำตัวอย่างโค้ดที่ให้มาไปใช้
  
2.  การติดตั้ง Aspose.GIS: ตรวจสอบให้แน่ใจว่าคุณได้ดาวน์โหลดและติดตั้งไลบรารี Aspose.GIS สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์ Aspose.GIS](https://releases.aspose.com/gis/net/).

## นำเข้าเนมสเปซ
ก่อนที่เราจะเริ่มต้น เรามานำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

เรามาแยกตัวอย่างออกเป็นหลายขั้นตอนเพื่อความเข้าใจที่ชัดเจน:
## ขั้นตอนที่ 1: เริ่มกระบวนการแปลง
```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```
บรรทัดนี้เพียงแสดงข้อความที่ระบุถึงการเริ่มต้นกระบวนการแปลงพิกัด
## ขั้นตอนที่ 2: แปลงเป็นองศาทศนิยม
```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```
 ที่นี่เราแปลงพิกัด (25.5, 45.5) เป็นรูปแบบองศาทศนิยมโดยใช้`AsPointText` วิธีการด้วย`PointFormats.DecimalDegrees` พารามิเตอร์. ผลลัพธ์จะถูกพิมพ์ไปยังคอนโซล
## ขั้นตอนที่ 3: แปลงเป็นนาทีทศนิยมระดับ
```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```
ขั้นตอนนี้จะแปลงพิกัดเป็นรูปแบบนาทีทศนิยมและพิมพ์ผลลัพธ์
## ขั้นตอนที่ 4: แปลงเป็นองศานาทีวินาที
```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```
ในทำนองเดียวกัน เราแปลงพิกัดเป็นรูปแบบองศา นาที วินาที และแสดงผลลัพธ์
## ขั้นตอนที่ 5: แปลงเป็น GeoRef
```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```
สุดท้าย เราจะแปลงพิกัดเป็นรูปแบบ GeoRef และพิมพ์ผลลัพธ์

## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการแปลงพิกัดโดยใช้ Aspose.GIS สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนและใช้ไลบรารี Aspose.GIS คุณสามารถจัดการข้อมูลเชิงพื้นที่ภายในแอปพลิเคชัน .NET ของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### Aspose.GIS เข้ากันได้กับภาษาการเขียนโปรแกรมอื่นหรือไม่
Aspose.GIS มีเป้าหมายหลักคือนักพัฒนา .NET แต่นำเสนอความสามารถในการทำงานร่วมกับ Java ผ่าน Aspose.GIS สำหรับ Java
### ฉันสามารถลองใช้ Aspose.GIS ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถเข้าถึง Aspose.GIS รุ่นทดลองใช้ฟรีได้จาก[เว็บไซต์](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.GIS ได้อย่างไร
 คุณสามารถขอความช่วยเหลือได้จากฟอรัมชุมชน Aspose.GIS[ที่นี่](https://forum.aspose.com/c/gis/33).
### มีใบอนุญาตชั่วคราวสำหรับ Aspose.GIS หรือไม่
 ใช่ สามารถรับใบอนุญาตชั่วคราวได้จาก[หน้าใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/).
### ฉันจะซื้อ Aspose.GIS ได้ที่ไหน
 คุณสามารถซื้อ Aspose.GIS ได้จาก[หน้าซื้อ](https://purchase.aspose.com/buy).