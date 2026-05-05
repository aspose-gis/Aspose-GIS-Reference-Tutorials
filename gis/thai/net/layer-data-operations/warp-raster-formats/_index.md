---
date: 2026-05-05
description: เรียนรู้วิธีการรับขนาดเซลล์ของราสเตอร์และวิธีการแปลงรูปแบบราสเตอร์โดยใช้
  Aspose.GIS สำหรับ .NET คู่มือแบบขั้นตอนต่อขั้นตอนสำหรับการแสดงผลข้อมูลเชิงพื้นที่.
keywords:
- get raster cell size
- how to warp raster
- Aspose GIS raster
linktitle: รูปแบบเรสเตอร์แบบ Warp
second_title: Aspose.GIS .NET API
title: รับขนาดเซลล์เรสเตอร์ – บิดเบือนรูปแบบเรสเตอร์ด้วย Aspose.GIS
url: /th/net/layer-data-operations/warp-raster-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# รับขนาดเซลล์เรสเตอร์ – บิดรูปแบบเรสเตอร์

## บทนำ
ยินดีต้อนรับสู่โลกที่น่าตื่นเต้นของการเขียนโปรแกรมเชิงพื้นที่กับ Aspose.GIS สำหรับ .NET! ในบทเรียนนี้ คุณจะ **รับขนาดเซลล์เรสเตอร์** หลังจากทำการบิดเรสเตอร์ และเรียนรู้ **วิธีบิดรูปแบบเรสเตอร์** ทีละขั้นตอน ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น เตรียมตัวให้พร้อมขณะเราลงลึกในรายละเอียดของการจัดการ GeoTIFF เพื่อให้ข้อมูลเชิงพื้นที่ของคุณได้รับมุมมองใหม่ทั้งหมด.

