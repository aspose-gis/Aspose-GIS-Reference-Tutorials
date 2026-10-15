---
date: 2026-10-15
description: เรียนรู้วิธีสร้าง GeoJSON จากพิกัดและเขียนลงสตรีมโดยใช้ Aspose.GIS for
  .NET. บทเรียนนี้แสดงขั้นตอนการแปลงจุดแบบ step‑by‑step และการสร้างโค้ด GeoJSON C#
keywords:
- create geojson from coordinates
- stream large geojson files
- write geojson to stream
- geojson tutorial c#
- compress geojson with gzip
lastmod: 2026-10-15
linktitle: เขียน GeoJSON ไปยังสตรีม
og_description: เรียนรู้วิธีสร้าง GeoJSON จากพิกัดและเขียนลงสตรีมโดยใช้ Aspose.GIS
  for .NET – คู่มือ step‑by‑step สำหรับชุดข้อมูลขนาดใหญ่
og_image_alt: Screenshot of Aspose.GIS code generating GeoJSON stream in C#
og_title: สร้าง GeoJSON จากพิกัด, เขียนลงสตรีมใน .NET
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create geojson from coordinates and write it to a stream
    using Aspose.GIS for .NET. This tutorial shows step‑by‑step conversion of points
    and generation of GeoJSON C# code.
  headline: Create geojson from coordinates, write to a stream in .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET geospatial
- C# stream processing
- GIS data conversion
title: สร้าง GeoJSON จากพิกัด, เขียนลงสตรีมใน .NET
url: /th/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง geojson จากพิกัดและเขียนลงสตรีม

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีสร้าง geojson จากพิกัด** และเขียนโดยตรงลงสตรีมโดยใช้ Aspose.GIS สำหรับ .NET เราจะเดินผ่านการตั้งค่าสภาพแวดล้อม การสร้างเลเยอร์ การเติมข้อมูลฟีเจอร์ และการสตรีมผลลัพธ์ เพื่อให้คุณสามารถฝังข้อมูลเชิงพื้นที่ใน API, ฟังก์ชันคลาวด์ หรือบริการแบบไม่มีไฟล์โดยไม่ต้องใช้ไฟล์ชั่วคราว

## คำตอบสั้น
- **คลาสใดที่เขียน GeoJSON ลงสตรีม?** `VectorLayer` ร่วมกับ `GeoJsonDriver`.
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **ฉันสามารถแปลงคอลเลกชันของจุดเป็น GeoJSON ได้หรือไม่?** ได้ – สร้าง `Feature` สำหรับแต่ละจุดและกำหนดเรขาคณิต `Point`.
- **การสตรีมเหมาะกับชุดข้อมูลขนาดใหญ่หรือไม่?** แน่นอน – `MemoryStream` ช่วยให้คุณเขียน GeoJSON ขนาดกิกะไบต์โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ.

## GeoJSON คืออะไร?
GeoJSON คือรูปแบบเปิดที่ใช้ JSON สำหรับเข้ารหัสฟีเจอร์ทางภูมิศาสตร์ เช่น จุด, เส้น, และโพลิกอน มันประกอบด้วย `FeatureCollection` ที่รวมวัตถุ `Feature` แต่ละอันซึ่งมีเรขาคณิตและข้อมูลแอตทริบิวต์ เนื่องจากเป็นรูปแบบที่เบาและเป็นมิตรต่อเว็บ GeoJSON จึงเป็นมาตรฐานที่ใช้กันอย่างกว้างขวางสำหรับการแลกเปลี่ยนข้อมูลเชิงพื้นที่ระหว่างเบราว์เซอร์, เซิร์ฟเวอร์ GIS, และแอปมือถือ

## ทำไมต้องใช้ Aspose.GIS สำหรับการสร้าง geojson?
Aspose.GIS รองรับ **ไฟล์ฟอร์แมตเชิงพื้นที่กว่า 35+** และสามารถสตรีมไฟล์ที่ใหญ่กว่า **2 GB** ในขณะที่ใช้หน่วยความจำต่ำกว่า **50 MB**. เครื่องยนต์สตรีมประสิทธิภาพสูงของมันเขียน GeoJSON โดยตรงไปยัง `Stream` ของ .NET ใด ๆ, ลบความจำเป็นของไฟล์ชั่วคราวกลางและลดความหน่วงของ I/O ได้ถึง **70 %** ในสถานการณ์คลาวด์ทั่วไป.

