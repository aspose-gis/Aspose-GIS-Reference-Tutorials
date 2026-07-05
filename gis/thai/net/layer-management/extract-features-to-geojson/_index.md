---
date: 2026-07-05
description: เรียนรู้วิธีแปลง shapefile เป็น geojson ด้วย Aspose.GIS for .NET. คู่มือนี้ยังครอบคลุมการคัดลอกแอตทริบิวต์ระหว่างเลเยอร์และการสร้างไฟล์
  geojson ด้วย c#
keywords:
- convert shapefile to geojson
- export shapefile as geojson
- aspose gis conversion
- read shapefile c#
- write geojson c#
linktitle: สกัดคุณลักษณะเป็น GeoJSON
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  headline: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  name: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  steps:
  - name: Open Input Shapefile
    text: The `VectorLayer.Open` method reads a Shapefile and returns an enumerable
      collection of `Feature` objects that you can iterate over.
  - name: Create Output GeoJSON
    text: '`VectorLayer.Create` with the `Drivers.GeoJson` driver creates an empty
      GeoJSON file ready to receive features.'
  - name: Copy Attributes Between Layers
    text: '`CopyAttributes` copies the attribute schema (field names and data types)
      from the source Shapefile to the new GeoJSON layer in a single call.'
  - name: Process Features
    text: Iterate through each feature in the Shapefile so you can apply any custom
      logic before writing it out.
  - name: Filter Features by Date
    text: In this example we skip records whose `dob` (date of birth) field is missing
      or earlier than 1 Jan 1982. Adjust the filter to match your own data requirements.
  - name: Construct a New Feature (C# Generate GeoJSON File)
    text: A `Feature` represents a single spatial element containing geometry and
      attribute data. Here we build a new `Feature` for the GeoJSON layer, copy the
      geometry and attribute values, and add it to the output. This is the core of
      *c# generate geojson file*. Congratulations! You’ve successfully **conver
  type: HowTo
- questions:
  - answer: Visit the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for in‑depth information.
    question: Where can I find more documentation?
  - answer: You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I seek support?
  - answer: Yes, you can find the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can buy the product [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: แปลง Shapefile เป็น GeoJSON ด้วย Aspose.GIS for .NET
url: /th/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง Shapefile เป็น GeoJSON ด้วย Aspose.GIS สำหรับ .NET

## บทนำ
ในบทแนะนำเชิงลึกแบบขั้นตอน‑ต่อ​ขั้นตอนนี้ คุณจะได้เรียนรู้ **how to convert shapefile to geojson** ด้วยไลบรารี Aspose.GIS ที่ทรงพลังสำหรับ .NET ไม่ว่าคุณจะสร้างบริการเว็บแมปปิ้ง, เตรียมข้อมูลสำหรับแอป GIS บนมือถือ, หรือแค่ต้องการแลกเปลี่ยนข้อมูลระหว่างรูปแบบต่าง ๆ คู่มือฉบับนี้จะแสดงให้คุณเห็นอย่างชัดเจนว่าต้องทำอะไร, ทำไมแต่ละขั้นตอนถึงสำคัญ, และจะหลีกเลี่ยงข้อผิดพลาดทั่วไปอย่างไร

## คำตอบด่วน
- **บทเรียนนี้ครอบคลุมอะไรบ้าง?** การแปลง Shapefile เป็นไฟล์ GeoJSON, การคัดลอกแอตทริบิวต์ระหว่างเลเยอร์, และการสร้างผลลัพธ์ด้วย C#.
- **ต้องใช้ไลบรารีใด?** Aspose.GIS สำหรับ .NET.
- **ต้องมีไลเซนส์หรือไม่?** จำเป็นต้องมีไลเซนส์ชั่วคราวหรือเต็มสำหรับการใช้งานจริง; เวอร์ชันทดลองฟรีใช้ได้สำหรับการประเมิน.
- **ใช้เวลานานเท่าไหร่ในการทำงาน?** ประมาณ 10‑15 นาทีสำหรับการแปลงพื้นฐาน.
- **สามารถรันบน .NET Core/.NET 6 ได้หรือไม่?** ได้ – โค้ดทำงานบนทุกเวอร์ชัน .NET ที่รองรับ.

## การแปลง shapefile เป็น geojson คืออะไร?
การแปลง Shapefile เป็น GeoJSON หมายถึงการอ่านฟีเจอร์เวกเตอร์จากรูปแบบ Shapefile ของ ESRI แบบคลาสสิกและเขียนออกเป็นเอกสาร GeoJSON สมัยใหม่ที่เป็นมิตรกับเว็บ การแปลงนี้ทำให้คุณสามารถส่งข้อมูล GIS ไปยังไลบรารีแผนที่ JavaScript เช่น Leaflet หรือ Mapbox GL ได้โดยตรง และช่วยให้การแลกเปลี่ยนข้อมูลระหว่างเครื่องมือ GIS บนเดสก์ท็อปและเว็บ API ง่ายขึ้น

## ทำไมต้องใช้ Aspose.GIS สำหรับการแปลงนี้?
Aspose.GIS แยกการแยกวิเคราะห์ไบนารีระดับต่ำออก, รองรับรูปแบบเข้าและออกกว่า 50 รูปแบบ, และสามารถประมวลผลชุดข้อมูลหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ไลบรารียังมี API แบบวัตถุ‑ออเรียนเทดที่สะอาดและทำงานได้บน .NET Framework, .NET Core, และ .NET 5/6 ทำให้คุณใช้เวลาในการเขียนโลจิกธุรกิจแทนการจัดการรูปแบบไฟล์

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- Aspose.GIS for .NET: ตรวจสอบว่าคุณได้ติดตั้งไลบรารีแล้ว หากยังไม่ได้คุณสามารถดาวน์โหลดได้จากหน้า [Aspose.GIS for .NET page](https://releases.aspose.com/gis/net/).
- Shapefile Data: มี Shapefile พร้อมสำหรับการนำเข้า หากต้องการข้อมูลตัวอย่าง คุณสามารถหาได้ใน [Aspose.GIS documentation](https://reference.aspose.com/gis/net/).
- .NET Environment: ตั้งค่าสภาพแวดล้อม .NET เพื่อรันโค้ดที่ให้มา
- Document Directory: กำหนดเส้นทางไปยังไดเรกทอรีเอกสารของคุณในโค้ดสแนป

ตอนนี้คุณมีทุกอย่างพร้อมแล้ว, มาเริ่มแปลง shapefile เป็น geojson กันเถอะ!

## วิธีแปลง Shapefile เป็น GeoJSON
โหลด Shapefile ต้นฉบับ, สร้างเลเยอร์ GeoJSON ปลายทาง, คัดลอกสคีม่าแอตทริบิวต์, กรองเรคคอร์ด, และเขียนผลลัพธ์—ทั้งหมดในไม่กี่ขั้นตอนที่กระชับ กระบวนการทำงานทั้งหมดพอดีในบล็อก `using` เดียว, ทำให้ทรัพยากรถูกปล่อยโดยอัตโนมัติ

### ขั้นตอนที่ 1: เปิด Shapefile อินพุต
เมธอด `VectorLayer.Open` อ่าน Shapefile และคืนคอลเลกชันที่วนได้ของอ็อบเจกต์ `Feature` ที่คุณสามารถวนผ่านได้

```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```

### ขั้นตอนที่ 2: สร้าง GeoJSON เอาต์พุต
`VectorLayer.Create` พร้อมไดรเวอร์ `Drivers.GeoJson` สร้างไฟล์ GeoJSON ว่างพร้อมรับฟีเจอร์

```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```

### ขั้นตอนที่ 3: คัดลอกแอตทริบิวต์ระหว่างเลเยอร์
`CopyAttributes` คัดลอกสคีม่าแอตทริบิวต์ (ชื่อฟิลด์และประเภทข้อมูล) จาก Shapefile ต้นฉบับไปยังเลเยอร์ GeoJSON ใหม่ในหนึ่งคำสั่ง

```csharp
outputLayer.CopyAttributes(inputLayer);
```

### ขั้นตอนที่ 4: ประมวลผลฟีเจอร์
วนผ่านแต่ละฟีเจอร์ใน Shapefile เพื่อให้คุณสามารถใช้ตรรกะกำหนดเองก่อนเขียนออก

```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```

### ขั้นตอนที่ 5: กรองฟีเจอร์ตามวันที่
ในตัวอย่างนี้เราข้ามเรคคอร์ดที่ฟิลด์ `dob` (date of birth) ขาดหายหรือก่อนวันที่ 1 Jan 1982 ปรับตัวกรองให้ตรงกับความต้องการข้อมูลของคุณ

```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```

### ขั้นตอนที่ 6: สร้าง Feature ใหม่ (C# Generate GeoJSON File)
`Feature` แทนองค์ประกอบเชิงพื้นที่เดียวที่มีเรขาคณิตและข้อมูลแอตทริบิวต์  
ที่นี่เราสร้าง `Feature` ใหม่สำหรับเลเยอร์ GeoJSON, คัดลอกเรขาคณิตและค่าต่าง ๆ ของแอตทริบิวต์, แล้วเพิ่มเข้าไปในผลลัพธ์ นี่คือหัวใจของ *c# generate geojson file*

```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```

ยินดีด้วย! คุณได้ทำการ **convert shapefile to geojson** สำเร็จและได้เรียนรู้วิธี **copy attributes between layers** ระหว่างทาง

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| ไฟล์ผลลัพธ์ว่างเปล่า | `CopyAttributes` ถูกเรียกหลังจากเลเยอร์เอาต์พุตถูกปิด | ตรวจสอบให้บล็อก `using` สำหรับ `outputLayer` เปิดอยู่จนกว่าจะเพิ่มฟีเจอร์ทั้งหมดเสร็จ |
| ตัวกรองวันที่ลบเรคคอร์ดทั้งหมด | ชื่อฟิลด์ผิดหรือรูปแบบวันที่ไม่คาดคิด | ตรวจสอบชื่อแอตทริบิวต์ (`dob`) และใช้ `GetValue<string>` หากวันที่ถูกเก็บเป็นสตริง |
| ข้อยกเว้นไลเซนส์ | รันโดยไม่มีไลเซนส์ Aspose.GIS ที่ถูกต้องในสภาพการผลิต | ใช้ไลเซนส์ชั่วคราวหรือเต็มตามที่อธิบายในเอกสาร Aspose |

## คำถามที่พบบ่อย
**Q: จะหาเอกสารเพิ่มเติมได้จากที่ไหน?**  
A: เยี่ยมชม [Aspose.GIS documentation](https://reference.aspose.com/gis/net/) เพื่อข้อมูลเชิงลึก

**Q: จะขอไลเซนส์ชั่วคราวได้อย่างไร?**  
A: คุณสามารถรับไลเซนส์ชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)

**Q: จะหาการสนับสนุนได้จากที่ไหน?**  
A: เข้าร่วม [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อรับการสนับสนุนจากชุมชนและการสนทนา

**Q: มีการทดลองใช้ฟรีหรือไม่?**  
A: มี, คุณสามารถดาวน์โหลดการทดลองใช้ฟรีได้ [ที่นี่](https://releases.aspose.com/)

**Q: จะซื้อ Aspose.GIS สำหรับ .NET ได้จากที่ไหน?**  
A: คุณสามารถสั่งซื้อผลิตภัณฑ์ได้ [ที่นี่](https://purchase.aspose.com/buy)

## สรุป
ในบทเรียนนี้เราได้สำรวจกระบวนการเต็มของ **convert shapefile to geojson** ด้วย Aspose.GIS สำหรับ .NET, แสดงวิธี **copy attributes between layers**, และนำเสนอวิธีที่สะอาดในการ *c# generate geojson file* ทดลองใช้ตัวกรองต่าง ๆ, ชุดข้อมูลขนาดใหญ่, หรือการแปลงเรขาคณิตเพิ่มเติมเพื่อใช้ศักยภาพของไลบรารีอย่างเต็มที่

---

**อัปเดตล่าสุด:** 2026-07-05  
**ทดสอบด้วย:** Aspose.GIS for .NET (latest stable release)  
**ผู้เขียน:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## บทเรียนที่เกี่ยวข้อง

- [วิธีแปลง GeoJSON เป็น File GDB ด้วย Aspose.GIS สำหรับ .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [วิธีอ่าน GeoJSON จาก Stream ด้วย Aspose.GIS สำหรับ .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [วิธีแปลง GeoJSON เป็น TopoJSON ด้วย Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}