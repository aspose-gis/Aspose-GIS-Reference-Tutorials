---
date: 2026-04-03
description: เรียนรู้วิธีสร้างเลเยอร์เวกเตอร์และจำกัดความแม่นยำเมื่ออ่านรูปทรงเรขาคณิตโดยใช้
  Aspose.GIS สำหรับ .NET คู่มือแบบขั้นตอนต่อขั้นตอนสำหรับการจัดการข้อมูลเชิงพื้นที่อย่างเหมาะสม
keywords:
- create vector layer
- reduce shapefile size
- set precision model
linktitle: จำกัดความละเอียดการอ่านรูปทรงเรขาคณิต
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
เมื่อทำงานกับข้อมูลเชิงพื้นที่ คุณมักต้อง **create vector layer** objects และตัดสินใจว่าต้องการรายละเอียดตำแหน่งพิกัดในรูปแบบทศนิยมกี่ตำแหน่ง การจำกัดความแม่นยำไม่เพียงทำให้การประมวลผลเร็วขึ้น แต่ยัง **reduce shapefile size** ทำให้การจัดเก็บและการถ่ายโอนมีประสิทธิภาพมากขึ้น ในบทเรียนนี้เราจะอธิบายขั้นตอนการสร้าง vector layer, เขียน geometry จุดอย่างง่าย, แล้วอ่านกลับโดยใช้โมเดลความแม่นยำแบบ exact และ rounding สุดท้ายคุณจะเข้าใจวิธี **set precision model** ที่เหมาะกับความต้องการความแม่นยำของแอปพลิเคชันของคุณ

## คำตอบอย่างรวดเร็ว
- **อะไรหมายถึง “limit precision”?** มันทำการปัดค่าพิกัดให้เป็นจำนวนทศนิยมที่กำหนด  
- **ทำไมต้องสร้าง vector layer ก่อน?** Vector layer คือคอนเทนเนอร์ที่เก็บ geometry เช่น จุด, เส้น, และโพลิกอน  
- **โมเดลความแม่นยำที่มีให้เลือกคืออะไร?** `PrecisionModel.Exact` (ไม่มีการปัด) และ `PrecisionModel.Rounding(n)` (ปัดเป็นทศนิยม *n* ตัว)  
- **ต้องมีไลเซนส์เพื่อทดลองใช้งานหรือไม่?** มีเวอร์ชันทดลองฟรีจากหน้า releases  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core, และ .NET 5/6+

