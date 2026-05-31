---
date: 2026-05-31
description: เรียนรู้วิธีจำกัดความแม่นยำเมื่อเขียนเรขาคณิตด้วย Aspose.GIS สำหรับ .NET
  เพื่อลดขนาด GeoJSON และควบคุมพิกัด
keywords:
- how to limit precision
- reduce geojson size
- Aspose.GIS precision control
linktitle: จำกัดความแม่นยำในการเขียนเรขาคณิต
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  headline: How to Limit Precision Writing Geometries with Aspose.GIS
  type: TechArticle
- description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  name: How to Limit Precision Writing Geometries with Aspose.GIS
  steps:
  - name: Define Precision Options
    text: The `GeoJsonOptions` class lets you specify how many fractional digits to
      keep for X/Y and Z coordinates. `PrecisionModel` defines how coordinate values
      are rounded or kept exact during writing.
  - name: Set Output Path
    text: Specify where the resulting GeoJSON file will be saved. `VectorLayer` is
      Aspose.GIS's container for a collection of features that share the same schema;
      it writes to the path you provide using the options set earlier.
  - name: Create and Populate Geometry
    text: Open a new `VectorLayer` with the options defined above, construct a `Point`
      geometry, and add it to the layer. `Point` represents a single coordinate (X,
      Y, optional Z) in a spatial reference system. It is the simplest geometry type
      and is used here to demonstrate precision rounding.
  - name: Read and Verify Precision
    text: Open the file you just created and print the coordinates. You should see
      the X/Y values rounded to three decimal places while the Z value remains exact.
      When you read the file back, Aspose.GIS parses the rounded values directly,
      so the in‑memory `Point` reflects the precision you defined during writ
  type: HowTo
- questions:
  - answer: Yes, it supports **50+** formats—including Shapefile, GeoJSON, KML, GML,
      and CSV—allowing seamless conversion between them.
    question: Is Aspose.GIS for .NET compatible with other GIS formats?
  - answer: Absolutely. A free trial is available from the download page, giving you
      full access to all features for evaluation.
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: Temporary evaluation licenses can be generated via the Aspose license
      portal; they are valid for 30 days.
    question: How do I obtain a temporary license for testing?
  - answer: The Aspose.GIS forum and Stack Overflow tag `aspose-gis` are great places
      to ask questions and find community solutions.
    question: Where can I get help if I run into issues?
  - answer: Yes, Aspose.GIS is designed to handle everything from quick prototypes
      to high‑throughput server workloads, processing multi‑gigabyte datasets with
      low memory overhead.
    question: Does the library work for both small scripts and enterprise‑scale applications?
  type: FAQPage
second_title: Aspise.GIS .NET API
title: วิธีจำกัดความแม่นยำในการเขียนเรขาคณิตด้วย Aspose.GIS
url: /th/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีจำกัดความแม่นยำในการเขียนเรขาคณิตด้วย Aspose.GIS

หากคุณกำลังสงสัย **วิธีจำกัดความแม่นยำ** เมื่อเขียนเรขาคณิตในแอปพลิเคชัน GIS บน .NET, Aspose.GIS for .NET มีวิธีที่ตรงไปตรงมาและประสิทธิภาพสูงในการควบคุมการปัดเศษพิกัด ในบทแนะนำนี้เราจะพาคุณผ่านกระบวนการทั้งหมด—ตั้งแต่การเตรียมสภาพแวดล้อมจนถึงการตรวจสอบว่าผลลัพธ์ปฏิบัติตามกฎความแม่นยำที่คุณกำหนด

## คำตอบสั้น
- **หมายความว่า “limit precision” คืออะไร?** มันทำการปัดเศษค่าพิกัดให้เป็นจำนวนตำแหน่งทศนิยมที่กำหนดขณะเขียนไฟล์เชิงพื้นที่  
- **รูปแบบใดที่ใช้ในตัวอย่าง?** GeoJSON, แต่ตัวเลือกเดียวกันสามารถใช้กับรูปแบบอื่นที่รองรับได้  
- **ฉันต้องมีลิขสิทธิ์เพื่อทดลองใช้งานหรือไม่?** การทดลองใช้ฟรีทำงานได้สำหรับการพัฒนาและการทดสอบ; จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในสภาพแวดล้อมจริง  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **ฉันสามารถควบคุมความแม่นยำของพิกัด Z แยกต่างหากได้หรือไม่?** ใช่—ใช้ `ZPrecisionModel` เพื่อกำหนดค่าที่แม่นยำหรือปัดเศษ  

