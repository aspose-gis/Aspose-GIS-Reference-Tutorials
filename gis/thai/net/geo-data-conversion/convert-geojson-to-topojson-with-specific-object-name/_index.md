---
title: แปลง GeoJSON เป็น TopoJSON ด้วยชื่อวัตถุเฉพาะ
linktitle: แปลง GeoJSON เป็น TopoJSON ด้วยชื่อวัตถุเฉพาะ
second_title: Aspose.GIS .NET API
description: เรียนรู้วิธีแปลง GeoJSON เป็น TopoJSON ด้วยชื่อออบเจ็กต์เฉพาะโดยใช้ Aspose.GIS สำหรับ .NET บทช่วยสอนนี้ให้คำแนะนำทีละขั้นตอนสำหรับการจัดการข้อมูลทางภูมิศาสตร์ที่มีประสิทธิภาพ
weight: 12
url: /th/net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง GeoJSON เป็น TopoJSON ด้วยชื่อวัตถุเฉพาะ

## การแนะนำ
Aspose.GIS สำหรับ .NET เป็นเครื่องมืออันทรงพลังสำหรับการทำงานกับข้อมูลทางภูมิศาสตร์ในแอปพลิเคชัน .NET ไม่ว่าคุณกำลังพัฒนาแอปพลิเคชันการทำแผนที่ การวิเคราะห์ข้อมูลเชิงพื้นที่ หรือจัดการไฟล์ geojson Aspose.GIS มีชุดคุณสมบัติที่ครอบคลุมเพื่อปรับปรุงขั้นตอนการทำงานของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกเรื่องการแปลง GeoJSON เป็น TopoJSON ด้วยชื่ออ็อบเจ็กต์เฉพาะโดยใช้ Aspose.GIS สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
### 1. ติดตั้ง Aspose.GIS สำหรับ .NET
 มุ่งหน้าไปที่[หน้าดาวน์โหลด](https://releases.aspose.com/gis/net/) และรับ Aspose.GIS เวอร์ชันล่าสุดสำหรับ .NET
### 2. ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณ
ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่า Visual Studio หรือสภาพแวดล้อมการพัฒนา .NET อื่นๆ ไว้ในระบบของคุณแล้ว
### 3. เตรียมไฟล์ GeoJSON ของคุณให้พร้อม
มีไฟล์ GeoJSON ที่คุณต้องการแปลงเป็น TopoJSON หากคุณยังไม่มี คุณสามารถใช้ไฟล์ GeoJSON ตัวอย่างใดก็ได้สำหรับบทช่วยสอนนี้

## นำเข้าเนมสเปซ
ก่อนที่เราจะเริ่มกระบวนการแปลง เรามานำเข้าเนมสเปซที่จำเป็นก่อน:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: กำหนดเส้นทางไฟล์
```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithObjectName_out.topojson";
```
 แทนที่`"Your Document Directory"`ด้วยเส้นทางไดเรกทอรีจริงที่มีไฟล์ GeoJSON ของคุณอยู่ และตำแหน่งที่คุณต้องการบันทึกไฟล์ TopoJSON ที่แปลงแล้ว
## ขั้นตอนที่ 2: ตั้งค่าตัวเลือกการแปลง
```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // ระบุชื่อของวัตถุที่ควรเขียนคุณลักษณะ
        DefaultObjectName = "name_of_the_object",
    }
};
```
 ในขั้นตอนนี้ เราจะสร้าง a`ConversionOptions` วัตถุและระบุ`DefaultObjectName`ซึ่งเป็นชื่อของออบเจ็กต์ที่ควรเขียนคุณลักษณะในไฟล์ TopoJSON ที่เป็นผลลัพธ์
## ขั้นตอนที่ 3: ทำการแปลง
```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```
 ในที่สุดเราก็เรียกว่า`Convert` วิธีการของ`VectorLayer` คลาส ส่งผ่านเส้นทางของไฟล์ GeoJSON อินพุต ไดรเวอร์อินพุตและเอาต์พุต และตัวเลือกการแปลง

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแปลง GeoJSON เป็น TopoJSON ด้วยชื่อออบเจ็กต์เฉพาะโดยใช้ Aspose.GIS สำหรับ .NET ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถจัดการและจัดการข้อมูลทางภูมิศาสตร์ในแอปพลิเคชัน .NET ของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.GIS สำหรับ .NET ในโครงการเชิงพาณิชย์ของฉันได้หรือไม่
ได้ คุณสามารถใช้ Aspose.GIS สำหรับ .NET ทั้งในโครงการเชิงพาณิชย์และส่วนบุคคล
### มีการทดลองใช้ฟรีสำหรับ Aspose.GIS สำหรับ .NET หรือไม่
ใช่ คุณสามารถทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.GIS สำหรับ .NET ได้ที่ไหน
 คุณสามารถรับการสนับสนุนจาก[ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33).
### ฉันจะซื้อใบอนุญาตสำหรับ Aspose.GIS สำหรับ .NET ได้อย่างไร
 คุณสามารถซื้อใบอนุญาตได้จาก[ที่นี่](https://purchase.aspose.com/buy).
### ฉันจำเป็นต้องมีใบอนุญาตชั่วคราวเพื่อการประเมินผลหรือไม่?
 ใช่ คุณสามารถรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
