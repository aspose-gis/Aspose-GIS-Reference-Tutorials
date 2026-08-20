---
date: 2026-07-05
description: เรียนรู้วิธีตัด Layer Features ด้วย Aspose.GIS สำหรับ .NET รวมถึงวิธีตัด
  raster ด้วย polygon, ดึง raster cell size, และดึง raster extent. ดาวน์โหลด free
  trial ของคุณตอนนี้.
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: วิธีตัด Layer Features
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: วิธีตัด Layer Features ด้วย Aspose.GIS สำหรับ .NET
url: /th/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการตัดชั้นข้อมูล

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีการตัดชั้นข้อมูล** ด้วย Aspose.GIS for .NET ซึ่งเป็นไลบรารีที่ทรงพลังที่ช่วยให้คุณ **ตัด raster ด้วยรูปหลายเหลี่ยม**, **ดึงขนาดเซลล์ raster**, และ **ดึงขอบเขต raster** เพื่อการวิเคราะห์เชิงพื้นที่ที่แม่นยำ ไม่ว่าคุณจะกำลังเตรียมข้อมูลสำหรับเว็บแผนที่, ตัดภาพดาวเทียม, หรือแยกพื้นที่ที่สนใจ คู่มือขั้นตอนนี้จะแสดงให้คุณเห็นวิธีทำงานให้เสร็จเร็วและเชื่อถือได้

## คำตอบสั้น
- **“crop layer” หมายถึงอะไร?** มันจะตัด raster หรือ vector layer ให้เหลือเฉพาะขอบเขตของ geometry ที่กำหนด, ทิ้งส่วนที่อยู่นอกออกทั้งหมด  
- **รูปหลายเหลี่ยมใดที่ใช้ในตัวอย่างนี้?** รูปหลายเหลี่ยมที่กำหนดในรูปแบบ WKT (Well‑Known Text)  
- **ฉันสามารถดึงขนาดเซลล์หลังการตัดได้หรือไม่?** ใช่ – property `CellSize` จะคืนค่าความกว้างและความสูงของเซลล์ raster  
- **ฉันต้องมีลิขสิทธิ์เพื่อรันโค้ดหรือไม่?** ลิขสิทธิ์ชั่วคราวใช้ได้สำหรับการประเมิน; จำเป็นต้องมีลิขสิทธิ์เต็มสำหรับการใช้งานในผลิตภัณฑ์  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7

## “การตัดชั้นข้อมูล” คืออะไร?
**การตัดชั้นข้อมูลหมายถึงการจำกัดชุดข้อมูลให้อยู่ในพื้นที่ทางภูมิศาสตร์เฉพาะ, ทิ้งส่วนที่อยู่นอกออก** การดำเนินการนี้ช่วยลดขนาดไฟล์, เร่งการประมวลผลต่อไป, และมุ่งเน้นการวิเคราะห์ไปยังพื้นที่ที่คุณสนใจ การจำกัดข้อมูลให้กับพื้นที่ที่ต้องการยังทำให้กระบวนการต่อไปเช่นการจัดสไตล์, การวิเคราะห์, และการเผยแพร่ ง่ายขึ้น, พร้อมคงระบบอ้างอิงพิกัดและเมตาดาต้าต้นฉบับ

## ทำไมต้องใช้ Aspose.GIS สำหรับการตัดข้อมูล?
**Aspose.GIS สามารถประมวลผลไฟล์ raster ขนาดสูงสุด 2 GB โดยไม่ต้องโหลดภาพทั้งหมดเข้าสู่หน่วยความจำและรองรับรูปแบบ raster มากกว่า 30 รูปแบบ, รวมถึง GeoTIFF, JPEG2000, และ PNG** ไลบรารีนี้ให้การเรียกใช้ `Crop` เพียงบรรทัดเดียว, การจัดการ CRS อัตโนมัติ, และประสิทธิภาพแบบหลายเธรดที่สามารถตัด GeoTIFF ขนาด 500 MB ได้ภายในไม่กี่วินาทีบนเซิร์ฟเวอร์ทั่วไป

## ข้อกำหนดเบื้องต้น
ก่อนที่จะลงลึกในความมหัศจรรย์ของการจัดการเชิงพื้นที่, โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:

- Aspose.GIS for .NET Library: ตรวจสอบว่าคุณได้ติดตั้งไลบรารี Aspose.GIS ในโปรเจค .NET ของคุณแล้ว. คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/gis/net/).  
- Document Directory: ตั้งค่าโฟลเดอร์เพื่อเก็บเอกสารของคุณ. แทนที่ `"Your Document Directory"` ในโค้ดที่ให้ไว้ด้วยพาธจริงของโฟลเดอร์เอกสารของคุณ

ตอนนี้, มาดำดิ่งสู่คู่มือขั้นตอนต่อขั้นตอนกัน

## นำเข้า Namespaces
`Namespace` `Aspose.Gis` มีประเภทหลักทั้งหมดสำหรับการจัดการ raster และ vector. นำเข้าเพื่อเข้าถึงคลาส `Layer`, `Geometry`, และคลาสที่เกี่ยวข้อง

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## ฉันจะตัดชั้นข้อมูลด้วยรูปหลายเหลี่ยมอย่างไร?
`Crop` เป็นเมธอดของคลาส `Layer` ที่ดึงส่วนย่อยของ raster ตาม geometry ที่กำหนด.  
โหลด raster ต้นฉบับ, กำหนด geometry รูปหลายเหลี่ยม, และเรียกเมธอด `Crop` – การดำเนินการทั้งหมดทำในบรรทัดเดียวของโค้ด. เมธอดนี้จะคืนค่า raster ใหม่ที่มีพิกเซลเฉพาะภายในรูปหลายเหลี่ยม, โดยคงระบบอ้างอิงเชิงพื้นที่เดิมโดยอัตโนมัติ