## ข้อกำหนดเบื้องต้น
1. **Aspose.GIS for .NET** ติดตั้งแล้ว ดาวน์โหลดแพคเกจ **Aspose.GIS for .NET** ที่ [here](https://releases.aspose.com/gis/net/).
2. โฟลเดอร์ที่สามารถเขียนได้ในโปรเจกต์ของคุณซึ่งคุณสามารถวางไฟล์ชั่วคราวได้หากต้องการ.
3. รันไทม์ .NET 5+ หรือ .NET Core 3.1+ ติดตั้งแล้ว.

ตอนนี้, เรามาเริ่มการทำงานกันเลย.

## วิธีสร้าง geojson จากพิกัดและเขียนลงสตรีม?
`VectorLayer` แสดงถึงชุดข้อมูลเวกเตอร์ในหน่วยความจำที่สามารถบันทึกในหลายรูปแบบ.  
`GeoJsonDriver` คือไดรเวอร์ที่ทำให้สามารถอ่านและเขียนไฟล์ GeoJSON ได้.

โหลด `VectorLayer` ด้วย `GeoJsonDriver`, เพิ่มอ็อบเจกต์ `Feature` ที่มีเรขาคณิต `Point`, แล้วเรียก `layer.Save(stream, new GeoJsonSaveOptions())`. การเรียกครั้งเดียวนี้จะทำการซีเรียลไลซ์คอลเลกชันฟีเจอร์ทั้งหมดเป็นเอกสาร GeoJSON ที่สอดคล้องกับมาตรฐานและอยู่ใน `MemoryStream` ที่ให้มา กระบวนการจะจัดการการแมปแอตทริบิวต์และการแปลงพิกัดโดยอัตโนมัติ ทำให้คุณได้รับ JSON payload ที่พร้อมใช้งานโดยไม่ต้องสร้างสตริงด้วยตนเอง.

### ตัวกำหนดความหมาย
**VectorLayer** คืออ็อบเจกต์หลักของ Aspose.GIS ที่แสดงชุดข้อมูลเวกเตอร์ที่สามารถแก้ไขได้ในหน่วยความจำ.  
**GeoJsonDriver** คือไดรเวอร์ที่รับผิดชอบการอ่านและเขียนไฟล์ GeoJSON.

## นำเข้าเนมสเปซ
ก่อนอื่นให้แน่ใจว่าได้รวมเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันของ Aspose.GIS ในโค้ดของคุณ:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
สร้างเส้นทางโฟลเดอร์ที่ Aspose.GIS สามารถจัดเก็บไฟล์ช่วยเหลือได้หากจำเป็น.  
```csharp
string dataDir = "Your Document Directory";
```
แทนที่ "Your Document Directory" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ.

## ขั้นตอนที่ 2: สร้าง memory stream
`MemoryStream` ให้บัฟเฟอร์ในหน่วยความจำที่สามารถส่งโดยตรงผ่าน HTTP หรือบันทึกลงคลาวด์สตอเรจได้.  
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## ขั้นตอนที่ 3: สร้าง vector layer ด้วย GeoJSON driver
คลาส `VectorLayer` แสดงถึงชุดข้อมูลเวกเตอร์ที่สามารถบันทึกในหลายรูปแบบ รวมถึง GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## ขั้นตอนที่ 4: กำหนดแอตทริบิวต์ของฟีเจอร์
กำหนดสกีม่าแอตทริบิวต์สำหรับฟีเจอร์ของคุณ (เช่น ID, Name).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## ขั้นตอนที่ 5: สร้างและเพิ่มฟีเจอร์
สร้างอ็อบเจกต์ `Feature`, กำหนดเรขาคณิตจุด, ตั้งค่าค่าแอตทริบิวต์, และเพิ่มลงในเลเยอร์.  
```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## ขั้นตอนที่ 6: แสดงผล GeoJSON
หลังจากบันทึก, รีเซ็ตตำแหน่งของสตรีมและอ่านสตริง JSON เพื่อการตรวจสอบหรือส่งต่อ.  
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

ขอแสดงความยินดี! คุณได้สร้าง geojson จากพิกัดและเขียนลงสตรีมสำเร็จโดยใช้ Aspose.GIS สำหรับ .NET.

## ปัญหาทั่วไปและวิธีแก้
- **สตรีมผลลัพธ์ว่าง:** ตรวจสอบให้แน่ใจว่าคุณรีเซ็ตตำแหน่งสตรีม (`stream.Position = 0`) ก่อนอ่าน.
- **ลำดับพิกัดไม่ถูกต้อง:** GeoJSON คาดหวังลำดับลองจิจูด‑ละติจูด; ตรวจสอบค่าจุดของคุณ.
- **ชุดข้อมูลขนาดใหญ่:** ใช้ `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` เพื่อสตรีมฟีเจอร์แบบเพิ่มทีละส่วนและรักษาการใช้หน่วยความจำให้ต่ำ.

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้ Aspose.GIS สำหรับ .NET ในสภาพแวดล้อม Windows และ Linux ได้หรือไม่?**  
ตอบ: ใช่, Aspose.GIS สำหรับ .NET ทำงานบน Windows, Linux, และ macOS พร้อมการสนับสนุน .NET Core เต็มรูปแบบ.

**ถาม: มีรุ่นทดลองใช้ฟรีหรือไม่?**  
ตอบ: แน่นอน! คุณสามารถสำรวจ **หน้าดาวน์โหลดรุ่นทดลองใช้** [ที่นี่](https://releases.aspose.com/).

**ถาม: ฉันจะหาเอกสารรายละเอียดได้จากที่ไหน?**  
ตอบ: ดู **เอกสาร Aspose.GIS .NET** [ที่นี่](https://reference.aspose.com/gis/net/).

**ถาม: ฉันจะขอรับไลเซนส์ชั่วคราวได้อย่างไร?**  
ตอบ: ไลเซนส์ชั่วคราวมีให้บน **หน้าลิขสิทธิ์ชั่วคราว** [ที่นี่](https://purchase.aspose.com/temporary-license/).

**ถาม: ต้องการความช่วยเหลือหรือมีคำถามเพิ่มเติม?**  
ตอบ: เยี่ยมชม **ฟอรั่มสนับสนุน GIS** ของเรา [ที่นี่](https://forum.aspose.com/c/gis/33).

**ถาม: ฉันสามารถสร้าง GeoJSON จากคอลเลกชันของจุดละติจูด/ลองจิจูดได้หรือไม่?**  
ตอบ: ได้ – สร้าง `Feature` สำหรับแต่ละจุด, กำหนดเรขาคณิต `Point`, และเพิ่มลงใน `VectorLayer`.

**ถาม: Aspose.GIS รองรับการเขียน GeoJSON ที่บีบอัด (gzip) หรือไม่?**  
ตอบ: คุณสามารถห่อ `MemoryStream` ด้วย `GZipStream` ก่อนบันทึกเพื่อสร้าง payload ที่บีบอัดได้.

**ถาม: ขนาดสูงสุดของไฟล์ GeoJSON ที่ Aspose.GIS สามารถจัดการได้คือเท่าไร?**  
ตอบ: ไลบรารีสามารถสตรีมไฟล์ที่ใหญ่กว่า 2 GB; การใช้หน่วยความจำยังคงต่ำเนื่องจากข้อมูลถูกเขียนแบบเพิ่มทีละส่วน.

---

**อัปเดตล่าสุด:** 2026-10-15  
**ทดสอบกับ:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

## บทแนะนำที่เกี่ยวข้อง

- [วิธีอ่าน GeoJSON จากสตรีมด้วย Aspose.GIS สำหรับ .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [วิธีแปลง GeoJSON เป็น TopoJSON ด้วย Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [วิธีแปลง Shapefile เป็น GeoJSON ด้วย Aspose.GIS สำหรับ .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}