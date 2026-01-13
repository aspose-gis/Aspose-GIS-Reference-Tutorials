---
date: 2026-01-13
description: เรียนรู้วิธีตัดคุณลักษณะของเลเยอร์ด้วย Aspose.GIS สำหรับ .NET รวมถึงวิธีตัดภาพราสเตอร์ด้วยโพลิกอน
  การสกัดขนาดเซลล์ของราสเตอร์ และการดึงขอบเขตของราสเตอร์ ดาวน์โหลดรุ่นทดลองฟรีของคุณเลย
linktitle: How to Crop Layer Features
second_title: Aspose.GIS .NET API
title: วิธีตัดฟีเจอร์ของเลเยอร์ด้วย Aspose.GIS สำหรับ .NET
url: /th/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการตัดคุณลักษณะของเลเยอร์

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีการตัดเลเยอร์** ด้วย Aspose.GIS for .NET ซึ่งเป็นวิธีที่ทรงพลังที่ช่วยให้คุณ **ตัด raster ด้วย polygon**, **สกัดขนาดเซลล์ของ raster**, และ **ดึงขอบเขตของ raster** เพื่อการวิเคราะห์เชิงพื้นที่ที่แม่นยำ ไม่ว่าคุณจะกำลังเตรียมข้อมูลสำหรับเว็บแผนที่, ตัดภาพถ่ายดาวเทียม, หรือแยกพื้นที่สนใจ ขั้นตอนต่อไปนี้จะแสดงให้คุณเห็นวิธีทำอย่างละเอียด

## คำตอบสั้น
- **“crop layer” หมายถึงอะไร?** เป็นการตัด raster หรือ vector layer ให้เหลือเฉพาะขอบเขตของเรขาคณิตที่กำหนด  
- **เรขาคณิตที่ใช้ในตัวอย่างนี้คืออะไร?** Polygon ที่กำหนดในรูปแบบ WKT  
- **ฉันสามารถสกัดขนาดเซลล์หลังจากการตัดได้หรือไม่?** ได้ – คุณสมบัติ `CellSize` จะให้ข้อมูลนั้น  
- **ต้องมีลิขสิทธิ์เพื่อรันโค้ดหรือไม่?** ลิขสิทธิ์ชั่วคราวใช้ได้สำหรับการประเมิน; ต้องมีลิขสิทธิ์เต็มสำหรับการใช้งานจริง  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7

## “how to crop layer” คืออะไร?
การตัดเลเยอร์หมายถึงการจำกัดชุดข้อมูลให้อยู่ในพื้นที่ทางภูมิศาสตร์ที่กำหนดไว้เท่านั้น โดยตัดส่วนที่อยู่นอกรูปทรงที่กำหนดออกไป วิธีนี้ช่วยลดขนาดไฟล์, เร่งความเร็วการประมวลผล, และทำให้การวิเคราะห์โฟกัสที่พื้นที่ที่คุณสนใจ

## ทำไมต้องใช้ Aspose.GIS สำหรับการตัด?
- **การจัดการ raster ที่ประสิทธิภาพสูง** – เหมาะสำหรับไฟล์ GeoTiff ขนาดใหญ่  
- **API ที่เรียบง่าย** – เรียก `Crop` เพียงบรรทัดเดียวพร้อมเรขาคณิตใดก็ได้  
- **รองรับ .NET อย่างเต็มรูปแบบ** – ทำงานได้บนแอปพลิเคชันเดสก์ท็อป, เซิร์ฟเวอร์, และคลาวด์  
- **การจัดการระบบอ้างอิงเชิงพื้นที่ที่แม่นยำ** – คงข้อมูล CRS ไว้อัตโนมัติ

## ข้อกำหนดเบื้องต้น
ก่อนจะลงลึกในเทคนิคการจัดการเชิงพื้นที่ โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งานแล้ว:

- Aspose.GIS for .NET Library: ตรวจสอบว่าคุณได้ติดตั้งไลบรารี Aspose.GIS ในโปรเจกต์ .NET ของคุณแล้ว สามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/gis/net/)  
- โฟลเดอร์เอกสาร: ตั้งค่าโฟลเดอร์เพื่อเก็บเอกสารของคุณ แทนที่ `"Your Document Directory"` ในโค้ดตัวอย่างด้วยพาธที่แท้จริงของโฟลเดอร์เอกสารของคุณ

ต่อไปนี้เป็นขั้นตอนแบบทีละขั้นตอน

