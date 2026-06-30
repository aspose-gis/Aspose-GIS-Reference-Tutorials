---
date: 2026-06-30
description: เรียนรู้วิธีเพิ่มเลเยอร์ไปยังชุดข้อมูล File GDB โดยใช้ Aspose.GIS พร้อมการอ้างอิงเชิงพื้นที่
  WGS84. ทำตามคำแนะนำทีละขั้นตอนนี้เพื่อเพิ่มเลเยอร์ใน .NET.
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: เพิ่มเลเยอร์ไปยังชุดข้อมูล File GDB
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: วิธีเพิ่มเลเยอร์ไปยังชุดข้อมูล File GDB ด้วยการอ้างอิงเชิงพื้นที่ WGS84 โดยใช้
  Aspose.GIS
url: /th/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มเลเยอร์ – spatial reference wgs84 กับ Aspose.GIS

## บทนำ
พร้อมที่จะเพิ่มประสิทธิภาพการทำงาน GIS ของคุณด้วย Aspose.GIS สำหรับ .NET หรือยัง? ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีเพิ่มเลเยอร์** ไปยังชุดข้อมูล File GDB พร้อมกับทำงานกับ **spatial reference WGS84** ระบบพิกัด เราจะเดินผ่านแต่ละขั้นตอน ตั้งแต่การเตรียมโฟลเดอร์ข้อมูลของคุณจนถึงการตรวจสอบเลเยอร์ที่สร้างใหม่ เพื่อให้คุณสามารถจัดการข้อมูลภูมิศาสตร์ได้อย่างมั่นใจและมีประสิทธิภาพ

## คำตอบด่วน
- **ระบบพิกัดหลักที่ใช้คืออะไร?** spatial reference wgs84 (WGS 84)  
- **ไลบรารีใดที่ให้ API?** Aspose.GIS for .NET  
- **ฉันต้องการใบอนุญาตสำหรับการทดสอบหรือไม่?** ใช่ – มีใบอนุญาต Aspose ชั่วคราวให้ใช้งาน  
- **ฉันสามารถเพิ่มแอตทริบิวต์ให้กับเลเยอร์ใหม่ได้หรือไม่?** แน่นอน คุณสามารถกำหนด feature attributes ได้ไม่จำกัดจำนวน  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## spatial reference wgs84 คืออะไร?
spatial reference wgs84 (World Geodetic System 1984) เป็นระบบพิกัดทางภูมิศาสตร์ที่ใช้กันอย่างแพร่หลายที่สุด มันกำหนดละติจูดและลองจิจูดเป็นองศาและทำหน้าที่เป็น CRS เริ่มต้นสำหรับชุดข้อมูล GIS จำนวนมาก รวมถึงชุดข้อมูลที่เราจะสร้างในคู่มือนี้

## ทำไมต้องใช้ Aspose.GIS เพื่อเพิ่มเลเยอร์?
โหลดข้อมูล GIS ของคุณโดยไม่ต้องใช้ไบนารีของบุคคลที่สามและรักษาการควบคุมเต็มรูปแบบเหนือการกำหนดสคีม่า Aspose.GIS รองรับ **40+ spatial reference systems**, สามารถประมวลผลไฟล์ที่ใหญ่กว่า **2 GB** โดยไม่ต้องโหลดชุดข้อมูลทั้งหมดเข้าสู่หน่วยความจำ และทำงานบน Windows, Linux, และ macOS สิ่งนี้ทำให้เป็นโซลูชันที่เชื่อถือได้, ข้ามแพลตฟอร์ม สำหรับการทำงานอัตโนมัติ GIS ระดับองค์กร

## ข้อกำหนดเบื้องต้น
- Aspose.GIS for .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Document Directory: สร้างโฟลเดอร์เฉพาะบนเครื่องของคุณเพื่อเก็บไฟล์ GIS.  
- ใบอนุญาต Aspose ชั่วคราว (ไม่บังคับสำหรับการประเมิน) – ดู FAQ ด้านล่างสำหรับลิงก์ดาวน์โหลด.

## นำเข้า Namespaces
เพิ่มคำสั่ง `using` ที่จำเป็นในโปรเจกต์ C# ของคุณเพื่อให้เข้าถึงคลาสของ Aspose.GIS:

*ไม่จำเป็นต้องมีบล็อกโค้ดที่นี่; เพียงเพิ่มบรรทัดต่อไปนี้ที่ส่วนบนของไฟล์ของคุณ:*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## ขั้นตอนที่ 1: คัดลอกไดเรกทอรี
**Definition anchor:** ชุดข้อมูล File GDB คือฐานข้อมูล ESRI แบบโฟลเดอร์ที่เก็บข้อมูลเชิงพื้นที่ในชุดไฟล์หลายไฟล์.  
แรกสุด ให้ทำสำเนาโฟลเดอร์ที่มีชุดข้อมูล GDB ดั้งเดิม การเก็บสำเนาช่วยปกป้องข้อมูลต้นฉบับขณะทดลอง.

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

