---
title: รูปแบบแรสเตอร์วิปริต
linktitle: รูปแบบแรสเตอร์วิปริต
second_title: Aspose.GIS .NET API
description: สำรวจโลกของการเขียนโปรแกรมเชิงพื้นที่ด้วย Aspose.GIS สำหรับ .NET เรียนรู้การบิดเบี้ยวรูปแบบแรสเตอร์ทีละขั้นตอนเพื่อการแสดงภาพข้อมูลเชิงพื้นที่ที่ดียิ่งขึ้น
type: docs
weight: 23
url: /th/net/layer-data-operations/warp-raster-formats/
---
## การแนะนำ
ยินดีต้อนรับสู่โลกที่น่าตื่นเต้นของการเขียนโปรแกรมเชิงพื้นที่ด้วย Aspose.GIS สำหรับ .NET! ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการวาร์ปรูปแบบแรสเตอร์โดยใช้ Aspose.GIS ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น เตรียมพร้อมในขณะที่เราเจาะลึกความซับซ้อนของการจัดการ geotiff ทำให้ข้อมูลเชิงพื้นที่ของคุณมีมุมมองใหม่ทั้งหมด
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้นการเดินทางนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.GIS สำหรับ .NET: หากคุณยังไม่ได้ดาวน์โหลด ให้ดาวน์โหลดและติดตั้งไลบรารี Aspose.GIS คุณสามารถค้นหาเวอร์ชันล่าสุดได้[ที่นี่](https://releases.aspose.com/gis/net/).
- ไดเร็กทอรีเอกสารของคุณ: ตั้งค่าไดเร็กทอรีเพื่อจัดเก็บเอกสารของคุณ นี่จะเป็นสิ่งสำคัญสำหรับการจัดการไฟล์ในระหว่างกระบวนการบิดเบี้ยวแรสเตอร์
ตอนนี้เราพร้อมแล้ว เรามาเจาะลึกโค้ดกันดีกว่า
## นำเข้าเนมสเปซ
ก่อนอื่น เราต้องแน่ใจว่าเรามีเครื่องมือที่เหมาะสมพร้อมใช้ นำเข้าเนมสเปซที่จำเป็นเพื่อเริ่มต้นการผจญภัยเชิงพื้นที่ของคุณ:
```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Raster;
using Aspose.Gis.SpatialReferencing;
```
## ขั้นตอนที่ 1: เริ่มต้นเส้นทาง
เริ่มต้นด้วยการกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ นี่คือที่ที่ความมหัศจรรย์ทั้งหมดจะเกิดขึ้น:
```csharp
string dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: เปิดเลเยอร์แรสเตอร์
เปิดเลเยอร์แรสเตอร์ GeoTiff และเตรียมพร้อมสำหรับการเปลี่ยนแปลง ขั้นตอนนี้จะกำหนดขั้นตอนสำหรับการดำเนินการวาร์ปครั้งต่อไป:
```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(dataDir, "raster_float32.tif")))
```
## ขั้นตอนที่ 3: บิดเบี้ยวแรสเตอร์
ตอนนี้ เรามาดำเนินการวาร์ปกันดีกว่า ระบุขนาดเป้าหมายและระบบอ้างอิงเชิงพื้นที่เพื่อสร้างชีวิตใหม่ให้กับข้อมูลแรสเตอร์ของคุณ:
```csharp
using (var warped = layer.Warp(new WarpOptions(){Height = 40, Width = 40, TargetSpatialReferenceSystem = SpatialReferenceSystem.Wgs84}))
```
## ขั้นตอนที่ 4: แยกข้อมูลแรสเตอร์
ถึงเวลาเปิดเผยความลับของแรสเตอร์ที่เปลี่ยนแปลงแล้ว แยกข้อมูลที่จำเป็น เช่น ขนาดของเซลล์ ระบบอ้างอิงเชิงพื้นที่ ขอบเขต และจำนวนแบนด์:
```csharp
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
var bandCount = warped.BandCount;
```
## ขั้นตอนที่ 5: พิมพ์รายละเอียดแรสเตอร์
มาพิมพ์รายละเอียดที่น่าสนใจที่เราค้นพบ เพื่อให้ข้อมูลเชิงลึกเกี่ยวกับแรสเตอร์ที่บิดเบี้ยว:
```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
Console.WriteLine($"bandCount: {bandCount}");
```
## ขั้นตอนที่ 6: สำรวจวงแรสเตอร์
เจาะลึกแต่ละแบนด์ของแรสเตอร์ คลี่คลายประเภทข้อมูล สถิติ และการมีอยู่ของค่า nodata:
```csharp
for (int i = 0; i < warped.BandCount; i++)
{
    var dataType = warped.GetBand(i).DataType;
    var hasNoData = !warped.NoDataValues.IsNull();
    var statistics = warped.GetStatistics(i);
    Console.WriteLine();
    Console.WriteLine($"Band: {i}");
    Console.WriteLine($"dataType: {dataType}");
    Console.WriteLine($"statistics: {statistics}");
    Console.WriteLine($"hasNoData: {hasNoData}");
    if (hasNoData)
        Console.WriteLine($"noData: {warped.NoDataValues[i]}");
}
```
## บทสรุป
ยินดีด้วย! คุณได้สำรวจโซนวาร์ปของการเขียนโปรแกรมเชิงพื้นที่โดยใช้ Aspose.GIS สำหรับ .NET สำเร็จแล้ว เมื่อทำตามขั้นตอนเหล่านี้ คุณจะได้รับข้อมูลเชิงลึกอันมีค่าเกี่ยวกับการปรับแต่งแรสเตอร์ ซึ่งจะช่วยปลดล็อกความเป็นไปได้ใหม่ๆ สำหรับข้อมูลเชิงพื้นที่ของคุณ
## คำถามที่พบบ่อย
### Aspose.GIS เข้ากันได้กับรูปแบบแรสเตอร์ทุกรูปแบบหรือไม่
ใช่ Aspose.GIS รองรับรูปแบบแรสเตอร์ที่หลากหลาย ซึ่งให้ความยืดหยุ่นในการจัดการชุดข้อมูลเชิงพื้นที่ต่างๆ
### ฉันสามารถทำการบิดงอแรสเตอร์บนรูปภาพที่ไม่ได้อ้างอิงทางภูมิศาสตร์ได้หรือไม่
Aspose.GIS ได้รับการออกแบบมาเพื่อจัดการข้อมูลอ้างอิงทางภูมิศาสตร์ เพื่อให้มั่นใจว่าการแปลงมีความแม่นยำ ตรวจสอบให้แน่ใจว่าภาพแรสเตอร์ของคุณมีข้อมูลอ้างอิงเชิงพื้นที่ที่เหมาะสม
### ฉันจะสนับสนุนชุมชน Aspose.GIS ได้อย่างไร
 ร่วมเสวนาเรื่อง[ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33) เพื่อแบ่งปันประสบการณ์ของคุณ ถามคำถาม และทำงานร่วมกับนักพัฒนารายอื่น
### Aspose.GIS มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถสำรวจความสามารถของ Aspose.GIS ได้ด้วยการดาวน์โหลดรุ่นทดลองใช้ฟรี[ที่นี่](https://releases.aspose.com/).
### มีใบอนุญาตชั่วคราวสำหรับ Aspose.GIS หรือไม่
 ใช่ หากคุณต้องการใบอนุญาตชั่วคราว คุณสามารถขอรับได้[ที่นี่](https://purchase.aspose.com/temporary-license/).