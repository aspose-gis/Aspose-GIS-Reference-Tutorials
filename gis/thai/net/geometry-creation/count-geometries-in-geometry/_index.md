---
title: นับเรขาคณิตในเรขาคณิตด้วย Aspose.GIS
linktitle: นับเรขาคณิตในเรขาคณิต
second_title: Aspose.GIS .NET API
description: เรียนรู้วิธีนับเรขาคณิตในเรขาคณิตโดยใช้ Aspose.GIS สำหรับ .NET บทช่วยสอนทีละขั้นตอนพร้อมตัวอย่างโค้ดสำหรับนักพัฒนา
weight: 23
url: /th/net/geometry-creation/count-geometries-in-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# นับเรขาคณิตในเรขาคณิตด้วย Aspose.GIS

## การแนะนำ
Aspose.GIS สำหรับ .NET เป็นเครื่องมืออันทรงพลังสำหรับนักพัฒนาที่ต้องการรวมฟังก์ชันการทำงานเชิงพื้นที่เข้ากับแอปพลิเคชัน .NET ของตน ไม่ว่าคุณกำลังสร้างซอฟต์แวร์แผนที่ บริการตามตำแหน่ง หรือเครื่องมือวิเคราะห์เชิงพื้นที่ Aspose.GIS มีชุดคุณลักษณะที่ครอบคลุมเพื่อตอบสนองความต้องการของคุณ ในบทช่วยสอนนี้ เราจะสำรวจวิธีนับเรขาคณิตภายในเรขาคณิตโดยใช้ Aspose.GIS สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. Visual Studio: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio ในระบบของคุณ
2. Aspose.GIS สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.GIS สำหรับ .NET จาก[หน้าดาวน์โหลด](https://releases.aspose.com/gis/net/).
3. ความรู้พื้นฐานของ C#: ทำความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม C#

## นำเข้าเนมสเปซ
ก่อนที่คุณจะเริ่มเขียนโค้ด คุณต้องนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.GIS

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 2: สร้างเรขาคณิตแบบจุด
```csharp
Point point = new Point(40.7128, -74.006);
```
 ที่นี่เราสร้าง`Point` เรขาคณิตที่มีละติจูด 40.7128 และลองจิจูด -74.006
## ขั้นตอนที่ 3: สร้างเรขาคณิต LineString
```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```
 ขั้นตอนนี้จะสร้าง`LineString` เรขาคณิตและเพิ่มจุดสองจุดเข้าไป
## ขั้นตอนที่ 4: สร้างคอลเลกชันเรขาคณิต
```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```
 จากนั้นเราก็สร้าง`GeometryCollection` และเพิ่มเรขาคณิตแบบจุดและเส้นที่สร้างไว้ก่อนหน้านี้ลงไป
## ขั้นตอนที่ 5: นับเรขาคณิต
```csharp
int geometriesCount = geometryCollection.Count;
```
 ขั้นตอนนี้จะนับจำนวนรูปทรงภายใน`GeometryCollection`.
## ขั้นตอนที่ 6: แสดงจำนวน
```csharp
Console.WriteLine(geometriesCount); // 2
```
 สุดท้าย เราจะพิมพ์จำนวนเรขาคณิตออกมา ซึ่งในกรณีนี้คือ`2`.

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีนับเรขาคณิตภายในเรขาคณิตโดยใช้ Aspose.GIS สำหรับ .NET ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถรวมฟังก์ชันภูมิสารสนเทศเข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### Aspose.GIS สำหรับ .NET เหมาะสำหรับทั้งเดสก์ท็อปและเว็บแอปพลิเคชันหรือไม่
ใช่ Aspose.GIS สำหรับ .NET สามารถใช้ได้ทั้งบนเดสก์ท็อปและเว็บแอปพลิเคชันได้อย่างราบรื่น
### ฉันสามารถดำเนินการสืบค้นเชิงพื้นที่โดยใช้ Aspose.GIS สำหรับ .NET ได้หรือไม่
แน่นอนว่า Aspose.GIS สำหรับ .NET ให้การสนับสนุนที่มีประสิทธิภาพสำหรับการดำเนินการสืบค้นเชิงพื้นที่บนรูปทรงเรขาคณิต
### Aspose.GIS สำหรับ .NET รองรับไฟล์ GIS หลากหลายรูปแบบหรือไม่
ใช่ Aspose.GIS สำหรับ .NET รองรับรูปแบบไฟล์ GIS ที่หลากหลาย รวมถึง SHP, KML และ GeoJSON
### มีการทดลองใช้ฟรีสำหรับ Aspose.GIS สำหรับ .NET หรือไม่
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[เว็บไซต์](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.GIS สำหรับ .NET ได้ที่ไหน
 คุณสามารถค้นหาการสนับสนุนได้ที่[ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