## ขั้นตอนที่ 2: เปิดชุดข้อมูลและตรวจสอบความสามารถในการสร้าง
`Dataset` แสดงถึงคอลเลกชันของเลเยอร์ GIS ที่เก็บใน File GDB. เปิดชุดข้อมูลที่คัดลอกใหม่และยืนยันว่ามันสามารถสร้างเลเยอร์ใหม่ได้ คุณสมบัติ `CanCreateLayers` ควรคืนค่า **True**. **`CanCreateLayers` คือคุณสมบัติแบบบูลีนที่บ่งบอกว่าชุดข้อมูลสนับสนุนการสร้างเลเยอร์ใหม่หรือไม่.**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## ขั้นตอนที่ 3: สร้างและเติมข้อมูลให้เลเยอร์ใหม่ด้วย spatial reference wgs84
ตอนนี้เราจะสร้างเลเยอร์ชื่อ **data** และกำหนด spatial reference ให้เป็น **Wgs84** อย่างชัดเจน เรายังเพิ่มแอตทริบิวต์ง่าย ๆ ชื่อ **Name** และแทรกฟีเจอร์จุดหนึ่งจุด **`CreateLayer` creates a new layer in the dataset with the specified name and spatial reference.** **`SpatialReference` represents the coordinate system used by a layer.** **`Feature` is an individual geographic object (point, line, or polygon) stored in a layer.**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## ขั้นตอนที่ 4: เปิดและตรวจสอบเลเยอร์ที่เพิ่ม
สุดท้าย เปิดเลเยอร์ที่คุณสร้างขึ้นและตรวจสอบเนื้อหาของมัน คอนโซลจะแสดงว่าเลเยอร์มีฟีเจอร์หนึ่งรายการและแอตทริบิวต์ **Name** ตรงกับค่าที่เราตั้งไว้ **`Layer.Open` opens an existing layer for reading or editing.** สิ่งนี้ยืนยันว่าเลเยอร์ถูกเพิ่มอย่างถูกต้องและ spatial reference คือ WGS84.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## วิธีเพิ่มเลเยอร์ไปยังชุดข้อมูล File GDB?
โหลดชุดข้อมูล, เรียก `CreateLayer` พร้อมชื่อและ spatial reference ที่ต้องการ, กำหนดสคีม่าแอตทริบิวต์, แล้วแทรกฟีเจอร์ทั้งหมดนี้สามารถทำได้ด้วยการเรียกเมธอดของ Aspose.GIS เพียงไม่กี่ครั้ง และ API จะจัดการการล็อกไฟล์และการตรวจสอบสคีม่าโดยอัตโนมัติ กระบวนการนี้ทำให้แน่ใจว่าเลเยอร์ใหม่สอดคล้องกับ spatial reference ของชุดข้อมูล, คำจำกัดความของแอตทริบิวต์ถูกเก็บในสคีม่าเลเยอร์, และข้อมูลสามารถเข้าถึงได้โดยซอฟต์แวร์ GIS ใด ๆ ที่รองรับ File GDB.

## ปัญหาทั่วไปและเคล็ดลับ
- **Incorrect path:** ตรวจสอบให้แน่ใจว่า `dataDir` ลงท้ายด้วยตัวคั่นพาธ (`/` หรือ `\`) เพื่อให้สตริงที่ต่อกันเป็นเส้นทางไฟล์ที่ถูกต้อง.  
- **License errors:** หากคุณเห็นคำเตือนเกี่ยวกับใบอนุญาต, ให้ใช้ใบอนุญาตชั่วคราวจากพอร์ทัลของ Aspose ก่อนรันโค้ด.  
- **CRS mismatch:** เมื่อเปิดเลเยอร์ในเครื่องมือ GIS อื่นในภายหลัง, ให้ยืนยันว่าเครื่องมือนั้นรับรู้ WGS 84 (EPSG:4326) เป็นระบบพิกัด.  
- **Large datasets:** สำหรับชุดข้อมูลที่ใหญ่กว่า 1 GB, พิจารณาใช้ `Dataset.OpenReadOnly` เพื่อลดการใช้หน่วยความจำ.

## คำถามที่พบบ่อย
### Q: ฉันสามารถใช้ Aspose.GIS สำหรับ .NET ร่วมกับไลบรารี GIS อื่นได้หรือไม่?
A: ใช่, Aspose.GIS ทำงานอย่างอิสระแต่สามารถผสานกับไลบรารีเช่น GDAL หรือ NetTopologySuite สำหรับการประมวลผลขั้นสูง.

### Q: มีใบอนุญาตชั่วคราวสำหรับการทดสอบหรือไม่?
A: ใช่, คุณสามารถรับใบอนุญาตชั่วคราวจาก [here](https://purchase.aspose.com/temporary-license/) สำหรับการทดสอบและประเมินผล.

### Q: Aspose.GIS สำหรับ .NET รองรับระบบ spatial reference ใดบ้าง?
A: Aspose.GIS รองรับมากกว่า **40 EPSG codes**, รวมถึงระบบที่นิยมเช่น WGS84 (EPSG:4326), Web Mercator (EPSG:3857), และ NAD83 (EPSG:4269). สำรวจเอกสารที่ครอบคลุม [here](https://reference.aspose.com/gis/net/).

### Q: ฉันสามารถมีส่วนร่วมกับชุมชน Aspose.GIS ได้หรือไม่?
A: แน่นอน! เข้าร่วมการสนทนาและแบ่งปันประสบการณ์ของคุณใน [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### Q: ฉันจะหาเอกสารรายละเอียดของ Aspose.GIS สำหรับ .NET ได้จากที่ไหน?
A: สำรวจเอกสารที่ครอบคลุม [here](https://reference.aspose.com/gis/net/) เพื่อรับข้อมูลเชิงลึกเกี่ยวกับคลาส, เมธอด, และแนวปฏิบัติที่ดีที่สุดทั้งหมด.

---

**อัปเดตล่าสุด:** 2026-06-30  
**ทดสอบด้วย:** Aspose.GIS for .NET (latest stable version)  
**ผู้เขียน:** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## บทแนะนำที่เกี่ยวข้อง

- [สร้าง File Geodatabase .NET Dataset ด้วย Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [สร้าง Vector Layer ใน File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [สร้าง File GDB Dataset และตั้งค่าความคลาดเคลื่อนสำหรับเลเยอร์](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}