---
date: 2026-05-21
description: เรียนรู้วิธีเขียน GeoJSON ไปยังสตรีมโดยใช้ Aspose.GIS สำหรับ .NET. tutorial
  geojson .net นี้แสดงการแปลงจุดแบบขั้นตอนต่อขั้นตอนและการสร้างโค้ด GeoJSON C#
keywords:
- how to write geojson
- convert points geojson
- geojson tutorial .net
- generate geojson c#
linktitle: เขียน GeoJSON ไปยังสตรีม
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to write GeoJSON to stream using Aspose.GIS for .NET. This
    geojson tutorial .net shows step‑by‑step conversion of points and generation of
    GeoJSON C# code.
  headline: How to Write GeoJSON to Stream with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: วิธีเขียน GeoJSON ไปยังสตรีมด้วย Aspose.GIS สำหรับ .NET
url: /th/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เขียน GeoJSON ไปยัง Stream

## บทนำ
ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีเขียน GeoJSON ไปยังสตรีม** ในแอปพลิเคชัน .NET โดยใช้ Aspose.GIS เราจะเดินผ่านแต่ละขั้นตอน ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการสร้างเอกสาร GeoJSON ที่ถูกต้อง เพื่อให้คุณสามารถผสานรวมข้อมูลเชิงพื้นที่ได้อย่างราบรื่นในบริการของคุณ

## คำตอบอย่างรวดเร็ว
- **อะไรคือคลาสหลักสำหรับการส่งออก GeoJSON?** `VectorLayer` with the `GeoJsonDriver`.
- **ฉันต้องการใบอนุญาตสำหรับการพัฒนาหรือไม่?** การทดลองใช้ฟรีทำงานได้สำหรับการพัฒนา; จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการผลิต.
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **ฉันสามารถแปลงชุดจุดเป็น GeoJSON ได้หรือไม่?** ใช่ – ใช้คลาส `Feature` และกำหนดเรขาคณิตจุด.
- **การสตรีมรองรับชุดข้อมูลขนาดใหญ่หรือไม่?** แน่นอน; `MemoryStream` ช่วยให้คุณเขียนโดยไม่ต้องใช้ไฟล์ชั่วคราว.

## GeoJSON คืออะไร?
GeoJSON เป็นรูปแบบมาตรฐานเปิดสำหรับการเข้ารหัสโครงสร้างข้อมูลทางภูมิศาสตร์หลายประเภทโดยใช้ JSON มันกำหนดอ็อบเจ็กต์เช่น FeatureCollection, Feature, และประเภทเรขาคณิต (Point, LineString, Polygon) การแสดงผลที่เบาและเป็นมิตรกับเว็บนี้ทำให้การแลกเปลี่ยนและการแสดงผลข้อมูลเชิงพื้นที่บนหลายแพลตฟอร์มและภาษาการเขียนโปรแกรมเป็นเรื่องง่าย

## ทำไมต้องใช้ Aspose.GIS สำหรับการสร้าง GeoJSON?
Aspose.GIS รองรับไฟล์เชิงพื้นที่มากกว่า 30 รูปแบบและสามารถประมวลผลไฟล์ที่ใหญ่กว่า 2 GB โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ เครื่องยนต์สตรีมประสิทธิภาพสูงของมันเขียน GeoJSON โดยตรงไปยังสตรีม ลดภาระ I/O ทำให้เหมาะสำหรับงานเชิงพื้นที่ระดับองค์กร, บริการคลาวด์, และแอปพลิเคชันเรียลไทม์

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะดำดิ่งสู่บทเรียน โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:
1. Aspose.GIS for .NET Library: ตรวจสอบว่าคุณได้ติดตั้งไลบรารี Aspose.GIS for .NET แล้ว คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/gis/net/).
2. Document Directory: มีโฟลเดอร์เอกสารตั้งค่าในโปรเจกต์ของคุณและจดบันทึกเส้นทางของมันไว้.

ตอนนี้, มาเริ่มต้นบทเรียนกันเถอะ!

## ฉันจะเขียน GeoJSON ไปยังสตรีมอย่างไร?
VectorLayer แทนชุดข้อมูลเวกเตอร์ที่สามารถบันทึกในหลายรูปแบบรวมถึง GeoJSON  
GeoJsonDriver คือไดรเวอร์ที่ Aspose.GIS ใช้เพื่ออ่านและเขียนไฟล์ GeoJSON  
`layer.Save` เขียนเนื้อหาเลเยอร์ไปยังสตรีมที่ให้โดยใช้ตัวเลือกการบันทึกที่ระบุ  

โหลด `VectorLayer` ด้วย `GeoJsonDriver`, เพิ่มฟีเจอร์ที่มีเรขาคณิตจุด, แล้วเรียก `layer.Save(stream, new GeoJsonSaveOptions())` วิธีนี้จะเขียนเอกสาร GeoJSON ที่สมบูรณ์และเป็นไปตามมาตรฐานโดยตรงลงใน `MemoryStream` ที่ให้ไว้ในไม่กี่บรรทัดของโค้ด วิธีการจะทำการซีเรียลไลซ์คอลเลกชันฟีเจอร์, จัดการข้อมูลแอตทริบิวต์และการแปลงเรขาคณิตโดยอัตโนมัติ ทำให้คุณได้ JSON payload ที่พร้อมใช้งานโดยไม่ต้องจัดการสตริงด้วยตนเอง

