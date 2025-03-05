---
title: แยกคุณสมบัติไปยัง GeoJSON
linktitle: แยกคุณสมบัติไปยัง GeoJSON
second_title: Aspose.GIS .NET API
description: สำรวจคำแนะนำทีละขั้นตอนเกี่ยวกับการใช้ Aspose.GIS สำหรับ .NET เพื่อแยกคุณสมบัติต่างๆ ให้กับ GeoJSON ควบคุมพลังของ GIS ได้อย่างง่ายดาย! #จัดทำ #GIS
type: docs
weight: 23
url: /th/net/layer-management/extract-features-to-geojson/
---
## การแนะนำ
ยินดีต้อนรับสู่บทช่วยสอนทีละขั้นตอนเกี่ยวกับการแยกคุณสมบัติต่างๆ ไปยัง GeoJSON โดยใช้ Aspose.GIS สำหรับ .NET! ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้นการเดินทางในการเขียนโปรแกรม GIS คู่มือนี้จะแนะนำคุณตลอดกระบวนการ เพื่อให้มั่นใจว่าคุณจะสามารถใช้ประโยชน์จาก Aspose.GIS สำหรับ .NET ได้อย่างเต็มที่
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
-  Aspose.GIS สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารีแล้ว ถ้าไม่เช่นนั้นคุณสามารถดาวน์โหลดได้จาก[Aspose.GIS สำหรับหน้า .NET](https://releases.aspose.com/gis/net/).
-  ข้อมูลเชปไฟล์: เตรียมเชปไฟล์ให้พร้อมสำหรับการป้อนข้อมูล หากคุณต้องการข้อมูลตัวอย่าง คุณสามารถค้นหาได้ใน[เอกสาร Aspose.GIS](https://reference.aspose.com/gis/net/).
- สภาพแวดล้อม .NET: ตั้งค่าสภาพแวดล้อม .NET เพื่อเรียกใช้โค้ดที่ให้มา
- ไดเรกทอรีเอกสาร: กำหนดเส้นทางไปยังไดเรกทอรีเอกสารของคุณในข้อมูลโค้ด
ตอนนี้คุณมีทุกอย่างพร้อมแล้ว มาเริ่มแยกคุณสมบัติต่างๆ ให้กับ GeoJSON กัน!
## นำเข้าเนมสเปซ
ขั้นแรก ใส่เนมสเปซที่จำเป็นในโค้ดของคุณ:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
เนมสเปซเหล่านี้จำเป็นสำหรับการทำงานกับฟังก์ชัน Aspose.GIS
## ขั้นตอนที่ 1: เปิดอินพุตเชปไฟล์
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // รหัสของคุณสำหรับการประมวลผลเชปไฟล์อินพุตอยู่ที่นี่
}
```
 เปิดอินพุต Shapefile โดยใช้ไฟล์`VectorLayer.Open` วิธี.
## ขั้นตอนที่ 2: สร้างเอาต์พุต GeoJSON
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // รหัสของคุณสำหรับการสร้างเอาต์พุต GeoJSON อยู่ที่นี่
}
```
 สร้างเอาต์พุต GeoJSON โดยใช้ไฟล์`VectorLayer.Create` วิธี.
## ขั้นตอนที่ 3: คัดลอกแอตทริบิวต์
```csharp
outputLayer.CopyAttributes(inputLayer);
```
 คัดลอกแอตทริบิวต์จากเลเยอร์อินพุตไปยังเลเยอร์เอาต์พุตโดยใช้`CopyAttributes` วิธี.
## ขั้นตอนที่ 4: คุณสมบัติกระบวนการ
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // รหัสของคุณสำหรับการประมวลผลคุณลักษณะอินพุตแต่ละรายการอยู่ที่นี่
}
```
วนซ้ำแต่ละฟีเจอร์ในเลเยอร์อินพุตและประมวลผลทีละรายการ
## ขั้นตอนที่ 5: กรองคุณสมบัติตามวันที่
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
คุณสมบัติการกรองตามเงื่อนไขวันที่ ในตัวอย่างนี้ จะข้ามฟีเจอร์ที่มีวันเกิดก่อนปี 1982
## ขั้นตอนที่ 6: สร้างคุณลักษณะใหม่
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
สร้างคุณลักษณะใหม่สำหรับเลเยอร์เอาต์พุต โดยคัดลอกเรขาคณิตและค่าจากคุณลักษณะอินพุต
ยินดีด้วย! คุณได้แตกคุณลักษณะไปยัง GeoJSON โดยใช้ Aspose.GIS สำหรับ .NET สำเร็จแล้ว
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการแยกคุณสมบัติไปยัง GeoJSON โดยใช้ Aspose.GIS สำหรับ .NET ห้องสมุดอันทรงพลังนี้เปิดโลกแห่งความเป็นไปได้สำหรับการพัฒนา GIS ทดลองใช้ชุดข้อมูลและฟังก์ชันต่างๆ เพื่อปลดล็อกศักยภาพสูงสุดของ Aspose.GIS
## คำถามที่พบบ่อย
### ถาม: ฉันจะหาเอกสารเพิ่มเติมได้จากที่ไหน?
 เยี่ยมชม[เอกสาร Aspose.GIS](https://reference.aspose.com/gis/net/) เพื่อข้อมูลเชิงลึก
### ถาม: ฉันจะได้รับใบอนุญาตชั่วคราวได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: ฉันสามารถขอรับการสนับสนุนได้ที่ไหน?
 เข้าร่วม[ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33) สำหรับการสนับสนุนและการอภิปรายของชุมชน
### ถาม: มีการทดลองใช้ฟรีหรือไม่?
 ใช่ คุณสามารถค้นหารุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะซื้อ Aspose.GIS สำหรับ .NET ได้ที่ไหน
 ท่านสามารถซื้อสินค้าได้[ที่นี่](https://purchase.aspose.com/buy).