## วิธีจำกัดความแม่นยำเมื่อเขียนเรขาคณิต

โหลดตัวเขียน GeoJSON ของคุณด้วยอ็อบเจ็กต์ `GeoJsonOptions` ที่ระบุความแม่นยำของ X/Y และ Z ที่ต้องการ, จากนั้นเขียนเรขาคณิตและอ่านกลับ—กระบวนการทั้งหมดนี้ใช้โค้ดไม่เกินสิบบรรทัดและรับประกันว่าพิกัดทั้งหมดจะถูกปัดเศษตามที่คุณกำหนด

การจำกัดความแม่นยำเป็นสิ่งสำคัญเมื่อคุณต้องการการแสดงพิกัดที่สอดคล้องกันในเครื่องมือ GIS ต่าง ๆ, ลดขนาดไฟล์, หรือปฏิบัติตามมาตรฐานการแลกเปลี่ยนข้อมูล ด้านล่างเราจะกำหนดตัวเลือกความแม่นยำ, เขียนเรขาคณิต, แล้วอ่านกลับเพื่อยืนยันการปัดเศษ

## ความหมายของการจำกัดความแม่นยำ

การจำกัดความแม่นยำคือกระบวนการปัดเศษส่วนของค่าพิกัดให้เป็นจำนวนตำแหน่งทศนิยมที่กำหนดก่อนบันทึกเรขาคณิตลงในรูปแบบไฟล์ ซึ่งทำให้ผู้ใช้ไฟล์ทุกคนเห็นค่าตัวเลขเดียวกัน ช่วยหลีกเลี่ยงความไม่ตรงกันเล็กน้อยที่อาจทำให้เกิดข้อผิดพลาดด้านโทโพโลยี

## ทำไมต้องใช้ Aspose.GIS สำหรับการควบคุมความแม่นยำ?

Aspose.GIS รองรับ **50+** รูปแบบการนำเข้าและส่งออก—including GeoJSON, Shapefile, KML, และ GML—และสามารถประมวลผลไฟล์ที่มี **หลายแสนฟีเจอร์** ได้โดยไม่ต้องโหลดชุดข้อมูลทั้งหมดเข้าสู่หน่วยความจำ โมเดลความแม่นยำในตัวช่วยให้คุณปัดเศษพิกัดได้ในหนึ่งคำสั่งเดียว, ลดความจำเป็นในการเขียนสคริปต์หลังการประมวลผลด้วยตนเอง

## ข้อกำหนดเบื้องต้น

