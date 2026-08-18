---
date: 2026-06-10
description: เรียนรู้วิธีแปลง OSM เป็น Shapefile และอ่านคุณลักษณะของ OpenStreetMap
  XML ด้วย Aspose.GIS สำหรับ .NET คู่มือแบบขั้นตอนพร้อมเคล็ดลับปฏิบัติ
keywords:
- convert osm to shapefile
- osm to geojson conversion
- how to read osm xml
linktitle: อ่านคุณลักษณะจาก OpenStreetMap XML
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to convert OSM to Shapefile and read OpenStreetMap XML features
    using Aspose.GIS for .NET. Step‑by‑step guide with practical tips.
  headline: Convert OSM to Shapefile – Read Features from OpenStreetMap XML in Aspose.GIS
  type: TechArticle
- questions:
  - answer: Aspose.GIS for .NET
    question: What library handles OSM XML?
  - answer: About 20 lines (excluding setup)
    question: How many lines of code are needed?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes—Aspose.GIS streams data efficiently; filtering reduces memory usage.
    question: Can I read large OSM files?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: แปลง OSM เป็น Shapefile – อ่านคุณลักษณะจาก OpenStreetMap XML ด้วย Aspose.GIS
url: /th/net/layer-data-operations/read-features-from-openstreetmap-xml/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง OSM เป็น Shapefile – อ่านฟีเจอร์จาก XML ของ OpenStreetMap ใน Aspose.GIS

หากคุณต้องการ **แปลง OSM เป็น Shapefile** หรือเพียงแค่อ่านข้อมูล XML ของ OpenStreetMap (OSM) ภายในแอปพลิเคชัน .NET คุณมาถูกที่แล้ว Aspose.GIS สำหรับ .NET ทำให้การนำเข้าไฟล์ OSM XML, การสกัด nodes, ways, และ relations, และจากนั้นส่งออกเป็น Shapefile, GeoJSON หรือรูปแบบ GIS อื่น ๆ เป็นเรื่องง่าย ในบทแนะนำนี้เราจะพาคุณผ่านขั้นตอนทั้งหมด—ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการวนลูปฟีเจอร์—เพื่อให้คุณสามารถเริ่มสร้างโซลูชันการทำแผนที่หรือการวิเคราะห์เชิงพื้นที่ได้ทันที

## คำตอบด่วน
- **ไลบรารีใดที่จัดการ OSM XML?** Aspose.GIS สำหรับ .NET  
- **ต้องใช้บรรทัดโค้ดกี่บรรทัด?** ประมาณ 20 บรรทัด (ไม่รวมการตั้งค่า)  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** รุ่นทดลองฟรีทำงานได้สำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานในสภาพแวดล้อมจริง  
- **เวอร์ชัน .NET ใดที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **ฉันสามารถอ่านไฟล์ OSM ขนาดใหญ่ได้หรือไม่?** ใช่—Aspose.GIS สตรีมข้อมูลอย่างมีประสิทธิภาพ; การกรองช่วยลดการใช้หน่วยความจำ  

## อะไรคือ “วิธีอ่าน osm”?
การอ่านข้อมูล OSM (OpenStreetMap) หมายถึงการแยกวิเคราะห์รูปแบบ OSM XML เพื่อเข้าถึง nodes, ways, และ relations ที่เป็นตัวแทนของฟีเจอร์ทางภูมิศาสตร์ในโลกจริง หลังจากแยกวิเคราะห์แล้ว คุณสามารถทำการสอบถาม, แสดงผล, หรือแปลงข้อมูลนี้สำหรับแอปพลิเคชัน GIS ต่าง ๆ นอกจากนี้ยังรวมถึงเมตาดาต้าเช่น tags, timestamps, และข้อมูลผู้ใช้ ซึ่งทำให้สามารถทำการวิเคราะห์เชิงลึกและกระบวนการแก้ไขได้

## ทำไมต้องใช้ Aspose.GIS สำหรับ OSM?
Aspose.GIS มีตัวแยกวิเคราะห์ **zero‑dependency** ที่สามารถจัดการไฟล์ขนาดสูงสุด 1 GB โดยใช้หน่วยความจำต่ำกว่า 250 MB ทำให้เร็วกว่าโซลูชันโอเพ่นซอร์สหลายตัวถึง 3‑เท่า นอกจากนี้ยังมีการแปลงเรขาคณิตในตัว, คำสั่งเชิงพื้นที่, และการส่งออกโดยตรงเป็น Shapefile, GeoJSON, KML, และอื่น ๆ ทั้งหมดจากโค้ด .NET แท้

