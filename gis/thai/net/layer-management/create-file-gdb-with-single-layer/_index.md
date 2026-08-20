---
date: 2026-06-30
description: เรียนรู้วิธีสร้างเลเยอร์เวกเตอร์ใน File Geodatabase ด้วย Aspose.GIS สำหรับ
  .NET. จัดการข้อมูลเชิงพื้นที่ด้วยระบบอ้างอิงเชิงพื้นที่ WGS84 และตัวเลือก file gdb.
keywords:
- create vector layer
- add line feature
- manage geospatial data
- feature count example
- file gdb compression
linktitle: สร้าง File GDB ด้วยเลเยอร์เดียว
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  headline: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  type: TechArticle
- description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  name: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  steps:
  - name: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
    text: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
  - name: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
    text: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
  type: HowTo
- questions:
  - answer: It means adding a new vector dataset (points, lines, or polygons) to a
      geodatabase file.
    question: What does “create vector layer” mean?
  - answer: Aspose.GIS for .NET provides full support for File GDB creation and editing.
    question: Which library should I use?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `SpatialReferenceSystem.Wgs84` for the common WGS84 datum.
    question: Can I set the spatial reference?
  - answer: Less than 30 lines to create the GDB, add a line feature, and read back
      the feature count.
    question: How many lines of code?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: สร้างเลเยอร์เวกเตอร์ใน File GDB – Aspose.GIS .NET Tutorial
url: /th/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเลเยอร์เวกเตอร์ใน File GDB

## บทนำ
หากคุณต้องการ **create vector layer** ภายใน File Geodatabase (GDB) และจัดการข้อมูลเชิงพื้นที่อย่างมีประสิทธิภาพ Aspose.GIS for .NET จะมอบวิธีการแบบ code‑first ที่สะอาด ในคู่มือขั้นตอนนี้เราจะแสดงวิธีเขียนฟีเจอร์เส้น, กำหนดค่าตัวเลือกไฟล์ GDB, และทำงานกับ spatial reference WGS84 — ทั้งหมดในไม่กี่บรรทัดของ C# เมื่อเสร็จคุณจะสามารถนับจำนวนฟีเจอร์ในเลเยอร์และรวม GDB ที่ได้เข้ากับกระบวนการแมปหรือวิเคราะห์ใด ๆ บน .NET

## คำตอบสั้น
- **What does “create vector layer” mean?** หมายความว่าเป็นการเพิ่มชุดข้อมูลเวกเตอร์ใหม่ (points, lines, or polygons) ไปยังไฟล์ geodatabase  
- **Which library should I use?** Aspose.GIS for .NET ให้การสนับสนุนเต็มรูปแบบสำหรับการสร้างและแก้ไข File GDB  
- **Do I need a license for development?** การทดลองใช้ฟรีทำงานสำหรับการทดสอบ; จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานจริง  
- **Can I set the spatial reference?** ใช่ – ใช้ `SpatialReferenceSystem.Wgs84` สำหรับ datum WGS84 ที่ทั่วไป  
- **How many lines of code?** น้อยกว่า 30 บรรทัดเพื่อสร้าง GDB, เพิ่มฟีเจอร์เส้น, และอ่านจำนวนฟีเจอร์กลับมา  

## การดำเนินการ “create vector layer” คืออะไร?
การสร้างเลเยอร์เวกเตอร์กำหนดตารางใหม่ใน geodatabase ที่เก็บวัตถุเชิงเรขาคณิต (points, lines, polygons) และแอตทริบิวต์ของมัน แต่ละแถวแทนฟีเจอร์หนึ่งและคอลัมน์ geometry จะเก็บรูปร่างของฟีเจอร์นั้น ใน Aspose.GIS คุณสร้างโดยการสร้างอินสแตนซ์ของ `FeatureClass` ภายใน `FileGdbDataSource` และระบุประเภท geometry

## ทำไมต้องใช้ Aspose.GIS เพื่อสร้างเลเยอร์เวกเตอร์?
Aspose.GIS ขจัดการพึ่งพาภายนอกและรองรับ **50+** ฟอร์แมต GIS ทำให้เป็นโซลูชันครบวงจรสำหรับนักพัฒนา .NET  
มันให้การบีบอัด File GDB ในตัว (ลดขนาดได้ถึง 70 % สำหรับข้อมูลเวกเตอร์ทั่วไป) การทำดัชนีเชิงพื้นที่, และการจัดการ WGS84 อย่างเต็มรูปแบบโดยไม่ต้องตั้งค่าเพิ่มเติม ไลบรารีทำงานบน .NET Framework 4.6+, .NET Core 2.0+, และ .NET 5/6 จึงสามารถใช้ได้กับ Windows หรือสภาพแวดล้อมข้ามแพลตฟอร์มสมัยใหม่โดยไม่ต้องติดตั้งไลบรารีเนทีฟเพิ่มเติม

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามรายการต่อไปนี้:

1. **Aspose.GIS for .NET** – ดาวน์โหลดจากหน้า [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/)  
2. **A .NET development environment** – Visual Studio, Rider, หรือ `dotnet` CLI  
3. **A folder** ที่ File GDB จะถูกสร้าง (เราจะเรียกว่า *Your Document Directory*)

## นำเข้า Namespaces
คำสั่ง `using` จะนำประเภทที่จำเป็นเข้าสู่สโคป  

Namespace `Document` ให้วัตถุ GIS หลัก, ส่วน `System.IO` จัดการเส้นทางไฟล์

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```

## ขั้นตอนที่ 1: ตั้งค่า Your Document Directory
แทนที่ `"Your Document Directory"` ด้วยเส้นทางเต็มที่คุณต้องการให้ File GDB อยู่  
การสร้างโฟลเดอร์ล่วงหน้าช่วยหลีกเลี่ยงข้อผิดพลาด “File not found” ที่มักทำให้ผู้ใช้ใหม่ติดขัด

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้าง File Geodatabase พร้อมเลเยอร์เดียว
`FileGdbOptions` เป็นคลาสที่ให้คุณกำหนดค่าการบีบอัด, การทำดัชนีเชิงพื้นที่, และการตั้งค่าอื่น ๆ สำหรับ File Geodatabase  
โค้ดตัวอย่างนี้ **creates a vector layer** ด้วย `FileGdbOptions`, เขียนฟีเจอร์เส้นง่าย ๆ, และเก็บไว้ใน File GDB ที่ใช้ **spatial reference WGS84**

```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```

## ขั้นตอนที่ 3: เปิด File Geodatabase และดึงข้อมูลเลเยอร์
`FileGdbDataSource` เป็นจุดเริ่มต้นสำหรับการสร้างและเปิด File Geodatabases  
`FeatureClass` แทนเลเยอร์เวกเตอร์ภายใน geodatabase และให้เข้าถึงฟีเจอร์ต่าง ๆ  
ที่นี่เราจะ **count features in the layer** โดยเปิดชุดข้อมูลและพิมพ์จำนวนฟีเจอร์ – ในกรณีนี้คือ `1`

```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```

## คุณจะตรวจสอบว่าเลเยอร์ถูกสร้างอย่างถูกต้องได้อย่างไร?
เปิด geodatabase ด้วย `FileGdbDataSource.Open` และสอบถาม `FeatureClass` คุณสมบัติ `Count` จะคืนค่าจำนวนฟีเจอร์ทั้งหมด ยืนยันว่าเส้นได้ถูกบันทึกไว้ ขั้นตอนตรวจสอบอย่างรวดเร็วนี้ช่วยให้คุณจับข้อผิดพลาดได้ตั้งแต่แรก โดยเฉพาะเมื่อทำการนำเข้าจำนวนมากแบบอัตโนมัติ

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| **`File not found`** | ตัวแปร `path` ไม่ถูกต้อง | ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่มีอยู่และ `path` ถูกผสานกับชื่อไฟล์ เช่น `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | ใช้ประเภท geometry ที่ไม่อนุญาตใน File GDB | ใช้ `Point`, `LineString`, หรือ `Polygon` สำหรับเลเยอร์พื้นฐาน. |
| **`License not set`** | ทำงานโดยไม่มีใบอนุญาตที่ถูกต้องในสภาพการผลิต | ลงทะเบียนใบอนุญาตของคุณด้วย `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.GIS for .NET ในโครงการ .NET ที่มีอยู่ของฉันได้หรือไม่?
ใช่, Aspose.GIS for .NET สามารถผสานรวมอย่างราบรื่นกับโครงการ .NET ที่คุณมีอยู่แล้ว

### มีเวอร์ชันทดลองสำหรับ Aspose.GIS for .NET หรือไม่?
ใช่, คุณสามารถสำรวจคุณสมบัติของ Aspose.GIS for .NET ได้โดยดาวน์โหลด [free trial version](https://releases.aspose.com/)

### ฉันจะหาเอกสารรายละเอียดสำหรับ Aspose.GIS for .NET ได้จากที่ไหน?
ดูที่ [documentation](https://reference.aspose.com/gis/net/) เพื่อรับข้อมูลเชิงลึกทั้งหมดเกี่ยวกับ Aspose.GIS for .NET

### ฉันจะรับการสนับสนุนสำหรับ Aspose.GIS for .NET ได้อย่างไร?
เยี่ยมชม [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อรับการสนับสนุนจากชุมชนและความช่วยเหลือ

### มีใบอนุญาตชั่วคราวสำหรับ Aspose.GIS for .NET หรือไม่?
ใช่, คุณสามารถรับ [temporary license](https://purchase.aspose.com/temporary-license/) สำหรับ Aspose.GIS for .NET

---

**Last Updated:** 2026-06-30  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [สร้าง File Geodatabase .NET Dataset ด้วย Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [สร้าง Vector Layer และตั้งค่า Layer Spatial Reference System](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [วิธีลบ Layer จาก File GDB Dataset ด้วย Aspose.GIS](/gis/net/layer-data-operations/remove-layers-from-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}