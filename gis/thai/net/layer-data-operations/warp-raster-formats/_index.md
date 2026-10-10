---
date: 2026-10-10
description: เรียนรู้วิธีรับขนาดเซลล์ raster และเปลี่ยนความละเอียด raster โดยการแปลงรูปแบบ
  raster ด้วย Aspose.GIS สำหรับ .NET – คู่มือขั้นตอนต่อขั้นตอนสำหรับการแสดงผลข้อมูลเชิงพื้นที่
keywords:
- get raster cell size
- change raster resolution
- convert geotiff .net
lastmod: 2026-10-10
linktitle: แปลงรูปแบบ raster
og_description: รับขนาดเซลล์ raster หลังจากแปลง raster ด้วย Aspose.GIS สำหรับ .NET
  บทเรียนนี้แสดงวิธีเปลี่ยนความละเอียด raster, แปลงไฟล์ GeoTIFF, และดึงข้อมูลเมตาดาต้า
  raster อย่างละเอียดในไม่กี่ขั้นตอนง่ายๆ
og_image_alt: 'Developer guide: Get raster cell size and warp raster formats using
  Aspose.GIS for .NET'
og_title: รับขนาดเซลล์ raster และแปลง raster ด้วย Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to get raster cell size and change raster resolution by warping
    raster formats using Aspose.GIS for .NET – a step‑by‑step guide for spatial data
    visualization.
  headline: Get raster cell size – warp raster formats
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS supports a wide range of raster formats, providing flexibility
      in handling various spatial datasets.
    question: Is Aspose.GIS compatible with all raster formats?
  - answer: Aspose.GIS is designed to handle georeferenced data, ensuring accurate
      transformations. Ensure your raster images have proper spatial reference information.
    question: Can I perform raster warping on non‑georeferenced images?
  - answer: Join the discussion on the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      to share your experiences, ask questions, and collaborate with other developers.
    question: How can I contribute to the Aspose.GIS community?
  - answer: Yes, you can explore the capabilities of Aspose.GIS by downloading a free
      trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.GIS?
  - answer: Yes, if you need a temporary license, you can obtain one [here](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- raster processing
- Aspose.GIS
- .NET GIS
- geotiff warp
title: รับขนาดเซลล์ raster – แปลงรูปแบบ raster
url: /th/net/layer-data-operations/warp-raster-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# รับขนาดเซลล์ของเรสเตอร์ – การบิดรูปแบบเรสเตอร์

## บทนำ
ในบทเรียนนี้คุณจะ **รับขนาดเซลล์ของเรสเตอร์** หลังจากทำการบิดรูปภาพและค้นพบวิธีการ **เปลี่ยนความละเอียดของเรสเตอร์** สำหรับ GeoTIFF ใด ๆ โดยใช้ Aspose.GIS for .NET ไม่ว่าคุณจะกำลังเตรียมข้อมูลสำหรับบริการเว็บแมพ, จัดเรียงเลเยอร์สำหรับการวิเคราะห์เชิงพื้นที่, หรือเพียงต้องการตรวจสอบว่าการแปลงพิกัดยังคงรายละเอียดที่ต้องการ ขั้นตอนเหล่านี้จะให้คุณควบคุมรูปทรงและเมตาดาต้าของเรสเตอร์ได้อย่างเต็มที่ มาดำเนินการตามขั้นตอน ตั้งแต่การโหลดเรสเตอร์จนถึงการสกัดขนาดเซลล์และคุณสมบัติสำคัญอื่น ๆ

## คำตอบอย่างรวดเร็ว
- **เป้าหมายหลักคืออะไร?** เพื่อรับขนาดเซลล์ของเรสเตอร์หลังจากทำการบิดรูปภาพ.  
- **ใช้ไลบรารีใด?** Aspose.GIS for .NET.  
- **ฉันต้องการใบอนุญาตหรือไม่?** มีรุ่นทดลองฟรี; จำเป็นต้องมีใบอนุญาตสำหรับการใช้งานจริง.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **ตัวอย่างใช้เวลารันนานเท่าไหร่?** น้อยกว่านาทีหนึ่งบนเครื่องทั่วไป.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มการเดินทางนี้ โปรดตรวจสอบว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้พร้อมอยู่:
- Aspose.GIS for .NET: หากคุณยังไม่ได้ทำ, ดาวน์โหลดและติดตั้งไลบรารี Aspose.GIS คุณสามารถค้นหาเวอร์ชันล่าสุดได้ [here](https://releases.aspose.com/gis/net/).
- ไดเรกทอรีเอกสารของคุณ: ตั้งค่าไดเรกทอรีเพื่อเก็บเอกสารของคุณ ซึ่งจะสำคัญสำหรับการจัดการไฟล์ระหว่างกระบวนการบิดเรสเตอร์.

ตอนนี้เราพร้อมแล้ว, มาดำดิ่งสู่โค้ดกัน.

## นำเข้าเนมสเปซ
`Aspose.GIS` namespace ให้คลาสหลักสำหรับการดำเนินการเรสเตอร์และเวกเตอร์ นำเข้าเนมสเปซที่จำเป็นเพื่อเริ่มการผจญภัยด้านภูมิสารสนเทศของคุณ.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Raster;
using Aspose.Gis.SpatialReferencing;
```

## ขั้นตอนที่ 1: เริ่มต้นเส้นทาง
เริ่มต้นโดยกำหนดเส้นทางไปยังไดเรกทอรีเอกสารของคุณ นี่คือที่ที่ทุกอย่างจะเกิดขึ้น:

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: เปิดเลเยอร์เรสเตอร์
คลาส `RasterLayer` แทนชุดข้อมูลเรสเตอร์เดียวที่โหลดเข้าสู่หน่วยความจำ การเปิด GeoTIFF จะเตรียมพร้อมสำหรับการแปลงต่อไป.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(dataDir, "raster_float32.tif")))
```

## ขั้นตอนที่ 3: บิดเรสเตอร์
เมธอด `Warp` ทำการแปลงพิกัดและรีแซมพลิงเรสเตอร์ไปยังระบบอ้างอิงพิกัดและความละเอียดใหม่ มันซ่อนความซับซ้อนของคณิตศาสตร์ ทำให้คุณสามารถระบุขนาดเป้าหมายและระบบอ้างอิงเชิงพื้นที่เป้าหมายได้ในหนึ่งคำสั่ง  
`WarpOptions` ให้คุณกำหนดพารามิเตอร์เช่น ความกว้าง, ความสูงของผลลัพธ์, และระบบอ้างอิงเชิงพื้นที่เป้าหมายสำหรับการบิด.

```csharp
using (var warped = layer.Warp(new WarpOptions(){Height = 40, Width = 40, TargetSpatialReferenceSystem = SpatialReferenceSystem.Wgs84}))
```

## ขั้นตอนที่ 4: สกัดข้อมูลเรสเตอร์
หลังจากการบิด, คุณสามารถสอบถามเรสเตอร์ที่ได้สำหรับเมตาดาต้าสำคัญ เช่น ขนาดเซลล์, ระบบอ้างอิงเชิงพื้นที่, ขอบเขต, และจำนวนแบนด์ คุณสมบัติเหล่านี้ช่วยให้คุณตรวจสอบว่าการแปลงทำงานตามที่คาดหวัง.

```csharp
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
var bandCount = warped.BandCount;
```

## ขั้นตอนที่ 5: พิมพ์รายละเอียดเรสเตอร์
เรามาแสดงรายละเอียดสำคัญที่เราสกัดออกมา ให้คุณได้มองภาพรวดเร็วของรูปทรงและเนื้อหาของเรสเตอร์ที่บิดแล้ว.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
Console.WriteLine($"bandCount: {bandCount}");
```

## ขั้นตอนที่ 6: สำรวจแบนด์ของเรสเตอร์
`RasterBand` แทนแบนด์ (เลเยอร์) เดี่ยวของข้อมูลเรสเตอร์ เช่น สีแดง, สีเขียว, สีน้ำเงิน, หรือค่าระดับความสูง แบนด์แต่ละอันเก็บช่องข้อมูลแยกที่สามารถตรวจสอบประเภทข้อมูล, สถิติ, และการจัดการ NoData ได้.

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

## ทำไมต้องรับขนาดเซลล์ของเรสเตอร์?
การรับขนาดเซลล์ของเรสเตอร์หลังการบิดบอกระยะทางบนพื้นดินที่แต่ละพิกเซลแทนค่า ข้อมูลนี้สำคัญเมื่อคุณต้องการจัดเรียงหลายเลเยอร์, ทำการวิเคราะห์ตามระยะทาง, หรือยืนยันว่าการบิดได้รักษาความละเอียดเชิงพื้นที่ที่ต้องการ.

## วิธีบิดรูปแบบเรสเตอร์อย่างมีประสิทธิภาพ
เมธอด `Warp` ซ่อนตรรกะการแปลงพิกัดที่ซับซ้อน ทำให้คุณมุ่งเน้นที่พารามิเตอร์อินพุตเช่น ขนาดเป้าหมายและระบบอ้างอิงเชิงพื้นที่เป้าหมาย ซึ่งทำให้การแปลงข้อมูลระหว่างระบบพิกัด, รีแซมพลิงเป็นความละเอียดอื่น, หรือคลิปเป็นพื้นที่เฉพาะเป็นเรื่องง่าย.

## ประโยชน์เชิงปริมาณของ Aspose.GIS
Aspose.GIS รองรับ **มากกว่า 30 รูปแบบเรสเตอร์** และสามารถประมวลผลไฟล์ได้ถึง **2 GB** โดยไม่ต้องโหลดภาพทั้งหมดเข้าสู่หน่วยความจำ ให้การแปลงที่เร็วและใช้หน่วยความจำน้อยบนฮาร์ดแวร์เซิร์ฟเวอร์ทั่วไป.

## ปัญหาทั่วไปและวิธีแก้
- **ค่าขนาดเซลล์ที่ไม่คาดคิด:** ตรวจสอบให้แน่ใจว่าพารามิเตอร์ `Height` และ `Width` ตรงกับความละเอียดผลลัพธ์ที่ต้องการ.  
- **ไม่มีระบบอ้างอิงเชิงพื้นที่:** หาก `spatialRefSys` คืนค่า null, ตรวจสอบว่า GeoTIFF ต้นฉบับมีเมตาดาต้า CRS ที่ถูกต้อง.  
- **การจัดการ NoData:** ใช้ `warped.NoDataValues.IsNull()` เพื่อตรวจจับข้อมูลที่หายไป; คุณยังสามารถกำหนดค่า NoData ที่กำหนดเองก่อนการบิดได้.

## คำถามที่พบบ่อย

**Q: Aspose.GIS รองรับรูปแบบเรสเตอร์ทั้งหมดหรือไม่?**  
A: ใช่, Aspose.GIS รองรับรูปแบบเรสเตอร์หลากหลาย ให้ความยืดหยุ่นในการจัดการชุดข้อมูลเชิงพื้นที่ต่าง ๆ.

**Q: ฉันสามารถทำการบิดเรสเตอร์บนภาพที่ไม่มีการอ้างอิงเชิงพื้นที่ได้หรือไม่?**  
A: Aspose.GIS ถูกออกแบบให้จัดการข้อมูลที่อ้างอิงเชิงพื้นที่, เพื่อให้การแปลงแม่นยำ ตรวจสอบให้แน่ใจว่าภาพเรสเตอร์ของคุณมีข้อมูลระบบอ้างอิงเชิงพื้นที่ที่ถูกต้อง.

**Q: ฉันจะมีส่วนร่วมกับชุมชน Aspose.GIS อย่างไร?**  
A: เข้าร่วมการสนทนาที่ [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อแบ่งปันประสบการณ์, ถามคำถาม, และร่วมมือกับนักพัฒนาคนอื่น.

**Q: มีรุ่นทดลองฟรีสำหรับ Aspose.GIS หรือไม่?**  
A: ใช่, คุณสามารถสำรวจความสามารถของ Aspose.GIS โดยดาวน์โหลดรุ่นทดลองฟรี [here](https://releases.aspose.com/).

**Q: มีใบอนุญาตชั่วคราวสำหรับ Aspose.GIS หรือไม่?**  
A: ใช่, หากคุณต้องการใบอนุญาตชั่วคราว, คุณสามารถรับได้จาก [here](https://purchase.aspose.com/temporary-license/).

---

**อัปเดตล่าสุด:** 2026-10-10  
**ทดสอบด้วย:** Aspose.GIS for .NET (latest release)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [การดำเนินการข้อมูลเลเยอร์](/gis/net/layer-data-operations/)
- [วิธีเพิ่มเลเยอร์ไปยังชุดข้อมูล File GDB ด้วยระบบอ้างอิงเชิงพื้นที่ WGS84 โดยใช้ Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)
- [วิธีสร้างเลเยอร์เวกเตอร์ด้วย SRS โดยใช้ Aspose.GIS for .NET](/gis/net/layer-management/create-vector-layer-with-srs/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}