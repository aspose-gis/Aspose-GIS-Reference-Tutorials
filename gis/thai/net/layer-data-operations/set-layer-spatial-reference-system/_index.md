---
title: ตั้งค่าระบบอ้างอิงเชิงพื้นที่เลเยอร์
linktitle: ตั้งค่าระบบอ้างอิงเชิงพื้นที่เลเยอร์
second_title: Aspose.GIS .NET API
description: การตั้งค่าหลักระบบอ้างอิงเชิงพื้นที่เลเยอร์ด้วย Aspose.GIS สำหรับ .NET ยกระดับโครงการ GIS ของคุณด้วยบทช่วยสอนทีละขั้นตอนนี้
weight: 19
url: /th/net/layer-data-operations/set-layer-spatial-reference-system/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าระบบอ้างอิงเชิงพื้นที่เลเยอร์

## การแนะนำ
ในภูมิทัศน์อันกว้างใหญ่ของระบบสารสนเทศทางภูมิศาสตร์ (GIS) Aspose.GIS สำหรับ .NET มีความโดดเด่นในฐานะเครื่องมือที่แข็งแกร่งและอเนกประสงค์สำหรับนักพัฒนา บทช่วยสอนนี้จะแนะนำคุณตลอดขั้นตอนการตั้งค่า Layer Spatial Reference System โดยใช้ Aspose.GIS สำหรับ .NET ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเป็นมือใหม่ในการพัฒนา GIS คำแนะนำทีละขั้นตอนนี้จะช่วยให้คุณใช้ประโยชน์จากพลังของ Aspose.GIS เพื่อปรับปรุงความสามารถในการจัดการข้อมูลเชิงพื้นที่ของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้การทำงานของการเขียนโปรแกรม .NET
- ติดตั้ง Visual Studio บนระบบของคุณแล้ว
-  Aspose.GIS สำหรับไลบรารี .NET ซึ่งคุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/gis/net/).
- ความเข้าใจพื้นฐานเกี่ยวกับระบบอ้างอิงเชิงพื้นที่ใน GIS
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ให้เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานที่ Aspose.GIS มอบให้ ใช้ข้อมูลโค้ดต่อไปนี้:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```
## ขั้นตอนที่ 1: ระบุไดเร็กทอรีเอกสาร
เริ่มต้นด้วยการระบุเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ นี่จะเป็นตำแหน่งที่เก็บไฟล์ข้อมูลเชิงพื้นที่ของคุณ
```csharp
string dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: สร้างและตั้งค่าระบบอ้างอิงเชิงพื้นที่
กำหนดเส้นทางสำหรับ Shapefile และสร้างระบบอ้างอิงเชิงพื้นที่ใหม่โดยใช้รหัส EPSG (26918 ในตัวอย่างนี้)
```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```
## ขั้นตอนที่ 3: สร้างเลเยอร์เวกเตอร์
ใช้ Aspose.GIS เพื่อสร้าง Vector Layer ด้วยเส้นทาง Shapefile ที่ระบุ ประเภทไดรเวอร์ (Shapefile) และระบบอ้างอิงเชิงพื้นที่
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // รหัสของคุณสำหรับการดำเนินการเพิ่มเติมบนเลเยอร์อยู่ที่นี่
}
```
## ขั้นตอนที่ 4: เพิ่มคุณสมบัติให้กับเลเยอร์
สร้างคุณลักษณะใหม่และตั้งค่าเรขาคณิต (ในกรณีนี้คือจุดที่มีพิกัด 60, 24) เพิ่มคุณสมบัตินี้ให้กับ Vector Layer
```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```
## ขั้นตอนที่ 5: ดึงข้อมูลระบบอ้างอิงเชิงพื้นที่
เปิด Vector Layer และดึงข้อมูลเกี่ยวกับระบบอ้างอิงเชิงพื้นที่
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_โซน_18N
}
```
ทำซ้ำขั้นตอนเหล่านี้ตามกรณีการใช้งานเฉพาะของคุณ แล้วคุณจะสามารถเชี่ยวชาญศิลปะในการตั้งค่า Layer Spatial Reference System ด้วย Aspose.GIS สำหรับ .NET ได้
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจขั้นตอนสำคัญในการตั้งค่าระบบอ้างอิงเชิงพื้นที่ของเลเยอร์โดยใช้ Aspose.GIS สำหรับ .NET ด้วย API ที่ใช้งานง่ายและฟีเจอร์อันทรงพลัง Aspose.GIS ช่วยให้นักพัฒนาสามารถจัดการข้อมูลเชิงพื้นที่ได้อย่างราบรื่น รวมเทคนิคเหล่านี้เข้ากับโครงการ GIS ของคุณเพื่อยกระดับความสามารถในการประมวลผลข้อมูลเชิงพื้นที่ของคุณ
## คำถามที่พบบ่อย
### Aspose.GIS เข้ากันได้กับไลบรารี GIS อื่นหรือไม่
ใช่ Aspose.GIS ทำงานร่วมกับไลบรารี GIS อื่นๆ ได้ดีและสามารถใช้ร่วมกับห้องสมุดเหล่านั้นได้
### ฉันสามารถใช้ Aspose.GIS สำหรับทั้งเดสก์ท็อปและเว็บแอปพลิเคชันได้หรือไม่
อย่างแน่นอน! Aspose.GIS มีความหลากหลายและสามารถใช้ได้ทั้งในแอปพลิเคชันบนเดสก์ท็อปและบนเว็บ
### มีตัวเลือกสิทธิ์การใช้งานสำหรับ Aspose.GIS หรือไม่
 ใช่ คุณสามารถสำรวจตัวเลือกใบอนุญาตและทำการซื้อได้[ที่นี่](https://purchase.aspose.com/buy).
### Aspose.GIS มีรุ่นทดลองใช้ฟรีหรือไม่
 แน่นอน! คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะขอรับการสนับสนุนสำหรับการสืบค้นที่เกี่ยวข้องกับ Aspose.GIS ได้ที่ไหน
 สำหรับการสนับสนุนหรือข้อสงสัยใด ๆ โปรดไปที่[ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
