---
date: 2025-11-30
description: เรียนรู้วิธีแปลง GeoJSON เป็น TopoJSON พร้อมชื่ออ็อบเจกต์เฉพาะโดยใช้
  Aspose.GIS สำหรับ .NET – คู่มือฉบับสมบูรณ์สำหรับการแปลง Aspose GIS.
linktitle: How to Convert GeoJSON to TopoJSON with Specific Object Name
second_title: Aspose.GIS .NET API
title: วิธีแปลง GeoJSON เป็น TopoJSON พร้อมชื่อวัตถุเฉพาะ
url: /th/net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแปลง GeoJSON เป็น TopoJSON พร้อมชื่ออ็อบเจกต์ที่กำหนด

## บทนำ
ในบทเรียนนี้คุณจะได้ค้นพบ **วิธีแปลง GeoJSON** เป็นไฟล์ TopoJSON พร้อมกำหนดชื่ออ็อบเจกต์แบบกำหนดเองโดยใช้ **Aspose.GIS for .NET** ไม่ว่าคุณจะกำลังสร้างบริการแผนที่, เตรียมข้อมูลสำหรับการแสดงผลบนเว็บ, หรือเพียงต้องการวิธีที่สะอาดในการเปลี่ยนชื่ออ็อบเจกต์ผลลัพธ์ คู่มือขั้นตอน‑โดย‑ขั้นตอนนี้จะแสดงให้คุณเห็นอย่างชัดเจนว่าต้องทำอะไรบ้าง

## คำตอบสั้น
- **การแปลงทำอะไร?** มันแปลงชุดฟีเจอร์ GeoJSON ให้เป็นโทโพโลจี TopoJSON และให้คุณกำหนดชื่ออ็อบเจกต์ราก  
- **ไลบรารีใดรับผิดชอบการแปลง?** Aspose.GIS for .NET (ส่วนหนึ่งของชุดการแปลง Aspose GIS)  
- **ฉันต้องมีลิขสิทธิ์หรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการทดสอบ; จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **ใช้เวลานานเท่าไหร่ในการดำเนินการ?** ประมาณ 5‑10 นาทีเมื่อสภาพแวดล้อมพร้อม  

## การ “แปลง GeoJSON เป็น TopoJSON” คืออะไร?
การแปลง GeoJSON เป็น TopoJSON หมายถึงการนำชุดฟีเจอร์ GeoJSON มารหัสเป็นโทโพโลจี TopoJSON ซึ่ง TopoJSON จะลดขนาดไฟล์โดยการแชร์ขอบเรขาคณิต และด้วย Aspose.GIS คุณสามารถระบุ **DefaultObjectName** เพื่อให้ไฟล์ผลลัพธ์มีอ็อบเจกต์ที่ตั้งชื่อตามที่คุณต้องการ

## ทำไมต้องใช้ Aspose.GIS .NET สำหรับการแปลงนี้?
- **Robust API** – จัดการชุดข้อมูลขนาดใหญ่และเรขาคณิตซับซ้อนได้โดยไม่ต้องพาร์สด้วยตนเอง  
- **Built‑in conversion options** – ตั้งชื่ออ็อบเจกต์, ความแม่นยำของพิกัด, และอื่น ๆ ได้โดยตรง  
- **Cross‑platform** – ทำงานในสภาพแวดล้อม .NET ใด ๆ ตั้งแต่แอปเดสก์ท็อปจนถึงบริการคลาวด์  
- **Comprehensive support** – เป็นส่วนหนึ่งของตระกูลการแปลง Aspose GIS มีการอัปเดตและเอกสารอย่างสม่ำเสมอ  

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน ให้ตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมแล้ว:

### 1. ติดตั้ง Aspose.GIS for .NET
ไปที่ [download page](https://releases.aspose.com/gis/net/) เพื่อดาวน์โหลดเวอร์ชันล่าสุดของ Aspose.GIS for .NET

### 2. ตั้งค่าสภาพแวดล้อมการพัฒนา
Visual Studio, Rider หรือ IDE ที่รองรับ .NET ใด ๆ ก็ใช้ได้ ตรวจสอบให้แน่ใจว่าโครงการของคุณตั้งค่าเป้าหมายเป็น .NET Framework 4.5+ หรือ .NET Core 3.1+

### 3. เตรียมไฟล์ GeoJSON
เตรียมไฟล์ GeoJSON ที่คุณต้องการแปลง หากไม่มีคุณสามารถสร้างไฟล์ง่าย ๆ หรือใช้ไฟล์ตัวอย่างใด ๆ สำหรับบทเรียนนี้ได้

## นำเข้า Namespaces
ก่อนที่เราจะเริ่มกระบวนการแปลง, ให้เรานำเข้า namespaces ที่จำเป็น:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: กำหนดเส้นทางไฟล์
```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithObjectName_out.topojson";
```
แทนที่ `"Your Document Directory"` ด้วยโฟลเดอร์จริงที่ไฟล์ GeoJSON ของคุณอยู่และที่คุณต้องการบันทึกผลลัพธ์ TopoJSON

### ขั้นตอนที่ 2: ตั้งค่าตัวเลือกการแปลง (Aspose GIS conversion)
```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // specify the name of the object where features should be written
        DefaultObjectName = "name_of_the_object",
    }
};
```
ที่นี่เราสร้างอินสแตนซ์ของ `ConversionOptions` และตั้งค่า `DefaultObjectName`. สิ่งนี้บอก Aspose.GIS ให้เขียนฟีเจอร์ทั้งหมดภายใต้อ็อบเจกต์ที่ชื่อ **name_of_the_object** ในไฟล์ TopoJSON ที่สร้างขึ้น

### ขั้นตอนที่ 3: ดำเนินการแปลง (convert geojson to topojson)
```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```
เมธอด `VectorLayer.Convert` ทำหน้าที่หลัก: มันอ่าน GeoJSON ต้นฉบับ, ใช้ตัวเลือกที่กำหนดไว้ข้างต้น, และเขียนไฟล์ TopoJSON พร้อมชื่ออ็อบเจกต์ที่กำหนดเอง

## ปัญหาและเคล็ดลับทั่วไป
- **ข้อผิดพลาดของเส้นทาง** – ตรวจสอบให้แน่ใจว่าข้อความของไดเรกทอรีลงท้ายด้วยตัวคั่นเส้นทาง (`\` หรือ `/`) หรือใช้ `Path.Combine` เพื่อความปลอดภัย  
- **ไฟล์ขนาดใหญ่** – สำหรับไฟล์ GeoJSON ขนาดใหญ่มาก, พิจารณาเพิ่มขีดจำกัดหน่วยความจำของกระบวนการหรือสตรีมข้อมูล  
- **ความขัดแย้งของชื่ออ็อบเจกต์** – `DefaultObjectName` ต้องเป็นเอกลักษณ์ภายในไฟล์ TopoJSON; มิฉะนั้นอ็อบเจกต์ที่มีอยู่อาจถูกเขียนทับ  

## สรุป
คุณได้เรียนรู้ **วิธีแปลง GeoJSON เป็น TopoJSON พร้อมชื่ออ็อบเจกต์ที่กำหนด** ด้วย Aspose.GIS for .NET เทคนิคนี้ช่วยทำให้การเตรียมข้อมูลสำหรับแผนที่บนเว็บง่ายขึ้น, ลดขนาดไฟล์, และให้คุณควบคุมโครงสร้างของโทโพโลจีผลลัพธ์ได้อย่างเต็มที่

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้ Aspose.GIS for .NET ในโครงการเชิงพาณิชย์ได้หรือไม่?**  
**ตอบ:** ใช่, Aspose.GIS for .NET สามารถใช้ได้ทั้งในแอปพลิเคชันเชิงพาณิชย์และส่วนบุคคลโดยมีลิขสิทธิ์ที่ถูกต้อง

**ถาม: มีการทดลองใช้ฟรีสำหรับ Aspose.GIS for .NET หรือไม่?**  
**ตอบ:** มี, คุณสามารถรับการทดลองใช้ฟรีได้จาก [here](https://releases.aspose.com/)

**ถาม: ฉันจะหาแหล่งสนับสนุนสำหรับ Aspose.GIS for .NET ได้จากที่ไหน?**  
**ตอบ:** การสนับสนุนมีให้ผ่าน [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)

**ถาม: ฉันจะซื้อไลเซนส์สำหรับ Aspose.GIS for .NET อย่างไร?**  
**ตอบ:** สามารถซื้อไลเซนส์ได้จาก [here](https://purchase.aspose.com/buy)

**ถาม: ฉันต้องการไลเซนส์ชั่วคราวสำหรับการประเมินหรือไม่?**  
**ตอบ:** ใช่, มีไลเซนส์การประเมินชั่วคราวที่สามารถรับได้จาก [here](https://purchase.aspose.com/temporary-license/)

**อัปเดตล่าสุด:** 2025-11-30  
**ทดสอบด้วย:** Aspose.GIS for .NET (รุ่นล่าสุด)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}