### 1. ดาวน์โหลดและการติดตั้ง
ดาวน์โหลดแพ็กเกจ Aspose.GIS for .NET ล่าสุดจากเว็บไซต์ทางการ: [download link](https://releases.aspose.com/gis/net/). ทำตามคู่มือการติดตั้งเพื่อเพิ่มแพ็กเกจ NuGet ไปยังโปรเจกต์ของคุณ

### 2. การนำเข้า Namespace
เพิ่ม namespace ที่จำเป็นเพื่อให้คุณสามารถเข้าถึงคลาส GIS และยูทิลิตี้ช่วยเหลือต่าง ๆ

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: กำหนดตัวเลือกความแม่นยำ
คลาส `GeoJsonOptions` ให้คุณระบุจำนวนตำแหน่งทศนิยมที่ต้องการเก็บสำหรับพิกัด X/Y และ Z  

`PrecisionModel` กำหนดวิธีการปัดเศษหรือเก็บค่าพิกัดให้แม่นยำขณะเขียน  

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

### ขั้นตอนที่ 2: ตั้งค่าเส้นทางการส่งออก
ระบุที่ตั้งที่ไฟล์ GeoJSON ที่สร้างขึ้นจะถูกบันทึก  

`VectorLayer` คือคอนเทนเนอร์ของ Aspose.GIS สำหรับชุดฟีเจอร์ที่ใช้สคีม่าเดียวกัน; มันจะเขียนไปยังเส้นทางที่คุณระบุโดยใช้ตัวเลือกที่ตั้งค่าไว้ก่อนหน้า  

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### ขั้นตอนที่ 3: สร้างและเติมข้อมูลเรขาคณิต
เปิด `VectorLayer` ใหม่ด้วยตัวเลือกที่กำหนดข้างต้น, สร้างเรขาคณิต `Point` และเพิ่มลงในเลเยอร์  

`Point` แทนพิกัดเดียว (X, Y, optional Z) ในระบบอ้างอิงเชิงพื้นที่ เป็นประเภทเรขาคณิตที่ง่ายที่สุดและใช้ที่นี่เพื่อสาธิตการปัดเศษความแม่นยำ  

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### ขั้นตอนที่ 4: อ่านและตรวจสอบความแม่นยำ
เปิดไฟล์ที่คุณสร้างขึ้นและพิมพ์พิกัดออก คุณควรเห็นค่าพิกัด X/Y ถูกปัดเศษเป็นสามตำแหน่งทศนิยม ส่วนค่าพิกัด Z ยังคงแม่นยำ  

เมื่อคุณอ่านไฟล์กลับมา, Aspose.GIS จะวิเคราะห์ค่าที่ปัดเศษโดยตรง, ดังนั้น `Point` ในหน่วยความจำจะแสดงความแม่นยำที่คุณกำหนดขณะเขียน  

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

## ปัญหาทั่วไปและเคล็ดลับ

- **Path Errors:** ตรวจสอบให้แน่ใจว่าไดเรกทอรีใน `path` มีอยู่หรือใช้ `Path.Combine` กับ `Environment.CurrentDirectory` เพื่อสร้างเส้นทางไฟล์ที่ปลอดภัย  
- **Precision Not Applied:** ตรวจสอบว่าคุณส่งอ็อบเจ็กต์ `GeoJsonOptions` ขณะสร้างเลเยอร์; หากไม่ทำจะใช้ความแม่นยำเริ่มต้น (double เต็มรูปแบบ)  
- **Large Datasets:** สำหรับการดำเนินการเป็นกลุ่ม, พิจารณาใช้ `VectorLayer` ตัวเดียวซ้ำและเพิ่มฟีเจอร์เป็นชุดเพื่อปรับปรุงประสิทธิภาพ  

## คำถามที่พบบ่อย

**Q: Aspose.GIS for .NET รองรับรูปแบบ GIS อื่น ๆ หรือไม่?**  
A: ใช่, รองรับ **50+** รูปแบบ—including Shapefile, GeoJSON, KML, GML, และ CSV—ทำให้การแปลงระหว่างรูปแบบต่าง ๆ เป็นไปอย่างราบรื่น  

**Q: ฉันสามารถทดลองใช้ Aspose.GIS for .NET ก่อนซื้อได้หรือไม่?**  
A: แน่นอน. มีการทดลองใช้ฟรีจากหน้าดาวน์โหลด, ให้คุณเข้าถึงฟีเจอร์ทั้งหมดเพื่อการประเมิน  

**Q: ฉันจะขอรับลิขสิทธิ์ชั่วคราวสำหรับการทดสอบได้อย่างไร?**  
A: สามารถสร้างลิขสิทธิ์ประเมินชั่วคราวผ่านพอร์ทัลลิขสิทธิ์ของ Aspose; มีอายุการใช้งาน 30 วัน  

**Q: ฉันจะหาแนวทางช่วยเหลือเมื่อเจอปัญหาได้จากที่ไหน?**  
A: ฟอรั่ม Aspose.GIS และแท็ก Stack Overflow `aspose-gis` เป็นแหล่งที่ดีสำหรับถามคำถามและค้นหาโซลูชันจากชุมชน  

**Q: ไลบรารีนี้ทำงานได้ทั้งสคริปต์เล็ก ๆ และแอปพลิเคชันระดับองค์กรหรือไม่?**  
A: ใช่, Aspose.GIS ถูกออกแบบให้จัดการทุกอย่างตั้งแต่ต้นแบบเร็ว ๆ จนถึงงานเซิร์ฟเวอร์ที่มีปริมาณสูง, ประมวลผลชุดข้อมูลหลายกิกะไบต์ด้วยการใช้หน่วยความจำน้อย  

**อัปเดตล่าสุด:** 2026-05-31  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

## บทแนะนำที่เกี่ยวข้อง

- [สร้าง Vector Layer, จำกัดความแม่นยำด้วย Aspose.GIS for .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [วิธีแปลง GeoJSON – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [วิธีตรวจสอบเรขาคณิตด้วย Aspose.GIS for .NET](/gis/net/geometry-analysis/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

{{< /blocks/products/pf/main-wrap-class >}}