---
date: 2025-12-20
description: เรียนรู้วิธีสร้างเลเยอร์เวกเตอร์และจำกัดความแม่นยำเมื่ออ่านเรขาคณิตโดยใช้
  Aspose.GIS สำหรับ .NET คู่มือขั้นตอนต่อขั้นตอนเพื่อการจัดการข้อมูลภูมิศาสตร์ที่เหมาะสมที่สุด
linktitle: Limit Precision Reading Geometries
second_title: Aspose.GIS .NET API
title: สร้างเลเยอร์เวกเตอร์, จำกัดความแม่นยำด้วย Aspose.GIS สำหรับ .NET
url: /th/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง Vector Layer, จำกัดความแม่นยำด้วย Aspose.GIS สำหรับ .NET

## บทนำ
เมื่อทำงานกับข้อมูลเชิงพื้นที่ คุณมักต้อง **สร้าง vector layer** และควบคุมว่ารายละเอียดเชิงตัวเลขที่เก็บไว้มีความละเอียดเท่าใดในขณะอ่านข้อมูล Aspose.GIS สำหรับ .NET ทำให้การจำกัดความแม่นยำเป็นเรื่องง่าย ซึ่งสามารถปรับปรุงประสิทธิภาพและลดขนาดการจัดเก็บเมื่อไม่ต้องการความแม่นยำระดับสูงสุด ในบทแนะนำนี้คุณจะได้เห็นวิธีสร้าง vector layer, เขียน geometry จุดแบบง่าย, แล้วอ่านกลับด้วยความแม่นยำแบบเต็มและแบบตัดทอน

