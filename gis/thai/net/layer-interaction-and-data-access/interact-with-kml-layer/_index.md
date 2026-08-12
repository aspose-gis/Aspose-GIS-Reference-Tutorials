---
date: 2026-05-26
description: เรียนรู้วิธีสร้าง KML Layer ด้วย C# โดยใช้ Aspose.GIS สำหรับ .NET คู่มือแบบขั้นตอนต่อขั้นตอนเพื่อจัดการข้อมูล
  geospatial พร้อมตัวอย่างโค้ดและแนวปฏิบัติที่ดีที่สุด ดาวน์โหลด free trial ตอนนี้!
keywords:
- create kml layer c#
- Aspose.GIS .NET
- geospatial data C#
linktitle: โต้ตอบกับ KML Layer
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to create KML layer C# using Aspose.GIS for .NET. Step‑by‑step
    guide to manipulate geospatial data, with code snippets and best practices. Download
    the free trial now!
  headline: How to Create KML Layer in C# with Aspose.GIS
  type: TechArticle
- questions:
  - answer: Yes – Aspose.GIS lets you create KML layers programmatically.
    question: Can I generate KML files with C#?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: A free trial works for evaluation; a license is required for production.
    question: Do I need a license for development?
  - answer: Over 30 input and output formats, including KML, Shapefile, GeoJSON, and
      GML.
    question: How many GIS formats does Aspose.GIS handle?
  - answer: Files up to 2 GB are processed without loading the entire document into
      memory.
    question: Is there a size limit for KML files?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: วิธีสร้าง KML Layer ด้วย C# และ Aspose.GIS
url: /th/net/layer-interaction-and-data-access/interact-with-kml-layer/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างชั้น KML ใน C# ด้วย Aspose.GIS

## บทนำ
หากคุณต้องการ **create KML layer C#** อย่างรวดเร็วและเชื่อถือได้ Aspose.GIS สำหรับ .NET จะมอบ API ที่ครบถ้วนซึ่งทำงานบนแพลตฟอร์ม .NET ใดก็ได้ ในบทแนะนำนี้เราจะพาคุณผ่านขั้นตอนที่จำเป็นในการสร้างชั้น KML, เพิ่มแอตทริบิวต์, เติมข้อมูลฟีเจอร์, และบันทึกไฟล์ — ทั้งหมดโดยไม่ต้องออกจาก Visual Studio เมื่อเสร็จคุณจะเข้าใจว่าทำไม Aspose.GIS จึงเป็นโซลูชันพร้อมใช้งานสำหรับการจัดการข้อมูลเชิงพื้นที่

## คำตอบอย่างรวดเร็ว
- **ฉันสามารถสร้างไฟล์ KML ด้วย C# ได้หรือไม่?** Yes – Aspose.GIS lets you create KML layers programmatically.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **ฉันต้องการใบอนุญาตสำหรับการพัฒนาหรือไม่?** A free trial works for evaluation; a license is required for production.  
- **Aspose.GIS รองรับรูปแบบ GIS กี่รูปแบบ?** Over 30 input and output formats, including KML, Shapefile, GeoJSON, and GML.  
- **มีขนาดจำกัดสำหรับไฟล์ KML หรือไม่?** Files up to 2 GB are processed without loading the entire document into memory.

## ชั้น KML คืออะไร?
ชั้น KML คือคอนเทนเนอร์ข้อมูลภูมิศาสตร์ที่เก็บ placemarks, styles, และ geometry ในรูปแบบ Keyhole Markup Language ซึ่งใช้กันอย่างแพร่หลายสำหรับแผนที่บนเว็บและ Google Earth มันสามารถรวมจุด, เส้น, โพลิกอน, และเมทาดาต้าที่เกี่ยวข้อง ทำให้สามารถสร้างการแสดงผลที่หลากหลายในเบราว์เซอร์, แอปพลิเคชัน GIS, และ Google Earth รูปแบบนี้อิงตาม XML ทำให้ทั้งมนุษย์และเครื่องสามารถอ่านและประมวลผลได้

## ทำไมต้องใช้ Aspose.GIS สำหรับการสร้างชั้น KML?
Aspose.GIS รองรับ **30+ GIS formats** และสามารถประมวลผล **ไฟล์หลายร้อยเมกะไบต์** ในขณะที่ใช้หน่วยความจำต่ำกว่า 100 MB ด้วยสถาปัตยกรรมสตรีมมิงของมัน ไลบรารียังรับประกัน **การปฏิบัติตามสคีม่า 100 %** ดังนั้น KML ที่คุณสร้างจะทำงานได้อย่างไม่มีข้อบกพร่องในโปรแกรมดูทั้งหมด นอกจากนี้ไลบรารียังมีการตรวจสอบความถูกต้องในตัวและการจัดการระบบพิกัดอัตโนมัติ ทำให้คุณไม่ต้องใช้เครื่องมือภายนอกเพื่อให้แน่ใจว่าตรงตามมาตรฐาน

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มการเดินทางนี้ โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:
- Aspose.GIS for .NET: ดาวน์โหลดและติดตั้งไลบรารีจาก [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).
- Development Environment: ตั้งค่าสภาพแวดล้อมการพัฒนาที่เหมาะสม เช่น Visual Studio เพื่อรวม Aspose.GIS อย่างราบรื่นในโครงการ .NET ของคุณ.

ตอนนี้ เรามาเริ่มบทแนะนำกันเลย

