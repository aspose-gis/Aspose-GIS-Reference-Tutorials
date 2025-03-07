---
title: คำนวณ Convex Hull ด้วย Aspose.GIS สำหรับ .NET
linktitle: รับตัวเรือเรขาคณิตนูน
second_title: Aspose.GIS .NET API
description: เรียนรู้วิธีการคำนวณส่วนนูนของเรขาคณิตใน .NET โดยใช้ Aspose.GIS บทช่วยสอนที่ครอบคลุมพร้อมตัวอย่างโค้ดและคำถามที่พบบ่อย
weight: 20
url: /th/net/geometry-analysis/get-geometry-convex-hull/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# คำนวณ Convex Hull ด้วย Aspose.GIS สำหรับ .NET

## การแนะนำ
Aspose.GIS สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งมีฟังก์ชันการทำงานที่หลากหลายสำหรับการทำงานกับระบบสารสนเทศภูมิศาสตร์ (GIS) ในแอปพลิเคชัน .NET ไม่ว่าคุณจะสร้างแอปพลิเคชันการทำแผนที่ วิเคราะห์ข้อมูลเชิงพื้นที่ หรือดำเนินการเชิงพื้นที่ Aspose.GIS จะทำให้กระบวนการง่ายขึ้นด้วย API ที่ใช้งานง่ายและชุดคุณลักษณะที่ครอบคลุม
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเจาะลึกบทช่วยสอนเกี่ยวกับวิธีสร้างส่วนนูนของเรขาคณิตโดยใช้ Aspose.GIS สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### 1. ติดตั้ง Aspose.GIS สำหรับ .NET
 เยี่ยมชม[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/gis/net/) เพื่อรับ Aspose.GIS เวอร์ชันล่าสุดสำหรับ .NET ปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้ในเอกสารประกอบเพื่อการผสานรวมเข้ากับสภาพแวดล้อม .NET ของคุณได้อย่างราบรื่น
### 2. ความคุ้นเคยกับการพัฒนา .NET
จำเป็นต้องมีความรู้พื้นฐานเกี่ยวกับการพัฒนา C# และ .NET พร้อมด้วยตัวอย่างในบทช่วยสอนนี้ หากคุณยังใหม่กับ .NET ให้พิจารณาสำรวจแหล่งข้อมูลเบื้องต้นเพื่อเริ่มต้นใช้งาน
### 3. ตั้งค่าสภาพแวดล้อมการพัฒนา
ตรวจสอบให้แน่ใจว่าคุณได้กำหนดค่าสภาพแวดล้อมการพัฒนาที่เหมาะสม รวมถึง Visual Studio หรือ IDE ที่ต้องการสำหรับการพัฒนา .NET

## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ให้เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานที่ Aspose.GIS มอบให้

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
เนมสเปซนี้ให้การเข้าถึงฟังก์ชันหลักของ Aspose.GIS สำหรับ .NET รวมถึงคลาสและวิธีการทำงานกับข้อมูลทางภูมิศาสตร์

เนมสเปซของระบบเป็นสิ่งจำเป็นสำหรับการดำเนินการอินพุต/เอาท์พุตพื้นฐานและฟังก์ชันหลักอื่นๆ ของเฟรมเวิร์ก .NET

ตอนนี้ เรามาดำดิ่งลงสู่กระบวนการทีละขั้นตอนในการรับส่วนนูนของเรขาคณิตโดยใช้ Aspose.GIS สำหรับ .NET
## ขั้นตอนที่ 1: สร้างเรขาคณิตหลายจุด
ขั้นแรก ให้กำหนดเรขาคณิตหลายจุดที่มีหลายจุด จุดเหล่านี้จะเป็นพื้นฐานในการคำนวณตัวถังนูน
```csharp
var geometry = new MultiPoint
{
    new Point(3, 2),
    new Point(0, 0),
    new Point(6, 5),
    new Point(5, 10),
    new Point(10, 0),
    new Point(8, 2),
    new Point(4, 3),
};
```
ข้อมูลโค้ดนี้สร้างเรขาคณิตแบบหลายจุดโดยมีจุดที่แตกต่างกันเจ็ดจุด
## ขั้นตอนที่ 2: รับ Convex Hull
 ต่อไปให้เรียกใช้`GetConvexHull()` วิธีการบนวัตถุเรขาคณิตเพื่อคำนวณตัวถังนูน