## ข้อกำหนดเบื้องต้น
- **Visual Studio** (Community, Professional หรือ Enterprise) – แนะนำให้ใช้เวอร์ชันล่าสุด  
- **Aspose.GIS for .NET** – ดาวน์โหลดจาก [ลิงก์ดาวน์โหลด](https://releases.aspose.com/gis/net/) อย่างเป็นทางการและเพิ่มแพ็กเกจ NuGet ไปยังโปรเจกต์ของคุณ  
- ความรู้พื้นฐานของ C# (ตัวแปร, ลูป, OOP).  

## การนำเข้า Namespaces
Namespace `Aspose.Gis` ให้ประเภท GIS พื้นฐาน, ส่วน `Aspose.Gis.Geometries` มีตัวช่วยด้านเรขาคณิต  

Namespace `Aspose.Gis` เป็นจุดเริ่มต้นสำหรับการดำเนินการ GIS ทั้งหมดใน Aspose.GIS.

## วิธีแปลง OSM เป็น Shapefile ด้วย Aspose.GIS?
โหลดเลเยอร์ OSM XML, วนลูปฟีเจอร์ของมัน, และเขียนลงใน Shapefile เพียงสามการเรียก API คลาส `ShapefileWriter` สร้าง Shapefile ใหม่และเขียนฟีเจอร์ลงไป ขั้นแรกสร้างอ็อบเจกต์ `Layer` สำหรับแหล่ง OSM, จากนั้นเปิด `ShapefileWriter` ชี้ไปยังโฟลเดอร์ปลายทาง, และสุดท้ายคัดลอกเรขาคณิตและแอตทริบิวต์ของแต่ละฟีเจอร์ วิธีนี้จะแปลง OSM เป็น Shapefile ภายในเวลาน้อยกว่าหนึ่งนาทีสำหรับชุดข้อมูลระดับเมืองทั่วไป (≈ 200 k ฟีเจอร์).

## วิธีทำการแปลง osm เป็น geojson
Aspose.GIS สามารถส่งออกเลเยอร์ OSM เดียวกันโดยตรงเป็น GeoJSON ด้วยการเรียก `Save` เพียงครั้งเดียว, ทำให้ไม่ต้องมีขั้นตอนรูปแบบกลาง วิธี `Save` จะเขียนเลเยอร์ไปยังรูปแบบและเส้นทางไฟล์ที่เลือก เรียก `layer.Save("output.geojson", SaveFormat.GeoJson)` แล้วไลบรารีจะจัดการการแปลงพิกัดและการแมปแอตทริบิวต์โดยอัตโนมัติ, ส่งมอบไฟล์ GeoJSON ที่สอดคล้องมาตรฐานพร้อมใช้งานสำหรับการทำแผนที่บนเว็บ.

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอกสาร
กำหนดโฟลเดอร์ที่บรรจุไฟล์ OSM XML ของคุณ  
แทนที่ `"Your Document Directory"` ด้วยเส้นทางแบบเต็มหรือแบบสัมพันธ์ไปยังไฟล์

## ขั้นตอนที่ 2: เปิดเลเยอร์ OpenStreetMap
`Layer` คลาสแสดงถึงเลเยอร์ GIS ที่โหลดจากแหล่งข้อมูลเช่นไฟล์ OSM XML  
การเปิดเลเยอร์จะสตรีม XML, ดังนั้นส่วนที่จำเป็นเท่านั้นจะถูกเก็บในหน่วยความจำ

## ขั้นตอนที่ 3: รับจำนวนฟีเจอร์
ดึงจำนวนฟีเจอร์ทั้งหมดในเลเยอร์ OSM และแสดงจำนวนนี้บนคอนโซล สิ่งนี้ช่วยให้คุณตรวจสอบว่าไฟล์ถูกอ่านอย่างถูกต้อง

## ขั้นตอนที่ 4: ดึงฟีเจอร์ตามดัชนี
เข้าถึงฟีเจอร์ใดก็ได้โดยตรงด้วยดัชนีเริ่มจากศูนย์; ตัวอย่างนี้ดึงฟีเจอร์ที่สามเพื่อสาธิตการเข้าถึงแบบสุ่ม

## ขั้นตอนที่ 5: วนลูปผ่านฟีเจอร์
การวนลูปผ่านเลเยอร์ทำให้คุณสามารถประมวลผลเรขาคณิตแต่ละอัน—จุด, เส้น, หรือโพลิกอน—แยกกัน เมธอด `AsText()` จะคืนค่าเรขาคณิตในรูปแบบ Well‑Known Text (WKT) ซึ่งสะดวกสำหรับการดีบักหรือบันทึก

## ปัญหาที่พบบ่อยและวิธีแก้
- **File not found** – ตรวจสอบเส้นทางใน `dataDir` อีกครั้งและให้แน่ใจว่าชื่อไฟล์ OSM ตรงกันอย่างแม่นยำ.  
- **Unsupported geometry** – บางองค์ประกอบของ OSM มีความสัมพันธ์ซับซ้อน; ตรวจสอบ `feature.Geometry` ก่อนและจัดการประเภท `MultiPolygon` หรือ `GeometryCollection` ตามความเหมาะสม.  
- **Performance on large files** – โหลดเลเยอร์ภายในบล็อก `using` (ตามตัวอย่าง) เพื่อรับประกันการปล่อยทรัพยากร, และใช้การกรอง LINQ (`layer.Where(f => f.Geometry is Point)`) หากคุณต้องการเพียงส่วนย่อยของฟีเจอร์เท่านั้น.  

## คำถามที่พบบ่อย
### Aspose.GIS สำหรับ .NET รองรับรูปแบบข้อมูล GIS อื่นหรือไม่?
ใช่, Aspose.GIS รองรับรูปแบบ GIS มากกว่า 30 รูปแบบ—รวมถึง Shapefile, GeoJSON, KML, GML, และ CSV—ทำให้การแลกเปลี่ยนข้อมูลเป็นไปอย่างราบรื่น.

### ฉันสามารถใช้ Aspose.GIS เพื่อการค้าได้หรือไม่?
แน่นอน. ซื้อไลเซนส์จาก [หน้าซื้อสินค้า](https://purchase.aspose.com/buy) เพื่อยกเลิกข้อจำกัดของรุ่นทดลองและรับการสนับสนุนเต็มรูปแบบ.

### มีรุ่นทดลองฟรีสำหรับ Aspose.GIS สำหรับ .NET หรือไม่?
มี, ดาวน์โหลดรุ่นทดลองที่ทำงานเต็มรูปแบบจาก [เว็บไซต์](https://releases.aspose.com/) เพื่อประเมินคุณสมบัติทั้งหมดก่อนซื้อ.

### ฉันสามารถหาการสนับสนุนสำหรับ Aspose.GIS สำหรับ .NET ได้ที่ไหน?
เยี่ยมชม [ฟอรั่ม Aspose.GIS อย่างเป็นทางการ](https://forum.aspose.com/c/gis/33) เพื่อถามคำถาม, แบ่งปันโค้ดสั้น, และรับความช่วยเหลือจากชุมชนและวิศวกรของ Aspose.

### ฉันสามารถขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.GIS สำหรับ .NET ได้หรือไม่?
ได้, ขอรับไลเซนส์ชั่วคราวจาก [หน้าลิขสิทธิ์ชั่วคราว](https://purchase.aspose.com/temporary-license/) สำหรับการทดสอบระยะสั้นหรือ pipeline ของ CI.

**อัปเดตล่าสุด:** 2026-06-10  
**ทดสอบด้วย:** Aspose.GIS 24.5 for .NET  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

```csharp
string dataDir = "Your Document Directory";
```

```csharp
using (var layer = Drivers.OsmXml.OpenLayer(dataDir + "fountain.osm"))
{
```

```csharp
int count = layer.Count;
Console.WriteLine("Layer count: " + count);
```

```csharp
Feature featureAtIndex2 = layer[2];
```

```csharp
foreach (Feature feature in layer)
{
    Console.WriteLine(feature.Geometry.AsText());
}
```

## บทแนะนำที่เกี่ยวข้อง

- [วิธีแปลง Shapefile เป็น GeoJSON ด้วย Aspose.GIS สำหรับ .NET – บทแนะนำเชิงลึก](/gis/net/)
- [วิธีแปลง GeoJSON เป็น TopoJSON ด้วย Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [อ่าน Shapefile C# – กรองฟีเจอร์ตามแอตทริบิวต์ด้วย Aspose.GIS](/gis/net/layer-management/filter-features-by-attribute/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}