## คำตอบอย่างรวดเร็ว
- **เป้าหมายหลักคืออะไร?** เพื่อรับขนาดเซลล์เรสเตอร์หลังจากทำการบิด.  
- **ใช้ไลบรารีใด?** Aspose.GIS สำหรับ .NET.  
- **ต้องการไลเซนส์หรือไม่?** มีรุ่นทดลองฟรี; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **ตัวอย่างใช้เวลารันเท่าไหร่?** น้อยกว่านาทีหนึ่งบนเครื่องทั่วไป.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มการเดินทางนี้ โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมอยู่:
- Aspose.GIS สำหรับ .NET: หากคุณยังไม่ได้ทำ, ดาวน์โหลดและติดตั้งไลบรารี Aspose.GIS คุณสามารถค้นหาเวอร์ชันล่าสุดได้ [ที่นี่](https://releases.aspose.com/gis/net/).
- โฟลเดอร์เอกสารของคุณ: ตั้งค่าโฟลเดอร์เพื่อเก็บเอกสารของคุณ ซึ่งจะสำคัญสำหรับการจัดการไฟล์ระหว่างกระบวนการบิดเรสเตอร์

ตอนนี้เราพร้อมแล้ว, มาดำดิ่งสู่โค้ดกันเถอะ.

## นำเข้าเนมสเปซ
สิ่งแรกที่ต้องทำคือให้แน่ใจว่าเรามีเครื่องมือที่เหมาะสมอยู่ในมือ นำเข้าเนมสเปซที่จำเป็นเพื่อเริ่มต้นการผจญภัยเชิงพื้นที่ของคุณ:
```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Raster;
using Aspose.Gis.SpatialReferencing;
```

## ขั้นตอนที่ 1: เริ่มต้นเส้นทาง
เริ่มต้นโดยกำหนดเส้นทางไปยังโฟลเดอร์เอกสารของคุณ นี่คือที่ที่ทุกอย่างจะเกิดขึ้น:
```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: เปิดชั้นเรสเตอร์
เปิดชั้นเรสเตอร์ GeoTiff และเตรียมพร้อมสำหรับการแปลง ขั้นตอนนี้เป็นการวางพื้นฐานสำหรับการบิดต่อไป:
```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(dataDir, "raster_float32.tif")))
```

## ขั้นตอนที่ 3: บิดเรสเตอร์
ตอนนี้ให้ทำการบิดข้อมูล ระบุขนาดเป้าหมายและระบบอ้างอิงเชิงพื้นที่เพื่อให้ข้อมูลเรสเตอร์ของคุณมีชีวิตใหม่:
```csharp
using (var warped = layer.Warp(new WarpOptions(){Height = 40, Width = 40, TargetSpatialReferenceSystem = SpatialReferenceSystem.Wgs84}))
```

## ขั้นตอนที่ 4: ดึงข้อมูลเรสเตอร์
ถึงเวลาที่จะเปิดเผยความลับของเรสเตอร์ที่แปลงแล้ว ดึงข้อมูลสำคัญเช่น ขนาดเซลล์, ระบบอ้างอิงเชิงพื้นที่, ขอบเขต, และจำนวนแบนด์:
```csharp
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
var bandCount = warped.BandCount;
```

## ขั้นตอนที่ 5: พิมพ์รายละเอียดเรสเตอร์
เรามาพิมพ์รายละเอียดที่ได้ค้นพบเพื่อให้เข้าใจเรสเตอร์ที่บิดแล้ว:
```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
Console.WriteLine($"bandCount: {bandCount}");
```

## ขั้นตอนที่ 6: สำรวจแบนด์ของเรสเตอร์
สำรวจแบนด์แต่ละอันของเรสเตอร์ ค้นหาชนิดข้อมูล, สถิติ, และการมีค่าที่ไม่มีข้อมูล (NoData):
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

## ทำไมต้องรับขนาดเซลล์เรสเตอร์?
การทราบขนาดเซลล์หลังการบิดช่วยให้คุณเข้าใจความละเอียดเชิงพื้นที่ของชุดข้อมูลที่ได้ เป็นสิ่งสำคัญเมื่อคุณต้องการจัดชั้นหลายชั้นให้สอดคล้อง, ทำการวิเคราะห์ที่ขึ้นกับระยะทางบนพื้นดิน, หรือเพียงตรวจสอบว่าการบิดได้รักษาระดับรายละเอียดที่ต้องการไว้หรือไม่.

## วิธีบิดรูปแบบเรสเตอร์อย่างมีประสิทธิภาพ
เมธอด `Warp` แยกตรรกะการแปลงพิกัดที่ซับซ้อนออก ให้คุณมุ่งเน้นที่พารามิเตอร์อินพุตเช่น ขนาดเป้าหมายและระบบอ้างอิงเชิงพื้นที่เป้าหมาย ทำให้การแปลงข้อมูลระหว่างระบบพิกัด, การสุ่มตัวอย่างใหม่เป็นความละเอียดต่าง ๆ, หรือการคลิปไปยังพื้นที่เฉพาะเป็นเรื่องง่าย.

## ปัญหาทั่วไปและวิธีแก้
- **ค่าขนาดเซลล์ที่ไม่คาดคิด:** ตรวจสอบให้แน่ใจว่าพารามิเตอร์ `Height` และ `Width` ตรงกับความละเอียดผลลัพธ์ที่ต้องการ.  
- **ไม่มีระบบอ้างอิงเชิงพื้นที่:** หาก `spatialRefSys` คืนค่า null, ตรวจสอบว่า GeoTIFF ต้นทางมีเมตาดาต้า CRS ที่ถูกต้อง.  
- **การจัดการ NoData:** ใช้ `warped.NoDataValues.IsNull()` เพื่อตรวจจับข้อมูลที่หายไป; คุณยังสามารถกำหนดค่า NoData แบบกำหนดเองก่อนการบิดได้.

## คำถามที่พบบ่อย

**Q: Aspose.GIS รองรับรูปแบบเรสเตอร์ทั้งหมดหรือไม่?**  
A: ใช่, Aspose.GIS รองรับรูปแบบเรสเตอร์หลายประเภท ให้ความยืดหยุ่นในการจัดการชุดข้อมูลเชิงพื้นที่ต่าง ๆ.

**Q: ฉันสามารถทำการบิดเรสเตอร์บนภาพที่ไม่มีการอ้างอิงเชิงพื้นที่ได้หรือไม่?**  
A: Aspose.GIS ถูกออกแบบให้จัดการข้อมูลที่อ้างอิงเชิงพื้นที่ เพื่อให้การแปลงแม่นยำ ตรวจสอบให้แน่ใจว่าภาพเรสเตอร์ของคุณมีข้อมูลอ้างอิงเชิงพื้นที่ที่ถูกต้อง.

**Q: ฉันจะมีส่วนร่วมกับชุมชน Aspose.GIS อย่างไร?**  
A: เข้าร่วมการสนทนาที่ [ฟอรั่ม Aspose.GIS](https://forum.aspose.com/c/gis/33) เพื่อแบ่งปันประสบการณ์, ถามคำถาม, และร่วมมือกับนักพัฒนาคนอื่น ๆ.

**Q: มีรุ่นทดลองฟรีสำหรับ Aspose.GIS หรือไม่?**  
A: มี, คุณสามารถสำรวจความสามารถของ Aspose.GIS ได้โดยดาวน์โหลดรุ่นทดลองฟรี [ที่นี่](https://releases.aspose.com/).

**Q: มีไลเซนส์ชั่วคราวสำหรับ Aspose.GIS หรือไม่?**  
A: มี, หากคุณต้องการไลเซนส์ชั่วคราว คุณสามารถรับได้ [ที่นี่](https://purchase.aspose.com/temporary-license/).

**อัปเดตล่าสุด:** 2026-05-05  
**ทดสอบด้วย:** Aspose.GIS สำหรับ .NET (รุ่นล่าสุด)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}