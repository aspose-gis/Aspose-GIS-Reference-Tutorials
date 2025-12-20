---
date: 2025-12-20
description: เรียนรู้วิธีจำกัดความแม่นยำเมื่อเขียนรูปทรงเรขาคณิตโดยใช้ Aspose.GIS
  สำหรับ .NET คู่มือขั้นตอนต่อขั้นตอนนี้ช่วยให้คุณจัดการข้อมูลเชิงพื้นที่ด้วยการควบคุมพิกัดที่แม่นยำ
linktitle: Limit Precision Writing Geometries
second_title: Aspose.GIS .NET API
title: วิธีจำกัดความแม่นยำในการเขียนรูปทรงเรขาคณิตด้วย Aspose.GIS
url: /th/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีจำกัดความแม่นยำในการเขียนเรขาคณิตด้วย Aspose.GIS

หากคุณกำลังสงสัย **วิธีจำกัดความแม่นยำ** เมื่อเขียนเรขาคณิตในแอปพลิเคชัน .NET GIS, Aspose.GIS for .NET ให้วิธีที่ตรงไปตรงมาและมีประสิทธิภาพสูงในการควบคุมการปัดเศษพิกัด ในบทแนะนำนี้เราจะเดินผ่านกระบวนการทั้งหมด—ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการตรวจสอบว่าผลลัพธ์เคารพกฎความแม่นยำที่คุณกำหนด

## คำตอบอย่างรวดเร็ว
- **“limit precision” หมายถึงอะไร?** มันจะปัดเศษค่าพิกัดให้เป็นจำนวนตำแหน่งทศนิยมที่กำหนดขณะเขียนไฟล์เชิงพื้นที่  
- **ฟอร์แมตที่ใช้ในตัวอย่างคืออะไร?** GeoJSON, แต่ตัวเลือกเดียวกันใช้ได้กับฟอร์แมตที่รองรับอื่น ๆ  
- **ฉันต้องมีลิขสิทธิ์เพื่อทดลองใช้งานหรือไม่?** การทดลองใช้ฟรีทำงานได้สำหรับการพัฒนาและทดสอบ; จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **ฉันสามารถควบคุมความแม่นยำของพิกัด Z แยกต่างหากได้หรือไม่?** ได้—ใช้ `ZPrecisionModel` เพื่อกำหนดค่าที่แม่นยำหรือปัดเศษ  

## วิธีจำกัดความแม่นยำเมื่อเขียนเรขาคณิต
การจำกัดความแม่นยำเป็นสิ่งสำคัญเมื่อคุณต้องการการแสดงพิกัดที่สอดคล้องกันระหว่างเครื่องมือ GIS ต่าง ๆ ลดขนาดไฟล์ หรือปฏิบัติตามมาตรฐานการแลกเปลี่ยนข้อมูล ด้านล่างเราจะกำหนดตัวเลือกความแม่นยำ, เขียนเรขาคณิต, แล้วอ่านกลับมาเพื่อยืนยันการปัดเศษ

## ข้อกำหนดเบื้องต้น

