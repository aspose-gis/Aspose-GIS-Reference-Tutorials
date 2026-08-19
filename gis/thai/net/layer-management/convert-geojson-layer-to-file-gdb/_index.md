---
date: 2026-06-20
description: เรียนรู้วิธีแปลง geojson เป็น gdb ด้วย Aspose.GIS สำหรับ .NET คู่มือขั้นตอนต่อขั้นตอนนี้ครอบคลุมการอ่าน
  GeoJSON ใน C#, การสร้าง File Geodatabase และการจัดการปัญหาทั่วไป
keywords:
- convert geojson to gdb
- how to convert geojson
- read geojson c#
- asp.net geojson conversion
linktitle: แปลงชั้น GeoJSON เป็น GDB
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to convert geojson to gdb with Aspose.GIS for .NET. This
    step‑by‑step guide covers reading GeoJSON in C#, creating a File Geodatabase,
    and handling common issues.
  headline: How to Convert GeoJSON to GDB Using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Converting a GeoJSON layer to a GDB with Aspose.GIS for .NET.
    question: What does this guide teach?
  - answer: '*convert geojson to gdb*.'
    question: Which primary keyword is targeted?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Supported .NET versions?
  - answer: Roughly 10‑15 minutes for a basic conversion.
    question: Implementation time?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: วิธีแปลง GeoJSON เป็น GDB ด้วย Aspose.GIS สำหรับ .NET
url: /th/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแปลง GeoJSON เป็น GDB ด้วย Aspose.GIS สำหรับ .NET

## บทนำ
หากคุณกำลังมองหา **convert geojson to gdb** อย่างรวดเร็วและเชื่อถือได้ คุณอยู่ในที่ที่ถูกต้อง tutorial นี้จะพาคุณผ่านทุกขั้นตอน ตั้งแต่การอ่านไฟล์ GeoJSON ใน C# ไปจนถึงการสร้าง File Geodatabase (GDB) ด้วย Aspose.GIS คุณจะได้เห็นว่าทำไม Aspose.GIS ถึงเป็นไลบรารีที่นิยมสำหรับการแปลงข้อมูลเชิงพื้นที่ วิธีตั้งค่าสภาพแวดล้อม และวิธีรันการแปลงในเวลาไม่กี่นาที

## คำตอบสั้น
- **คู่มือนี้สอนอะไร?** การแปลงเลเยอร์ GeoJSON เป็น GDB ด้วย Aspose.GIS สำหรับ .NET.  
- **คำหลักหลักที่มุ่งเป้า?** *convert geojson to gdb*.  
- **ฉันต้องการใบอนุญาตหรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการทดสอบ; จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานจริง.  
- **เวอร์ชัน .NET ที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **เวลาการดำเนินการ?** ประมาณ 10‑15 นาทีสำหรับการแปลงพื้นฐาน.

## GeoJSON คืออะไรและ File GDB คืออะไร?
GeoJSON เป็นรูปแบบที่มีน้ำหนักเบาและเป็นข้อความสำหรับฟีเจอร์ทางภูมิศาสตร์ ในขณะที่ File GDB เป็นฐานข้อมูลเชิงพื้นที่ ESRI ประสิทธิภาพสูงที่อิงโฟลเดอร์  
GeoJSON เก็บจุด, เส้น, และโพลิกอนเป็นข้อความธรรมดา ทำให้ง่ายต่อการแชร์และแก้ไข ในขณะที่ File GDB เก็บข้อมูลในไฟล์ไบนารีที่ให้การสืบค้นเชิงพื้นที่ที่รวดเร็วและการจัดการแอตทริบิวต์ที่แข็งแรง  
ร่วมกันพวกเขาครอบคลุมทั้งการแลกเปลี่ยนที่เป็นมิตรกับเว็บและการประมวลผล GIS บนเดสก์ท็อปที่ความเร็วสูง

## ทำไมต้องใช้ Aspose.GIS สำหรับการแปลงข้อมูลเชิงพื้นที่?
Aspose.GIS ให้ API เดียวที่สอดคล้องกันซึ่งซ่อนความแปลกประหลาดของแต่ละรูปแบบ มันรองรับ **30+ รูปแบบเชิงพื้นที่**, สามารถประมวลผลไฟล์ขนาดถึง **2 GB** โดยไม่ต้องโหลดชุดข้อมูลทั้งหมดเข้าสู่หน่วยความจำ และอัตโนมัติรักษาระบบอ้างอิงพิกัด นั่นหมายความว่าคุณใช้เวลาน้อยลงในการเขียนพาร์เซอร์และใช้เวลามากขึ้นในการสร้างตรรกะของแอปพลิเคชันของคุณ

