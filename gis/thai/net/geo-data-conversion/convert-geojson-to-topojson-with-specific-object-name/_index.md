---
date: 2026-01-31
description: เรียนรู้วิธีแปลง GeoJSON เป็น TopoJSON พร้อมชื่อวัตถุที่กำหนดโดยใช้ Aspose.GIS
  สำหรับ .NET – คู่มือฉบับสมบูรณ์สำหรับการแปลง Aspose GIS.
linktitle: How to Convert GeoJSON to TopoJSON with Specific Object Name
second_title: Aspose.GIS .NET API
title: วิธีแปลง GeoJSON เป็น TopoJSON พร้อมชื่ออ็อบเจกต์ที่กำหนด
url: /th/net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแปลง GeoJSON เป็น TopoJSON พร้อมชื่ออ็อบเจ็กต์ที่กำหนดเอง

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีแปลงไฟล์ GeoJSON** เป็น TopoJSON พร้อมกำหนดชื่ออ็อบเจ็กต์แบบกำหนดเอง โดยใช้ **Aspose.GIS for .NET** ไม่ว่าคุณจะกำลังสร้างบริการแผนที่, เตรียต้องในการตั้งชื่ออ็อบเจ็กต์ผลลัพธ์ คู่มือขั้นตอน‑ต่อ‑ขั้นตอนนี้จะแสดงให้คุณเห็นอย่างชัดเจนว่าต้องทำอะไร

## คำตอบสั้น
- **การแปลงทำอะไร?** แปลงคอลเลกชันฟีเจอร์ GeoJSON ให้เป็นโทโพโลจี TopoJSON และให้คุณตั้งชื่ออ็อบเจ็กต์รากได้  
- **ไลบรารีที่ทำการแปลงคืออะไร?** Aspose.GIS for .NET (ส่วนหนึ่งose GIS)  
- **ต้องใช้ไลเซนส์หรือไม่?** มีรุ่นทดลองฟรีสำหรับการทดสอบ; ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **ใช้เวลานานเท่าไหร่ในการ5‑10 นาที เมื่อสภาพแวดล้อมพร้อม

## วิธีแปลง GeoJSON เป็น TopoJSON
การแปลง GeoJSON เป็น TopoJSON หมายถึงการนำคอลเลกชันฟีเจอร์ GeoJSON มารหัสเป็นโทโพโลจี TopoJSON ซึ่ง TopoJSON จะลดขนาดไฟล์โดยการแชร์ขอบของรูปทรง และด้วย Aspose.GIS คุณสามารถระบุ **DefaultObjectName** เพื่อให้ไฟล์ผลลัพธ์มีอ็อบเจ็กต์ที่ตั้งชื่อตามที่คุณต้องการ

## ทำไมต้องใช้ Aspose.GIS .NET สำหรับการแปลงนี้?
- **API ที่แข็งแรง** – จัดการตัวเลือกการแปลงในตัว** – ตั้งชื่ออ็อบเจพิกัด, และอื่น ๆ ได้โดยตรง  
- **ข้ามแพลตฟอร์ม** – ทำงานในสภาพแวดล้อม .NET ใด ๆ ตั้งแต่แอปเดสก์ท็อปจนถึงบริการคลาวด์  
- **การสนับสนุนครบวงจร** – เป็นส่วนหนึ่งของตระกูลการแปลง Aspose GIS มีการอัปเดตและเอกสารอย่างสม่ำเสมอ

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

