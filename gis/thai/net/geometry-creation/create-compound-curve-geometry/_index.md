---
title: สร้างเรขาคณิตเส้นโค้งผสมด้วย Aspose.GIS ใน .NET
linktitle: สร้างเรขาคณิตเส้นโค้งผสม
second_title: Aspose.GIS .NET API
description: เรียนรู้วิธีสร้างเรขาคณิตเส้นโค้งผสมใน .NET โดยใช้ Aspose.GIS เพื่อการประมวลผลข้อมูลภูมิสารสนเทศที่ราบรื่น
weight: 19
url: /th/net/geometry-creation/create-compound-curve-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเรขาคณิตเส้นโค้งผสมด้วย Aspose.GIS ใน .NET

## การแนะนำ
ในโลกของการพัฒนา .NET นั้น Aspose.GIS เป็นเครื่องมืออันทรงพลังที่มีฟังก์ชันการทำงานมากมายสำหรับการทำงานกับข้อมูลเชิงพื้นที่ ไม่ว่าคุณกำลังพัฒนาแอปพลิเคชันสำหรับการทำแผนที่ บริการตามตำแหน่ง หรือการวิเคราะห์ทางภูมิศาสตร์ Aspose.GIS มีเครื่องมือที่จำเป็นในการปรับปรุงกระบวนการพัฒนาของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
### ติดตั้ง Visual Studio แล้ว
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio บนระบบของคุณ คุณสามารถดาวน์โหลดและติดตั้งได้จากเว็บไซต์ Visual Studio
### ติดตั้ง Aspose.GIS สำหรับ .NET แล้ว
 ดาวน์โหลดและติดตั้ง Aspose.GIS สำหรับ .NET จาก[หน้าดาวน์โหลด](https://releases.aspose.com/gis/net/). ทำตามคำแนะนำการติดตั้งที่ให้มาเพื่อตั้งค่า Aspose.GIS ในสภาพแวดล้อมการพัฒนาของคุณ

## นำเข้าเนมสเปซ
หากต้องการเริ่มทำงานกับ Aspose.GIS ในโปรเจ็กต์ .NET คุณต้องนำเข้าเนมสเปซที่จำเป็น ต่อไปนี้คือวิธีที่คุณสามารถทำได้:
## ขั้นตอนที่ 1: เปิดโครงการ Visual Studio ของคุณ
เปิด Visual Studio และเปิดโครงการ .NET ของคุณที่คุณต้องการใช้ Aspose.GIS
## ขั้นตอนที่ 2: เพิ่มการอ้างอิงเนมสเปซ
เพิ่มเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์โค้ดของคุณ:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## สร้างเรขาคณิตเส้นโค้งผสม
ตอนนี้ เรามาเจาะลึกการสร้างเรขาคณิตเส้นโค้งผสมโดยใช้ Aspose.GIS สำหรับ .NET กันดีกว่า ตัวอย่างนี้สาธิตวิธีการสร้างเส้นโค้งผสม ซึ่งประกอบด้วยเส้นโค้งหลายเส้นที่เชื่อมต่อกันจนกลายเป็นรูปร่างที่ซับซ้อน
### ขั้นตอนที่ 1: กำหนดเส้นทางเอาต์พุต
```csharp
string path = "Your Document Directory" + "CreateCompoundCurve_out.shp";
```
 แทนที่`"Your Document Directory"` ด้วยเส้นทางที่คุณต้องการบันทึก Shapefile เอาต์พุต
### ขั้นตอนที่ 2: สร้างเลเยอร์เวกเตอร์
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // บล็อกโค้ดสำหรับสร้างเรขาคณิตเส้นโค้งผสมจะถูกแทรกที่นี่
}
```
ข้อมูลโค้ดนี้เริ่มต้น VectorLayer ใหม่สำหรับจัดเก็บเรขาคณิตของเส้นโค้งผสมในรูปแบบ Shapefile
### ขั้นตอนที่ 3: สร้างเส้นโค้งผสม
```csharp
var feature = layer.ConstructFeature();
var compoundCurve = new CompoundCurve();
```
ที่นี่ เราเริ่มต้นคุณลักษณะใหม่และเรขาคณิตเส้นโค้งผสม
### ขั้นตอนที่ 4: กำหนดเส้นโค้งส่วนประกอบ
```csharp
var bottom = (ILineString)Geometry.FromText("LineString (0 0, 3 0)");
var firstArc = (ICircularString)Geometry.FromText("CircularString (3 0, 4 1, 3 2)");
var middle = (ILineString)Geometry.FromText("LineString (3 2, 1 2)");
var secondArc = (ICircularString)Geometry.FromText("CircularString (1 2, 0 3, 1 4)");
var top = (ILineString)Geometry.FromText("LineString (1 4, 4 4)");
```
กำหนดเส้นโค้งส่วนประกอบที่จะสร้างเส้นโค้งผสม ซึ่งรวมถึงสตริงเส้นและสตริงวงกลม
### ขั้นตอนที่ 5: เพิ่มเส้นโค้งส่วนประกอบให้กับเส้นโค้งผสม
```csharp
compoundCurve.AddCurve(bottom);
compoundCurve.AddCurve(firstArc);
compoundCurve.AddCurve(middle);
compoundCurve.AddCurve(secondArc);
compoundCurve.AddCurve(top);
```
เพิ่มเส้นโค้งส่วนประกอบที่กำหนดไว้ให้กับเรขาคณิตของเส้นโค้งผสม
### ขั้นตอนที่ 6: ตั้งค่าเรขาคณิตสำหรับคุณสมบัติ
```csharp
feature.Geometry = compoundCurve;
```
กำหนดเรขาคณิตของเส้นโค้งประสมให้กับจุดสนใจ
### ขั้นตอนที่ 7: เพิ่มคุณสมบัติให้กับเลเยอร์
```csharp
layer.Add(feature);
```
เพิ่มคุณลักษณะด้วยเรขาคณิตเส้นโค้งผสมลงในเลเยอร์เวกเตอร์

## บทสรุป
ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีสร้างเรขาคณิตเส้นโค้งผสมโดยใช้ Aspose.GIS สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณสามารถรวมรูปทรงเรขาคณิตที่ซับซ้อนเข้ากับแอปพลิเคชัน .NET ของคุณสำหรับการประมวลผลข้อมูลเชิงพื้นที่ได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.GIS สำหรับ .NET กับเฟรมเวิร์ก .NET อื่นๆ ได้หรือไม่
ใช่ Aspose.GIS สำหรับ .NET เข้ากันได้กับเฟรมเวิร์ก .NET ต่างๆ รวมถึง .NET Framework, .NET Core และ .NET Standard
### Aspose.GIS รองรับการอ่านและการเขียนไฟล์ภูมิสารสนเทศในรูปแบบต่างๆ หรือไม่
อย่างแน่นอน! Aspose.GIS ให้การสนับสนุนอย่างกว้างขวางสำหรับการอ่านและการเขียนรูปแบบไฟล์ภูมิสารสนเทศยอดนิยม เช่น Shapefile, GeoJSON, KML และอื่นๆ
### Aspose.GIS เหมาะสำหรับทั้งเดสก์ท็อปและเว็บแอปพลิเคชันหรือไม่
ใช่ Aspose.GIS สามารถใช้ได้ทั้งบนเดสก์ท็อปและแอปพลิเคชันบนเว็บ โดยนำเสนอความคล่องตัวในการพัฒนาภูมิสารสนเทศ
### ฉันสามารถทำการวิเคราะห์เชิงพื้นที่ด้วย Aspose.GIS สำหรับ .NET ได้หรือไม่
ใช่ Aspose.GIS มีฟังก์ชันการวิเคราะห์เชิงพื้นที่ที่หลากหลาย รวมถึงการคำนวณระยะทาง การดำเนินการทางเรขาคณิต และการสืบค้นเชิงพื้นที่
### มีฟอรัมชุมชนหรือช่องทางการสนับสนุนสำหรับผู้ใช้ Aspose.GIS หรือไม่
 ใช่คุณสามารถเยี่ยมชม[ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33) เพื่อถามคำถาม แบ่งปันความคิด และขอความช่วยเหลือจากชุมชนและทีมสนับสนุน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
