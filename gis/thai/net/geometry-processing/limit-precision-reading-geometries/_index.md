---
date: 2026-09-10
description: เรียนรู้วิธีสร้าง vector layer ด้วย Aspose.GIS for .NET และจำกัด precision
  เพื่อลดขนาด shapefile, เพิ่ม performance, และรักษา coordinate accuracy
keywords:
- how to create vector layer
- limit precision reading geometries
- reduce shapefile size
lastmod: 2026-09-10
linktitle: จำกัด Precision การอ่าน Geometries
og_description: เรียนรู้วิธีสร้าง vector layer ด้วย Aspose.GIS for .NET และจำกัด precision
  เพื่อลดขนาด shapefile, ปรับปรุง performance, และจัดการ coordinate accuracy
og_image_alt: Screenshot showing Aspose.GIS code for creating a vector layer and setting
  precision
og_title: วิธีสร้าง vector layer ด้วย Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  headline: How to create vector layer with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  name: How to create vector layer with Aspose.GIS for .NET
  steps:
  - name: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
    text: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
  - name: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
    text: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
  - name: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
    text: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
  - name: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
    text: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
  type: HowTo
- questions:
  - answer: No. Precision is applied only when reading the geometry; the source file
      remains unchanged.
    question: Does limiting precision affect the original shapefile?
  - answer: Aspose.GIS currently applies the same `XYPrecisionModel` to both axes.
    question: Can I use a different precision model for X and Y coordinates?
  - answer: The API supports only the built‑in `PrecisionModel.Rounding(int)` method.
      For custom logic, you would need to post‑process the coordinates after reading.
    question: Is it possible to set a custom rounding function?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- Aspose.GIS
- vector layer
- precision model
- .NET GIS
title: วิธีสร้าง vector layer ด้วย Aspose.GIS for .NET
url: /th/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างเลเยอร์เวกเตอร์ด้วย Aspose.GIS สำหรับ .NET

## บทนำ
เมื่อคุณทำงานกับข้อมูลเชิงพื้นที่ คุณมักสงสัย **วิธีสร้างเลเยอร์เวกเตอร์** ที่ตรงกับความแม่นยำที่แอปพลิเคชันของคุณต้องการจริง ๆ การปัดเศษพิกัดให้เป็นจำนวนทศนิยมที่เหมาะสมไม่เพียงทำให้การแยกวิเคราะห์เร็วขึ้น แต่ยังสามารถ **ลดขนาด shapefile ได้ถึง 30 %** สำหรับชุดข้อมูลจุดทั่วไป ในคู่มือขั้นตอนนี้คุณจะได้เห็นวิธีสร้างเลเยอร์เวกเตอร์ เขียนเรขาคณิตจุด แล้วอ่านกลับโดยใช้โมเดลความแม่นยำที่แม่นยำและที่ปัดเศษกัน ในตอนท้ายคุณจะรู้วิธี **ตั้งค่าโมเดลความแม่นยำ** ที่สมดุลระหว่างประสิทธิภาพกับความแม่นยำเชิงพื้นที่ที่ต้องการ

## คำตอบอย่างรวดเร็ว
- **คำว่า “limit precision” หมายถึงอะไร?** มันทำการปัดเศษค่าพิกัดให้เป็นจำนวนทศนิยมที่กำหนด  
- **ทำไมต้องสร้างเลเยอร์เวกเตอร์ก่อน?** เลเยอร์เวกเตอร์เป็นคอนเทนเนอร์ที่เก็บเรขาคณิตเช่น จุด เส้น และโพลิกอน  
- **โมเดลความแม่นยำใดบ้างที่มี?** `PrecisionModel.Exact` (ไม่มีการปัดเศษ) และ `PrecisionModel.Rounding(n)` (ปัดเศษเป็นทศนิยม *n* จำนวน)  
- **ฉันต้องมีไลเซนส์เพื่อทดลองใช้นี้หรือไม่?** มีรุ่นทดลองฟรีจากหน้า releases  
- **เวอร์ชัน .NET ใดที่รองรับ?** .NET Framework 4.5+, .NET Core, และ .NET 5/6+

