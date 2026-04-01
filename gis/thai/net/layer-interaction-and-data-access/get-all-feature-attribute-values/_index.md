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

## การแนะนำ
ยินดีต้อนรับสู่โลกของการพัฒนาเชิงพื้นที่ด้วย Aspose.GIS for .NET! ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีอ่าน shapefile C#** และดึงค่าอีกครั้งทั้งหมดจากคุณสมบัติของระบบสร้างแอปแผนที่หรือข้อสังเกตข้อมูลเชิงพื้นที่เป็นชุดการตรวจหาการสกัดที่สำคัญอย่างยิ่งมาดูโค้ดการทำงานของอีกครั้ง

## คำตอบด่วน
- **โค้ดนี้ทำอะไร?** มันเปิด Shapefile และอ่านค่าได้ทั้งหมด, เป็นตัวอย่าง, หรือการถ่ายโอนข้อมูลตามปกติจากทุกๆ คน.
- **ต้องใช้ไลบรารีใด** Aspose.GIS สำหรับ .NET (เข้ากันได้กับ .NET Framework และ .NET Core)
- **ฉันจำเป็นต้องมีใบอนุญาตหรือไม่** ไลเซนส์ชั่วคราวเพื่อตรวจสอบ; ไลเซนส์เต็มความจำเป็นจริง.
- **ฉันสามารถอ่านรูปแบบอื่นๆ ได้หรือไม่** มีปัญหา – API เดียวกันกับ GeoJSON, KML, ประสิทธิภาพสูงมาก
- **จะถ่ายโอนข้อมูลแอตทริบิวต์อย่างไร** ใช้ `feature.GetValuesDump()` เพื่อรับอาเรย์ออบเจ็กต์ที่ต่อมา

## “อ่านเชพไฟล์ C#” คืออะไร?
ไดร์เวอร์ Shapefile ด้วย C# โดยทั่วไปไฟล์ .shp ด้วยไลบรารี GIS, วนมหัศจรรย์ผ่านฟังก์ชั่นของมัน, และประสิทธิภาพสูงที่เข้าถึงข้อมูลได้ที่ไหนบ้างที่ไฟล์ .dbf ที่มาพร้อมกัน Aspose.GIS การจัดการไฟล์ระดับต่ำออกไป, โฟกัสที่ค่าต่างๆ ที่ต้องการเข้าถึงข้อมูลที่ต้องการทราบ...

## เหตุใดจึงต้องใช้ Aspose.GIS เพื่ออ่านแอตทริบิวต์
- **Simple API** – คุณยังเข้าใจง่ายเช่น `GetValues` และ `GetValuesDump`.
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS ด้วย .NET Core
- **รองรับรูปแบบที่หลากหลาย** – การจัดการ Shapefile, GeoJSON, GML, การตรวจสอบเพิ่มเติมสามารถทำได้เพิ่มเติม
- **Performance‑optimized** – การวนซ้ำที่เร็วชุดข้อมูลขนาดใหญ่

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้นการเดินทางนี้ ขอสนับสนุนให้คุณทราบพร้อมในเรื่อง:
- Aspose.GIS for .NET: ดาวน์โหลดไลบรารีจาก [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/)
- สภาพแวดล้อมการพัฒนา: การพิจารณาการพัฒนา .NET เช่น Visual Studio.
- Shapefile: มี Shapefile อธิบายได้ (เช่น "InputShapeFile.shp") พร้อมด้วยในเอกสารของคุณ

## นำเข้าเนมสเปซ
ในโค้ด C# ของคุณ ให้เริ่มต้นด้วยการนำเข้า namespace ที่จำเป็นเพื่อใช้ฟังก์ชันของ Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
```csharp
string dataDir = "Your Document Directory";
```
แทนที่ "Your Document Directory" ด้วยพาธจริงที่เก็บ Shapefile ของคุณ

## ขั้นตอนที่ 2: เปิด VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
ขั้นตอนนี้เกี่ยวกับการเปิด Shapefile ด้วย Aspose.GIS โดยระบุพาธไฟล์และรูปแบบ (ในกรณีนี้คือ Shapefile)

## ขั้นตอนที่ 3: ดึงค่าแอตทริบิวต์ของฟีเจอร์ทั้งหมด
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

## ขั้นตอนที่ 4: ดึงค่าแอตทริบิวต์ของฟีเจอร์หลายรายการ
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

## ขั้นตอนที่ 5: ดึงค่าแอตทริบิวต์เป็น Object Dump
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

## ปัญหาทั่วไปและแนวทางแก้ไข
- **Array size mismatch** – ถ่ายทำเพื่อตรวจสอบอาเรย์ที่ส่งให้ `GetValues` ส่วนใหญ่จะใช้เวลาที่ที่เก็บข้อมูล; มิฉะนั้นคุณจะได้รับค่า `null`.
- **ไม่พบไฟล์** – การควบคุม `dataDir` ชี้ไปที่การควบคุมที่ถูกต้องและชื่อ Shapefile สะกดอย่างมีประสิทธิภาพ
- **ข้อยกเว้นใบอนุญาต** – หากพบเกี่ยวกับเรื่องนี้เซนส์ ให้ใช้เซนส์ชั่วคราวหรือเต็มก่อนเรียกใช้เมธอด API ใด ๆ

## คำถามที่พบบ่อย
### Aspose.GIS เข้ากันได้กับ .NET Core หรือไม่
สามารถทำได้, Aspose.GIS รองรับ .NET Core คุณสามารถดาวน์โหลดแอปพลิเคชันข้ามแพลตฟอร์มได้

### ฉันสามารถทำงานกับไฟล์ GIS รูปแบบต่างๆ โดยใช้ Aspose.GIS ได้หรือไม่
แน่นอน! Aspose.GIS รองรับรูปแบบที่แตกต่างกันและ Shapefile, GeoJSON, มีขนาดเล็กมาก

### มีฟอรัมชุมชนสำหรับการสนับสนุน Aspose.GIS หรือไม่
ไม่จำเป็นต้องรู้สึกยินดีและร่วมสนทนากับชุมชน Aspose.GIS ได้ที่ [support forum](https://forum.aspose.com/c/gis/33)

### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS ได้อย่างไร
หากต้องการรับไลเซนส์ชั่วคราวสำหรับการทดสอบจาก [ที่นี่](https://purchase.aspose.com/temporary-license/)

### ฉันจะหาเอกสารโดยละเอียดสำหรับ Aspose.GIS ได้ที่ไหน
เอกสารฉบับเต็มพร้อมให้ศึกษาได้ที่ [ที่นี่](https://reference.aspose.com/gis/net/)

### ฉันจะดึงเฉพาะแอตทริบิวต์ "ชื่อ" จากแต่ละคุณลักษณะได้อย่างไร
ใช้ `GetValues` กับอาเรย์ขนาดหนึ่งและส่งดัชนีของศูนย์ “Name”, หรือเรียก `feature["Name"]` โดยตรง

### อะไรคือความแตกต่างระหว่าง `GetValues` และ `GetValuesDump`?
`GetValues` เติมค่าในอาเรย์ที่จัดสรรไว้ล่วงหน้าด้วยค่าดิบ, ส่วน `GetValuesDump` คืนอาเรย์ออบเจ็กต์ที่สามารถวนลูปได้โดยไม่ต้องรู้สคีมาล่วงหน้า

---

**อัปเดตล่าสุด:** 2026-01-05  
**ทดสอบด้วย:** Aspose.GIS for .NET (latest release)  
**ผู้เขียน:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
