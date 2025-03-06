---
title: ตรวจสอบเรขาคณิตเพื่อความเท่าเทียมกัน
linktitle: ตรวจสอบเรขาคณิตเพื่อความเท่าเทียมกัน
second_title: Aspose.GIS .NET API
description: เรียนรู้วิธีใช้ Aspose.GIS สำหรับ .NET เพื่อตรวจสอบรูปทรงเรขาคณิตเพื่อความเท่าเทียมกันในแอปพลิเคชัน .NET ของคุณด้วยบทช่วยสอนที่ครอบคลุมนี้
weight: 10
url: /th/net/geometry-analysis/check-geometries-for-equality/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตรวจสอบเรขาคณิตเพื่อความเท่าเทียมกัน

## การแนะนำ
Aspose.GIS สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถทำงานกับข้อมูลภูมิสารสนเทศในแอปพลิเคชัน .NET ได้อย่างมีประสิทธิภาพ ไม่ว่าคุณกำลังสร้างแอปพลิเคชันการทำแผนที่ เครื่องมือวิเคราะห์เชิงพื้นที่ หรือบูรณาการฟังก์ชันเชิงพื้นที่เข้ากับซอฟต์แวร์ที่มีอยู่ Aspose.GIS ก็มีเครื่องมือที่คุณต้องการเพื่อให้งานสำเร็จลุล่วงได้
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มใช้ Aspose.GIS สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### ติดตั้ง .NET Framework แล้ว
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง .NET Framework บนระบบของคุณ คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Microsoft
### Aspose.GIS สำหรับไลบรารี .NET
 ดาวน์โหลดและติดตั้งไลบรารี Aspose.GIS สำหรับ .NET จาก[หน้าดาวน์โหลด](https://releases.aspose.com/gis/net/). ปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้ในเอกสารประกอบ
### การพัฒนาสภาพแวดล้อม
ตั้งค่าสภาพแวดล้อมการพัฒนาที่คุณต้องการ เช่น Visual Studio สำหรับการพัฒนา .NET

## นำเข้าเนมสเปซ
ในแอปพลิเคชัน .NET ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อใช้ฟังก์ชัน Aspose.GIS:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: กำหนดรูปทรงเรขาคณิต
ขั้นแรก ให้กำหนดรูปทรงที่คุณต้องการเปรียบเทียบ ในตัวอย่างนี้ เรามีรูปทรงเรขาคณิตสองแบบ:`geometry1` และ`geometry2`.
```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```
## ขั้นตอนที่ 2: ตรวจสอบรูปทรงเรขาคณิตเพื่อความเท่าเทียมกัน
 ตอนนี้ ตรวจสอบว่าเรขาคณิตเท่ากันเชิงพื้นที่หรือไม่โดยใช้`SpatiallyEquals` วิธีการจัดทำโดย Aspose.GIS
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // จริง
```
 นี้จะพิมพ์`True` ไปยังคอนโซลตั้งแต่นั้นมา`geometry1` และ`geometry2` มีความเท่าเทียมกันในเชิงพื้นที่
## ขั้นตอนที่ 3: ปรับเปลี่ยนเรขาคณิต
 ต่อไปเรามาปรับเปลี่ยนกัน`geometry2` โดยการเพิ่มจุดใหม่
```csharp
geometry2.AddPoint(3, 3);
```
## ขั้นตอนที่ 4: ตรวจสอบความเท่าเทียมกันอีกครั้ง
ตอนนี้ ให้ตรวจสอบความเท่าเทียมกันของรูปทรงอีกครั้งหลังการปรับเปลี่ยน
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // เท็จ
```
 คราวนี้ผลลัพธ์จะเป็น`False` เนื่องจากรูปทรงเรขาคณิตไม่เท่ากันในเชิงพื้นที่อีกต่อไปเนื่องจากมีการปรับเปลี่ยน`geometry2`.

## บทสรุป
โดยสรุป Aspose.GIS สำหรับ .NET มอบเครื่องมือที่มีประสิทธิภาพสำหรับการทำงานกับข้อมูลเชิงพื้นที่ในแอปพลิเคชัน .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถตรวจสอบรูปทรงเรขาคณิตเพื่อความเท่าเทียมกันได้อย่างง่ายดายโดยใช้วิธี Aspose.GIS
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.GIS สำหรับ .NET กับเฟรมเวิร์ก .NET อื่นๆ ได้หรือไม่
ใช่ Aspose.GIS สำหรับ .NET เข้ากันได้กับเฟรมเวิร์ก .NET ต่างๆ รวมถึง .NET Core และ .NET Standard
### มีการทดลองใช้ฟรีสำหรับ Aspose.GIS สำหรับ .NET หรือไม่
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[หน้าเผยแพร่](https://releases.aspose.com/).
### ฉันจะหาเอกสารสำหรับ Aspose.GIS สำหรับ .NET ได้ที่ไหน
 คุณสามารถดูเอกสารรายละเอียดได้ที่[หน้าเอกสารประกอบของ Aspose.GIS](https://reference.aspose.com/gis/net/).
### ฉันจะรับการสนับสนุน Aspose.GIS สำหรับ .NET ได้อย่างไร
 คุณสามารถรับการสนับสนุนจากฟอรัมชุมชน Aspose.GIS[ที่นี่](https://forum.aspose.com/c/gis/33).
### ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.GIS สำหรับ .NET ได้หรือไม่
 ใช่ คุณสามารถซื้อใบอนุญาตชั่วคราวได้จาก[หน้าซื้อ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