### 1. ดาวน์โหลดและการติดตั้ง
ดาวน์โหลดแพ็กเกจ Aspose.GIS for .NET ล่าสุดจากเว็บไซต์อย่างเป็นทางการ: [download link](https://releases.aspose.com/gis/net/). ปฏิบัติตามคู่มือการติดตั้งเพื่อเพิ่มแพ็กเกจ NuGet ไปยังโปรเจคของคุณ

### 2. การนำเข้า Namespace
เพิ่ม Namespace ที่จำเป็นเพื่อให้คุณสามารถเข้าถึงคลาส GIS และยูทิลิตี้ช่วยเหลือได้

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: กำหนดตัวเลือกความแม่นยำ
สร้างอินสแตนซ์ `GeoJsonOptions` และบอก Aspose.GIS ว่าต้องการตำแหน่งทศนิยมกี่ตำแหน่งสำหรับพิกัด X/Y และ Z

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### ขั้นตอนที่ 2: ตั้งค่าเส้นทางการส่งออก
ระบุที่ที่ไฟล์ GeoJSON ที่ได้จะถูกบันทึก

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### ขั้นตอนที่ 3: สร้างและเติมข้อมูลเรขาคณิต
เปิด `VectorLayer` ใหม่ด้วยตัวเลือกที่กำหนดข้างต้น, สร้างเรขาคณิต `Point`, แล้วเพิ่มเข้าไปในเลเยอร์

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

### ขั้นตอนที่ 4: อ่านและตรวจสอบความแม่นยำ
เปิดไฟล์ที่คุณเพิ่งสร้างและพิมพ์พิกัดออกมา คุณควรเห็นค่าพิกัด X/Y ถูกปัดเศษเป็นสามตำแหน่งทศนิยมในขณะที่ค่าพิกัด Z ยังคงเป็นค่าที่แม่นยำ

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

## ปัญหาทั่วไปและเคล็ดลับ
- **ข้อผิดพลาดของเส้นทาง:** ตรวจสอบให้แน่ใจว่าไดเรกทอรีใน `path` มีอยู่หรือใช้ `Path.Combine` กับ `Environment.CurrentDirectory` เพื่อสร้างเส้นทางไฟล์ที่ปลอดภัย  
- **ความแม่นยำไม่ถูกนำไปใช้:** ยืนยันว่าคุณส่งอ็อบเจกต์ `GeoJsonOptions` เมื่อสร้างเลเยอร์; มิฉะนั้นจะใช้ความแม่นยำเริ่มต้น (double เต็มรูปแบบ)  
- **ชุดข้อมูลขนาดใหญ่:** สำหรับการดำเนินการเป็นชุดใหญ่, พิจารณาใช้ `VectorLayer` ตัวเดียวซ้ำและเพิ่มฟีเจอร์เป็นชุดเพื่อปรับปรุงประสิทธิภาพ  

## คำถามที่พบบ่อย

**Q: Aspose.GIS for .NET รองรับฟอร์แมต GIS อื่น ๆ หรือไม่?**  
A: ใช่, รองรับ Shapefile, GeoJSON, KML, GML, และอื่น ๆ อีกมากมาย, ทำให้การแปลงฟอร์แมตเป็นไปอย่างราบรื่น  

**Q: ฉันสามารถทดลองใช้ Aspose.GIS for .NET ก่อนซื้อได้หรือไม่?**  
A: แน่นอน. มีการทดลองใช้ฟรีจากหน้าดาวน์โหลด, ให้คุณเข้าถึงคุณสมบัติทั้งหมดเพื่อการประเมินผล  

**Q: ฉันจะขอรับลิขสิทธิ์ชั่วคราวสำหรับการทดสอบได้อย่างไร?**  
A: สามารถสร้างลิขสิทธิ์ประเมินชั่วคราวผ่านพอร์ทัลลิขสิทธิ์ของ Aspose; มีอายุการใช้งาน 30 วัน  

**Q: ฉันจะหาแนวทางช่วยเหลือได้จากที่ไหนหากเจอปัญหา?**  
A: ฟอรั่ม Aspose.GIS และแท็ก Stack Overflow `aspose-gis` เป็นแหล่งที่ดีสำหรับถามคำถามและค้นหาโซลูชันจากชุมชน  

**Q: ไลบรารีนี้ทำงานได้ทั้งสคริปต์ขนาดเล็กและแอปพลิเคชันระดับองค์กรหรือไม่?**  
A: ใช่, Aspose.GIS ถูกออกแบบให้จัดการทุกอย่างตั้งแต่ต้นแบบเร็ว ๆ ไปจนถึงแอปพลิเคชันเซิร์ฟเวอร์ที่มีการประมวลผลสูง  

## สรุป
โดยทำตามขั้นตอนข้างต้น, คุณจะรู้ **วิธีจำกัดความแม่นยำ** เมื่อเขียนเรขาคณิตด้วย Aspose.GIS for .NET การควบคุมการปัดเศษพิกัดช่วยให้ข้อมูลเชิงพื้นที่ของคุณสะอาด, สามารถทำงานร่วมกันได้, และประหยัดพื้นที่จัดเก็บ—เป็นประโยชน์สำคัญสำหรับโครงการที่เน้น GIS ใด ๆ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2025-12-20  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose