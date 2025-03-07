---
title: จำกัดเรขาคณิตการอ่านที่แม่นยำด้วย Aspose.GIS สำหรับ .NET
linktitle: จำกัดเรขาคณิตการอ่านที่แม่นยำ
second_title: Aspose.GIS .NET API
description: เรียนรู้วิธีจัดการความแม่นยำอย่างมีประสิทธิภาพเมื่ออ่านรูปทรงเรขาคณิตโดยใช้ Aspose.GIS สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการจัดการข้อมูลที่เหมาะสมที่สุด
weight: 12
url: /th/net/geometry-processing/limit-precision-reading-geometries/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# จำกัดเรขาคณิตการอ่านที่แม่นยำด้วย Aspose.GIS สำหรับ .NET

## การแนะนำ
ในขอบเขตของการจัดการข้อมูลเชิงพื้นที่ Aspose.GIS สำหรับ .NET ถือเป็นเครื่องมืออันทรงพลังที่นำเสนอฟังก์ชันการทำงานมากมายให้กับนักพัฒนาและวิศวกร ความสามารถอย่างหนึ่งคือความสามารถในการจำกัดความแม่นยำเมื่ออ่านรูปทรง ซึ่งเป็นส่วนสำคัญในการใช้งานบางอย่างที่ความแม่นยำอาจไม่ได้เป็นสิ่งสำคัญยิ่ง ในบทช่วยสอนนี้ เราจะเจาะลึกถึงวิธีการบรรลุเป้าหมายนี้โดยใช้ Aspose.GIS สำหรับ .NET โดยแจกแจงกระบวนการออกเป็นขั้นตอนที่สามารถจัดการได้
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้นการเดินทางนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  การติดตั้ง: ควรติดตั้งไลบรารี Aspose.GIS สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ ถ้าไม่เช่นนั้นคุณสามารถดาวน์โหลดได้จาก[หน้าเผยแพร่](https://releases.aspose.com/gis/net/).
2. ความคุ้นเคยกับ .NET: ความรู้พื้นฐานเกี่ยวกับ C# และกรอบงาน .NET เป็นสิ่งจำเป็นในการทำความเข้าใจและนำตัวอย่างโค้ดที่ให้มาไปใช้
3. สภาพแวดล้อมการพัฒนา: จำเป็นต้องมีสภาพแวดล้อมการพัฒนา .NET เช่น Visual Studio
4. ไดเร็กทอรีเอกสาร: ตั้งค่าไดเร็กทอรีที่คุณสามารถจัดเก็บและเข้าถึงเชปไฟล์ที่สร้างขึ้นระหว่างกระบวนการได้

## นำเข้าเนมสเปซ
ก่อนที่เราจะเริ่มใช้งานฟังก์ชันเพื่อจำกัดความแม่นยำเมื่ออ่านรูปทรงเรขาคณิต เราต้องแน่ใจว่าเรานำเข้าเนมสเปซที่จำเป็นก่อน:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: การสร้างเลเยอร์เวกเตอร์
ขั้นแรก เราต้องสร้างเลเยอร์เวกเตอร์ที่เราสามารถเพิ่มรูปทรงเรขาคณิตได้ สามารถทำได้โดยใช้ข้อมูลโค้ดต่อไปนี้:
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```
## ขั้นตอนที่ 2: การตั้งค่าตัวเลือกความแม่นยำ
ต่อไป เราต้องกำหนดตัวเลือกสำหรับการอ่านรูปทรงเรขาคณิต โดยระบุแบบจำลองความแม่นยำที่ต้องการ เราสามารถทำได้ดังนี้:
```csharp
var options = new ShapefileOptions();
// อ่านข้อมูลตามที่เป็น
options.XYPrecisionModel = PrecisionModel.Exact;
```
## ขั้นตอนที่ 3: การอ่านรูปทรงเรขาคณิตด้วยความแม่นยำที่แน่นอน
ตอนนี้ เรามาเปิดเลเยอร์เวกเตอร์ด้วยตัวเลือกที่ระบุเพื่ออ่านรูปทรงเรขาคณิตที่มีความแม่นยำแน่นอน:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```
## ขั้นตอนที่ 4: การตัดทอนความแม่นยำ
สุดท้ายนี้ หากเราต้องการตัดทอนความแม่นยำให้เหลือตำแหน่งทศนิยมตามที่กำหนด เราสามารถปรับโมเดลความแม่นยำได้ตามนั้น:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## บทสรุป
โดยสรุป การจัดการความแม่นยำเมื่ออ่านรูปทรงเรขาคณิตเป็นส่วนสำคัญของการจัดการข้อมูลเชิงพื้นที่ Aspose.GIS สำหรับ .NET มีฟังก์ชันการทำงานที่มีประสิทธิภาพเพื่อให้บรรลุเป้าหมายนี้ได้อย่างมีประสิทธิภาพ ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถจำกัดความแม่นยำได้อย่างราบรื่นตามความต้องการของคุณ ทำให้มั่นใจได้ถึงการจัดการข้อมูลที่เหมาะสมที่สุดในแอปพลิเคชันของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.GIS สำหรับ .NET กับเฟรมเวิร์ก .NET อื่นๆ เช่น .NET Core หรือ .NET Standard ได้หรือไม่
ใช่ Aspose.GIS สำหรับ .NET เข้ากันได้กับเฟรมเวิร์ก .NET ต่างๆ รวมถึง .NET Core และ .NET Standard
### มีรุ่นทดลองใช้สำหรับ Aspose.GIS สำหรับ .NET หรือไม่
 ใช่ คุณสามารถขอรับเวอร์ชันทดลองใช้ฟรีได้จาก[หน้าเผยแพร่](https://releases.aspose.com/).
### ฉันจะหาเอกสารที่ครอบคลุมสำหรับ Aspose.GIS สำหรับ .NET ได้ที่ไหน
 คุณสามารถอ้างถึง[เอกสารประกอบ](https://reference.aspose.com/gis/net/) สำหรับข้อมูลโดยละเอียดและตัวอย่าง
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS สำหรับ .NET ได้อย่างไร
 ใบอนุญาตชั่วคราวสามารถรับได้จาก[หน้าซื้อ](https://purchase.aspose.com/temporary-license/) สำหรับ Aspose.GIS
### ฉันจะขอความช่วยเหลือหรือสนับสนุน Aspose.GIS สำหรับ .NET ได้ที่ไหน
 คุณสามารถเยี่ยมชม Aspose.GIS[ฟอรั่ม](https://forum.aspose.com/c/gis/33) สำหรับข้อสงสัย การสนทนา หรือความต้องการการสนับสนุน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
