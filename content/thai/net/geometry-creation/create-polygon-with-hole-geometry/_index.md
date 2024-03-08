---
title: สร้างรูปหลายเหลี่ยมด้วย Hole Geometry โดยใช้ Aspose.GIS
linktitle: สร้างรูปหลายเหลี่ยมด้วย Hole Geometry
second_title: Aspose.GIS .NET API
description: เรียนรู้วิธีสร้างรูปหลายเหลี่ยมด้วยรูปทรงของรูโดยใช้ Aspose.GIS สำหรับ .NET บทช่วยสอนทีละขั้นตอนพร้อมตัวอย่างโค้ด
type: docs
weight: 13
url: /th/net/geometry-creation/create-polygon-with-hole-geometry/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนการสร้างรูปหลายเหลี่ยมด้วยเรขาคณิตของรูโดยใช้ Aspose.GIS สำหรับ .NET Aspose.GIS เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับข้อมูลเชิงพื้นที่ในแอปพลิเคชัน .NET ของตนได้ 
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Aspose.GIS สำหรับ .NET Library: คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/gis/net/).
2. สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณมีสภาพแวดล้อมการพัฒนาที่ตั้งค่าด้วย Visual Studio หรือติดตั้ง .NET IDE อื่น ๆ
## นำเข้าเนมสเปซ
ขั้นแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับฟังก์ชัน Aspose.GIS ต่อไปนี้เป็นวิธีดำเนินการ:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

ตอนนี้ เรามาสร้างรูปหลายเหลี่ยมที่มีรูปทรงของรูโดยใช้ Aspose.GIS สำหรับ .NET กันดีกว่า
## ขั้นตอนที่ 1: สร้างวัตถุรูปหลายเหลี่ยม
```csharp
Polygon polygon = new Polygon();
```
## ขั้นตอนที่ 2: กำหนดวงแหวนภายนอก
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## ขั้นตอนที่ 3: กำหนดวงแหวนภายใน (รู)
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## ขั้นตอนที่ 4: กำหนดวงแหวนภายนอกและเพิ่มวงแหวนภายในให้กับรูปหลายเหลี่ยม
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีสร้างรูปหลายเหลี่ยมด้วยเรขาคณิตของรูโดยใช้ Aspose.GIS สำหรับ .NET เรียบร้อยแล้ว ความรู้นี้จะเป็นประโยชน์สำหรับการใช้งานเชิงพื้นที่ต่างๆ ที่เรขาคณิตดังกล่าวมีความจำเป็น
## คำถามที่พบบ่อย
### 1. Aspose.GIS คืออะไร
Aspose.GIS เป็นไลบรารี .NET ที่ช่วยให้นักพัฒนาสามารถทำงานกับข้อมูลเชิงพื้นที่ ช่วยให้พวกเขาสามารถสร้าง อ่าน และจัดการรูปแบบไฟล์เชิงพื้นที่ต่างๆ ได้
### 2. ฉันสามารถใช้ Aspose.GIS สำหรับโครงการเชิงพาณิชย์ได้หรือไม่
 ได้ คุณสามารถใช้ Aspose.GIS สำหรับทั้งโครงการส่วนบุคคลและเชิงพาณิชย์โดยการซื้อใบอนุญาต เยี่ยม[ที่นี่](https://purchase.aspose.com/buy) สำหรับรายละเอียดเพิ่มเติม
### 3. Aspose.GIS มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถทดลองใช้ Aspose.GIS ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### 4. ฉันจะรับการสนับสนุนสำหรับ Aspose.GIS ได้ที่ไหน
 คุณสามารถค้นหาการสนับสนุนสำหรับ Aspose.GIS ได้ที่[ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33).
### 5. ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS ได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).