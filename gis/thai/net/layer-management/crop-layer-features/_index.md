---
title: คุณสมบัติครอบตัดเลเยอร์
linktitle: คุณสมบัติครอบตัดเลเยอร์
second_title: Aspose.GIS .NET API
description: ปลดล็อกความมหัศจรรย์เชิงพื้นที่ด้วย Aspose.GIS สำหรับ .NET! คุณสมบัติเลเยอร์ครอบตัดได้อย่างง่ายดาย ดาวน์โหลดรุ่นทดลองใช้ฟรีของคุณทันที #Aspose #GIS #ภูมิสารสนเทศ
weight: 19
url: /th/net/layer-management/crop-layer-features/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# คุณสมบัติครอบตัดเลเยอร์

## การแนะนำ
ในขอบเขตอันกว้างใหญ่ของการประมวลผลข้อมูลเชิงพื้นที่ Aspose.GIS สำหรับ .NET กลายเป็นเครื่องมืออันทรงพลัง ช่วยให้นักพัฒนาได้รับประสบการณ์ที่ราบรื่นในการจัดการข้อมูลทางภูมิศาสตร์ บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการฟีเจอร์เลเยอร์การครอบตัดโดยใช้ Aspose.GIS ซึ่งช่วยให้คุณปรับแต่งข้อมูลเชิงพื้นที่ให้ตรงตามข้อกำหนดเฉพาะได้
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเจาะลึกความมหัศจรรย์ของการจัดการภูมิสารสนเทศ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.GIS สำหรับไลบรารี .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.GIS ในโปรเจ็กต์ .NET ของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/gis/net/).
-  ไดเร็กทอรีเอกสาร: ตั้งค่าไดเร็กทอรีเพื่อจัดเก็บเอกสารของคุณ แทนที่`"Your Document Directory"` ในโค้ดที่ให้มาพร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ
ตอนนี้ เรามาดูรายละเอียดคำแนะนำทีละขั้นตอนกันดีกว่า
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อควบคุมประสิทธิภาพเต็มรูปแบบของ Aspose.GIS:
```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```
## ขั้นตอนที่ 1: เปิดและครอบตัดเลเยอร์
เริ่มต้นด้วยการเปิดเลเยอร์ GeoTiff และครอบตัดตามรูปหลายเหลี่ยมที่กำหนด สิ่งนี้ทำให้แน่ใจได้ว่าข้อมูลภูมิสารสนเทศของคุณได้รับการปรับแต่งให้เหมาะกับพื้นที่ที่คุณสนใจโดยเฉพาะ
```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```
## ขั้นตอนที่ 2: ดึงข้อมูลแรสเตอร์
เมื่อครอบตัดเลเยอร์แล้ว ให้ดึงข้อมูลที่สำคัญเกี่ยวกับข้อมูลแรสเตอร์ เช่น ขนาดเซลล์ ระบบอ้างอิงเชิงพื้นที่ และขอบเขต
```csharp
// อ่านและพิมพ์แรสเตอร์
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```
## ขั้นตอนที่ 3: แสดงข้อมูล
พิมพ์ข้อมูลที่แยกออกมาเพื่อทำความเข้าใจผลกระทบของกระบวนการครอบตัดกับข้อมูลเชิงพื้นที่ของคุณ
```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```
ทำซ้ำขั้นตอนเหล่านี้ตามความจำเป็นเพื่อปรับแต่งและปรับแต่งข้อมูลเชิงพื้นที่ของคุณให้ตรงตามข้อกำหนดเฉพาะของโครงการ
## บทสรุป
Aspose.GIS สำหรับ .NET เปิดขอบเขตความเป็นไปได้สำหรับนักพัฒนาที่ทำงานกับข้อมูลภูมิสารสนเทศ ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะได้เรียนรู้วิธีครอบตัดคุณลักษณะของเลเยอร์อย่างมีประสิทธิภาพ ซึ่งเป็นรากฐานสำหรับการปรับแต่งเชิงพื้นที่ขั้นสูงยิ่งขึ้น
## คำถามที่พบบ่อย
### ถาม: Aspose.GIS สำหรับ .NET มีใบอนุญาตชั่วคราวหรือไม่
 ตอบ: ได้ คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: ฉันจะหาเอกสารที่ครอบคลุมสำหรับ Aspose.GIS สำหรับ .NET ได้ที่ไหน
 ตอบ: มีเอกสารประกอบให้[ที่นี่](https://reference.aspose.com/gis/net/).
### ถาม: ฉันจะขอรับการสนับสนุนหรือเชื่อมต่อกับชุมชนสำหรับ Aspose.GIS สำหรับ .NET ได้อย่างไร
 ตอบ: เยี่ยมชม[ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33) เพื่อการสนับสนุนและการมีส่วนร่วมของชุมชน
### ถาม: ฉันสามารถดาวน์โหลด Aspose.GIS สำหรับ .NET รุ่นทดลองใช้ฟรีได้หรือไม่
 ตอบ: ได้ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะซื้อ Aspose.GIS สำหรับ .NET ได้ที่ไหน
 ตอบ: คุณสามารถซื้อห้องสมุดได้[ที่นี่](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