## นำเข้า Namespaces
`Namespace` `Aspose.Gis` ให้คลาสหลักสำหรับทำงานกับข้อมูล GIS การนำเข้าจะทำให้คุณเข้าถึง `KmlLayer`, `Feature`, และยูทิลิตี้การจัดการแอตทริบิวต์.

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Drawing;
using System.Threading;
using Aspose.Gis.Formats.Kml;
using Aspose.Gis.Formats.Kml.Styles;
using Aspose.Gis.Geometries;
using Point = Aspose.Gis.Geometries.Point;
```

## วิธีสร้างชั้น KML ใน C#?
โหลดไดเรกทอรีเป้าหมาย, สร้างอ็อบเจ็กต์ `KmlLayer` ด้วยชื่อไฟล์ที่ต้องการ, แล้วเรียก `Save()` — นั่นคือทั้งหมดที่คุณต้องทำเพื่อสร้างไฟล์ KML ที่ถูกต้อง API จะเขียนโครงสร้าง XML ที่จำเป็นโดยอัตโนมัติ ดังนั้นคุณไม่ต้องจัดการ markup ระดับต่ำด้วยตนเอง.

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
กำหนดเส้นทางไปยังไดเรกทอรีเอกสารของคุณที่ไฟล์ KML จะถูกจัดเก็บ.

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้างชั้น KML
คลาส `KmlLayer` คือการแสดงผลของไฟล์ KML บนดิสก์ของ Aspose.GIS การเริ่มต้นด้วยเส้นทางไฟล์จะสร้างชั้นว่างพร้อมสำหรับฟีเจอร์.

```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```

## ขั้นตอนที่ 3: กำหนดแอตทริบิวต์
`FeatureAttribute` แสดงการกำหนดคอลัมน์สำหรับฟีเจอร์ โดยระบุชื่อและประเภทข้อมูล เพิ่มแอตทริบิวต์ลงในชั้น KML เพื่อแสดงประเภทข้อมูลต่าง ๆ เช่น string, integer, boolean, และ double.

```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```

## ขั้นตอนที่ 4: สร้างและเติมข้อมูลฟีเจอร์
`Feature` คืออ็อบเจ็กต์ที่เก็บ geometry และค่าของแอตทริบิวต์สำหรับบันทึก GIS รายการเดียว สร้างฟีเจอร์ที่แสดงเอนทิตี้เชิงพื้นที่และกำหนดค่าตามแอตทริบิวต์ที่กำหนดไว้.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```

## ขั้นตอนที่ 5: เพิ่มฟีเจอร์อีกหนึ่งรายการ
ทำซ้ำกระบวนการเพื่อเพิ่มฟีเจอร์ที่สองด้วยค่าของแอตทริบิวต์ที่แตกต่างและ geometry เป็น null.

```csharp
Feature feature2 = layer.ConstructFeature();
feature2.SetValue("string_data", "string value2");
feature2.SetValue("int_data", 100);
feature2.SetValue("bool_data", false);
feature2.SetValue("float_data", 3.1415);
feature2.Geometry = Geometry.Null;
layer.Add(feature2);
```

## ปัญหาทั่วไปและวิธีแก้ไข
- **คำเตือน geometry เป็น null** – หากฟีเจอร์ไม่มี geometry ให้แน่ใจว่าคุณตั้งค่า geometry เป็น `null` อย่างชัดเจนก่อนบันทึก; มิฉะนั้น API อาจโยนข้อยกเว้น.  
- **ประเภทแอตทริบิวต์ไม่ตรงกัน** – ค่าที่คุณกำหนดต้องตรงกับประเภทที่ประกาศของแอตทริบิวต์; มิฉะนั้นจะเกิดข้อผิดพลาดขณะรัน.  
- **ข้อผิดพลาดเส้นทางไฟล์** – ใช้เส้นทางแบบ absolute หรือยืนยันว่าแอปพลิเคชันมีสิทธิ์เขียนไปยังโฟลเดอร์เป้าหมาย.

## คำถามที่พบบ่อย

### Aspose.GIS รองรับรูปแบบ GIS อื่นหรือไม่?
ใช่, Aspose.GIS รองรับรูปแบบ GIS ต่าง ๆ รวมถึง shapefile, GeoJSON, และ KML.

### ฉันสามารถแสดงผลข้อมูลเชิงพื้นที่ที่สร้างด้วย Aspose.GIS ได้หรือไม่?
แน่นอน! Aspose.GIS ผสานรวมกับไลบรารีการทำแผนที่อย่างราบรื่น ทำให้คุณสามารถแสดงผลข้อมูลเชิงพื้นที่ของคุณได้.

### มีเวอร์ชันทดลองของ Aspose.GIS หรือไม่?
ใช่, คุณสามารถสำรวจคุณสมบัติของ Aspose.GIS ได้โดยดาวน์โหลด [free trial version](https://releases.aspose.com/).

### ฉันจะรับการสนับสนุนสำหรับ Aspose.GIS ได้อย่างไร?
เยี่ยมชม [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อรับการสนับสนุนจากชุมชนหรือสำรวจตัวเลือกการสนับสนุนระดับพรีเมียม [here](https://purchase.aspose.com/buy).

### มีใบอนุญาตชั่วคราวสำหรับ Aspose.GIS หรือไม่?
ใช่, คุณสามารถรับใบอนุญาตชั่วคราว [here](https://purchase.aspose.com/temporary-license/).

**อัปเดตล่าสุด:** 2026-05-26  
**ทดสอบกับ:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีแก้ไขชั้น – การโต้ตอบชั้น Aspose.GIS .NET](/gis/net/layer-interaction-and-data-access/)
- [รับแอตทริบิวต์ของชั้น – ดึงข้อมูลแอตทริบิวต์ของชั้นด้วย Aspose.GIS สำหรับ .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [วิธีตัดฟีเจอร์ของชั้นด้วย Aspose.GIS สำหรับ .NET](/gis/net/layer-management/crop-layer-features/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}