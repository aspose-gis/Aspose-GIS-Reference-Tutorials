---
date: 2025-12-06
description: เรียนรู้วิธีแปลง GeoJSON เป็น TopoJSON พร้อมการจัดกลุ่ม ตั้งค่าคุณลักษณะชื่อวัตถุ
  และจัดกลุ่มฟีเจอร์ GeoJSON ด้วย Aspose.GIS สำหรับ .NET
language: th
linktitle: How to Convert GeoJSON to TopoJSON with Grouping using Aspose.GIS
second_title: Aspose.GIS .NET API
title: วิธีแปลง GeoJSON เป็น TopoJSON พร้อมการจัดกลุ่มโดยใช้ Aspose.GIS
url: /net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแปลง GeoJSON เป็น TopoJSON พร้อมการจัดกลุ่มโดยใช้ Aspose.GIS

## คำแนะนำ

ในบทแนะนำแบบขั้นตอนนี้ คุณจะได้เรียนรู้ **วิธีแปลง GeoJSON** เป็นไฟล์ TopoJSON พร้อมการจัดกลุ่มฟีเจอร์ตามแอตทริบิวต์ที่เลือก การใช้ Aspose.GIS .NET API ทำให้การแปลงเร็ว เชื่อถือได้ และสามารถควบคุมได้อย่างเต็มที่จากโค้ด C# ของคุณ ไม่ว่าคุณจะสร้างบริการแปลง GeoJSON บน ASP.NET หรือเครื่องมือ GIS บนเดสก์ท็อป คู่มือนี้จะแสดงให้คุณเห็นขั้นตอนที่ต้องทำอย่างชัดเจน

## คำตอบด่วน
- **ไลบรารีที่จัดการการแปลงคืออะไร?** Aspose.GIS for .NET  
- **ใช้เวลานานเท่าไหร่ในการทำงานนี้?** โดยทั่วไป 5‑10 นาทีสำหรับการตั้งค่าเบื้องต้น  
- **ต้องการไลเซนส์สำหรับการใช้งานจริงหรือไม่?** ใช่ จำเป็นต้องมีไลเซนส์เชิงพาณิชย์ (มีการทดลองใช้ฟรี)  
- **สามารถจัดกลุ่มฟีเจอร์ตามแอตทริบิวต์ใดก็ได้หรือไม่?** ใช่ – ตั้งค่า `ObjectNameAttribute` ให้เป็นฟิลด์ที่คุณต้องการจัดกลุ่ม  
- **รองรับ .NET Core หรือไม่?** แน่นอน – API ทำงานกับ .NET Core, .NET 5/6 และ .NET Framework รุ่นคลาสสิก  

## GeoJSON และ TopoJSON คืออะไร?

GeoJSON เป็นรูปแบบ JSON ที่ใช้กันอย่างแพร่หลายสำหรับการเข้ารหัสฟีเจอร์ทางภูมิศาสตร์ เช่น จุด, เส้น, และโพลิกอน TopoJSON ขยาย GeoJSON โดยเก็บข้อมูลโทโพโลยี (ส่วนเส้นที่ใช้ร่วมกัน) ซึ่งช่วยลดขนาดไฟล์และปรับปรุงประสิทธิภาพการแสดงผลสำหรับแผนที่ที่ซับซ้อน การแปลงระหว่างสองรูปแบบนี้เป็นขั้นตอนทั่วไปเมื่อคุณต้องการข้อมูลแผนที่ที่กระชับสำหรับการแสดงผลบนเว็บ

## ทำไมต้องจัดกลุ่มฟีเจอร์ GeoJSON?

การจัดกลุ่ม (`group geojson features`) ช่วยให้คุณจัดระเบียบเรขาคณิตที่เกี่ยวข้องภายใต้วัตถุที่มีชื่อเดียวใน TopoJSON ที่ได้ผลลัพธ์ ซึ่งมีประโยชน์เป็นพิเศษเมื่อ:
- คุณต้องการสร้างชั้นแยกสำหรับเขตการปกครองต่าง ๆ  
- ไลบรารีแผนที่ฝั่งหน้า (front‑end) ของคุณคาดหวังวัตถุที่มีชื่อสำหรับการจัดสไตล์หรือการโต้ตอบ  
- คุณต้องการลดการทำซ้ำโดยการแชร์พรมแดนระหว่างฟีเจอร์ที่อยู่ติดกัน  

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้:

1. **Aspose.GIS for .NET** – ดาวน์โหลดและติดตั้งจากเว็บไซต์ทางการ [ที่นี่](https://releases.aspose.com/gis/net/).  
2. **สภาพแวดล้อมการพัฒนา** – Visual Studio, Visual Studio Code หรือ IDE ใด ๆ ที่รองรับ C#.  
3. **ไฟล์ GeoJSON ตัวอย่าง** – ไฟล์ที่มีฟีเจอร์ที่คุณต้องการแปลง.  

## นำเข้า Namespaces

ขั้นแรก ให้เพิ่ม Namespaces ที่จำเป็นในโปรเจกต์ของคุณ:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: กำหนดเส้นทางไฟล์

ระบุที่ตั้งของไฟล์ GeoJSON ต้นฉบับและตำแหน่งที่ต้องการเขียนไฟล์ TopoJSON:

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

> **เคล็ดลับ:** ใช้ `Path.Combine` เพื่อสร้างเส้นทางแบบข้ามแพลตฟอร์ม หากคุณกำหนดเป้าหมายเป็น .NET Core.

### ขั้นตอนที่ 2: กำหนดค่าตัวเลือกการแปลง (ตั้งค่า Object Name Attribute)

สร้างอินสแตนซ์ `ConversionOptions` และบอก Aspose.GIS วิธีการจัดกลุ่มฟีเจอร์:

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // Specify the attribute in GeoJSON layer by which we are going to group into objects
        ObjectNameAttribute = "group",
        // Specify the default object name for features with unknown attribute values
        DefaultObjectName = "unnamed",
    }
};
```

แทนที่ `"group"` ด้วยชื่อคุณสมบัติจริงใน GeoJSON ของคุณที่ต้องการใช้สำหรับ **การจัดกลุ่มฟีเจอร์ GeoJSON**. `DefaultObjectName` จะทำให้ทุกฟีเจอร์อยู่ในวัตถุ TopoJSON แม้ว่าจะไม่มีแอตทริบิวต์นั้นก็ตาม.

### ขั้นตอนที่ 3: ดำเนินการแปลง (แปลง GeoJSON เป็น TopoJSON)

เรียกใช้การแปลงด้วยการเรียก API เพียงครั้งเดียว:

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

หลังจากดำเนินการเสร็จ `convertedSampleWithGrouping_out.topojson` จะมีการแสดงผล TopoJSON พร้อมฟีเจอร์ที่จัดกลุ่มตามแอตทริบิวต์ที่คุณระบุ.

## ปัญหาที่พบบ่อยและการแก้ไข

| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ไข |
|---------|--------------|-----|
| **ฟีเจอร์ทั้งหมดอยู่ใน “unnamed”** | `ObjectNameAttribute` ไม่ตรงกับคุณสมบัติใดใน GeoJSON | ตรวจสอบชื่อคุณสมบัติให้ตรง (คำนึงถึงตัวพิมพ์ใหญ่‑เล็ก) แล้วอัปเดตตัวเลือก |
| **ไฟล์ผลลัพธ์ว่างเปล่า** | เส้นทางไฟล์ไม่ถูกต้องหรือไม่มีสิทธิ์อ่าน | ใช้เส้นทางแบบเต็มหรือให้แน่ใจว่าแอปมีสิทธิ์เข้าถึงระบบไฟล์ |
| **การแปลงโยนข้อผิดพลาด `NotSupportedException`** | พยายามแปลง GeoJSON ที่มีประเภทเรขาคณิตที่ไม่รองรับ (เช่น GeometryCollection) | ทำให้ข้อมูลต้นฉบับง่ายลงหรืออัปเกรดเป็นเวอร์ชันล่าสุดของ Aspose.GIS |

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถจัดกลุ่มฟีเจอร์ตามหลายแอตทริบิวต์ได้หรือไม่?**  
**ตอบ:** ใช่ คุณสามารถต่อหลายฟิลด์เข้าด้วยกันเป็นแอตทริบิวต์เสมือนหนึ่งหรือทำการแปลงหลายครั้งโดยใช้ค่า `ObjectNameAttribute` ต่างกัน  

**ถาม: Aspose.GIS รองรับ ASP.NET Core หรือไม่?**  
**ตอบ:** แน่นอน – ไลบรารีทำงานกับ ASP.NET Core, .NET 5, .NET 6 และ .NET Framework รุ่นคลาสสิก  

**ถาม: ฉันสามารถแปลงรูปแบบภูมิศาสตร์อื่น ๆ นอกจาก GeoJSON ได้หรือไม่?**  
**ตอบ:** ใช่ Aspose.GIS รองรับ Shapefile, KML, GML, CSV และรูปแบบอื่น ๆ อีกมากมาย ทั้งการนำเข้าและส่งออก  

**ถาม: Aspose.GIS มีรุ่นทดลองใช้ฟรีหรือไม่?**  
**ตอบ:** มี คุณสามารถรับรุ่นทดลองใช้ฟรีของ Aspose.GIS จาก [ที่นี่](https://releases.aspose.com/).  

**ถาม: ฉันจะหาการสนับสนุนสำหรับ Aspose.GIS ได้จากที่ไหน?**  
**ตอบ:** คุณสามารถรับการสนับสนุนจากฟอรั่มชุมชน Aspose.GIS [ที่นี่](https://forum.aspose.com/c/gis/33).  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**อัปเดตล่าสุด:** 2025-12-06  
**ทดสอบด้วย:** Aspose.GIS for .NET (latest release)  
**ผู้เขียน:** Aspose