### 1. ติดตั้ง Aspose.GIS for .NET
ไปที่ [หน้าดาวน์โหลด](https://###  หรือ IDE ที่รองรับ .NET ใดก็ได้ ตรวจสอบให้โปรเจกต์ของคุณตั้งเป้าหมายเป็น .NET Framework 4.5+ หรือ .NET Core 3.1+

### 3. เตรียมไฟล์ GeoJSON
มีไฟล์ GeoJSON ที่ต้องการแปลงพร้อม หากไม่มีคุณสามารถสร้างไฟล์ง่าย ๆ หรือใช้ไฟล์ตัวอย่างใด ๆ สำหรับบทแนะนำนี้

## นำเข้า Namespaces
ก่อนเริ่มกระบวนการแปลง ให้นำเข้า namespaces ที่จำเป็น:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## คู่มือขั้นตอน‑ต่อ‑ขั้นตอน

### ขั้นตอนที่ 1: กำหนดเส้นทางไฟล์
```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithObjectName_out.topojson";
```
แทนที่ `"Your Document Directory"` ด้วยโฟลเดอร์จริงที่เก็บไฟล์ GeoJSON ต้นฉบับและที่คุณต้องการบันทึกผลลัพธ์ TopoJSON

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
ที่นี่เราจะสร้างอินสแตนซ์ `ConversionOptions` และตั้งค่า `DefaultObjectName` ซึ่งบอก Aspose.GIS ให้เขียนฟีเจอร์ทั้งหมดภายใต้ชื่ออ็อบเจ็กต์ **name_of_the_object** ในไฟล์ TopoJSON ที่สร้างขึ้น

### ขั้นตอนที่ 3: ดำเนินการแปลง (convert geojson to topojson)
```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```
เมธอด `VectorLayer.Convert` จะทำหน้าที่หลัก: อ่าน GeoJSON ต้นฉบับ, ใช้ตัวเลือกที่กำหนดไว้ข้างต้น, และเขียนไฟล์ TopoJSON พร้อมชื่ออ็อบเจ็กต์ที่กำหนดเอง

## วิธีจัดการไฟล์ GeoJSON ขนาดใหญ่
เมื่อทำงานกับชุดข้อมูล GeoJSON ขนาดมหาศาล ให้คำนึงถึงเคล็ดลับต่อไปนี้:

- **ข้อผิดพลาดของ Path** – ใช้ `Path.Combine` เพื่อสร้างเส้นทางไฟล์อย่างปลอดภัยและหลีกเลี่ยงการขาดเครื่องหมายคั่น  
- **การจัดการหน่วยความจำ** – สำหรับไฟล์ GeoJSON ขนาดใหญ่มาก ให้เพิ่มขีดจำกัดหน่วยความจำของโปรเซสหรือสตรีมข้อมูลแทนการโหลดทั้งหมดในครั้งเดียว  
- **การชนชื่ออ็อบเจ็กต์** – ตรวจสอบให้ `DefaultObjectName` มีความเป็นเอกลักษณ์ภายในไฟล์ TopoJSON; ชื่อซ้ำอาจทำให้ข้อมูลถูกเขียนทับ  

แนวทางเหล่านี้ช่วยให้คุณ **จัดการไฟล์ GeoJSON ขนาดใหญ่** ได้อย่างมีประสิทธิภาพขณะแปลงเป็น TopoJSON

## ปัญหาที่พบบ่อยและเคล็ดลับ
- **ข้อผิดพลาดของ Path** – ตรวจสอบให้สตริงของไดเรกทอรีลงท้ายด้วยเครื่องหมายคั่น (`\` หรือ `/`) หรือใช้ `Path.Combine` เพื่อความปลอดภัย  
- **ไฟล์ขนาดใหญ่** – สำหรับไฟล์ GeoJSON ขนาดใหญ่ ควรพิจารณาเพิ่มขีดจำกัดหน่วยความจำของโปรเซสหรือสตรีมข้อมูล  
- **การชนชื่ออ็อบเจ็กต์** – `DefaultObjectName` ต้องเป็นชื่อที่ไม่ซ้ำกันในไฟล์ TopoJSON; หากซ้ำอาจทำให้
คุณได้เรียนรู้ **วิธีแปลง GeoJSON เป็น TopoJSON พร้อมชื่ออ็อบเจ็กต์ที่กำหนดเอง** ด้วย Aspose.GIS for .NET เทคนิคนี้ช่วยทำให้การเตรียมข้อมูลสำหรับแผนที่เว็บง่ายขึ้น, ลดขนาดไฟล์, และให้คุณควบคุมโครงสร้างโทโพโลจีผลลัพธ์ได้อย่างเต็มที่

## คำถามที่พบบ่อย

**ถาม: สามารถใช้ Aspose.GIS for .NET ในโครงการเชิงพาณิชย์ได้หรือไม่?**  
ตอบ: ใช่, Aspose.GIS for .NET สามารถใช้ได้ทั้งในแอปพลิเคชันเชิงพาณิชย์และส่วนบุคคลโดยต้องมีไลเซนส์ที่ถูกต้อง

**ถามose.GIS for .NET หรือไม่?**  
ตอบ: มี, คุณสามารถรับรุ่นทดลองฟรีได้จาก [ที่นี่](https://releases.aspose.com/)

**ถาม: จะหาแหล่งสนับสนุนสำหรับ Aspose.GIS for .NET ได้จากที่ไหน?**  
ตอบ: มีการสนับสนุนผ่าน [ฟอรั่ม Aspose.GIS](https://forum.aspose.com/c/gis/33)

**ถาม: จะซื้อไลเซนส์สำหรับ Aspose.GIS for .NET อย่างไร?**  
ตอบ: สามารถซื้อไลเซนส์ได้จาก [ที่นี่](https://purchase.aspose.com/buy)

**ถาม: ต้องการไลเซนส์ชั่วคราวสำหรับการประเมินผลหรือไม่?**  
ตอบ: ใช่, มีไคราวให้ดาวน์โหลดจาก [ที่นี่](https://purchase.aspose.com/temporary-license/)

**ถาม: สามารถแปลงชุดข้อมูล GeoJSON ขนาดใหญ่มากโดยไม่ทำให้หน่วยความจำหมดได้หรือไม่?**  
ตอบ: ได้—โดยสตรีมแหล่งข้อมูลหรือเพิ่มการจัดสรรหน่วยความจำของแอปพลิเคชัน คุณสามารถจัดการไฟล์ขนาดใหญ่ได้อย่างมีประสิทธิภาพ

---

**อัปเดตล่าสุด:** 2026-01-31  
**ทดสอบกับ:** Aspose.GIS for .NET (รุ่นล่าสุด)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}