## ข้อกำหนดเบื้องต้น
- ความคุ้นเคยกับ C# และโครงสร้างโปรเจกต์ .NET  
- ติดตั้ง Aspose.GIS สำหรับ .NET หากคุณยังไม่ได้ติดตั้ง ดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/gis/net/) และทำตามคู่มือการติดตั้ง คุณยังสามารถสำรวจผลิตภัณฑ์ Aspose อื่น ๆ ได้ที่ [ที่นี่](https://releases.aspose.com/)

## นำเข้า Namespaces
ขั้นตอนแรกคือการนำ namespaces ที่จำเป็นเข้าสู่สโคป

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## วิธีอ่าน GeoJSON ใน C#?
โหลดไฟล์ GeoJSON ด้วยคลาส `GeoJsonReader` ซึ่งทำการพาร์ส JSON และสร้าง `FeatureCollection` ในหน่วยความจำ ตัวอ่านจะตรวจจับระบบอ้างอิงพิกัดโดยอัตโนมัติ ดังนั้นคุณไม่ต้องจัดการการพาร์ส CRS ด้วยตนเอง มันยังรองรับการสตรีมไฟล์ขนาดใหญ่ การรักษาชนิดแอตทริบิวต์ และสามารถรวมกับการแปลงรูปทรงเรขาคณิตแบบกำหนดเองได้หากต้องการ

```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Add attributes
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    // Construct and add features
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```

## ขั้นตอนที่ 1: ตั้งค่าเลเยอร์ GeoJSON
สร้างไฟล์ GeoJSON ชั่วคราวที่มีแอตทริบิวต์และฟีเจอร์ที่คุณต้องการแปลง ตัวอย่างนี้เพิ่มฟีเจอร์จุดสองจุดแบบง่าย

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## ขั้นตอนที่ 2: คัดลอกชุดข้อมูลทดสอบ
เพื่อให้ข้อมูลทดสอบต้นฉบับไม่ถูกแก้ไข ให้ทำสำเนาชุดข้อมูล File GDB ที่มีอยู่ นี่จะทำให้สภาพแวดล้อมสำหรับการแปลงสะอาด

```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copy attributes
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Add features
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```

## ขั้นตอนที่ 3: แปลง GeoJSON เป็น GDB
`FileGdb` แทนคอนเทนเนอร์ File Geodatabase และให้เมธอดสำหรับจัดการเลเยอร์ เปิดเลเยอร์ GeoJSON, สร้างเลเยอร์ใหม่ภายใน File GDB ที่คัดลอก, คัดลอกแอตทริบิวต์, และถ่ายโอนแต่ละฟีเจอร์ นี่คือแกนหลักของกระบวนการ **Aspose.GIS conversion** process

CODE_BLOCK_PLACEHOLDER_4_END

## วิธีแปลง GeoJSON เป็น GDB?
โหลด GeoJSON ด้วย `GeoJsonReader`, สร้างอ็อบเจ็กต์ `FileGdb` ที่ชี้ไปยังโฟลเดอร์ปลายทางของคุณ, สร้างเลเยอร์ฟีเจอร์ใหม่, แล้วทำการวนซ้ำแต่ละฟีเจอร์เพื่อแทรกเข้าไป ในทางปฏิบัติเป็นกระบวนการสามขั้นตอน—อ่าน, สร้าง, คัดลอก—ที่เสร็จภายในน้อยกว่านาทีสำหรับชุดข้อมูลทั่วไป

## ปัญหาที่พบบ่อยและวิธีแก้ไข
- **Missing spatial reference:** ตรวจสอบให้แน่ใจว่า GeoJSON ต้นทางมีการกำหนด CRS หรือกำหนด `SpatialReferenceSystem.Wgs84` อย่างชัดเจนเมื่อสร้างเลเยอร์ GDB.  
- **Attribute type mismatch:** ชนิดข้อมูลแอตทริบิวต์ใน GeoJSON ต้องตรงกับสคีมาที่เป้าหมาย; หากไม่เช่นนั้น Aspose.GIS จะโยนข้อยกเว้น.  
- **File access errors:** ตรวจสอบว่าโฟลเดอร์ปลายทางมีสิทธิ์เขียนและไม่มีโปรเซสอื่นล็อกไฟล์ GDB.

## คำถามที่พบบ่อย
### Aspose.GIS รองรับ .NET Framework ล่าสุดหรือไม่?
ใช่, Aspose.GIS ทำงานกับ .NET Framework 4.5+, .NET Core 3.1+, .NET 5, และ .NET 6+.

### ฉันสามารถแปลงรูปแบบเชิงพื้นที่อื่นด้วย Aspose.GIS ได้หรือไม่?
แน่นอน! Aspose.GIS รองรับรูปแบบอินพุตและเอาต์พุตมากกว่า 30 รูปแบบ รวมถึง Shapefile, KML, GML, และ SQLite.

### มีเวอร์ชันทดลองสำหรับ Aspose.GIS หรือไม่?
ใช่, คุณสามารถสำรวจฟังก์ชันของ Aspose.GIS โดยดาวน์โหลดเวอร์ชันทดลองได้จาก [ที่นี่](https://releases.aspose.com/).

### ฉันจะขอรับการสนับสนุนสำหรับคำถามที่เกี่ยวกับ Aspose.GIS ได้อย่างไร?
ไปที่ฟอรั่ม Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) เพื่อรับการช่วยเหลือจากชุมชนและทีมผลิตภัณฑ์

### ฉันสามารถรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS ได้หรือไม่?
ใช่, คุณสามารถรับใบอนุญาตชั่วคราวได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/).

---

**อัปเดตล่าสุด:** 2026-06-20  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [สร้างชุดข้อมูล File Geodatabase .NET ด้วย Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [อ่านฟีเจอร์จาก File Geodatabase ใน Aspose.GIS](/gis/net/layer-data-operations/read-features-from-file-geodatabase/)
- [สร้างเลเยอร์เวกเตอร์ใน File GDB – บทแนะนำ Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}