---
date: 2026-01-13
description: เรียนรู้วิธีแปลง shapefile เป็น geojson ด้วย Aspose.GIS สำหรับ .NET คู่มือนี้ยังครอบคลุมการคัดลอกแอตทริบิวต์ระหว่างเลเยอร์และการสร้างไฟล์
  geojson ด้วย C#
linktitle: Extract Features to GeoJSON
second_title: Aspose.GIS .NET API
title: วิธีแปลง Shapefile เป็น GeoJSON ด้วย Aspose.GIS สำหรับ .NET
url: /th/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง Shapefile เป็น GeoJSON ด้วย Aspose.GIS สำหรับ .NET

## บทนำ
ในบทแนะนำเชิงลึกแบบขั้นตอน‑ต่อ‑ขั้นตอนนี้ คุณจะได้เรียนรู้ **วิธีแปลง shapefile เป็น geojson** ด้วยไลบรารี Aspose.GIS ที่ทรงพลังสำหรับ .NET ไม่ว่าคุณจะกำลังสร้างบริการเว็บแมปปิ้ง, เตรียมข้อมูลสำหรับแอป GIS บนมือถือ, หรือเพียงต้องการแลกเปลี่ยนข้อมูลระหว่างรูปแบบต่าง ๆ คู่มือนี้จะแสดงให้คุณเห็นว่าต้องทำอะไร, ทำไมขั้นตอนแต่ละขั้นตอนสำคัญ, และวิธีหลีกเลี่ยงข้อผิดพลาดทั่วไป

## คำตอบสั้น
- **บทเรียนนี้ครอบคลุมอะไร?** การแปลง Shapefile เป็นไฟล์ GeoJSON, การคัดลอกแอตทริบิวต์ระหว่างเลเยอร์, และการสร้างผลลัพธ์ด้วย C#  
- **ต้องใช้ไลบรารีอะไร?** Aspose.GIS สำหรับ .NET  
- **ต้องมีลิขสิทธิ์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์ชั่วคราวหรือเต็มสำหรับการใช้งานจริง; เวอร์ชันทดลองฟรีใช้ได้สำหรับการประเมินผล  
- **ใช้เวลานานเท่าไหร่ในการทำงาน?** ประมาณ 10‑15 นาทีสำหรับการแปลงพื้นฐาน  
- **สามารถรันบน .NET Core/.NET 6 ได้หรือไม่?** ได้ – โค้ดทำงานบนทุกเวอร์ชัน .NET ที่รองรับ  

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึก โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้แล้ว:

- Aspose.GIS สำหรับ .NET: ตรวจสอบว่าคุณได้ติดตั้งไลบรารีแล้ว หากยังไม่มีสามารถดาวน์โหลดได้จาก [หน้า Aspose.GIS สำหรับ .NET](https://releases.aspose.com/gis/net/)  
- ข้อมูล Shapefile: มี Shapefile พร้อมใช้เป็นอินพุต หากต้องการตัวอย่างข้อมูลสามารถหาได้ใน [เอกสาร Aspose.GIS](https://reference.aspose.com/gis/net/)  
- สภาพแวดล้อม .NET: ตั้งค่าสภาพแวดล้อม .NET เพื่อรันโค้ดที่ให้มา  
- โฟลเดอร์เอกสาร: กำหนดเส้นทางไปยังโฟลเดอร์เอกสารของคุณในโค้ดสแนป

เมื่อคุณเตรียมทุกอย่างพร้อมแล้ว เริ่มแปลง shapefile เป็น geojson กันเถอะ!

## “convert shapefile to geojson” คืออะไร?
การแปลง Shapefile เป็น GeoJSON หมายถึงการอ่านฟีเจอร์เวกเตอร์จากรูปแบบไฟล์ ESRI Shapefile แบบคลาสสิกและเขียนออกเป็นเอกสาร GeoJSON สมัยใหม่ที่เป็นมิตรกับเว็บ GeoJSON ถูกใช้กันอย่างกว้างขวางในไลบรารีแมปปิ้ง JavaScript (Leaflet, Mapbox GL) และ API ต่าง ๆ ทำให้การแปลงนี้เป็นงานที่พบบ่อยในการพัฒนา GIS

## ทำไมต้องใช้ Aspose.GIS สำหรับการแปลงนี้?
Aspose.GIS จัดการรายละเอียดระดับต่ำของรูปแบบไฟล์, ทำให้คุณคัดลอกตารางแอตทริบิวต์ได้อย่างง่ายดาย, และให้ API แบบวัตถุ‑ออริเอนต์ที่ทำงานข้าม .NET Framework, .NET Core, และ .NET 5/6 ดังนั้นคุณสามารถมุ่งเน้นที่ตรรกะธุรกิจแทนการพาร์สไฟล์ไบนารี

## นำเข้า Namespaces
ก่อนอื่นให้เพิ่ม Namespaces ที่จำเป็นในโค้ดของคุณ:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Namespaces เหล่านี้เป็นสิ่งจำเป็นสำหรับการทำงานกับฟังก์ชันของ Aspose.GIS

## วิธีแปลง Shapefile เป็น GeoJSON
ด้านล่างเป็นเวิร์กโฟลว์เต็มที่แบ่งเป็นขั้นตอนชัดเจน แต่ละขั้นตอนมีคำอธิบายสั้น ๆ ตามด้วยโค้ดบล็อกที่ต้องคัดลอกไปใส่ในโปรเจกต์ของคุณ

### ขั้นตอนที่ 1: เปิด Shapefile อินพุต
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```
เปิด Shapefile อินพุตด้วยเมธอด `VectorLayer.Open` ซึ่งจะให้คอลเลกชันแบบ enumerable ของอ็อบเจกต์ `Feature`

### ขั้นตอนที่ 2: สร้าง GeoJSON เอาต์พุต
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```
สร้างไฟล์เอาต์พุตด้วยเมธอด `VectorLayer.Create` โดยระบุไดรเวอร์ `Drivers.GeoJson`

### ขั้นตอนที่ 3: คัดลอกแอตทริบิวต์ระหว่างเลเยอร์
```csharp
outputLayer.CopyAttributes(inputLayer);
```
บรรทัดเดียวนี้คัดลอกสคีม่าแอตทริบิวต์ (ชื่อฟิลด์, ชนิด) จาก Shapefile ต้นทางไปยังเลเยอร์ GeoJSON ใหม่ – ตรงกับคีย์เวิร์ดรอง *copy attributes between layers* ที่อธิบายไว้

### ขั้นตอนที่ 4: ประมวลผลฟีเจอร์
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```
วนลูปผ่านแต่ละฟีเจอร์ใน Shapefile เพื่อให้คุณสามารถใส่ตรรกะส่วนตัวก่อนเขียนออก

### ขั้นตอนที่ 5: กรองฟีเจอร์ตามวันที่
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
ในตัวอย่างนี้เราข้ามเรคคอร์ดที่ฟิลด์ `dob` (date of birth) ขาดหายหรือก่อนวันที่ 1 ม.ค. 1982 ปรับตัวกรองตามความต้องการของข้อมูลของคุณได้เลย

### ขั้นตอนที่ 6: สร้างฟีเจอร์ใหม่ (C# Generate GeoJSON File)
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
ที่นี่เราสร้าง `Feature` ใหม่สำหรับเลเยอร์ GeoJSON, คัดลอกเรขาคณิตและค่าแอตทริบิวต์, แล้วเพิ่มลงในเอาต์พุต นี่คือหัวใจของ *c# generate geojson file*

ยินดีด้วย! คุณได้ **แปลง shapefile เป็น geojson** สำเร็จและเรียนรู้วิธีคัดลอกแอตทริบิวต์ระหว่างเลเยอร์ไปพร้อมกัน

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| ไฟล์เอาต์พุตว่าง | `CopyAttributes` ถูกเรียกหลังจากเลเยอร์เอาต์พุตถูกปิด | ตรวจสอบให้แน่ใจว่า `using` block สำหรับ `outputLayer` ยังคงเปิดอยู่จนกว่าจะเพิ่มฟีเจอร์ทั้งหมดเสร็จ |
| ตัวกรองวันที่ลบทุกเรคคอร์ด | ชื่อฟิลด์ผิดหรือรูปแบบวันที่ไม่คาดคิด | ตรวจสอบชื่อแอตทริบิวต์ (`dob`) และใช้ `GetValue<string>` หากวันที่เก็บเป็นสตริง |
| ข้อยกเว้นลิขสิทธิ์ | รันโดยไม่มีลิขสิทธิ์ Aspose.GIS ที่ถูกต้องในสภาพการผลิต | ใช้ลิขสิทธิ์ชั่วคราวหรือเต็มตามที่อธิบายในเอกสาร Aspose |

## คำถามที่พบบ่อย
**ถาม: จะหาเอกสารเพิ่มเติมได้จากที่ไหน?**  
ตอบ: เยี่ยมชม [เอกสาร Aspose.GIS](https://reference.aspose.com/gis/net/) เพื่อข้อมูลเชิงลึก

**ถาม: จะขอรับลิขสิทธิ์ชั่วคราวได้อย่างไร?**  
ตอบ: คุณสามารถรับลิขสิทธิ์ชั่วคราวได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/)

**ถาม: จะหาการสนับสนุนได้จากที่ไหน?**  
ตอบ: เข้าร่วม [ฟอรั่ม Aspose.GIS](https://forum.aspose.com/c/gis/33) เพื่อรับการสนับสนุนจากชุมชนและการสนทนา

**ถาม: มีการทดลองใช้แบบฟรีหรือไม่?**  
ตอบ: มี, คุณสามารถดาวน์โหลดการทดลองใช้ฟรีได้จาก [ที่นี่](https://releases.aspose.com/)

**ถาม: จะซื้อ Aspose.GIS สำหรับ .NET ได้จากที่ไหน?**  
ตอบ: คุณสามารถสั่งซื้อผลิตภัณฑ์ได้จาก [ที่นี่](https://purchase.aspose.com/buy)

## สรุป
ในบทแนะนำนี้เราได้สำรวจกระบวนการทั้งหมดของ **convert shapefile to geojson** ด้วย Aspose.GIS สำหรับ .NET, แสดงวิธีคัดลอกแอตทริบิวต์ระหว่างเลเยอร์, และนำเสนอวิธีที่สะอาดในการ *c# generate geojson file* ทดลองใช้ตัวกรองต่าง ๆ, ชุดข้อมูลขนาดใหญ่, หรือการแปลงเรขาคณิตเพิ่มเติมเพื่อใช้ศักยภาพของไลบรารีให้เต็มที่

---

**อัปเดตล่าสุด:** 2026-01-13  
**ทดสอบด้วย:** Aspose.GIS สำหรับ .NET (รุ่นเสถียรล่าสุด)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}