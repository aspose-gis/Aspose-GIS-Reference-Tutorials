---
date: 2026-06-10
description: เรียนรู้วิธีสร้าง linestring geometry ใน .NET และแปลง geometry เป็น WKB
  ด้วย Aspose.GIS สำหรับ .NET พร้อมตัวแปร ExtendedPostGis
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: ระบุ WKB Variant ในการแปล
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  headline: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  name: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  steps:
  - name: Creating a Geometry Object
    text: The `Geometry` class is Aspose.GIS's base type that represents any spatial
      object in memory. Linestring represents a series of connected points forming
      a linear geometry. In this step we instantiate a `Linestring` with a collection
      of coordinate pairs that model a simple road segment.
  - name: Generating WKB Representation
    text: '`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to
      include SRID in the output binary. Here we call the `AsBinary` method, passing
      the EWKB variant, which returns a `byte[]` containing the full binary representation.'
  - name: Writing to File
    text: '`File.WriteAllBytes` writes the binary array to disk. The resulting file
      (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB`
      function.'
  type: HowTo
- questions:
  - answer: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which
      PostGIS reads directly via `ST_GeomFromEWKB`.
    question: Can I use the EWKB file with PostGIS?
  - answer: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry
      from its binary form.
    question: Is it possible to read a WKB file back into a geometry object?
  - answer: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons,
      and many more spatial types.
    question: Does the library support other geometry types like polygons?
  - answer: Set the `SRID` property on the geometry object before calling `AsBinary`,
      e.g., `linestring.SRID = 4326;`.
    question: How do I specify a different SRID when creating the geometry?
  - answer: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6
      without modification.
    question: Will this code work on .NET Core?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: สร้าง Linestring Geometry และ WKB Variant ใน Aspose.GIS สำหรับ .NET
url: /th/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเรขาคณิต Linestring & ตัวแปร WKB ใน Aspose.GIS สำหรับ .NET

## บทนำ
หากคุณต้องการ **สร้างเรขาคณิต linestring ใน .NET** แล้วแปลงเรขาคณิตนั้นเป็นรูปแบบไบนารี Aspose.GIS สำหรับ .NET จะมอบ API ที่สะอาดและมีประสิทธิภาพสูงซึ่งทำงานได้บน .NET Framework, .NET Core, และ .NET 5/6+ ในบทแนะนำนี้เราจะพาคุณผ่านทุกขั้นตอน—ตั้งแต่การนำเข้า namespace ไปจนถึงการเขียนไฟล์ EWKB—เพื่อให้คุณสามารถเก็บข้อมูล SRID ไว้และผสานข้อมูล GIS เข้ากับ PostgreSQL/PostGIS หรือเวิร์กโฟลว์ที่ใช้ไบนารีใด ๆ ได้อย่างไม่มีปัญหา

## คำตอบสั้น
- **WKB ย่อมาจากอะไร?** Well‑Known Binary, การแสดงผลไบนารีแบบกะทัดรัดของวัตถุเรขาคณิต.  
- **ตัวแปร WKB ใดที่เก็บ SRID?** ตัวแปร `ExtendedPostGis` (EWKB) ฝัง SRID ไว้โดยตรงในไบนารี.  
- **ฉันต้องการไลเซนส์หรือไม่?** จำเป็นต้องมีไลเซนส์ Aspose.GIS แบบชั่วคราวหรือเต็มสำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6+.  
- **การทำงานนี้ใช้เวลานานเท่าไหร่?** ปกติใช้เวลาน้อยกว่า 10 นาทีสำหรับตัวอย่างพื้นฐาน.

## Linestring Geometry คืออะไร?
เรขาคณิต linestring คือรูปทรงง่าย ๆ ที่ประกอบด้วยรายการจุดที่เรียงลำดับกันโดยเชื่อมต่อด้วยเส้นตรง มันเป็นรูปแบบมาตรฐานสำหรับฟีเจอร์เชิงเส้นเช่นถนน, ท่อส่ง, หรือเส้นแม่น้ำในฐานข้อมูลเชิงพื้นที่.

## ทำไมต้องระบุตัวแปร WKB?
การใช้ตัวแปร WKB ที่ถูกต้องรับประกันว่าข้อมูลเมตาดาต้าที่สำคัญ—โดยเฉพาะ Spatial Reference System Identifier (SRID)—จะถูกส่งมาพร้อมกับเรขาคณิตของคุณ ตัวแปร `ExtendedPostGis` (EWKB) จะเก็บ SRID ไว้ใน payload ของไบนารี ทำให้สามารถทำ round‑tripping อย่างราบรื่นกับ PostGIS, Oracle Spatial หรือระบบใด ๆ ที่คาดหวังไบนารีที่มีข้อมูล SRID.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

### การติดตั้ง Aspose.GIS สำหรับ .NET
1. ดาวน์โหลด Aspose.GIS: เยี่ยมชม [download link](https://releases.aspose.com/gis/net/) เพื่อรับแพคเกจล่าสุด.  
2. เพิ่มแพคเกจ NuGet ลงในโปรเจกต์ของคุณ (เช่น `Install-Package Aspose.GIS`).  

### ความคุ้นเคยกับการเขียนโปรแกรม C#
- ความเข้าใจพื้นฐานเกี่ยวกับไวยากรณ์ C# และโครงสร้างโปรเจกต์.  
- ความสามารถในการรันโปรเจกต์คอนโซลหรือคลาส‑ไลบรารีของ .NET.  

## นำเข้า Namespace
Namespace `Aspose.GIS` ให้คุณเข้าถึงคลาสที่เกี่ยวข้องกับเรขาคณิตทั้งหมด.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Namespace เหล่านี้ให้ฟังก์ชันหลักของ GIS รวมถึงการสร้างเรขาคณิต, การแปลง, และการทำซีเรียลไลซ์เป็นไบนารี.

## วิธีสร้างเรขาคณิต linestring?
เพื่อสร้าง linestring ให้สร้างอ็อบเจ็กต์ `Linestring` ด้วยรายการคู่พิกัดที่เรียงลำดับ ตั้งค่า SRID หากต้องการ แล้วทำการซีเรียลไลซ์เป็นตัวแปร WKB ที่ต้องการ กระบวนการประกอบด้วยสามขั้นตอน: สร้างเรขาคณิต, เลือกตัวแปร `ExtendedPostGis` เพื่อเก็บ SRID, และเขียนอาร์เรย์ไบต์ที่ได้ลงไฟล์.

### ขั้นตอนที่ 1: สร้างอ็อบเจ็กต์ Geometry
คลาส `Geometry` เป็นประเภทฐานของ Aspose.GIS ที่แสดงถึงวัตถุเชิงพื้นที่ใด ๆ ในหน่วยความจำ.  
Linestring แสดงชุดของจุดที่เชื่อมต่อกันเป็นเรขาคณิตเชิงเส้น.

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
ในขั้นตอนนี้เราจะสร้างอ็อบเจ็กต์ `Linestring` ด้วยคอลเลกชันของคู่พิกัดที่จำลองส่วนของถนนอย่างง่าย.

### ขั้นตอนที่ 2: สร้างการแสดงผล WKB
`WkbVariant.ExtendedPostGis` เป็นค่า enum ที่บอก Aspose.GIS ให้รวม SRID ไว้ในไบนารีผลลัพธ์.

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
ที่นี่เราเรียกเมธอด `AsBinary` โดยส่งตัวแปร EWKB ซึ่งจะคืนค่า `byte[]` ที่มีการแสดงผลไบนารีเต็มรูปแบบ.

### ขั้นตอนที่ 3: เขียนลงไฟล์
`File.WriteAllBytes` จะเขียนอาร์เรย์ไบต์ลงดิสก์.

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
ไฟล์ที่ได้ (`EWkbFile.ewkb`) สามารถนำเข้าโดยตรงไปยังตาราง PostGIS ด้วยฟังก์ชัน `ST_GeomFromEWKB`.

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| **ไฟล์ว่าง** | `Path.Combine` ชี้ไปยังไดเรกทอรีที่ไม่มีอยู่. | ตรวจสอบให้แน่ใจว่าไดเรกทอรีเป้าหมายมีอยู่หรือสร้างด้วย `Directory.CreateDirectory`. |
| **SRID ไม่ถูกต้อง** | การใช้ค่าเริ่มต้น `WkbVariant.Standard` จะทำให้ SRID หายไป. | ควรใช้ `WkbVariant.ExtendedPostGis` เสมอเมื่อจำเป็นต้องเก็บ SRID. |
| **ข้อยกเว้นไลเซนส์** | รันโดยไม่มีไลเซนส์ที่ถูกต้องในสภาพแวดล้อมการผลิต. | ใช้ไลเซนส์ชั่วคราวหรือเต็มก่อนดำเนินการโค้ดในสภาพแวดล้อมการผลิต. |

## คำถามที่พบบ่อย
**Q: ฉันสามารถใช้ไฟล์ EWKB กับ PostGIS ได้หรือไม่?**  
A: ใช่, ตัวแปร `ExtendedPostGis` สร้าง EWKB ที่รวม SRID ซึ่ง PostGIS สามารถอ่านโดยตรงผ่าน `ST_GeomFromEWKB`.

**Q: สามารถอ่านไฟล์ WKB กลับมาเป็นอ็อบเจ็กต์เรขาคณิตได้หรือไม่?**  
A: แน่นอน. ใช้ `Geometry.FromBinary(byteArray)` เพื่อสร้างเรขาคณิตจากรูปแบบไบนารี.

**Q: ไลบรารีนี้สนับสนุนประเภทเรขาคณิตอื่น ๆ เช่น polygon หรือไม่?**  
A: ใช่, Aspose.GIS รองรับ points, linestrings, polygons, multipolygons และประเภทเชิงพื้นที่อื่น ๆ อีกหลายประเภท.

**Q: ฉันจะระบุ SRID ที่แตกต่างเมื่อสร้างเรขาคณิตได้อย่างไร?**  
A: ตั้งค่า property `SRID` บนวัตถุเรขาคณิตก่อนเรียก `AsBinary` เช่น `linestring.SRID = 4326;`.

**Q: โค้ดนี้จะทำงานบน .NET Core หรือไม่?**  
A: ใช่, API เดียวกันทำงานได้บน .NET Framework, .NET Core, และ .NET 5/6 โดยไม่ต้องแก้ไข.

---

**อัปเดตล่าสุด:** 2026-06-10  
**ทดสอบกับ:** Aspose.GIS for .NET 23.9 (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [การแปลงเรขาคณิตเป็นรูปแบบ WKB ด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [ระบุตัวแปร WKT ในการแปลงโดยใช้ Aspose.GIS](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [สร้างเรขาคณิต MultiLineString ด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}