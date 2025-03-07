---
title: สร้าง MultiLineString Geometry โดยใช้ Aspose.GIS สำหรับ .NET
linktitle: สร้างเรขาคณิต MultiLineString
second_title: Aspose.GIS .NET API
description: สำรวจพลังของ Aspose.GIS สำหรับ .NET ในการจัดการข้อมูลเชิงพื้นที่อย่างมีประสิทธิภาพ ดาวน์โหลดตอนนี้เพื่อประสบการณ์ที่ราบรื่น
weight: 15
url: /th/net/geometry-creation/create-multilinestring-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง MultiLineString Geometry โดยใช้ Aspose.GIS สำหรับ .NET

## การแนะนำ
Aspose.GIS สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถทำงานกับข้อมูลเชิงพื้นที่ภายในแอปพลิเคชัน .NET ของตนได้อย่างราบรื่น ไม่ว่าคุณจะสร้างแอปพลิเคชันการทำแผนที่ ทำการวิเคราะห์เชิงพื้นที่ หรือผสานรวมคุณสมบัติตามตำแหน่งลงในซอฟต์แวร์ของคุณ Aspose.GIS มอบเครื่องมือที่คุณต้องการในการจัดการข้อมูลเชิงพื้นที่อย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มใช้ Aspose.GIS สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
### สภาพแวดล้อมการพัฒนา .NET
ขั้นตอนที่ 1: ติดตั้ง Visual Studio หรือสภาพแวดล้อมการพัฒนา .NET อื่นๆ ที่ต้องการ
ขั้นตอนที่ 2: ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณสำหรับการพัฒนา .NET
### Aspose.GIS สำหรับ .NET
 ขั้นตอนที่ 1: รับใบอนุญาตสำหรับ Aspose.GIS สำหรับ .NET จาก[buy.aspose.com](https://purchase.aspose.com/buy).
 ขั้นตอนที่ 2: ดาวน์โหลดไลบรารี Aspose.GIS สำหรับ .NET จาก[releases.aspose.com](https://releases.aspose.com/gis/net/).
ขั้นตอนที่ 3: ติดตั้งไลบรารีในโครงการ .NET ของคุณ

## นำเข้าเนมสเปซ
หากต้องการเริ่มใช้ Aspose.GIS สำหรับ .NET ให้นำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
เนมสเปซนี้ให้การเข้าถึงฟังก์ชันหลักของ Aspose.GIS ซึ่งช่วยให้คุณสามารถทำงานกับข้อมูลเชิงพื้นที่ประเภทต่างๆ ได้

ตอนนี้ เรามาแบ่งตัวอย่างที่ให้ไว้ออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: สร้างวัตถุ LineString
```csharp
LineString firstLine = new LineString();
firstLine.AddPoint(7.5, -3.5);
firstLine.AddPoint(-9.6, 12.6);
LineString secondLine = new LineString();
secondLine.AddPoint(8.5, -2.6);
secondLine.AddPoint(-8.6, 1.5);
```
ในขั้นตอนนี้ เราสร้างออบเจ็กต์ LineString สองรายการซึ่งเป็นตัวแทนของแต่ละบรรทัด คะแนนจะถูกเพิ่มลงในแต่ละ LineString เพื่อกำหนดรูปทรงเรขาคณิต
## ขั้นตอนที่ 2: สร้างวัตถุ MultiLineString
```csharp
MultiLineString multiLineString = new MultiLineString();
multiLineString.Add(firstLine);
multiLineString.Add(secondLine);
```
ที่นี่ เราสร้างอินสแตนซ์ของวัตถุ MultiLineString และเพิ่มวัตถุ LineString ที่สร้างไว้ก่อนหน้านี้ลงไป ซึ่งส่งผลให้เกิดคอลเลกชันของรายการที่ถูกจัดกลุ่มเข้าด้วยกันเป็นเอนทิตีเดียว

## บทสรุป
โดยสรุป Aspose.GIS สำหรับ .NET นำเสนอโซลูชันที่ครอบคลุมสำหรับการจัดการข้อมูลภูมิสารสนเทศในแอปพลิเคชัน .NET ด้วยการทำตามขั้นตอนที่อธิบายไว้ข้างต้น นักพัฒนาจะสามารถใช้ไลบรารีได้อย่างมีประสิทธิภาพเพื่อจัดการและจัดการข้อมูลเชิงพื้นที่ได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### Aspose.GIS สำหรับ .NET เข้ากันได้กับกรอบงาน .NET ทั้งหมดหรือไม่
ใช่ Aspose.GIS สำหรับ .NET เข้ากันได้กับเฟรมเวิร์ก .NET เวอร์ชันต่างๆ ซึ่งช่วยให้นักพัฒนามีความยืดหยุ่น
### ฉันสามารถลองใช้ Aspose.GIS สำหรับ .NET ก่อนซื้อได้หรือไม่
 อย่างแน่นอน! คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้จาก[releases.aspose.com](https://releases.aspose.com/) เพื่อสำรวจคุณสมบัติและความสามารถของมัน
### ฉันจะรับการสนับสนุน Aspose.GIS สำหรับ .NET ได้อย่างไร
 สำหรับการสนับสนุนและความช่วยเหลือคุณสามารถเยี่ยมชมได้ที่[ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33)ซึ่งคุณสามารถถามคำถามและมีส่วนร่วมกับผู้ใช้และผู้เชี่ยวชาญคนอื่นๆ ได้
### ฉันจำเป็นต้องมีใบอนุญาตชั่วคราวเพื่อการทดสอบหรือไม่?
แม้ว่าเวอร์ชันทดลองใช้จะพร้อมสำหรับการทดสอบ แต่หากคุณต้องการคุณสมบัติเพิ่มเติมหรือต้องการประเมินฟังก์ชันการทำงานทั้งหมด คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[buy.aspose.com](https://purchase.aspose.com/temporary-license/).
### Aspose.GIS สำหรับ .NET เหมาะสำหรับทั้งเดสก์ท็อปและเว็บแอปพลิเคชันหรือไม่
ใช่ Aspose.GIS สำหรับ .NET สามารถใช้งานได้หลากหลาย รวมถึงแอปพลิเคชันบนเดสก์ท็อป เว็บ และฝั่งเซิร์ฟเวอร์ ซึ่งให้ความคล่องตัวในสถานการณ์การพัฒนาที่แตกต่างกัน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
