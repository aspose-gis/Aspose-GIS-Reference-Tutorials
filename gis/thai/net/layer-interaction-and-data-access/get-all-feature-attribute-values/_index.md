---
title: รับค่าคุณสมบัติคุณสมบัติทั้งหมด
linktitle: รับค่าคุณสมบัติคุณสมบัติทั้งหมด
second_title: Aspose.GIS .NET API
description: สำรวจการพัฒนาเชิงพื้นที่ด้วย Aspose.GIS สำหรับ .NET! ดึงค่าคุณลักษณะคุณลักษณะได้อย่างราบรื่น ดาวน์โหลดตอนนี้เพื่อการผจญภัยในการเขียนโค้ดเชิงพื้นที่
weight: 15
url: /th/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# รับค่าคุณสมบัติคุณสมบัติทั้งหมด

## การแนะนำ
ยินดีต้อนรับสู่โลกแห่งการพัฒนาเชิงพื้นที่ด้วย Aspose.GIS สำหรับ .NET! ไลบรารีอันทรงพลังนี้ช่วยให้นักพัฒนาสามารถรวมฟังก์ชัน GIS เข้ากับแอปพลิเคชัน .NET ของตนได้อย่างราบรื่น ทำให้การประมวลผลข้อมูลเชิงพื้นที่เป็นเรื่องง่าย ในบทช่วยสอนที่ครอบคลุมนี้ เราจะสำรวจแง่มุมพื้นฐานด้านหนึ่ง นั่นคือการดึงค่าแอตทริบิวต์จากฟีเจอร์ต่างๆ มาดำน้ำกันเถอะ!
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้นการเดินทางที่น่าตื่นเต้นนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.GIS สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารีจาก[หน้าดาวน์โหลด Aspose.GIS สำหรับ .NET](https://releases.aspose.com/gis/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET เช่น Visual Studio
- เชปไฟล์: เตรียมเชปไฟล์ตัวอย่าง (เช่น "InputShapeFile.shp") ให้พร้อมในไดเร็กทอรีเอกสารของคุณ
## นำเข้าเนมสเปซ
ในโค้ด C# ของคุณ ให้เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชัน Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
```csharp
string dataDir = "Your Document Directory";
```
แทนที่ "Your Document Directory" ด้วยเส้นทางจริงที่มี Shapefile ของคุณอยู่
## ขั้นตอนที่ 2: เปิด VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // รหัสของคุณสำหรับขั้นตอนต่อไปอยู่ที่นี่
}
```
ขั้นตอนนี้เกี่ยวข้องกับการเปิด Shapefile โดยใช้ Aspose.GIS โดยระบุเส้นทางและรูปแบบของไฟล์ (ในกรณีนี้คือ Shapefile)
## ขั้นตอนที่ 3: ดึงค่าแอตทริบิวต์คุณสมบัติทั้งหมด
```csharp
foreach (var feature in layer)
{
    // อ่านคุณลักษณะทั้งหมดลงในอาร์เรย์
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // รหัสของคุณสำหรับจัดการค่าแอตทริบิวต์ทั้งหมดอยู่ที่นี่
    Console.WriteLine();
}
```
ข้อมูลโค้ดนี้สาธิตวิธีการดึงค่าแอตทริบิวต์ทั้งหมดสำหรับแต่ละคุณลักษณะใน Shapefile
## ขั้นตอนที่ 4: ดึงค่าคุณลักษณะคุณสมบัติหลายรายการ
```csharp
foreach (var feature in layer)
{
    // อ่านแอตทริบิวต์หลายรายการลงในอาร์เรย์
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // รหัสของคุณสำหรับจัดการค่าแอตทริบิวต์หลายค่าอยู่ที่นี่
    Console.WriteLine();
}
```
เช่นเดียวกับขั้นตอนที่ 3 ขั้นตอนนี้มุ่งเน้นไปที่การรับค่าแอตทริบิวต์เฉพาะจากคุณลักษณะ
## ขั้นตอนที่ 5: ดึงค่าแอตทริบิวต์เป็นการถ่ายโอนข้อมูลออบเจ็กต์
```csharp
foreach (var feature in layer)
{
    // อ่านแอตทริบิวต์เป็นการดัมพ์ของอ็อบเจ็กต์
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // รหัสของคุณสำหรับการจัดการค่าแอตทริบิวต์ที่ถูกทิ้งอยู่ที่นี่
    Console.WriteLine();
}
```
ขั้นตอนสุดท้ายนี้จะแสดงวิธีการดึงค่าแอตทริบิวต์ในรูปแบบดัมพ์ ซึ่งให้ความยืดหยุ่นในการจัดการข้อมูล
## บทสรุป
ยินดีด้วย! คุณได้สำรวจการเรียกค่าคุณลักษณะคุณลักษณะโดยใช้ Aspose.GIS สำหรับ .NET สำเร็จแล้ว นี่เป็นเพียงการสรุปความสามารถอันมากมายของไลบรารีนี้ สำรวจเพิ่มเติมและปลดล็อกศักยภาพสูงสุดของการพัฒนาเชิงพื้นที่ในแอปพลิเคชัน .NET ของคุณ
## คำถามที่พบบ่อย
### Aspose.GIS เข้ากันได้กับ .NET Core หรือไม่
ใช่ Aspose.GIS เข้ากันได้กับ .NET Core อย่างสมบูรณ์ ทำให้คุณสามารถสร้างแอปพลิเคชันข้ามแพลตฟอร์มได้
### ฉันสามารถทำงานกับไฟล์ GIS รูปแบบอื่นโดยใช้ Aspose.GIS ได้หรือไม่
อย่างแน่นอน! Aspose.GIS รองรับรูปแบบต่างๆ รวมถึง Shapefile, GeoJSON และอื่นๆ
### มีฟอรัมชุมชนสำหรับการสนับสนุน Aspose.GIS หรือไม่
 ใช่ คุณสามารถขอความช่วยเหลือและมีส่วนร่วมกับชุมชน Aspose.GIS ได้บน[ฟอรั่มการสนับสนุน](https://forum.aspose.com/c/gis/33).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวเพื่อการทดสอบได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะหาเอกสารโดยละเอียดสำหรับ Aspose.GIS ได้ที่ไหน
 มีเอกสารประกอบครบถ้วน[ที่นี่](https://reference.aspose.com/gis/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
