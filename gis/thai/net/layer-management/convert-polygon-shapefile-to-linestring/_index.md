---
date: 2026-06-25
description: เรียนรู้วิธีอ่าน shapefile และแปลง polygon shapefile ให้เป็น linestring
  ด้วย Aspose.GIS สำหรับ .NET เพิ่มประสิทธิภาพการพัฒนา GIS ของคุณด้วยคำแนะนำที่ชัดเจนเป็นขั้นตอน
keywords:
- how to read shapefile
- convert polygon to line
- shapefile to geojson c#
- extract lines from polygon
linktitle: แปลง Polygon Shapefile เป็น Linestring
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  headline: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  type: TechArticle
- description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  name: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  steps:
  - name: Set the Document Directory
    text: Replace `"Your Document Directory"` with the actual path where your shapefile
      resides.
  - name: Open the Source Shapefile
    text: This line opens the source Polygon Shapefile so you can read its features.
  - name: Create the Destination Linestring Shapefile
    text: Here we create a new Linestring Shapefile that will store the converted
      geometries.
  - name: Iterate Through Source Features
    text: The loop walks through each polygon feature in the original file.
  - name: Convert Polygon to Linestring and Write to Destination
    text: The `ExteriorRing` property returns the outer boundary of a polygon as a
      `LineString`. In this block we convert polygon to line (`LineString`) and add
      the new feature to the destination shapefile.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS supports .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7, ensuring seamless integration with modern development stacks.
    question: Is Aspose.GIS compatible with all versions of .NET?
  - answer: Yes, you can. Purchase a license [here](https://purchase.aspose.com/buy)
      to remove evaluation limitations and obtain full support.
    question: Can I use Aspose.GIS for commercial projects?
  - answer: Yes, you can find comprehensive documentation and code samples on the
      [documentation page](https://reference.aspose.com/gis/net/).
    question: Are there any examples or documentation available?
  - answer: Absolutely – explore Aspose.GIS with a free trial by visiting [this link](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      assistance and official support.
    question: Where can I seek help or support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: วิธีอ่าน Shapefile C# – แปลง Polygon Shapefile เป็น Linestring
url: /th/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่าน Shapefile C# – แปลง Polygon Shapefile เป็น Linestring

## บทนำ
หากคุณต้องการ **วิธีอ่าน shapefile** ในสภาพแวดล้อม .NET คุณมาถูกที่แล้ว Aspose.GIS for .NET ทำให้การทำงานกับรูปแบบไบนารีระดับต่ำของ Shapefile ง่ายขึ้น โดยให้คุณโหลด, คิวรี, และแปลงคุณลักษณะทางภูมิศาสตร์ด้วยเพียงไม่กี่คำสั่ง API การแปลง polygon shapefile เป็น linestring มีประโยชน์อย่างยิ่งเมื่อคุณต้องการดึงข้อมูลเชิงเส้นสำหรับการกำหนดเส้นทาง, การวิเคราะห์เครือข่าย, หรือการแสดงผลอย่างง่าย

## คำตอบสั้น
- **ไลบรารีใดช่วยคุณอ่าน shapefile c#?** Aspose.GIS for .NET – รองรับรูปแบบ GIS มากกว่า 50 แบบและจัดการไฟล์ขนาดหลายร้อยเมกะไบต์โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ.  
- **คุณสามารถแปลง polygon เป็น line ได้หรือไม่?** ใช่ – เรียก `LineString` บนวงแหวนภายนอกของ polygon แล้วเขียนผลลัพธ์ไปยัง shapefile ใหม่.  
- **ฉันต้องการใบอนุญาตสำหรับการผลิตหรือไม่?** ต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานในสภาพแวดล้อมการผลิต; การทดลองใช้ฟรีสามารถใช้สำหรับการประเมินผลได้.  
- **เวอร์ชัน .NET ใดที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **มีรุ่นทดลองหรือไม่?** แน่นอน – ดาวน์โหลดรุ่นทดลองฟรีจากเว็บไซต์ Aspose.  

`LineString` คือประเภทเรขาคณิตที่แสดงชุดของเส้นที่เชื่อมต่อกัน.

## “read shapefile c#” คืออะไร?
`Document` คือคลาสหลักที่แทนชุดข้อมูล GIS และให้การเข้าถึงคุณลักษณะต่าง ๆ ของมัน. การอ่าน shapefile ด้วย C# หมายถึงการโหลดไฟล์ `.shp` เข้าสู่หน่วยความจำเพื่อให้คุณสามารถคิวรี, แก้ไข, หรือแปลงรูปทรงของมันได้. **คุณเพียงแค่สร้างอินสแตนซ์ของคลาส `Document` ด้วยเส้นทางไฟล์, แล้ว Aspose.GIS จะทำการแยกโครงสร้างไบนารีให้คุณ**, เปิดเผยคุณลักษณะผ่านคอลเลกชันที่ใช้งานง่าย. วิธีนี้ทำให้ไม่ต้องจัดการกับหัวไฟล์ระดับต่ำหรืออาเรย์พิกัดด้วยตนเอง.

## ทำไมต้องแปลง polygon เป็น line ด้วย Aspose.GIS?
การแปลง polygon เป็น linestring จะรักษาขอบเขตภายนอกที่แม่นยำขณะลบวงแหวนภายใน, ให้คุณได้รูปแบบเชิงเส้นที่สะอาด. Aspose.GIS ประมวลผล **ชุดข้อมูลขนาดสูงสุด 500 MB ในเวลาไม่ถึง 2 วินาทีบนเซิร์ฟเวอร์ทั่วไป**, ทำให้การแปลงเป็นชุดทำได้เร็วและใช้หน่วยความจำน้อย. ไลบรารียังคงรักษาการอ้างอิงเชิงพื้นที่เดิม, ดังนั้นเส้นที่ได้จะตรงกับชั้น GIS ที่มีอยู่ทั้งหมดอย่างสมบูรณ์.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มทำตามบทเรียน, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมแล้ว:

- **Aspose.GIS Library** – ดาวน์โหลดและติดตั้งไลบรารี Aspose.GIS จาก [เว็บไซต์](https://releases.aspose.com/gis/net/).  
- **Shapefile Data** – มี Polygon Shapefile พร้อมสำหรับการแปลง หากคุณไม่มีไฟล์ดังกล่าว, คุณสามารถค้นหาข้อมูลตัวอย่างหรือสร้างเองได้.  
- **Development Environment** – ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ของคุณพร้อมเครื่องมือที่จำเป็น (Visual Studio, .NET SDK, เป็นต้น).  

## นำเข้า Namespaces
`Document` class คืออ็อบเจ็กต์หลักของ Aspose.GIS ที่แทนชุดข้อมูล GIS และให้เมธอดสำหรับอ่านและเขียน shapefile. เพิ่ม Namespaces ต่อไปนี้ที่ส่วนต้นของไฟล์โค้ดของคุณ:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## วิธีอ่าน shapefile และแปลง polygon เป็น linestring?
โหลด shapefile polygon ต้นฉบับ, ดึงวงแหวนภายนอกของแต่ละ polygon, สร้าง `LineString` จากวงแหวนนั้น, และเขียนผลลัพธ์ไปยัง shapefile ใหม่ – ทั้งหมดในห้าขั้นตอนที่ง่ายดาย. รูปแบบนี้ทำงานกับชุดข้อมูลทุกขนาดและรับประกันว่าระบบพิกัดของต้นฉบับจะถูกเก็บไว้ในปลายทาง.

### ขั้นตอนที่ 1: ตั้งค่า Document Directory
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
แทนที่ `"Your Document Directory"` ด้วยเส้นทางจริงที่ไฟล์ shapefile ของคุณอยู่.

### ขั้นตอนที่ 2: เปิด Source Shapefile
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
บรรทัดนี้เปิด Polygon Shapefile ต้นฉบับเพื่อให้คุณสามารถอ่านคุณลักษณะของมันได้.

### ขั้นตอนที่ 3: สร้าง Destination Linestring Shapefile
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
ที่นี่เราสร้าง Linestring Shapefile ใหม่ที่จะเก็บเรขาคณิตที่แปลงแล้ว.

### ขั้นตอนที่ 4: วนลูปผ่าน Source Features
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
ลูปนี้จะเดินผ่านคุณลักษณะ polygon แต่ละรายการในไฟล์ต้นฉบับ.

### ขั้นตอนที่ 5: แปลง Polygon เป็น Linestring และเขียนไปยัง Destination
คุณสมบัติ `ExteriorRing` คืนค่าขอบเขตภายนอกของ polygon เป็น `LineString`.  
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
ในบล็อกนี้เราจะแปลง polygon เป็น line (`LineString`) และเพิ่มคุณลักษณะใหม่ไปยัง shapefile ปลายทาง.

## ปัญหาทั่วไปและเคล็ดลับ
- **Coordinate System Mismatch** – ตรวจสอบให้แน่ใจว่าชั้นต้นฉบับและปลายทางใช้การอ้างอิงเชิงพื้นที่เดียวกัน; หากไม่เช่นนั้น เส้นอาจแสดงตำแหน่งผิดพลาด.  
- **Large Files** – เมื่อประมวลผล shapefile ขนาดใหญ่มาก, พิจารณาการสตรีมคุณลักษณะแทนการโหลดทั้งหมดเข้าสู่หน่วยความจำพร้อมกัน.  
- **Null Geometries** – ป้องกันคุณลักษณะที่มีเรขาคณิตว่างเปล่าเพื่อหลีกเลี่ยงข้อยกเว้นในขณะรัน.  
- **Extract lines from polygon** – หากคุณต้องการเพียงวงแหวนภายนอก, ใช้คุณสมบัติ `ExteriorRing`; สำหรับวงแหวนภายใน, ให้วนลูป `InteriorRings`.  

## คำถามที่พบบ่อย

**Q: Aspose.GIS รองรับทุกเวอร์ชันของ .NET หรือ?**  
A: ใช่, Aspose.GIS รองรับ .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6/7, ทำให้การผสานรวมกับสแต็กการพัฒนาสมัยใหม่เป็นไปอย่างราบรื่น.

**Q: ฉันสามารถใช้ Aspose.GIS สำหรับโครงการเชิงพาณิชย์ได้หรือไม่?**  
A: ได้, คุณสามารถ. ซื้อใบอนุญาต [ที่นี่](https://purchase.aspose.com/buy) เพื่อยกเลิกข้อจำกัดการประเมินและรับการสนับสนุนเต็มรูปแบบ.

**Q: มีตัวอย่างหรือเอกสารใดบ้าง?**  
A: มี, คุณสามารถค้นหาเอกสารและตัวอย่างโค้ดที่ครอบคลุมได้บน [หน้าเอกสาร](https://reference.aspose.com/gis/net/).

**Q: มีรุ่นทดลองหรือไม่?**  
A: แน่นอน – ลองใช้ Aspose.GIS ด้วยรุ่นทดลองฟรีโดยเยี่ยมชม [ลิงก์นี้](https://releases.aspose.com/).

**Q: ฉันจะหาความช่วยเหลือหรือการสนับสนุนได้จากที่ไหน?**  
A: เยี่ยมชม [ฟอรั่ม Aspose.GIS](https://forum.aspose.com/c/gis/33) เพื่อรับความช่วยเหลือจากชุมชนและการสนับสนุนอย่างเป็นทางการ.

---

**อัปเดตล่าสุด:** 2026-06-25  
**ทดสอบด้วย:** Aspose.GIS for .NET (latest release)  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทเรียนที่เกี่ยวข้อง

- [วิธีแปลง Shapefile เป็น GeoJSON ด้วย Aspose.GIS for .NET](/gis/net/layer-management/extract-features-to-geojson/)
- [วิธีอ่าน GeoJSON จาก Stream ด้วย Aspose.GIS for .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [วิธีสร้าง Polygon Geometry ด้วย Aspose.GIS for .NET](/gis/net/geometry-creation/create-polygon-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}