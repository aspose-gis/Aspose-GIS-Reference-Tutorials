---
title: รับค่าคุณสมบัติคุณสมบัติ (ค่าเริ่มต้น)
linktitle: รับค่าคุณสมบัติคุณสมบัติ (ค่าเริ่มต้น)
second_title: Aspose.GIS .NET API
description: ปลดล็อกพลังของ Aspose.GIS สำหรับ .NET! ดึงข้อมูลและจัดการค่าคุณลักษณะคุณลักษณะได้อย่างง่ายดายด้วยคำแนะนำทีละขั้นตอนนี้ ดาวน์โหลดรุ่นทดลองใช้ของคุณทันที!
type: docs
weight: 14
url: /th/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---
## การแนะนำ
ยินดีต้อนรับสู่โลกของ Aspose.GIS สำหรับ .NET! ในคู่มือที่ครอบคลุมนี้ เราจะเจาะลึกถึงความซับซ้อนของการเรียกค่าคุณลักษณะคุณลักษณะโดยใช้ความสามารถอันทรงพลังของ Aspose.GIS ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น บทช่วยสอนนี้จะให้คำแนะนำแบบทีละขั้นตอน เพื่อให้แน่ใจว่าคุณจะสามารถใช้ประโยชน์จากเครื่องมือที่น่าทึ่งนี้ได้อย่างเต็มศักยภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้นการผจญภัยการเขียนโค้ดนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้เกี่ยวกับการทำงานของ C# และ .NET framework
-  ติดตั้ง Aspose.GIS สำหรับ .NET แล้ว ถ้าไม่เช่นนั้นให้ดาวน์โหลดจาก[ที่นี่](https://releases.aspose.com/gis/net/).
- โปรแกรมแก้ไขโค้ด เช่น Visual Studio เพื่อติดตามได้อย่างราบรื่น
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ C# ของคุณ ตรวจสอบให้แน่ใจว่าได้รวมเนมสเปซที่จำเป็น:
```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
ตอนนี้ เราจะแบ่งแต่ละตัวอย่างออกเป็นชุดขั้นตอนที่ง่ายต่อการปฏิบัติตาม
## รับค่าคุณสมบัติคุณสมบัติ (ค่าเริ่มต้น)
### ขั้นตอนที่ 1: ตั้งค่าสภาพแวดล้อม
เริ่มต้นด้วยการกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ:
```csharp
string dataDir = "Your Document Directory";
```
### ขั้นตอนที่ 2: สร้างเลเยอร์ GeoJson
สร้างเลเยอร์ GeoJson และกำหนดแอตทริบิวต์ด้วยค่าเริ่มต้น:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### ขั้นตอนที่ 3: สร้างคุณลักษณะ
สร้างคุณลักษณะโดยใช้แอตทริบิวต์ที่กำหนด:
```csharp
    Feature feature = layer.ConstructFeature();
```
### ขั้นตอนที่ 4: ดึงค่า
ดึงค่าแอตทริบิวต์ที่มีสถานการณ์ต่างๆ:
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // ค่า == เป็นโมฆะ
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // ค่า == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // ค่า == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## การตั้งค่าเริ่มต้น
### ขั้นตอนที่ 1: สร้างเลเยอร์ GeoJson อื่น
ทำซ้ำขั้นตอนนี้ด้วยเลเยอร์ GeoJson อื่นและแอตทริบิวต์ double:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### ขั้นตอนที่ 2: สร้างคุณลักษณะ (อีกครั้ง)
```csharp
    Feature feature = layer.ConstructFeature();
```
### ขั้นตอนที่ 3: ดึงข้อมูลและตั้งค่า
ดึงข้อมูลและตั้งค่าแอตทริบิวต์ โดยแสดงค่าเริ่มต้น:
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // ค่า == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // ค่า == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // ค่า == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
ยินดีด้วย! คุณควบคุมพลังของ Aspose.GIS สำหรับ .NET ได้สำเร็จในการดึงและจัดการค่าคุณลักษณะของคุณลักษณะ
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจความแตกต่างในการเรียกค่าคุณลักษณะคุณลักษณะโดยใช้ Aspose.GIS สำหรับ .NET ด้วย API ที่ใช้งานง่ายและความสามารถที่แข็งแกร่ง Aspose.GIS เปิดโลกแห่งความเป็นไปได้สำหรับการพัฒนา GIS ในสภาพแวดล้อม .NET
## คำถามที่พบบ่อย
### Aspose.GIS เข้ากันได้กับ .NET Core หรือไม่
ใช่ Aspose.GIS เข้ากันได้กับ .NET Core อย่างสมบูรณ์ โดยให้การสนับสนุนข้ามแพลตฟอร์ม
### ฉันสามารถใช้ Aspose.GIS สำหรับโครงการเชิงพาณิชย์ได้หรือไม่
อย่างแน่นอน! Aspose.GIS มาพร้อมกับใบอนุญาตเชิงพาณิชย์ที่อนุญาตให้คุณนำไปใช้ในแอปพลิเคชันเชิงพาณิชย์ของคุณโดยไม่มีข้อจำกัดใดๆ
### ฉันจะหาการสนับสนุนและแหล่งข้อมูลเพิ่มเติมได้จากที่ไหน?
 เยี่ยมชม[ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33) สำหรับการสนับสนุนชุมชนและการสำรวจ[เอกสารประกอบ](https://reference.aspose.com/gis/net/) เพื่อข้อมูลเชิงลึก
### มีการทดลองใช้ฟรีหรือไม่?
 ใช่ คุณสามารถสำรวจ Aspose.GIS ได้ด้วยการทดลองใช้ฟรี ดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะขอรับใบอนุญาตชั่วคราวเพื่อการทดสอบได้อย่างไร
 สำหรับใบอนุญาตชั่วคราว โปรดไปที่[ที่นี่](https://purchase.aspose.com/temporary-license/).