## ทำไมต้องจำกัดความแม่นยำและมันช่วยอย่างไร?
- **เพิ่มประสิทธิภาพ** – จำนวนตัวเลขที่น้อยลงหมายถึงข้อมูลที่ต้องพาร์สและซีเรียลไลซ์น้อยลง  
- **ไฟล์ขนาดเล็กลง** – การปัดค่าพิกัดสามารถทำให้ shapefile ลดขนาดได้อย่างเห็นได้ชัด โดยเฉพาะกับชุดข้อมูลขนาดใหญ่  
- **ความแม่นยำที่เพียงพอ** – การวิเคราะห์ GIS จำนวนมากไม่ต้องการความแม่นยำระดับซับ‑มิลลิเมตร ดังนั้นการปัดเป็นทศนิยม 2‑3 ตำแหน่งมักเพียงพอ

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้นการเดินทางนี้ โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:
1. **Installation** – ควรติดตั้งไลบรารี Aspose.GIS for .NET ในสภาพแวดล้อมการพัฒนาของคุณ หากยังไม่ได้ติดตั้ง คุณสามารถดาวน์โหลดได้จาก [releases page](https://releases.aspose.com/gis/net/)  
2. **Familiarity with .NET** – จำเป็นต้องมีความรู้พื้นฐานเกี่ยวกับ C# และ .NET framework เพื่อเข้าใจและใช้งานตัวอย่างโค้ดที่ให้มา  
3. **Development Environment** – ต้องมีสภาพแวดล้อมการพัฒนา .NET ที่ทำงานได้ เช่น Visual Studio  
4. **Document Directory** – จัดเตรียมไดเรกทอรีที่คุณสามารถเก็บและเข้าถึง shapefile ที่สร้างขึ้นระหว่างกระบวนการได้

## นำเข้า Namespaces
ก่อนที่เราจะเริ่มต้นการทำงานเพื่อจำกัดความแม่นยำเมื่ออ่าน geometry ให้แน่ใจว่าเราได้นำเข้า namespace ที่จำเป็นแล้ว:
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
ขั้นตอนแรกคือการ **create vector layer** ที่จะเก็บ geometry ของเรา Layer นี้จะถูกบันทึกเป็น Shapefile เพื่อให้เราสามารถเปิดใหม่ด้วยการตั้งค่าความแม่นยำที่ต่างกันได้ในภายหลัง
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
ต่อไปเราต้องกำหนดตัวเลือกสำหรับการอ่าน geometry โดยระบุโมเดลความแม่นยำที่ต้องการ เราจะเริ่มต้นด้วยความแม่นยำแบบ exact:
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## การอ่าน Geometry ด้วย Exact Precision
ตอนนี้ให้เปิด vector layer พร้อมตัวเลือกที่กำหนดเพื่ออ่าน geometry ด้วยความแม่นยำแบบ exact:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## การตัด Precision
หากต้องการตัดความแม่นยำให้เหลือจำนวนทศนิยมที่กำหนด สามารถปรับโมเดลความแม่นยำได้ตามต้องการ:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## วิธีตั้ง Precision Model สำหรับสถานการณ์ต่าง ๆ
คุณอาจสงสัยว่าเมื่อไหร่ควรใช้ `Exact` กับ `Rounding` นี่คือตัวอย่างสองสถานการณ์ที่พบบ่อย:

| สถานการณ์ | โมเดลที่แนะนำ | เหตุผล |
|----------|-------------------|--------|
| การวิเคราะห์ทางวิทยาศาสตร์ความแม่นยำสูง | `PrecisionModel.Exact` | ไม่มีการสูญเสียรายละเอียดพิกัด |
| แผนที่เว็บหรือแอปมือถือ | `PrecisionModel.Rounding(2)` | ลดขนาดไฟล์และเร่งการแสดงผล |

การเลือกโมเดลที่เหมาะสมเป็นส่วนหนึ่งของกระบวนการ **set precision model** ที่ต้องพิจารณาความแม่นยำเทียบกับประสิทธิภาพ

## ปัญหาและวิธีแก้ไขทั่วไป
- **Unexpected coordinate values** – ตรวจสอบให้แน่ใจว่าคุณตั้งค่า `options.XYPrecisionModel` *ก่อน* เปิด layer การเปลี่ยนแปลงหลังจากเปิดจะไม่มีผล  
- **File not found** – ตรวจสอบว่า ตัวแปร `path` ชี้ไปยังไดเรกทอรีที่ถูกต้องและ Shapefile ถูกสร้างสำเร็จในขั้นตอนก่อนหน้า  
- **Incorrect geometry type** – ตัวอย่างใช้ `Point` หากใช้ geometry ประเภทอื่น (เช่น `LineString`) การแคสท์ต้องตรงกับประเภทจริง

## เคล็ดลับในการลดขนาด Shapefile
- ใช้ `PrecisionModel.Rounding` ด้วยจำนวนทศนิยมที่น้อยที่สุดที่ยังตอบสนองความต้องการความแม่นยำของคุณ  
- ลบฟิลด์ attribute ที่ไม่จำเป็นก่อนเขียน layer  
- บีบอัดไฟล์ `.shp`, `.shx`, และ `.dbf` ที่ได้ด้วยเครื่องมือ ZIP มาตรฐานหากต้องการถ่ายโอน

## สรุป
โดยสรุป การจัดการความแม่นยำเมื่ออ่าน geometry เป็นส่วนสำคัญของการจัดการข้อมูลเชิงพื้นที่ Aspose.GIS for .NET มีฟังก์ชันที่แข็งแกร่งเพื่อทำสิ่งนี้อย่างมีประสิทธิภาพ ด้วยการทำตามขั้นตอนข้างต้น คุณสามารถ **create vector layer** objects, **set precision model**, และแม้กระทั่ง **reduce shapefile size** เมื่อเหมาะสม เพื่อให้การจัดการข้อมูลในแอปพลิเคชันของคุณเป็นไปอย่างดีที่สุด

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.GIS for .NET กับเฟรมเวิร์ก .NET อื่น ๆ เช่น .NET Core หรือ .NET Standard ได้หรือไม่?
ใช่ Aspose.GIS for .NET รองรับเฟรมเวิร์ก .NET ต่าง ๆ รวมถึง .NET Core และ .NET Standard  
### มีเวอร์ชันทดลองสำหรับ Aspose.GIS for .NET หรือไม่?
มี คุณสามารถรับเวอร์ชันทดลองฟรีจาก [releases page](https://releases.aspose.com/)  
### ฉันจะหาเอกสารประกอบที่ครบถ้วนสำหรับ Aspose.GIS for .NET ได้จากที่ไหน?
คุณสามารถดูที่ [documentation](https://reference.aspose.com/gis/net/) เพื่อรับข้อมูลและตัวอย่างโดยละเอียด  
### ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.GIS for .NET ได้อย่างไร?
สามารถขอไลเซนส์ชั่วคราวได้จาก [purchase page](https://purchase.aspose.com/temporary-license/) สำหรับ Aspose.GIS  
### ฉันจะหาความช่วยเหลือหรือสนับสนุนสำหรับ Aspose.GIS for .NET ได้จากที่ไหน?
คุณสามารถเยี่ยมชม Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) เพื่อสอบถาม, สนทนา หรือขอการสนับสนุนได้

## คำถามที่พบบ่อย
**Q: การจำกัดความแม่นยำส่งผลต่อ shapefile ดั้งเดิมหรือไม่?**  
A: ไม่ การจำกัดความแม่นยำจะถูกนำไปใช้เฉพาะเมื่ออ่าน geometry; ไฟล์ต้นฉบับจะไม่ถูกเปลี่ยนแปลง  

**Q: ฉันสามารถใช้โมเดลความแม่นยำที่แตกต่างกันสำหรับพิกัด X และ Y ได้หรือไม่?**  
A: Aspose.GIS ปัจจุบันใช้ `XYPrecisionModel` เดียวกันสำหรับทั้งสองแกน  

**Q: สามารถตั้งฟังก์ชันการปัดค่าแบบกำหนดเองได้หรือไม่?**  
A: API รองรับเฉพาะเมธอด `PrecisionModel.Rounding(int)` ที่มีมาให้ หากต้องการตรรกะแบบกำหนดเองต้องทำการประมวลผลพิกัดหลังจากอ่านเสร็จ  

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}