## ขั้นตอนที่ 1: เปิดและตัดชั้นข้อมูล (crop raster ด้วยรูปหลายเหลี่ยม)
`Layer` แทนชุดข้อมูล raster ที่สามารถเปิด, คิวรี, และแก้ไขได้.  
คลาส `Layer` แทนชุดข้อมูล raster ที่สามารถเปิด, คิวรี, และแก้ไขได้. การเปิด GeoTIFF และตัดด้วยรูปหลายเหลี่ยมจะทำให้แยกพื้นที่ที่สนใจได้ด้วยคำสั่งไม่กี่บรรทัด

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## ขั้นตอนที่ 2: ดึงข้อมูล Raster (ดึงขนาดเซลล์ raster และดึงขอบเขต raster)
`CellSize` ให้ความกว้างและความสูงของแต่ละเซลล์ raster ในหน่วยพิกัด.  
`Extent` คืนค่ากล่องขอบเขตทางภูมิศาสตร์ของ raster.  
Property `CellSize` ให้ความกว้างและความสูงของแต่ละเซลล์ raster ในหน่วยพิกัด, ส่วน property `Extent` คืนค่ากล่องขอบเขตทางภูมิศาสตร์ของ raster ที่ถูกตัด. ข้อมูลทั้งสองนี้สำคัญสำหรับการคำนวณต่อไป เช่น การวัดพื้นที่หรือการทำ re‑projection

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## ขั้นตอนที่ 3: แสดงข้อมูล
พิมพ์ข้อมูลที่ดึงออกมาเพื่อทำความเข้าใจผลกระทบของกระบวนการตัดต่อข้อมูลเชิงพื้นที่ของคุณ

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

ทำซ้ำขั้นตอนเหล่านี้ตามต้องการเพื่อปรับแต่งข้อมูลเชิงพื้นที่ของคุณให้ตรงกับความต้องการของโครงการเฉพาะ

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **การวางแนวรูปหลายเหลี่ยมไม่ถูกต้อง** | ตรวจสอบให้แน่ใจว่า WKT polygon ปฏิบัติตามกฎมือขวา (ทิศทางนาฬิกาตรงกันข้ามสำหรับวงแหวนภายนอก). |
| **ไม่มีการอ้างอิงเชิงพื้นที่** | ตรวจสอบว่า GeoTiff ต้นฉบับมี CRS หรือไม่; หากไม่มีให้ตั้งค่าเองก่อนทำการตัด. |
| **ประสิทธิภาพช้าลงเมื่อทำงานกับ raster ขนาดใหญ่** | ใช้ `layer.Crop` กับสำเนาที่ลดขนาดลงหรือประมวลผล raster เป็นแผ่นย่อย (tiles). |

## คำถามที่พบบ่อย
**Q: มีลิขสิทธิ์ชั่วคราวสำหรับ Aspose.GIS for .NET หรือไม่?**  
A: ใช่, คุณสามารถรับลิขสิทธิ์ชั่วคราวได้จาก [here](https://purchase.aspose.com/temporary-license/).

**Q: ฉันสามารถหาเอกสารอธิบายอย่างละเอียดสำหรับ Aspose.GIS for .NET ได้ที่ไหน?**  
A: เอกสารสามารถดูได้ที่ [here](https://reference.aspose.com/gis/net/).

**Q: ฉันจะขอรับการสนับสนุนหรือเชื่อมต่อกับชุมชนของ Aspose.GIS for .NET ได้อย่างไร?**  
A: เยี่ยมชม [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อรับการสนับสนุนและเข้าร่วมชุมชน

**Q: ฉันสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีของ Aspose.GIS for .NET ได้หรือไม่?**  
A: ได้, คุณสามารถดาวน์โหลดรุ่นทดลองใช้ได้จาก [here](https://releases.aspose.com/).

**Q: ฉันสามารถซื้อ Aspose.GIS for .NET ได้จากที่ไหน?**  
A: คุณสามารถซื้อไลบรารีได้จาก [here](https://purchase.aspose.com/buy).

**Q: ฉันสามารถตัดหลายชั้นข้อมูลในรอบเดียวได้หรือไม่?**  
A: ได้—ทำลูปผ่านแต่ละชั้นและใช้การเรียก `Crop` เดียวกันกับ geometry ที่ต้องการ

**Q: API รองรับรูปแบบ raster อื่น ๆ (เช่น JPEG2000) หรือไม่?**  
A: Aspose.GIS รองรับทุกรูปแบบที่ไดรเวอร์ GDAL รองรับ, รวมถึง JPEG2000, PNG, และอื่น ๆ

## สรุป
ด้วยการทำตามคู่มือนี้คุณจะรู้ **วิธีการตัดชั้นข้อมูล** อย่างมีประสิทธิภาพด้วย Aspose.GIS for .NET. คุณสามารถ **ตัด raster ด้วยรูปหลายเหลี่ยม**, **ดึงขนาดเซลล์ raster**, และ **ดึงขอบเขต raster** เพื่อให้ตรงกับความต้องการของโครงการใด ๆ. สำรวจ API เพิ่มเติมสำหรับการทำ re‑projection, การจัดสไตล์ raster, และการวิเคราะห์ vector เพื่อเปิดศักยภาพเต็มของกระบวนการเชิงพื้นที่ของคุณ

---

**Last Updated:** 2026-07-05  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [How to Create Polygon Geometry with Aspose.GIS for .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Get Layer Attributes – Retrieve Layer Attribute Information with Aspose.GIS for .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Create Polygon Geometry C# and Check Intersection with Aspose.GIS for .NET](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}