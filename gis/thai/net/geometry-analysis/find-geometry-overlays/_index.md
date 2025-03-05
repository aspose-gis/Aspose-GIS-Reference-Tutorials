---
title: เชี่ยวชาญการวางซ้อนเรขาคณิตด้วย Aspose.GIS สำหรับ .NET
linktitle: ค้นหาการซ้อนทับทางเรขาคณิต
second_title: Aspose.GIS .NET API
description: เรียนรู้วิธีดำเนินการโอเวอร์เลย์เรขาคณิตโดยใช้ Aspose.GIS สำหรับ .NET การดำเนินการทางแยกหลัก สหภาพ ผลต่าง และผลต่างสมมาตร
type: docs
weight: 16
url: /th/net/geometry-analysis/find-geometry-overlays/
---
## การแนะนำ
ในขอบเขตของระบบสารสนเทศภูมิศาสตร์ (GIS) การดำเนินการซ้อนทับเป็นพื้นฐานสำหรับการวิเคราะห์เชิงพื้นที่ ช่วยให้สามารถเปรียบเทียบและรวมชุดข้อมูลเชิงพื้นที่ต่างๆ เข้าด้วยกันเพื่อให้ได้ข้อมูลเชิงลึกที่มีคุณค่า Aspose.GIS สำหรับ .NET มีฟังก์ชันการทำงานที่มีประสิทธิภาพสำหรับการแสดงภาพซ้อนทับทางเรขาคณิตอย่างมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะเจาะลึกการดำเนินการซ้อนทับต่างๆ เช่น Intersection, Union, Difference และ Symmetric Difference โดยใช้ Aspose.GIS สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### 1. สภาพแวดล้อมการพัฒนา .NET
ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา .NET บนเครื่องของคุณ คุณสามารถดาวน์โหลดและติดตั้ง .NET SDK ได้จากเว็บไซต์ .NET
### 2. Aspose.GIS สำหรับไลบรารี .NET
 ดาวน์โหลดและติดตั้งไลบรารี Aspose.GIS สำหรับ .NET จากไฟล์[เว็บไซต์](https://releases.aspose.com/gis/net/).
## นำเข้าเนมสเปซ
ก่อนที่คุณจะเริ่มใช้ Aspose.GIS สำหรับ .NET ได้ คุณจะต้องนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณก่อน
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: สร้างวัตถุรูปหลายเหลี่ยม
ขั้นแรก เราจะกำหนดวัตถุรูปหลายเหลี่ยมสองชิ้นที่แสดงถึงพื้นที่เชิงพื้นที่
```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```
## ขั้นตอนที่ 2: ดำเนินการทางแยก
ต่อไป เราจะหาจุดตัดของรูปหลายเหลี่ยมทั้งสอง
```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // รูปหลายเหลี่ยม
```
## ขั้นตอนที่ 3: พิมพ์จุดตัดกัน
เราจะพิมพ์จุดของรูปหลายเหลี่ยมที่ตัดกัน
```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```
## ขั้นตอนที่ 4: ดำเนินการปฏิบัติการสหภาพ
ทีนี้ เรามาค้นหาการรวมกันของสองรูปหลายเหลี่ยมกัน
```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // รูปหลายเหลี่ยม
```
## ขั้นตอนที่ 5: พิมพ์คะแนนยูเนี่ยน
พิมพ์จุดของรูปหลายเหลี่ยมแบบยูเนี่ยน
```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```
## ขั้นตอนที่ 6: ดำเนินการดำเนินการแตกต่าง
ต่อไป เรามาดูความแตกต่างระหว่างรูปหลายเหลี่ยมสองรูปนี้กัน
```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // รูปหลายเหลี่ยม
```
## ขั้นตอนที่ 7: พิมพ์จุดแตกต่าง
พิมพ์จุดของรูปหลายเหลี่ยมส่วนต่าง
```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```
## ขั้นตอนที่ 8: ดำเนินการผลต่างสมมาตร
สุดท้ายนี้ เรามาดูความแตกต่างแบบสมมาตรระหว่างรูปหลายเหลี่ยมสองรูปนี้กัน
```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // มัลติโพลิกอน
```
## ขั้นตอนที่ 9: พิมพ์รูปหลายเหลี่ยมส่วนต่างสมมาตร
พิมพ์จุดของแต่ละรูปหลายเหลี่ยมด้วยผลต่างสมมาตร
```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```
## บทสรุป
การเรียนรู้การซ้อนทับเรขาคณิตเป็นสิ่งสำคัญในการวิเคราะห์เชิงพื้นที่ และ Aspose.GIS สำหรับ .NET มอบชุดเครื่องมือที่ครอบคลุมเพื่อดำเนินการเหล่านี้อย่างมีประสิทธิภาพ เมื่อทำตามบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีใช้ Aspose.GIS สำหรับ .NET เพื่อดำเนินการตัดกัน การรวม ผลต่าง และผลต่างสมมาตรบนรูปทรงเรขาคณิต
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.GIS สำหรับ .NET ในโครงการเชิงพาณิชย์ของฉันได้หรือไม่
ใช่ Aspose.GIS สำหรับ .NET สามารถใช้ได้ทั้งในโครงการเชิงพาณิชย์และไม่ใช่เชิงพาณิชย์
### ถาม: Aspose.GIS สำหรับ .NET มีเวอร์ชันทดลองใช้งานหรือไม่
 ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะรับการสนับสนุน Aspose.GIS สำหรับ .NET ได้อย่างไร
 คุณสามารถรับการสนับสนุนจากฟอรัมชุมชน Aspose.GIS[ที่นี่](https://forum.aspose.com/c/gis/33).
### ถาม: มีใบอนุญาตชั่วคราวสำหรับ Aspose.GIS สำหรับ .NET หรือไม่
 ใช่ ใบอนุญาตชั่วคราวมีไว้เพื่อการทดสอบและประเมินผล คุณสามารถรับได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: ฉันสามารถซื้อ Aspose.GIS สำหรับ .NET ได้โดยตรงหรือไม่
 ใช่ คุณสามารถซื้อ Aspose.GIS สำหรับ .NET ได้จากเว็บไซต์[ที่นี่](https://purchase.aspose.com/buy).