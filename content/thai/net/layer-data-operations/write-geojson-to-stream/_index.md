---
title: เขียน GeoJSON เพื่อสตรีม
linktitle: เขียน GeoJSON เพื่อสตรีม
second_title: Aspose.GIS .NET API
description: สำรวจพลังของ Aspose.GIS สำหรับ .NET! เขียน GeoJSON เพื่อสตรีมได้อย่างง่ายดาย ดาวน์โหลดเดี๋ยวนี้เพื่อการบูรณาการเชิงพื้นที่อย่างราบรื่น
type: docs
weight: 25
url: /th/net/layer-data-operations/write-geojson-to-stream/
---
## การแนะนำ
คุณต้องการควบคุมพลังของ GeoJSON ในแอปพลิเคชัน .NET ของคุณโดยใช้ Aspose.GIS หรือไม่? คุณอยู่ในสถานที่ที่เหมาะสม! คำแนะนำทีละขั้นตอนนี้จะแนะนำคุณตลอดขั้นตอนการเขียน GeoJSON ลงในสตรีม โดยใช้ประโยชน์จากความสามารถที่แข็งแกร่งของ Aspose.GIS สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. Aspose.GIS สำหรับไลบรารี .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.GIS สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/gis/net/).
2. ไดเร็กทอรีเอกสาร: ตั้งค่าไดเร็กทอรีเอกสารในโครงการของคุณและจดบันทึกเส้นทางของมัน
เอาล่ะ เรามาเริ่มด้วยบทช่วยสอนกันดีกว่า!
## นำเข้าเนมสเปซ
ก่อนอื่น ตรวจสอบให้แน่ใจว่าได้รวมเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.GIS ในโค้ดของคุณ:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
```csharp
string dataDir = "Your Document Directory";
```
แทนที่ "Your Document Directory" ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ
## ขั้นตอนที่ 2: สร้างสตรีมหน่วยความจำ
```csharp
using (var memoryStream = new MemoryStream())
{
    // รหัสสำหรับขั้นตอนต่อไปอยู่ที่นี่
}
```
## ขั้นตอนที่ 3: สร้างเลเยอร์เวกเตอร์ด้วยไดรเวอร์ GeoJSON
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // รหัสสำหรับขั้นตอนต่อไปอยู่ที่นี่
}
```
## ขั้นตอนที่ 4: กำหนดคุณสมบัติคุณสมบัติ
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```
## ขั้นตอนที่ 5: สร้างและเพิ่มคุณสมบัติ
```csharp
// คุณสมบัติแรก
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// คุณสมบัติที่สอง
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```
## ขั้นตอนที่ 6: แสดงเอาต์พุต GeoJSON
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```
ยินดีด้วย! คุณเขียน GeoJSON ไปยังสตรีมโดยใช้ Aspose.GIS สำหรับ .NET สำเร็จแล้ว
## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงขั้นตอนพื้นฐานในการรวม Aspose.GIS สำหรับ .NET เข้ากับโปรเจ็กต์ของคุณ โดยเน้นไปที่การเขียน GeoJSON ลงในสตรีมโดยเฉพาะ ด้วยขั้นตอนง่ายๆ แต่ทรงพลังเหล่านี้ คุณสามารถปรับปรุงความสามารถเชิงพื้นที่ของแอปพลิเคชันของคุณได้
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.GIS สำหรับ .NET ทั้งในสภาพแวดล้อม Windows และ Linux ได้หรือไม่
ใช่ Aspose.GIS สำหรับ .NET เข้ากันได้กับทั้งระบบ Windows และ Linux
### มีการทดลองใช้ฟรีหรือไม่?
 อย่างแน่นอน! คุณสามารถสำรวจการทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารรายละเอียดได้ที่ไหน?
 ตรวจสอบเอกสาร[ที่นี่](https://reference.aspose.com/gis/net/).
### ฉันจะรับใบอนุญาตชั่วคราวได้อย่างไร
 มีใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ต้องการความช่วยเหลือหรือมีคำถามเพิ่มเติม?
 เยี่ยมชมฟอรั่มการสนับสนุนของเรา[ที่นี่](https://forum.aspose.com/c/gis/33).