## นำเข้า Namespaces
ก่อนอื่นให้แน่ใจว่าคุณได้รวม Namespaces ที่จำเป็นเพื่อเข้าถึงฟังก์ชันของ Aspose.GIS ในโค้ดของคุณ:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## ขั้นตอนที่ 1: ตั้งค่า Document Directory
```csharp
string dataDir = "Your Document Directory";
```
แทนที่ "Your Document Directory" ด้วยเส้นทางจริงของโฟลเดอร์เอกสารของคุณ

## ขั้นตอนที่ 2: สร้าง Memory Stream
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## ขั้นตอนที่ 3: สร้าง Vector Layer ด้วย GeoJSON Driver
คลาส `VectorLayer` แทนชุดข้อมูลเวกเตอร์ที่สามารถบันทึกในหลายรูปแบบรวมถึง GeoJSON  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## ขั้นตอนที่ 4: กำหนด Feature Attributes
กำหนดสคีม่าแอตทริบิวต์สำหรับฟีเจอร์ของคุณ (เช่น ID, Name)  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## ขั้นตอนที่ 5: สร้างและเพิ่ม Features
สร้างอ็อบเจ็กต์ `Feature`, กำหนดเรขาคณิตจุด, ตั้งค่าแอตทริบิวต์, และเพิ่มลงในเลเยอร์  
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
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

ยินดีด้วย! คุณได้เขียน GeoJSON ไปยังสตรีมสำเร็จโดยใช้ Aspose.GIS for .NET

## ปัญหาที่พบบ่อยและวิธีแก้
- **สตรีมผลลัพธ์ว่าง:** ตรวจสอบให้แน่ใจว่าคุณรีเซ็ตตำแหน่งสตรีม (`stream.Position = 0`) ก่อนอ่าน.
- **ลำดับพิกัดไม่ถูกต้อง:** GeoJSON ต้องการลำดับลองจิจูด‑ละติจูด; ตรวจสอบค่าจุดของคุณ.
- **ชุดข้อมูลขนาดใหญ่:** ใช้ `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` เพื่อสตรีมฟีเจอร์แบบต่อเนื่อง.

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.GIS for .NET ในสภาพแวดล้อม Windows และ Linux ได้หรือไม่?
ใช่, Aspose.GIS for .NET เข้ากันได้กับระบบ Windows และ Linux ทั้งสอง

### มีการทดลองใช้ฟรีหรือไม่?
แน่นอน! คุณสามารถสำรวจการทดลองใช้ฟรีได้จาก [here](https://releases.aspose.com/)

### ฉันจะหาเอกสารรายละเอียดได้จากที่ไหน?
ดูเอกสารเพิ่มเติมได้ที่ [here](https://reference.aspose.com/gis/net/)

### ฉันจะขอรับใบอนุญาตชั่วคราวได้อย่างไร?
ใบอนุญาตชั่วคราวมีให้บริการที่ [here](https://purchase.aspose.com/temporary-license/)

### ต้องการความช่วยเหลือหรือมีคำถามเพิ่มเติม?
เยี่ยมชมฟอรั่มสนับสนุนของเราที่ [here](https://forum.aspose.com/c/gis/33)

**Q: ฉันสามารถสร้าง GeoJSON จากชุดจุดละติจูด/ลองจิจูดได้หรือไม่?**  
A: ใช่ – สร้าง `Feature` สำหรับแต่ละจุด, กำหนดเรขาคณิต `Point`, แล้วเพิ่มลงใน `VectorLayer`.

**Q: Aspose.GIS รองรับการเขียน GeoJSON แบบบีบอัด (gzip) หรือไม่?**  
A: คุณสามารถห่อ `MemoryStream` ด้วย `GZipStream` ก่อนบันทึกเพื่อสร้าง payload ที่บีบอัดได้.

**Q: ขนาดสูงสุดของไฟล์ GeoJSON ที่ Aspose.GIS สามารถจัดการได้คือเท่าไหร่?**  
A: ไลบรารีสามารถสตรีมไฟล์ที่ใหญ่กว่า 2 GB; การใช้หน่วยความจำต่ำเนื่องจากข้อมูลถูกเขียนแบบต่อเนื่อง.

---

**Last Updated:** 2026-05-21  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทเรียนที่เกี่ยวข้อง

- [วิธีอ่าน GeoJSON จากสตรีมด้วย Aspose.GIS for .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [วิธีแปลง GeoJSON เป็น TopoJSON ด้วย Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [วิธีแปลง Shapefile เป็น GeoJSON ด้วย Aspose.GIS for .NET](/gis/net/layer-management/extract-features-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}