## คำตอบสั้น
- **“จำกัดความแม่นยำ” หมายถึงอะไร?** จะทำการปัดค่าพิกัดให้เป็นจำนวนทศนิยมที่กำหนด  
- **ทำไมต้องสร้าง vector layer ก่อน?** Vector layer คือคอนเทนเนอร์ที่เก็บ geometry เช่น จุด, เส้น, และโพลิกอน  
- **มี precision model ใดบ้าง?** `PrecisionModel.Exact` (ไม่มีการปัด) และ `PrecisionModel.Rounding(n)` (ปัดเป็นทศนิยม *n* ตัว)  
- **ต้องมีลิขสิทธิ์เพื่อทดลองหรือไม่?** มีรุ่นทดลองฟรีให้ดาวน์โหลดจากหน้า releases  
- **รองรับ .NET เวอร์ชันใดบ้าง?** .NET Framework 4.5+, .NET Core, และ .NET 5/6+

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:
1. **การติดตั้ง** – ควรติดตั้งไลบรารี Aspose.GIS สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ หากยังไม่ได้ติดตั้งสามารถดาวน์โหลดได้จาก [releases page](https://releases.aspose.com/gis/net/)  
2. **ความคุ้นเคยกับ .NET** – ต้องมีความรู้พื้นฐานเกี่ยวกับ C# และ .NET framework เพื่อเข้าใจและใช้งานตัวอย่างโค้ดที่ให้มา  
3. **สภาพแวดล้อมการพัฒนา** – จำเป็นต้องมีสภาพแวดล้อมการพัฒนา .NET ที่ทำงานได้ เช่น Visual Studio  
4. **ไดเรกทอรีเอกสาร** – สร้างไดเรกทอรีที่คุณจะเก็บและเข้าถึง shapefile ที่สร้างขึ้นระหว่างกระบวนการ

## นำเข้า Namespaces
ก่อนที่เราจะเริ่มทำงานฟังก์ชันการจำกัดความแม่นยำเมื่ออ่าน geometry ให้แน่ใจว่าได้นำเข้า namespace ที่จำเป็นแล้ว:
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

## วิธีสร้าง Vector Layer
ขั้นตอนแรกคือ **สร้าง vector layer** ที่จะเก็บ geometry ของเรา Layer นี้จะถูกบันทึกเป็น Shapefile เพื่อให้เราสามารถเปิดใหม่ด้วยการตั้งค่าความแม่นยำที่ต่างกันได้ในภายหลัง
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## การตั้งค่า Precision Options
ต่อไปเราต้องกำหนดตัวเลือกสำหรับการอ่าน geometry โดยระบุ precision model ที่ต้องการ เราสามารถเริ่มต้นด้วยความแม่นยำเต็มได้ดังนี้:
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## การอ่าน Geometry ด้วย Exact Precision
ตอนนี้ให้เปิด vector layer ด้วยตัวเลือกที่กำหนดเพื่ออ่าน geometry ด้วยความแม่นยำเต็ม:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## การตัดทอนความแม่นยำ
หากต้องการตัดทอนความแม่นยำให้เหลือจำนวนทศนิยมที่กำหนด สามารถปรับ precision model ได้ดังนี้:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## ปัญหาที่พบบ่อยและวิธีแก้
- **ค่าพิกัดที่ไม่คาดคิด** – ตรวจสอบให้แน่ใจว่าได้ตั้งค่า `options.XYPrecisionModel` *ก่อน* เปิด layer การเปลี่ยนแปลงหลังจากเปิดจะไม่มีผล  
- **ไฟล์ไม่พบ** – ตรวจสอบว่า ตัวแปร `path` ชี้ไปยังไดเรกทอรีที่ถูกต้องและ Shapefile ถูกสร้างสำเร็จในขั้นตอนก่อนหน้า  
- **ประเภท geometry ไม่ตรง** – ตัวอย่างใช้ `Point` หากใช้ geometry ประเภทอื่น (เช่น `LineString`) ต้องทำการแคสต์ให้ตรงกับประเภทจริง

## สรุป
โดยสรุป การจัดการความแม่นยำเมื่ออ่าน geometry เป็นส่วนสำคัญของการจัดการข้อมูลเชิงพื้นที่ Aspose.GIS สำหรับ .NET มีฟังก์ชันที่แข็งแกร่งเพื่อทำสิ่งนี้ได้อย่างมีประสิทธิภาพ ด้วยการทำตามขั้นตอนในบทแนะนำนี้ คุณสามารถ **สร้าง vector layer** อย่างราบรื่นและจำกัดความแม่นยำตามความต้องการของคุณ เพื่อให้การจัดการข้อมูลเป็นไปอย่างเหมาะสมในแอปพลิเคชันของคุณ

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.GIS สำหรับ .NET กับเฟรมเวิร์ก .NET อื่น ๆ เช่น .NET Core หรือ .NET Standard ได้หรือไม่?
ได้, Aspose.GIS สำหรับ .NET รองรับเฟรมเวิร์ก .NET ต่าง ๆ รวมถึง .NET Core และ .NET Standard  
### มีรุ่นทดลองสำหรับ Aspose.GIS สำหรับ .NET หรือไม่?
มี, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีได้จาก [releases page](https://releases.aspose.com/)  
### จะหาเอกสารประกอบที่ครบถ้วนสำหรับ Aspose.GIS สำหรับ .NET ได้ที่ไหน?
ดูรายละเอียดและตัวอย่างเพิ่มเติมได้ที่ [documentation](https://reference.aspose.com/gis/net/)  
### จะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.GIS สำหรับ .NET ได้อย่างไร?
สามารถขอรับลิขสิทธิ์ชั่วคราวได้จาก [purchase page](https://purchase.aspose.com/temporary-license/) สำหรับ Aspose.GIS  
### จะขอรับการสนับสนุนหรือความช่วยเหลือสำหรับ Aspose.GIS สำหรับ .NET ได้จากที่ไหน?
คุณสามารถเข้าไปที่ฟอรั่ม Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) เพื่อสอบถาม, สนทนา หรือขอความช่วยเหลือได้

## คำถามที่พบบ่อยเพิ่มเติม
**ถาม: การจำกัดความแม่นยำส่งผลต่อไฟล์ shapefile ดั้งเดิมหรือไม่?**  
ตอบ: ไม่. ความแม่นยำจะถูกนำไปใช้เฉพาะเมื่ออ่าน geometry; ไฟล์ต้นฉบับจะไม่ถูกเปลี่ยนแปลง  

**ถาม: สามารถใช้ precision model ที่แตกต่างกันสำหรับพิกัด X และ Y ได้หรือไม่?**  
ตอบ: ปัจจุบัน Aspose.GIS ใช้ `XYPrecisionModel` เดียวกันสำหรับทั้งสองแกน  

**ถาม: สามารถกำหนดฟังก์ชันการปัดค่าแบบกำหนดเองได้หรือไม่?**  
ตอบ: API รองรับเพียงเมธอดในตัว `PrecisionModel.Rounding(int)` เท่านั้น หากต้องการตรรกะแบบกำหนดเองต้องทำการประมวลผลพิกัดหลังจากอ่านเสร็จ

---

**อัปเดตล่าสุด:** 2025-12-20  
**ทดสอบกับ:** Aspose.GIS 24.11 สำหรับ .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}