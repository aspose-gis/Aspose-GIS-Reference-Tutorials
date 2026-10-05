---
date: 2026-10-05
description: เรียนรู้วิธีอ่าน geojson จาก stream ด้วย Aspose.GIS for .NET คู่มือ step‑by‑step
  นี้แสดงวิธีโหลด geojson stream, parse, และ extract properties ใน C#.
keywords:
- how to read geojson
- load geojson stream
- parse geojson c#
- open geojson layer
- extract geojson properties
lastmod: 2026-10-05
linktitle: อ่าน GeoJSON จาก Stream
og_description: เรียนรู้วิธีอ่าน geojson จาก stream ด้วย Aspose.GIS for .NET รวมถึงการ
  parsing, การเปิด geojson layer, และการ extract properties ใน C#.
og_image_alt: Tutorial guide showing how to read geojson from a stream with Aspose.GIS
  in C#
og_title: วิธีอ่าน geojson จาก stream ด้วย Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  headline: How to read geojson from a stream with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  name: How to read geojson from a stream with Aspose.GIS for .NET
  steps:
  - name: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
    text: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
  - name: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
    text: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
  type: HowTo
- questions:
  - answer: Aspose.GIS for .NET – it handles 30+ GIS formats out of the box.
    question: What library should I use?
  - answer: Yes – call `VectorLayer.Open` with `AbstractPath.FromStream`.
    question: Can I read GeoJSON directly from a stream?
  - answer: A free trial works for testing; a full license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Which .NET versions are supported?
  - answer: Absolutely – use `GetValue<T>(columnName)` on a feature.
    question: Is extracting properties simple?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET GIS
- C# geospatial
title: วิธีอ่าน geojson จาก stream ด้วย Aspose.GIS for .NET
url: /th/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีอ่าน geojson จากสตรีมด้วย Aspose.GIS สำหรับ .NET

## บทนำ
หากคุณกำลังสงสัย **วิธีอ่าน geojson** ในแอปพลิเคชัน .NET คุณมาถูกที่แล้ว ในบทเรียนนี้เราจะพาคุณผ่านตัวอย่าง **C# GeoJSON example** ที่ครบถ้วน ซึ่งจะแสดงวิธีแปลงสตริง GeoJSON, **load geojson stream** ไปยัง memory stream, เปิดชั้น GeoJSON, และดึงคุณสมบัติ GeoJSON ด้วย Aspose.GIS เมื่อเสร็จแล้วคุณจะได้รูปแบบที่นำกลับมาใช้ใหม่ได้ซึ่งสามารถใส่ลงในโปรเจกต์ใดก็ได้ที่ต้องทำงานกับข้อมูลเชิงพื้นที่

## คำตอบอย่างรวดเร็ว
- **ควรใช้ไลบรารีอะไร?** Aspose.GIS for .NET – รองรับรูปแบบ GIS มากกว่า 30 แบบโดยอัตโนมัติ  
- **สามารถอ่าน GeoJSON โดยตรงจากสตรีมได้หรือไม่?** ใช่ – เรียก `VectorLayer.Open` พร้อม `AbstractPath.FromStream`.  
- **ต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** ไลเซนส์ทดลองฟรีใช้สำหรับการทดสอบ; ต้องมีไลเซนส์เต็มสำหรับการใช้งานจริง.  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **การดึงคุณสมบัติง่ายหรือไม่?** แน่นอน – ใช้ `GetValue<T>(columnName)` บนฟีเจอร์.

**VectorLayer.Open** เปิดชั้น GIS จากแหล่งข้อมูลเช่นไฟล์หรือสตรีม. **AbstractPath.FromStream** สร้างอ็อบเจกต์ abstract path ที่แทนสตรีมที่ให้ไว้สำหรับไดรเวอร์ GIS. **GetValue<T>(columnName)** อ่านค่าของแอตทริบิวต์ที่ระบุจากฟีเจอร์และคืนค่าเป็นประเภท T.