## นำเข้า Namespaces
เริ่มต้นด้วยการนำเข้า namespaces ที่จำเป็นเพื่อใช้พลังเต็มของ Aspose.GIS:

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## ขั้นตอนที่ 1: เปิดและตัดเลเยอร์ (crop raster with polygon)
เปิดเลเยอร์ GeoTiff แล้วตัดตาม polygon ที่กำหนดไว้ ซึ่งจะทำให้ข้อมูลเชิงพื้นที่ของคุณถูกจำกัดให้ตรงกับพื้นที่สนใจ

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## ขั้นตอนที่ 2: ดึงข้อมูล Raster (extract raster cell size & retrieve raster extent)
หลังจากตัดเลเยอร์แล้ว สกัดข้อมูลสำคัญของ raster เช่น ขนาดเซลล์, ระบบอ้างอิงเชิงพื้นที่, และขอบเขต

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## ขั้นตอนที่ 3: แสดงข้อมูล
พิมพ์ข้อมูลที่สกัดออกมาดูเพื่อเข้าใจผลกระทบของกระบวนการตัดต่อข้อมูลเชิงพื้นที่ของคุณ

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

ทำซ้ำขั้นตอนเหล่านี้ตามต้องการเพื่อปรับแต่งและทำให้ข้อมูลเชิงพื้นที่ของคุณตรงกับความต้องการของโครงการ

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **ทิศทางของ polygon ไม่ถูกต้อง** | ตรวจสอบให้แน่ใจว่า polygon ในรูปแบบ WKT ปฏิบัติตามกฎมือขวา (counter‑clockwise สำหรับ outer rings) |
| **ไม่มีระบบอ้างอิงเชิงพื้นที่** | ยืนยันว่า GeoTiff ต้นทางมี CRS; หากไม่มีให้ตั้งค่า CRS ด้วยตนเองก่อนทำการตัด |
| **ประสิทธิภาพช้าบน raster ขนาดใหญ่** | ใช้ `layer.Crop` กับสำเนาที่ลดขนาดลงหรือประมวลผล raster เป็นส่วนย่อย (tiles) |

## คำถามที่พบบ่อย
### Q: มีลิขสิทธิ์ชั่วคราวสำหรับ Aspose.GIS for .NET หรือไม่?
A: มี, คุณสามารถรับลิขสิทธิ์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)  

### Q: จะหาเอกสารประกอบทั้งหมดของ Aspose.GIS for .NET ได้จากที่ไหน?
A: เอกสารพร้อมใช้งาน [ที่นี่](https://reference.aspose.com/gis/net/)  

### Q: จะขอรับการสนับสนุนหรือเข้าร่วมชุมชนของ Aspose.GIS for .NET ได้อย่างไร?
A: เยี่ยมชม [ฟอรั่ม Aspose.GIS](https://forum.aspose.com/c/gis/33) เพื่อรับการสนับสนุนและเข้าร่วมชุมชน  

### Q: สามารถดาวน์โหลดรุ่นทดลองฟรีของ Aspose.GIS for .NET ได้หรือไม่?
A: ได้, ดาวน์โหลดรุ่นทดลองฟรีได้ [ที่นี่](https://releases.aspose.com/)  

### Q: จะซื้อ Aspose.GIS for .NET ได้จากที่ไหน?
A: สามารถซื้อไลบรารีได้ [ที่นี่](https://purchase.aspose.com/buy)  

### Q: สามารถตัดหลายเลเยอร์ในครั้งเดียวได้หรือไม่?
A: ได้ — ทำลูปผ่านแต่ละเลเยอร์และเรียก `Crop` ด้วยเรขาคณิตที่ต้องการ  

### Q: API รองรับรูปแบบ raster อื่น ๆ (เช่น JPEG2000) หรือไม่?
A: Aspose.GIS รองรับทุกรูปแบบที่ไดรเวอร์ GDAL รองรับ รวมถึง JPEG2000, PNG, และอื่น ๆ  

## สรุป
ด้วยการทำตามคู่มือนี้ คุณได้เรียนรู้ **วิธีการตัดเลเยอร์** อย่างมีประสิทธิภาพด้วย Aspose.GIS for .NET คุณสามารถ **ตัด raster ด้วย polygon**, **สกัดขนาดเซลล์ของ raster**, และ **ดึงขอบเขตของ raster** เพื่อให้ตรงกับความต้องการของโครงการใด ๆ อย่าลืมสำรวจ API อื่น ๆ เช่น การแปลงพิกัด, การจัดรูปแบบ raster, และการวิเคราะห์เวกเตอร์ เพื่อเปิดศักยภาพเต็มที่ของกระบวนการทำงานเชิงพื้นที่ของคุณ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-01-13  
**ทดสอบด้วย:** Aspose.GIS 24.10 for .NET  
**ผู้เขียน:** Aspose  

---