```csharp
var convexHull = geometry.GetConvexHull();
```
วิธีนี้จะคำนวณส่วนนูนของรูปทรงอินพุต ซึ่งส่งผลให้ได้รูปทรงใหม่ที่แสดงถึงส่วนนูนของรูปทรง
## ขั้นตอนที่ 3: เข้าถึงจุดตัวถังนูน
เมื่อคำนวณตัวเรือนูนแล้ว คุณจะสามารถเข้าถึงจุดที่เป็นส่วนประกอบได้
```csharp
var ring = (ILinearRing)convexHull;
for (int i = 0; i < ring.Count; ++i)
{
    Console.WriteLine("[{0}] = ({1} {2})", i, ring[i].X, ring[i].Y);
}
```
การวนซ้ำนี้จะวนซ้ำผ่านจุดของตัวถังนูนและพิมพ์พิกัดไปยังคอนโซล

## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีใช้ Aspose.GIS สำหรับ .NET เพื่อให้ได้ส่วนนูนของเรขาคณิต ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณสามารถรวมฟังก์ชันเชิงพื้นที่เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น ทำให้สามารถจัดการและวิเคราะห์ข้อมูลทางภูมิศาสตร์ได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ถาม: Aspose.GIS สำหรับ .NET เหมาะสำหรับทั้งเดสก์ท็อปและเว็บแอปพลิเคชันหรือไม่
ใช่ Aspose.GIS สำหรับ .NET สามารถใช้ได้ทั้งบนเดสก์ท็อปและเว็บแอปพลิเคชัน ซึ่งให้ความคล่องตัวในการประมวลผลข้อมูลทางภูมิศาสตร์
### ถาม: Aspose.GIS รองรับรูปแบบภูมิสารสนเทศที่หลากหลายหรือไม่
แน่นอนว่า Aspose.GIS รองรับรูปแบบภูมิสารสนเทศที่หลากหลาย รวมถึงเชปไฟล์, GeoJSON, KML และอื่นๆ อีกมากมาย ช่วยให้สามารถทำงานร่วมกันได้อย่างราบรื่นกับแหล่งข้อมูลที่หลากหลาย
### ถาม: ฉันสามารถลองใช้ Aspose.GIS สำหรับ .NET ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถทดลองใช้ Aspose.GIS สำหรับ .NET ได้ฟรีจากโปรแกรมที่ให้มา[ลิงค์](https://releases.aspose.com/)ช่วยให้คุณสามารถสำรวจคุณลักษณะต่างๆ และประเมินความเหมาะสมกับโครงการของคุณได้
### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS ได้อย่างไร
 สามารถรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS ผ่านทางที่กำหนด[ลิงค์ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/)ช่วยให้ใช้งานได้ไม่สะดุดในช่วงทดลองใช้งานหรือโครงการระยะสั้น
### ถาม: ฉันจะขอความช่วยเหลือหรือมีส่วนร่วมในการสนทนาที่เกี่ยวข้องกับ Aspose.GIS ได้ที่ไหน
สำหรับการสนับสนุน คำแนะนำ และการโต้ตอบกับชุมชน โปรดไปที่ฟอรัม Aspose.GIS[ที่นี่](https://forum.aspose.com/c/gis/33)ซึ่งคุณสามารถมีส่วนร่วมกับเพื่อนนักพัฒนา ถามคำถาม และแบ่งปันข้อมูลเชิงลึก
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