## การสร้างเลเยอร์เวกเตอร์คืออะไร?
การ **สร้างเลเยอร์เวกเตอร์** หมายถึงการสร้างอินสแตนซ์ของคลาส `VectorLayer` ของ Aspose.GIS ซึ่งแทน shapefile เดียวบนดิสก์และเก็บคุณลักษณะเรขาคณิตทั้งหมดที่คุณเพิ่ม เลเยอร์นี้เป็นจุดเริ่มต้นสำหรับการอ่าน เขียน และจัดการข้อมูลเชิงพื้นที่ นอกจากนี้ยังให้คุณกำหนดฟิลด์แอตทริบิวต์และตั้งค่าการอ้างอิงเชิงพื้นที่สำหรับชุดข้อมูล

## ทำไมต้องจำกัดความแม่นยำและมันช่วยอย่างไร?
- **เพิ่มประสิทธิภาพ** – การลดจำนวนทศนิยมจะลดปริมาณข้อมูลไบนารีที่ต้องแยกวิเคราะห์และทำซีเรียลไลซ์ ซึ่งมักให้ความเร็วเพิ่มขึ้น 15‑20 % สำหรับไฟล์ขนาดใหญ่  
- **ไฟล์ขนาดเล็กลง** – การปัดเศษพิกัดเป็นสองหรือสามทศนิยมสามารถทำให้ shapefile ขนาด 10 MB ลดลงเหลือประมาณ 7 MB ช่วยลดการจัดเก็บและการถ่ายโอนผ่านเครือข่าย  
- **ความแม่นยำเพียงพอ** – การวิเคราะห์ GIS ส่วนใหญ่ (เช่น การทำแผนที่ระดับเมือง) ต้องการความแม่นยำระดับเมตรเท่านั้น ทำให้การปัดเศษ 3 ทศนิยมเพียงพออย่างมาก

