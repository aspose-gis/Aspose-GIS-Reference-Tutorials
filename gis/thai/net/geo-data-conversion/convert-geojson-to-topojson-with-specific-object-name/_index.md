---
date: 2025-11-29
description: เรียนรู้วิธีแปลง GeoJSON เป็น TopoJSON พร้อมชื่ออ็อบเจกต์ที่กำหนดโดยใช้
  Aspose.GIS สำหรับ .NET คู่มือแบบขั้นตอนนี้แสดงให้เห็นอย่างชัดเจนว่าจะแปลง GeoJSON
  เป็น TopoJSON อย่างมีประสิทธิภาพอย่างไร
language: th
linktitle: Convert GeoJSON to TopoJSON with Specific Object Name
second_title: Aspose.GIS .NET API
title: แปลง GeoJSON เป็น TopoJSON พร้อมชื่ออ็อบเจ็กต์เฉพาะ
url: /net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง GeoJSON เป็น TopoJSON พร้อมกำหนดชื่ออ็อบเจ็กต์เฉพาะ

## บทนำ
หากคุณต้องการ **แปลง GeoJSON เป็น TopoJSON** พร้อมควบคุมชื่อของอ็อบเจ็กต์ผลลัพธ์ Aspose.GIS for .NET จะทำให้คุณทำได้อย่างง่ายดาย ในบทเรียนนี้คุณจะได้เห็นวิธีแปลง GeoJSON เป็น TopoJSON อย่างละเอียด ทำไมคุณอาจต้องการชื่ออ็อบเจ็กต์ที่กำหนดเอง และจุดที่คุณควรใส่โค้ดนี้ในโปรเจกต์ .NET ที่มีอยู่ของคุณ

## คำตอบอย่างรวดเร็ว
- **การแปลงทำอะไร?** จะเขียนคุณลักษณะของ GeoJSON ใหม่เป็นโครงสร้าง TopoJSON โดยสามารถเปลี่ยนชื่ออ็อบเจ็กต์รากได้ตามต้องการ  
- **ใช้เวลานานแค่ไหนในการทำงาน?** ประมาณ 5‑10 นาทีหลังจากติดตั้ง Aspose.GIS แล้ว  
- **ต้องมีลิขสิทธิ์หรือไม่?** สามารถใช้รุ่นทดลองฟรีสำหรับการทดสอบได้; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **สามารถระบุชื่ออ็อบเจ็กต์ได้หรือไม่?** ได้ – ใช้ `DefaultObjectName` ใน `TopoJsonOptions`

## “แปลง GeoJSON เป็น TopoJSON” คืออะไร?
`convert geojson to topojson` คือกระบวนการแปลงไฟล์ GeoJSON (รูปแบบ JSON ธรรมดาที่แสดงคุณลักษณะทางภูมิศาสตร์) ให้เป็น TopoJSON ซึ่งเป็นรูปแบบที่บีบอัดมากขึ้นโดยเก็บส่วนเส้นที่ใช้ร่วมกันเป็นโค้ง (arc) ทำให้ขนาดไฟล์ลดลงและประสิทธิภาพการแสดงผลบนเว็บแมพดีขึ้น

## ทำไมต้องใช้ Aspose.GIS for .NET เพื่อแปลง GeoJSON เป็น TopoJSON?
- **การบูรณาการกับ .NET อย่างเต็มรูปแบบ** – ไม่ต้องใช้เครื่องมือ CLI ภายนอก  
- **การควบคุมระดับละเอียด** – สามารถกำหนดชื่ออ็อบเจ็กต์ผลลัพธ์ ความแม่นยำของพิกัด และอื่น ๆ ได้  
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, macOS ด้วย .NET Core/.NET 5+  
- **การจัดการข้อผิดพลาดที่แข็งแรง** – มีการตรวจสอบความถูกต้องของ GeoJSON เข้าและข้อยกเว้นที่ให้รายละเอียด

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มแปลง ให้ตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:

1. **Aspose.GIS for .NET** – ดาวน์โหลดเวอร์ชันล่าสุดจาก [official download page](https://releases.aspose.com/gis/net/)  
2. **สภาพแวดล้อมการพัฒนา .NET** – Visual Studio, Rider หรือ VS Code พร้อมส่วนขยาย C#  
3. **ไฟล์ GeoJSON ต้นฉบับ** – ไฟล์ GeoJSON ที่ถูกต้องตามสเปคใดก็ได้ที่คุณต้องการแปลงเป็น TopoJSON

## นำเข้า Namespaces
เริ่มต้นโดยนำ Namespaces ที่จำเป็นเข้ามาใช้:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: กำหนดเส้นทางไฟล์
บอก API ว่าไฟล์ GeoJSON ต้นฉบับของคุณอยู่ที่ไหนและไฟล์ TopoJSON ที่แปลงแล้วควรบันทึกไว้ที่ไหน

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithObjectName_out.topojson";
```

> **เคล็ดลับ:** ใช้ `Path.Combine` เพื่อสร้างเส้นทางที่ทำงานได้บนทุกแพลตฟอร์ม

### ขั้นตอนที่ 2: ตั้งค่าตัวเลือกการแปลง (วิธีแปลง GeoJSON เป็น TopoJSON พร้อมชื่ออ็อบเจ็กต์ที่กำหนดเอง)
สร้างอินสแตนซ์ `ConversionOptions` และระบุชื่ออ็อบเจ็กต์ที่ต้องการผ่าน `TopoJsonOptions.DefaultObjectName`

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

โค้ดนี้บอก Aspose.GIS ให้เขียนคุณลักษณะทั้งหมดภายใต้โหนด `"name_of_the_object"` ในไฟล์ TopoJSON ที่สร้างขึ้น

### ขั้นตอนที่ 3: ดำเนินการแปลง
สุดท้ายเรียกเมธอดสถิต `Convert` ของ `VectorLayer` เมธอดนี้จะอ่าน GeoJSON, ใช้ตัวเลือกที่กำหนด, แล้วเขียนไฟล์ TopoJSON

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

หากการแปลงสำเร็จ คุณจะพบไฟล์ TopoJSON ที่บีบอัดแล้วที่ `outputFilePath` พร้อมชื่ออ็อบเจ็กต์ที่คุณกำหนดไว้

## ปัญหาและวิธีแก้ไขทั่วไป
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| **ไม่พบไฟล์** | เส้นทางไม่ถูกต้องหรือขาดนามสกุลไฟล์ | ตรวจสอบ `sampleGeoJsonPath` ด้วย `File.Exists` |
| **GeoJSON ไม่ถูกต้อง** | ไฟล์อินพุตไม่เป็นไปตามสเปค GeoJSON | ใช้ `GeoJsonReader` ตรวจสอบความถูกต้องก่อนแปลง |
| **ชื่ออ็อบเจ็กต์ไม่ทำงาน** | ใช้ Aspose.GIS รุ่นเก่าที่ไม่มี `DefaultObjectName` | อัปเกรดเป็นรุ่นล่าสุดของ Aspose.GIS |
| **การเข้าถึงถูกปฏิเสธ** | โฟลเดอร์ปลายทางเป็นแบบอ่าน‑อย่างเท่านั้น | รันแอปพลิเคชันด้วยสิทธิ์ไฟล์ระบบที่เหมาะสม |

## สรุป
คุณได้เรียนรู้ **วิธีแปลง GeoJSON เป็น TopoJSON** พร้อมกำหนดชื่ออ็อบเจ็กต์เฉพาะโดยใช้ Aspose.GIS for .NET วิธีนี้ให้คุณควบคุมโครงสร้างผลลัพธ์ได้เต็มที่ ลดขนาดไฟล์ และผสานรวมอย่างราบรื่นกับเวิร์กโฟลว์ GIS ที่พัฒนาด้วย .NET

## คำถามที่พบบ่อย
### สามารถใช้ Aspose.GIS for .NET ในโครงการเชิงพาณิชย์ได้หรือไม่?
ได้ คุณสามารถใช้ Aspose.GIS for .NET ได้ทั้งในโครงการเชิงพาณิชย์และส่วนบุคคล  
### มีรุ่นทดลองฟรีสำหรับ Aspose.GIS for .NET หรือไม่?
มี คุณสามารถดาวน์โหลดรุ่นทดลองฟรีได้จาก [here](https://releases.aspose.com/)  
### จะหาแหล่งสนับสนุนสำหรับ Aspose.GIS for .NET ได้จากที่ไหน?
คุณสามารถขอรับการสนับสนุนจาก [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)  
### จะซื้อไลเซนส์สำหรับ Aspose.GIS for .NET ได้อย่างไร?
คุณสามารถซื้อไลเซนส์ได้จาก [here](https://purchase.aspose.com/buy)  
### จำเป็นต้องมีไลเซนส์ชั่วคราวสำหรับการประเมินหรือไม่?
ใช่ คุณสามารถรับไลเซนส์ชั่วคราวได้จาก [here](https://purchase.aspose.com/temporary-license/)  

## Frequently Asked Questions

**Q: ข้อได้เปรียบที่ใหญ่ที่สุดของ TopoJSON เมื่อเทียบกับ GeoJSON คืออะไร?**  
A: TopoJSON เก็บส่วนเส้นที่ใช้ร่วมกันเพียงครั้งเดียว ทำให้ขนาดไฟล์ลดลงอย่างมากสำหรับแผนที่ที่ซับซ้อน  

**Q: สามารถแปลงไฟล์ GeoJSON ขนาดใหญ่ (หลายร้อย MB) ได้หรือไม่?**  
A: ได้ Aspose.GIS ทำการสตรีมข้อมูล ดังนั้นการใช้หน่วยความจำจึงต่ำ; เพียงแค่ตรวจสอบว่ามีพื้นที่ดิสก์เพียงพอสำหรับไฟล์ผลลัพธ์  

**Q: สามารถตั้งค่าความแม่นยำของพิกัดระหว่างการแปลงได้หรือไม่?**  
A: แน่นอน ใช้ `TopoJsonOptions.Precision` เพื่อปัดพิกัดให้เป็นจำนวนทศนิยมที่ต้องการ  

**Q: การแปลงนี้รักษาคุณสมบัติทั้งหมดของ GeoJSON ไว้หรือไม่?**  
A: คุณสมบัติของฟีเจอร์ทั้งหมดจะถูกคัดลอกอย่างตรงไปตรงมาไปยังไฟล์ TopoJSON  

**Q: จะอ่าน TopoJSON ที่ได้ใน JavaScript อย่างไร?**  
A: ไลบรารีเช่น `topojson-client` สามารถแยกไฟล์ได้ และคุณสามารถอ้างอิงชื่ออ็อบเจ็กต์ที่กำหนดเอง (`name_of_the_object`) ที่ตั้งไว้  

**Last Updated:** 2025-11-29  
**Tested With:** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}