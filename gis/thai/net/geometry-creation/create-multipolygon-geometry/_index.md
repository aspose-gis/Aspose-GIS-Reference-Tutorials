---
title: สร้างเรขาคณิตหลายเหลี่ยมด้วย Aspose.GIS
linktitle: สร้างเรขาคณิตหลายรูปหลายเหลี่ยม
second_title: Aspose.GIS .NET API
description: เรียนรู้วิธีสร้างเรขาคณิต MultiPolygon โดยใช้ Aspose.GIS สำหรับ .NET คำแนะนำทีละขั้นตอนสำหรับผู้เริ่มต้น ทดลองใช้ฟรีได้
weight: 16
url: /th/net/geometry-creation/create-multipolygon-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเรขาคณิตหลายเหลี่ยมด้วย Aspose.GIS

## การแนะนำ
ในโลกของการพัฒนาระบบสารสนเทศภูมิศาสตร์ (GIS) Aspose.GIS สำหรับ .NET มีความโดดเด่นในฐานะเครื่องมืออันทรงพลังสำหรับการสร้าง แก้ไข และวิเคราะห์ข้อมูลเชิงพื้นที่ ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น การเรียนรู้ Aspose.GIS อย่างดีสามารถเปิดโลกแห่งความเป็นไปได้สำหรับโครงการของคุณได้
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มใช้ Aspose.GIS สำหรับ .NET มีข้อกำหนดเบื้องต้นบางประการที่คุณจำเป็นต้องมี:
### การติดตั้ง Aspose.GIS สำหรับ .NET
1.  ดาวน์โหลด Aspose.GIS: ตรงไปที่[หน้าดาวน์โหลด](https://releases.aspose.com/gis/net/)และเลือกเวอร์ชันที่เหมาะสมสำหรับสภาพแวดล้อมการพัฒนาของคุณ
2. ติดตั้ง Aspose.GIS: ทำตามคำแนะนำการติดตั้งที่ให้ไว้ในเอกสารประกอบเพื่อติดตั้ง Aspose.GIS สำหรับ .NET บนเครื่องของคุณ

## การนำเข้าเนมสเปซ
หากต้องการเริ่มทำงานกับ Aspose.GIS ในโปรเจ็กต์ .NET คุณจะต้องนำเข้าเนมสเปซที่จำเป็น:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: สร้างวงแหวนเชิงเส้น
ขั้นแรก เราต้องสร้าง LinearRings สำหรับแต่ละรูปหลายเหลี่ยม LinearRing แต่ละอันแสดงถึงสตริงเส้นปิดที่สร้างขอบเขตของรูปหลายเหลี่ยม
```csharp
LinearRing firstRing = new LinearRing();
firstRing.AddPoint(8.5, -2.5);
firstRing.AddPoint(-8.5, 2.5);
firstRing.AddPoint(8.5, -2.5);
LinearRing secondRing = new LinearRing();
secondRing.AddPoint(7.6, -3.6);
secondRing.AddPoint(-9.6, 1.5);
secondRing.AddPoint(7.6, -3.6);
```
## ขั้นตอนที่ 2: สร้างรูปหลายเหลี่ยม
ต่อไป เราจะสร้างวัตถุรูปหลายเหลี่ยมโดยใช้ LinearRings ที่เรากำหนดไว้
```csharp
Polygon firstPolygon = new Polygon(firstRing);
Polygon secondPolygon = new Polygon(secondRing);
```
## ขั้นตอนที่ 3: สร้าง MultiPolygon
ตอนนี้ เรามารวมรูปหลายเหลี่ยมเหล่านี้ให้เป็นเรขาคณิตหลายรูปหลายเหลี่ยมกัน
```csharp
MultiPolygon multiPolygon = new MultiPolygon();
multiPolygon.Add(firstPolygon);
multiPolygon.Add(secondPolygon);
```
ยินดีด้วย! คุณสร้างเรขาคณิต MultiPolygon โดยใช้ Aspose.GIS สำหรับ .NET สำเร็จแล้ว

## บทสรุป
การเรียนรู้ Aspose.GIS สำหรับ .NET เปิดโลกแห่งความเป็นไปได้สำหรับนักพัฒนาที่ทำงานกับข้อมูลภูมิสารสนเทศ ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะได้เรียนรู้วิธีสร้างเรขาคณิตหลายเหลี่ยม ซึ่งเป็นการวางรากฐานสำหรับแอปพลิเคชัน GIS ที่ซับซ้อนยิ่งขึ้น
## คำถามที่พบบ่อย
### Aspose.GIS สำหรับ .NET เหมาะสำหรับผู้เริ่มต้นหรือไม่
อย่างแน่นอน! Aspose.GIS นำเสนอเอกสารและบทช่วยสอนที่ครอบคลุมเพื่อช่วยให้นักพัฒนาทุกระดับทักษะเริ่มต้นได้
### ฉันสามารถลองใช้ Aspose.GIS ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/) เพื่อสำรวจคุณสมบัติต่างๆ ก่อนตัดสินใจซื้อ
### ฉันจะรับการสนับสนุนสำหรับ Aspose.GIS ได้ที่ไหน
 คุณสามารถเยี่ยมชมฟอรัม Aspose.GIS[ที่นี่](https://forum.aspose.com/c/gis/33) เพื่อสอบถามและรับความช่วยเหลือจากชุมชน
### มีใบอนุญาตชั่วคราวสำหรับ Aspose.GIS หรือไม่
 ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการประเมินผล
### ฉันสามารถซื้อ Aspose.GIS ได้โดยตรงหรือไม่
 ใช่ คุณสามารถซื้อ Aspose.GIS ได้จากเว็บไซต์[ที่นี่](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