## ข้อกำหนดเบื้องต้น
1. **การติดตั้ง** – ไลบรารี Aspose.GIS สำหรับ .NET ควรติดตั้งในสภาพแวดล้อมการพัฒนาของคุณ หากยังไม่ได้ติดตั้ง คุณสามารถดาวน์โหลดได้จาก [releases page](https://releases.aspose.com/gis/net/).  
2. **ความคุ้นเคยกับ .NET** – ความรู้พื้นฐานของ C# และเฟรมเวิร์ก .NET จำเป็นสำหรับการเข้าใจและใช้งานตัวอย่างโค้ดที่ให้มา  
3. **สภาพแวดล้อมการพัฒนา** – จำเป็นต้องมีสภาพแวดล้อมการพัฒนา .NET ที่ทำงานได้ เช่น Visual Studio  
4. **ไดเรกทอรีเอกสาร** – จัดเตรียมไดเรกทอรีที่คุณสามารถเก็บและเข้าถึง shapefile ที่สร้างขึ้นระหว่างกระบวนการ

## นำเข้าเนมสเปซ
ก่อนที่เราจะเริ่มทำงานฟังก์ชันการจำกัดความแม่นยำเมื่ออ่านเรขาคณิต ให้แน่ใจว่าเราได้นำเข้าเนมสเปซที่จำเป็น:
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

## วิธีสร้างเลเยอร์เวกเตอร์
โหลด `VectorLayer` ใหม่โดยระบุโฟลเดอร์ปลายทางและชื่อ shapefile ที่ต้องการ ซึ่งจะสร้างคอนเทนเนอร์เปล่าที่พร้อมรับวัตถุเรขาคณิต

คลาส `VectorLayer` เป็นอ็อบเจกต์ระดับบนของ Aspose.GIS ที่แทน shapefile เดียวบนดิสก์ หลังจากสร้างอินสแตนซ์คุณสามารถเพิ่มฟีเจอร์ กำหนดฟิลด์แอตทริบิวต์ และสุดท้ายเรียก `Save()` เพื่อบันทึกไฟล์ลงระบบไฟล์
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## การตั้งค่าตัวเลือกความแม่นยำ
`PrecisionModel` กำหนดว่าค่าพิกัดจะถูกปัดเศษหรือคงไว้เป็นค่าที่แม่นยำเมื่ออ่านเรขาคณิต คุณตั้งโมเดลบนอ็อบเจกต์ `ReadOptions` ก่อนเปิดเลเยอร์

คลาส `PrecisionModel` เป็นส่วนสำคัญของ Aspose.GIS ที่ควบคุมพฤติกรรมการปัดเศษสำหรับแกน X และ Y โดยการเลือกโมเดลที่เหมาะสมคุณจะกำหนดว่าห้องสมุดจะเก็บทุกหลักหรือจะตัดทอนเป็นจำนวนทศนิยมที่กำหนด
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## การอ่านเรขาคณิตด้วยความแม่นยำที่แน่นอน
`ReadOptions` ระบุพารามิเตอร์สำหรับการอ่านเลเยอร์เวกเตอร์ เช่น โมเดลความแม่นยำที่จะใช้  
เปิดเลเยอร์เวกเตอร์ที่บันทึกไว้ก่อนหน้านี้โดยใช้อินสแตนซ์ `ReadOptions` ที่อ้างอิง `PrecisionModel.Exact` ซึ่งทำให้ทุกพิกัดถูกอ่านโดยไม่มีการปัดเศษ

เมื่อคุณใช้ `PrecisionModel.Exact` Aspose.GIS จะอ่านค่าความแม่นยำแบบ double ดิบที่เก็บใน shapefile ทำให้มั่นใจว่าไม่มีข้อมูลสูญหายระหว่างการอ่าน
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## การตัดความแม่นยำ
หากคุณต้องการตัดความแม่นยำให้เป็นจำนวนทศนิยมที่กำหนด ให้แทนที่ `Exact` ด้วย `PrecisionModel.Rounding(n)` โดยที่ *n* คือจำนวนทศนิยมที่คุณต้องการเก็บ

การปัดเศษเป็นสองทศนิยม (`PrecisionModel.Rounding(2)`) มักลดขนาดไฟล์ได้ 20‑30 % พร้อมรักษาความแม่นยำของพิกัดไว้ในระดับไม่กี่เซนติเมตรสำหรับสเกลการทำแผนที่ส่วนใหญ่
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## วิธีตั้งค่าโมเดลความแม่นยำสำหรับสถานการณ์ต่าง ๆ
เลือกโมเดลที่ตรงกับกรณีการใช้งานของคุณ:

- **การวิเคราะห์วิทยาศาสตร์ความแม่นยำสูง** – ใช้ `PrecisionModel.Exact` เพื่อเก็บทุกหลัก  
- **แผนที่เว็บหรือแอปมือถือ** – ใช้ `PrecisionModel.Rounding(2)` เพื่อทำให้ไฟล์มีขนาดเบาและการเรนเดอร์เร็ว

การเลือกโมเดลที่เหมาะสมนั้นเป็นส่วนหนึ่งของกระบวนการตัดสินใจ **ตั้งค่าโมเดลความแม่นยำ** ที่สมดุลระหว่างความแม่นยำกับประสิทธิภาพ

## ปัญหาทั่วไปและวิธีแก้ไข
`XYPrecisionModel` เป็นคุณสมบัติของ `ReadOptions` ที่ตั้งค่าโมเดลความแม่นยำสำหรับพิกัด X และ Y ทั้งสอง

- **ค่าพิกัดที่ไม่คาดคิด** – ตรวจสอบว่าคุณตั้งค่า `options.XYPrecisionModel` *ก่อน* เปิดเลเยอร์ การเปลี่ยนแปลงหลังจากเปิดจะไม่มีผล  
- **ไม่พบไฟล์** – ยืนยันว่า ตัวแปร `path` ชี้ไปยังไดเรกทอรีที่ถูกต้องและ Shapefile ถูกสร้างสำเร็จในขั้นตอนก่อนหน้า  
- **ประเภทเรขาคณิตไม่ถูกต้อง** – ตัวอย่างใช้ `Point` สำหรับประเภทเรขาคณิตอื่น (เช่น `LineString`) การแคสท์ควรตรงกับประเภทจริง

## เคล็ดลับในการลดขนาด shapefile
- ใช้ `PrecisionModel.Rounding` ด้วยจำนวนทศนิยมที่น้อยที่สุดที่ยังตอบสนองความต้องการความแม่นยำของคุณ  
- ลบฟิลด์แอตทริบิวต์ที่ไม่จำเป็นก่อนเขียนเลเยอร์  
- บีบอัดไฟล์ `.shp`, `.shx`, และ `.dbf` ที่ได้โดยใช้ยูทิลิตี้ ZIP มาตรฐานหากต้องการถ่ายโอน

## สรุป
การจัดการความแม่นยำเมื่ออ่านเรขาคณิตเป็นด้านสำคัญของการจัดการข้อมูลเชิงพื้นที่ Aspose.GIS สำหรับ .NET ให้ฟังก์ชันที่แข็งแกร่งเพื่อทำเช่นนี้อย่างมีประสิทธิภาพ ด้วยการทำตามขั้นตอนข้างต้นคุณสามารถสร้างวัตถุ **vector layer** ได้อย่างราบรื่น, **ตั้งค่าโมเดลความแม่นยำ**, และแม้กระทั่ง **ลดขนาด shapefile** เมื่อเหมาะสม เพื่อให้การจัดการข้อมูลในแอปพลิเคชันของคุณเป็นไปอย่างดีที่สุด

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.GIS สำหรับ .NET กับเฟรมเวิร์ก .NET อื่น ๆ เช่น .NET Core หรือ .NET Standard ได้หรือไม่?
ใช่, Aspose.GIS สำหรับ .NET เข้ากันได้กับหลายเฟรมเวิร์กของ .NET รวมถึง .NET Core และ .NET Standard

### มีเวอร์ชันทดลองสำหรับ Aspose.GIS สำหรับ .NET หรือไม่?
ใช่, คุณสามารถรับเวอร์ชันทดลองฟรีจาก [releases page](https://releases.aspose.com/)

### ฉันจะหาเอกสารประกอบที่ครบถ้วนสำหรับ Aspose.GIS สำหรับ .NET ได้ที่ไหน?
คุณสามารถดูที่ [documentation](https://reference.aspose.com/gis/net/) เพื่อรับข้อมูลและตัวอย่างโดยละเอียด

### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS สำหรับ .NET ได้อย่างไร?
คุณสามารถขอรับใบอนุญาตชั่วคราวจาก [purchase page](https://purchase.aspose.com/temporary-license/) ของ Aspose.GIS

### ฉันจะขอความช่วยเหลือหรือสนับสนุนสำหรับ Aspose.GIS สำหรับ .NET ได้จากที่ไหน?
คุณสามารถเยี่ยมชม [forum](https://forum.aspose.com/c/gis/33) ของ Aspose.GIS สำหรับคำถาม การสนทนา หรือความต้องการสนับสนุน

## คำถามที่พบบ่อย
**Q: การจำกัดความแม่นยำส่งผลต่อ shapefile ต้นฉบับหรือไม่?**  
A: ไม่. ความแม่นยำจะถูกนำไปใช้เฉพาะเมื่ออ่านเรขาคณิต; ไฟล์ต้นทางจะไม่เปลี่ยนแปลง  

**Q: ฉันสามารถใช้โมเดลความแม่นยำที่แตกต่างกันสำหรับพิกัด X และ Y ได้หรือไม่?**  
A: ปัจจุบัน Aspose.GIS ใช้ `XYPrecisionModel` เดียวกันสำหรับทั้งสองแกน  

**Q: สามารถตั้งค่าฟังก์ชันการปัดเศษแบบกำหนดเองได้หรือไม่?**  
A: API รองรับเฉพาะเมธอด `PrecisionModel.Rounding(int)` ที่มีมาในตัวเท่านั้น สำหรับตรรกะแบบกำหนดเอง คุณต้องทำการประมวลผลพิกัดหลังจากอ่าน  

**อัปเดตล่าสุด:** 2026-09-10  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีจำกัดความแม่นยำในการเขียนเรขาคณิตด้วย Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)
- [วิธีสร้างเลเยอร์เวกเตอร์พร้อม SRS ด้วย Aspose.GIS สำหรับ .NET](/gis/net/layer-management/create-vector-layer-with-srs/)
- [สร้างเลเยอร์เวกเตอร์ใน File GDB – บทแนะนำ Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}