## วิธีการอ่าน geojson คืออะไร?
การอ่าน geojson คือกระบวนการแปลงสตริงหรือสตรีมที่อยู่ในรูปแบบ GeoJSON ให้เป็นอ็อบเจกต์ฟีเจอร์ทางภูมิศาสตร์ในหน่วยความจำ. รูปแบบนี้เข้ารหัสจุด, เส้น, และโพลิกอนโดยใช้ JSON ทำให้การแลกเปลี่ยนข้อมูลเชิงพื้นที่ระหว่างเว็บเซอร์วิส, ฐานข้อมูล, และแอปพลิเคชันไคลเอนต์เป็นเรื่องง่าย. เมื่อทำการพาร์เซแล้ว คุณสามารถสอบถาม, แก้ไข, หรือแสดงผลฟีเจอร์ด้วยไลบรารี .NET ที่รองรับ GIS ใดก็ได้ เช่น Aspose.GIS.

## ทำไมต้องใช้ Aspose.GIS เพื่อเปิดชั้น geojson?
Aspose.GIS ให้คุณเปิดชั้น GeoJSON โดยตรงจากสตรีม, ลดความจำเป็นในการใช้ไฟล์ชั่วคราวและลดภาระ I/O. ไลบรารีนี้รองรับรูปแบบ GIS มากกว่า 30 แบบและสามารถประมวลผลไฟล์ขนาดถึง 2 GB ได้โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ, ซึ่งเหมาะกับชุดข้อมูลขนาดใหญ่. นอกจากนี้ยังทำการปรับระบบพิกัดอ้างอิงโดยอัตโนมัติ, ทำให้คุณโฟกัสที่ตรรกะธุรกิจแทนการพาร์เซระดับต่ำ.

## เมื่อใดที่คุณควรโหลดสตรีม geojson?
คุณจะโหลดสตรีม GeoJSON เมื่อคุณได้รับข้อมูลเชิงพื้นที่จาก API, จำเป็นต้องจัดการไฟล์ที่ผู้ใช้อัปโหลดโดยไม่ต้องบันทึกลงดิสก์, หรือสร้าง GeoJSON แบบเรียลไทม์จากการคิวรีฐานข้อมูล. การสตรีมช่วยหลีกเลี่ยงการเขียนดิสก์ที่ไม่จำเป็น, ปรับปรุงประสิทธิภาพในสถานการณ์ที่มีการส่งผ่านข้อมูลสูง, และทำให้แอปพลิเคชันของคุณไม่มีสถานะ, ซึ่งมีคุณค่าอย่างยิ่งในไมโครเซอร์วิสแบบคลาวด์‑เนทีฟ.

