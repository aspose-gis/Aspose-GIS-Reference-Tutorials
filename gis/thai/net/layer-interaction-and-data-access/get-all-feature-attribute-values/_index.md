---
date: 2026-01-05
description: เรียนรู้วิธีอ่านไฟล์ shapefile ด้วย C# โดยใช้ Aspose.GIS สำหรับ .NET,
  ดึงค่าคุณลักษณะของฟีเจอร์ทั้งหมด, และทำการดัมพ์คุณลักษณะอย่างมีประสิทธิภาพ.
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: อ่าน Shapefile ด้วย C# – ดึงค่าคุณลักษณะทั้งหมดของฟีเจอร์
url: /th/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# รับค่าคุณลักษณะทั้งหมดของฟีเจอร์

## Introduction
ยินดีต้อนรับสู่โลกของการพัฒนาเชิงพื้นที่ด้วย Aspose.GIS for .NET! ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีอ่าน shapefile C#** และดึงค่าคุณลักษณะทั้งหมดจากฟีเจอร์ของมัน ไม่ว่าคุณจะสร้างแอปแผนที่หรือประมวลผลข้อมูลเชิงพื้นที่เป็นชุด การเชี่ยวชาญการสกัดคุณลักษณะเป็นสิ่งสำคัญ มาดูโค้ดที่ทำงานกันเลย

## Quick Answers
- **What does this code do?** มันเปิด Shapefile และอ่านค่าคุณลักษณะทั้งหมด, บางส่วน, หรือ dump ค่าคุณลักษณะจากแต่ละฟีเจอร์.  
- **Which library is required?** Aspose.GIS for .NET (compatible with .NET Framework and .NET Core).  
- **Do I need a license?** ไลเซนส์ชั่วคราวใช้สำหรับการทดสอบ; ไลเซนส์เต็มจำเป็นสำหรับการใช้งานจริง.  
- **Can I read other formats?** ใช่ – API เดียวกันรองรับ GeoJSON, KML, และอื่น ๆ อีกมาก.  
- **How to dump attributes?** ใช้ `feature.GetValuesDump()` เพื่อรับอาเรย์ออบเจ็กต์ที่ยืดหยุ่น.

## What is “read shapefile C#”?
การอ่าน Shapefile ด้วย C# หมายถึงการเปิดไฟล์ .shp ด้วยไลบรารี GIS, วนลูปผ่านฟีเจอร์เวกเตอร์ของมัน, และเข้าถึงข้อมูลคุณลักษณะที่เก็บไว้ในไฟล์ .dbf ที่มาพร้อมกัน Aspose.GIS ทำหน้าที่แยกการจัดการไฟล์ระดับต่ำออกไป ทำให้คุณโฟกัสที่ค่าคุณลักษณะที่ต้องการได้อย่างง่ายดาย

## Why use Aspose.GIS to read attributes?
- **Simple API** – วิธีการที่เข้าใจง่ายเช่น `GetValues` และ `GetValuesDump`.  
- **Cross‑platform** – ทำงานบน Windows, Linux, และ macOS ด้วย .NET Core.  
- **Rich format support** – จัดการ Shapefile, GeoJSON, GML, และอื่น ๆ โดยไม่ต้องใช้ปลั๊กอินเพิ่มเติม.  
- **Performance‑optimized** – การวนซ้ำที่เร็วสำหรับชุดข้อมูลขนาดใหญ่.

## Prerequisites
ก่อนที่เราจะเริ่มการเดินทางที่น่าตื่นเต้นนี้ โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมอยู่แล้ว:
- Aspose.GIS for .NET: ดาวน์โหลดและติดตั้งไลบรารีจาก [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).
- Development Environment: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET เช่น Visual Studio.
- Shapefile: มี Shapefile ตัวอย่าง (เช่น "InputShapeFile.shp") พร้อมในไดเรกทอรีเอกสารของคุณ.

## Import Namespaces
ในโค้ด C# ของคุณ ให้เริ่มต้นด้วยการนำเข้า namespace ที่จำเป็นเพื่อใช้ฟังก์ชันของ Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

## Step 1: Set the Document Directory
```csharp
string dataDir = "Your Document Directory";
```
แทนที่ "Your Document Directory" ด้วยพาธจริงที่เก็บ Shapefile ของคุณ

## Step 2: Open the VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
ขั้นตอนนี้เกี่ยวกับการเปิด Shapefile ด้วย Aspose.GIS โดยระบุพาธไฟล์และรูปแบบ (ในกรณีนี้คือ Shapefile)

## Step 3: Retrieve All Feature Attribute Values
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
โค้ดส่วนนี้แสดง **วิธีอ่านคุณลักษณะ** ของทุกฟีเจอร์โดยโหลดเข้าอาเรย์ขนาดคงที่

## Step 4: Retrieve Several Feature Attribute Values
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
ที่นี่เราสาธิต **วิธีอ่านค่าคุณลักษณะเฉพาะ** เมื่อคุณต้องการเพียงบางฟิลด์เท่านั้น

## Step 5: Retrieve Attribute Values as Objects Dump
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
ขั้นตอนสุดท้ายนี้แสดง **วิธี dump คุณลักษณะ** ด้วย `GetValuesDump()` ซึ่งจะคืนคอลเลกชันแบบยืดหยุ่นที่คุณสามารถตรวจสอบหรือทำการ serialize ได้

## Common Issues and Solutions
- **Array size mismatch** – ตรวจสอบให้แน่ใจว่าอาเรย์ที่ส่งให้ `GetValues` มีขนาดตรงกับจำนวนคุณลักษณะที่คาดหวัง; มิฉะนั้นคุณจะได้รับค่า `null`.  
- **File not found** – ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่ถูกต้องและชื่อ Shapefile ถูกสะกดอย่างแม่นยำ.  
- **License exception** – หากพบข้อผิดพลาดเกี่ยวกับไลเซนส์ ให้ใช้ไลเซนส์ชั่วคราวหรือเต็มก่อนเรียกใช้เมธอด API ใด ๆ.

## Frequently Asked Questions
### Is Aspose.GIS compatible with .NET Core?
ใช่, Aspose.GIS รองรับ .NET Core อย่างเต็มที่ ทำให้คุณสามารถสร้างแอปพลิเคชันข้ามแพลตฟอร์มได้

### Can I work with different GIS file formats using Aspose.GIS?
แน่นอน! Aspose.GIS รองรับรูปแบบต่าง ๆ รวมถึง Shapefile, GeoJSON, และอื่น ๆ อีกมาก

### Is there a community forum for Aspose.GIS support?
ใช่, คุณสามารถขอความช่วยเหลือและร่วมสนทนากับชุมชน Aspose.GIS ได้ที่ [support forum](https://forum.aspose.com/c/gis/33)

### How can I obtain a temporary license for Aspose.GIS?
คุณสามารถรับไลเซนส์ชั่วคราวสำหรับการทดสอบได้จาก [here](https://purchase.aspose.com/temporary-license/)

### Where can I find detailed documentation for Aspose.GIS?
เอกสารฉบับเต็มพร้อมให้ศึกษาได้ที่ [here](https://reference.aspose.com/gis/net/)

### How do I retrieve only the “Name” attribute from each feature?
ใช้ `GetValues` กับอาเรย์ขนาดหนึ่งและส่งดัชนีของฟิลด์ “Name”, หรือเรียก `feature["Name"]` โดยตรง

### What is the difference between `GetValues` and `GetValuesDump`?
`GetValues` เติมค่าในอาเรย์ที่จัดสรรไว้ล่วงหน้าด้วยค่าดิบ, ส่วน `GetValuesDump` คืนอาเรย์ออบเจ็กต์ที่สามารถวนลูปได้โดยไม่ต้องรู้สคีมาล่วงหน้า

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-01-05  
**ทดสอบด้วย:** Aspose.GIS for .NET (latest release)  
**ผู้เขียน:** Aspose  

---