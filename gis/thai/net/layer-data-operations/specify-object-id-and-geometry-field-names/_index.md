---
title: ระบุรหัสวัตถุและชื่อฟิลด์เรขาคณิต
linktitle: ระบุรหัสวัตถุและชื่อฟิลด์เรขาคณิต
second_title: Aspose.GIS .NET API
description: สำรวจความมหัศจรรย์ของ GIS ด้วย Aspose.GIS สำหรับ .NET! จัดการข้อมูลเชิงพื้นที่ได้อย่างง่ายดาย ดาวน์โหลดตอนนี้และปลดปล่อยพลังแห่งความฉลาดเชิงพื้นที่
weight: 20
url: /th/net/layer-data-operations/specify-object-id-and-geometry-field-names/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ระบุรหัสวัตถุและชื่อฟิลด์เรขาคณิต

## การแนะนำ
การเริ่มต้นการเดินทางสู่ขอบเขตของระบบสารสนเทศภูมิศาสตร์ (GIS) โดยใช้ Aspose.GIS สำหรับ .NET เปิดโลกแห่งความเป็นไปได้สำหรับนักพัฒนาและผู้ที่สนใจ ไลบรารีอันทรงพลังนี้ช่วยให้คุณจัดการข้อมูลเชิงพื้นที่ได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการระบุชื่อฟิลด์ Object ID และ Geometry ซึ่งเป็นการวางรากฐานสำหรับความพยายาม GIS ของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.GIS สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารีจาก[ที่นี่](https://releases.aspose.com/gis/net/).
- ไดเร็กทอรีเอกสาร: ตั้งค่าไดเร็กทอรีสำหรับเอกสารของคุณเพื่อจัดเก็บฐานข้อมูลทางภูมิศาสตร์
- สภาพแวดล้อม .NET: ตรวจสอบให้แน่ใจว่าคุณมีสภาพแวดล้อม .NET ที่ใช้งานได้
## นำเข้าเนมสเปซ
ในการเริ่มต้น คุณจะต้องนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ เนมสเปซเหล่านี้มีคลาสและวิธีการที่จำเป็นสำหรับการโต้ตอบกับ Aspose.GIS สำหรับ .NET
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```
## ขั้นตอนที่ 1: ระบุรหัสวัตถุและชื่อฟิลด์เรขาคณิต
ในขั้นตอนนี้ คุณจะได้เรียนรู้วิธีตั้งค่าชื่อฟิลด์ Object ID และ Geometry สำหรับข้อมูล GIS ของคุณ นี่เป็นสิ่งสำคัญสำหรับการจัดการข้อมูลที่มีประสิทธิภาพ
## ขั้นตอนที่ 1.1: ตั้งค่าไดเรกทอรีเอกสาร
เริ่มต้นด้วยการกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ:
```csharp
string dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 1.2: สร้าง GeoDatabase และกำหนดตัวเลือก
สร้าง GeoDatabase ด้วยชื่อฟิลด์ Object ID และ Geometry ที่ระบุ:
```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // ระบุชื่อฟิลด์รหัสออบเจ็กต์
        GeometryFieldName = "POINT",       // ระบุชื่อฟิลด์เรขาคณิต
    };
```
## ขั้นตอนที่ 1.3: สร้างและเพิ่มเลเยอร์
สร้างเลเยอร์ภายใน GeoDatabase และเพิ่มคุณลักษณะที่มีรูปทรงเรขาคณิตเฉพาะ:
```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  //ระบุรูปทรง (ในกรณีนี้คือจุด)
    layer.Add(feature);
}
```
## ขั้นตอนที่ 1.4: เปิดและดึงข้อมูลจากเลเยอร์
เปิดเลเยอร์และดึงข้อมูลจากเลเยอร์นั้นตามรหัสออบเจ็กต์ที่ระบุ:
```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // เอาท์พุท: 1
}
```
## บทสรุป
ยินดีด้วย! คุณได้สำรวจกระบวนการระบุ Object ID และชื่อฟิลด์ Geometry โดยใช้ Aspose.GIS สำหรับ .NET สำเร็จแล้ว นี่เป็นการวางรากฐานที่มั่นคงสำหรับโครงการ GIS ของคุณ ทำให้คุณสามารถจัดการข้อมูลเชิงพื้นที่ได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.GIS สำหรับ .NET บนเว็บแอปพลิเคชันของฉันได้หรือไม่
ตอบ: ใช่ Aspose.GIS สำหรับ .NET เหมาะสำหรับทั้งเดสก์ท็อปและเว็บแอปพลิเคชัน โดยให้ความสามารถด้านภูมิสารสนเทศที่หลากหลาย
### ถาม: มีเวอร์ชันทดลองใช้ก่อนซื้อหรือไม่
 ตอบ: ได้ คุณสามารถสำรวจคุณสมบัติของ Aspose.GIS สำหรับ .NET ได้พร้อมให้ทดลองใช้ฟรี[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS สำหรับ .NET ได้อย่างไร
 ตอบ: คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการประเมินผล
### ถาม: Aspose.GIS สำหรับ .NET รองรับระบบอ้างอิงเชิงพื้นที่ใดบ้าง
ตอบ: Aspose.GIS สำหรับ .NET รองรับระบบอ้างอิงเชิงพื้นที่ที่หลากหลาย ซึ่งให้ความยืดหยุ่นสำหรับชุดข้อมูลทางภูมิศาสตร์ที่แตกต่างกัน
### ถาม: ฉันจะขอความช่วยเหลือหรือหารือเกี่ยวกับคำถามที่เกี่ยวข้องกับ Aspose.GIS ได้ที่ไหน
 ตอบ: เยี่ยมชมฟอรัม Aspose.GIS[ที่นี่](https://forum.aspose.com/c/gis/33) สำหรับการสนับสนุนและการอภิปราย
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