## ข้อกำหนดเบื้องต้น
1. **พื้นฐานความรู้ของ C#** – คุณควรคุ้นเคยกับไวยากรณ์ .NET และ IDE ของ Visual Studio.  
2. **ติดตั้ง Aspose.GIS** – ดาวน์โหลดไลบรารีจาก [หน้าดาวน์โหลด Aspose.GIS .NET](https://releases.aspose.com/gis/net/).  
3. **สภาพแวดล้อมการพัฒนา** – Visual Studio, Visual Studio Code, หรือ JetBrains Rider จะทำงานได้ดี.  

## นำเข้า namespace
`Aspose.GIS` namespace ให้คลาส GIS หลัก. `System.IO` ให้ `MemoryStream`, และ `System.Text` มียูทิลิตี้การเข้ารหัส UTF‑8. การนำเข้า namespace เหล่านี้ทำให้โค้ดต่อไปสั้นและอ่านง่าย.

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## ขั้นตอนที่ 1: แปลงสตริง geojson – ตัวอย่าง C# GeoJSON
แรกเราจะสร้างสตริง JSON ที่แสดง `FeatureCollection` อย่างง่าย. นี่คือส่วน **convert geojson string** ของกระบวนการทำงาน.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## ขั้นตอนที่ 2: โหลดสตรีม geojson และดึงคุณสมบัติ geojson
ต่อไปเราจะใส่สตริงลงใน `MemoryStream`, เปิดเป็นชั้น GIS, และสาธิตวิธีอ่านค่าแอตทริบิวต์ (ขั้นตอน **extract geojson properties**).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **เคล็ดลับ:** `VectorLayer.Open` ตรวจจับรูปแบบ GeoJSON โดยอัตโนมัติเมื่อคุณส่ง `Drivers.GeoJson`. คุณยังสามารถเปิดไฟล์โดยตรงโดยระบุเส้นทางไฟล์แทนสตรีมได้.

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **รูปแบบ JSON ไม่ถูกต้อง** | ตรวจสอบว่าสตริง GeoJSON มีรูปแบบที่ถูกต้อง; ใช้ตัวตรวจสอบ JSON. |
| **ปัญหาการเข้ารหัส** | ตรวจสอบให้สตรีมใช้ UTF‑8 (`Encoding.UTF8.GetBytes`). |
| **ไม่มีคุณสมบัติ** | ตรวจสอบว่าชื่อคุณสมบัติมีการสะกดถูกต้อง (`"name"` ในตัวอย่าง). |
| **ข้อยกเว้นไลเซนส์** | ใช้ไลเซนส์ทดลองสำหรับการทดสอบ; ใช้ไลเซนส์ถาวรสำหรับการผลิต. |

## คำถามที่พบบ่อย
### Aspose.GIS รองรับรูปแบบ GIS อื่นหรือไม่?
ใช่, Aspose.GIS รองรับ GeoJSON, Shapefile, KML, GML, และรูปแบบเพิ่มเติมกว่า 20 รูปแบบ, ทำให้คุณสามารถสลับแหล่งข้อมูลได้โดยไม่ต้องเปลี่ยนโค้ด.

### ฉันสามารถทดลองใช้ Aspose.GIS ก่อนซื้อได้หรือไม่?
คุณสามารถดาวน์โหลดรุ่นทดลองฟรีของ Aspose.GIS ได้จาก [หน้าดาวน์โหลดทดลองใช้ Aspose.GIS](https://releases.aspose.com/).

### ฉันจะหาเอกสารสำหรับ Aspose.GIS ได้ที่ไหน?
คุณสามารถค้นหาเอกสารสำหรับ Aspose.GIS ได้ที่ [อ้างอิง API .NET ของ Aspose.GIS](https://reference.aspose.com/gis/net/).

### ฉันจะรับการสนับสนุนสำหรับ Aspose.GIS อย่างไร?
คุณสามารถรับการสนับสนุนสำหรับ Aspose.GIS ได้ที่ [ฟอรั่ม Aspose GIS](https://forum.aspose.com/c/gis/33).

### ฉันต้องการไลเซนส์ชั่วคราวเพื่อใช้ Aspose.GIS หรือไม่?
คุณสามารถรับไลเซนส์ชั่วคราวสำหรับ Aspose.GIS ได้จาก [หน้าขอไลเซนส์ชั่วคราว](https://purchase.aspose.com/temporary-license/).

## สรุป
ในคู่มือนี้เราได้ครอบคลุม **how to read geojson** จาก memory stream ด้วย Aspose.GIS สำหรับ .NET, แสดงขั้นตอนการทำงาน **C# read geojson**, และสาธิตวิธี **extract geojson properties** จากชั้นที่เปิด. ด้วยขั้นตอนเหล่านี้คุณสามารถผสานการจัดการข้อมูลเชิงพื้นที่เข้ากับแอปพลิเคชัน .NET ใดก็ได้อย่างราบรื่น.

---

**อัปเดตล่าสุด:** 2026-10-05  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [วิธีเขียน GeoJSON ไปยังสตรีมด้วย Aspose.GIS สำหรับ .NET](/gis/net/layer-data-operations/write-geojson-to-stream/)
- [วิธีแปลง GeoJSON เป็น GDB ด้วย Aspose.GIS สำหรับ .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [แปลง Shapefile เป็น GeoJSON ด้วย Aspose.GIS สำหรับ .NET](/gis/net/layer-management/extract-features-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}