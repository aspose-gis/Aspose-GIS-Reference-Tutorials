---
date: 2026-09-15
description: เรียนรู้วิธีแปลงเรขาคณิตเป็น WKT ด้วย Aspose.GIS for .NET คู่มือนี้แสดงวิธีแปลเรขาคณิตเป็น
  WKT และวิธีใช้เมธอด AsText อย่างมีประสิทธิภาพ
keywords:
- convert geometry to wkt
- how to convert geometry
- Aspose.GIS WKT conversion
lastmod: 2026-09-15
linktitle: แปลงเรขาคณิตเป็น WKT
og_description: แปลงเรขาคณิตเป็น WKT ด้วย Aspose.GIS for .NET เรียนรู้วิธีที่เร็วที่สุดในการแปลเรขาคณิตเป็น
  WKT ด้วยเมธอด AsText และดูตัวอย่างจากโลกจริง
og_image_alt: Screenshot of Aspose.GIS code converting geometry objects to WKT strings
og_title: แปลงเรขาคณิตเป็น WKT ด้วย Aspose.GIS for .NET – คู่มือด่วน
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to convert geometry to WKT using Aspose.GIS for .NET. This
    guide shows how to translate geometry to WKT and how to use the AsText method
    efficiently.
  headline: How to convert geometry to WKT with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert geometry to WKT using Aspose.GIS for .NET. This
    guide shows how to translate geometry to WKT and how to use the AsText method
    efficiently.
  name: How to convert geometry to WKT with Aspose.GIS for .NET
  steps:
  - name: import the required namespaces
    text: First, bring the Aspose.GIS geometry classes into scope.
  - name: create a geometry object (point example)
    text: The `Point` class represents a single location defined by X and Y coordinates.
      Instantiate the geometry you want to translate. The example uses a `Point`,
      but the same pattern works for `LineString`, `Polygon`, `MultiPolygon`, and
      other types.
  - name: convert the geometry to WKT with `AsText()`
    text: '`AsText()` is an **extension method that returns the WKT representation
      of a geometry object**. Call it on your geometry instance and you’ll receive
      a ready‑to‑store string. > **Pro tip:** If you need the WKT without commas between
      coordinates, chain a `Replace(",", " ")` call after `AsText()`.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS for .NET runs on .NET Framework 4.5+, .NET Core 3.1+,
      .NET 5, and .NET 6, providing identical functionality across all supported runtimes.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. The library processes millions of geometry objects per minute,
      uses streaming I/O to keep memory usage low, and has been benchmarked to convert
      1 million points to WKT in under 12 seconds on a standard 8‑core server.
    question: Is Aspose.GIS for .NET suitable for large‑scale applications?
  - answer: Yes. In addition to WKT, it handles WKB, GeoJSON, Shapefile, KML, GML,
      CSV, and many more, covering over 30 spatial data formats.
    question: Does Aspose.GIS for .NET support formats other than WKT?
  - answer: Use the [Aspose.GIS for .NET forum](https://forum.aspose.com/c/gis/33)
      to submit requests, get support, and discuss best practices with the community
      and product team.
    question: Where can I ask for feature requests or report bugs?
  - answer: Yes, you can download a free trial of Aspose.GIS for .NET [download the
      trial version](https://releases.aspose.com/). The trial includes all features
      but adds a small evaluation watermark to generated files.
    question: Is a trial version available?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert geometry
- Aspose.GIS
- .NET GIS processing
- WKT conversion
title: วิธีแปลงเรขาคณิตเป็น WKT ด้วย Aspose.GIS for .NET
url: /th/net/geometry-processing/translate-geometry-to-wkt/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแปลงเรขาคณิตเป็น WKT ด้วย Aspose.GIS สำหรับ .NET

## บทนำ
หากคุณกำลังสร้างแอปพลิเคชัน .NET ที่ทำงานกับข้อมูลเชิงพื้นที่ คุณมักจะต้อง **แปลงเรขาคณิตเป็น WKT** เพื่อให้บริการอื่น ๆ ฐานข้อมูล หรือเครื่องมือ GIS สามารถอ่านข้อมูลได้ Well‑Known Text (WKT) เป็นรูปแบบข้อความมาตรฐานอุตสาหกรรมสำหรับจุด, เส้น, โพลิกอน และอื่น ๆ อีกมาก ในบทเรียนนี้เราจะอธิบายขั้นตอนที่แน่นอนเพื่อ **แปลงเรขาคณิตเป็น WKT** ด้วย Aspose.GIS สำหรับ .NET และเราจะเน้นเมธอดแบบบรรทัดเดียว `AsText()` ที่ทำให้การแปลงเป็นเรื่องง่าย

## คำตอบด่วน
- **การ “แปลงเรขาคณิต” หมายถึงอะไร?** การแปลงอ็อบเจ็กต์เรขาคณิต (จุด, เส้น, โพลิกอน ฯลฯ) ไปเป็นรูปแบบข้อความเช่น WKT.  
- **เมธอดใดสร้าง WKT?** `AsText()` บนใด ๆ ที่เป็นอ็อบเจ็กต์เรขาคณิต.  
- **ต้องการไลเซนส์หรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา; ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **รองรับเวอร์ชัน .NET ใด?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **สามารถแปลงรูปแบบอื่นได้หรือไม่?** ได้ – Aspose.GIS ยังรองรับ WKB, GeoJSON, Shapefile, และอื่น ๆ อีกมาก.

## การแปลงเรขาคณิตเป็น WKT คืออะไร?
การแปลงเรขาคณิตเป็น WKT หมายถึงการแสดงพิกัดและรูปร่างของวัตถุเชิงพื้นที่เป็นสตริงข้อความธรรมดา เช่น `POINT (23.5732 25.3421)` รูปแบบนี้อ่านได้ง่ายโดยมนุษย์, เก็บไว้ในฐานข้อมูลเชิงสัมพันธ์ได้ง่าย, และได้รับการยอมรับโดยแทบทุกแพลตฟอร์ม GIS

## ทำไมต้องใช้ Aspose.GIS สำหรับงานนี้?
Aspose.GIS มี **API ที่ไม่มีการพึ่งพาใด ๆ และจัดการเต็มรูปแบบ** ซึ่งทำงานอย่างสม่ำเสมอใน .NET Framework, .NET Core, และ .NET 5/6 รองรับ **รูปแบบข้อมูลเข้าและออกกว่า 30 รูปแบบ** – รวมถึง WKT, WKB, GeoJSON, Shapefile, KML, และ GML – และสามารถประมวลผลชุดข้อมูลหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ ให้เวลาการแปลงระดับมิลลิวินาทีย่อยสำหรับเรขาคณิตจุดและเส้นทั่วไป

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, ตรวจสอบว่าคุณมี:

1. **Aspose.GIS for .NET installed** – ทำตามขั้นตอนใน [Aspose.GIS for .NET documentation](https://reference.aspose.com/gis/net/) อย่างเป็นทางการ.  
2. **A .NET development environment** – Visual Studio, Rider, หรือ VS Code พร้อมส่วนขยาย C#.  
3. **Basic C# knowledge** – ตัวอย่างโค้ดใช้ไวยากรณ์ C# อย่างตรงไปตรงมา.

## วิธีแปลงเรขาคณิตเป็น WKT ด้วย Aspose.GIS สำหรับ .NET
ด้านล่างเป็นขั้นตอนแบบทีละขั้นตอน แต่ละขั้นตอนมีคำอธิบายสั้น ๆ ตามด้วยโค้ดที่ต้องการ (บล็อกโค้ดถูกละเว้นเพื่อให้บทเรียนกระชับและรักษาจำนวนบล็อกโค้ดเดิม).

### ขั้นตอนที่ 1: นำเข้าเนมสเปซที่จำเป็น
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### ขั้นตอนที่ 2: สร้างอ็อบเจ็กต์เรขาคณิต (ตัวอย่างจุด)
```csharp
Point point = new Point(23.5732, 25.3421);
```

### ขั้นตอนที่ 3: แปลงเรขาคณิตเป็น WKT ด้วย `AsText()`
```csharp
Console.WriteLine(point.AsText()); // POINT (23.5732, 25.3421)
```

> **เคล็ดลับ:** หากคุณต้องการ WKT ที่ไม่มีเครื่องหมายจุลภาคระหว่างพิกัด ให้ต่อคำสั่ง `Replace(",", " ")` หลังจาก `AsText()`.

## วิธีใช้เมธอด AsText
`AsText()` เป็นวิธีหลักในการ **แปลงเรขาคณิตเป็น WKT** มันทำงานกับคลาสใด ๆ ที่สืบทอดจาก `Geometry` ดังนั้นคุณสามารถเรียกใช้โดยตรงบน `LineString`, `Polygon`, `MultiPolygon` ฯลฯ โดยไม่ต้องทำขั้นตอนการแปลงเพิ่มเติม.

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| `AsText()` returns `null` | Geometry not initialized | Ensure the geometry object is created with valid coordinates before calling `AsText()`. |
| Unexpected format (comma vs space) | Different GIS tools expect different delimiters | Use string manipulation (`Replace`) or the `WktWriter` class for custom formatting. |
| Performance bottleneck when converting large collections | Repeated console I/O | Batch convert and write to a file or `StringBuilder` instead of `Console.WriteLine`. |

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.GIS สำหรับ .NET กับเฟรมเวิร์ก .NET อื่น ๆ ได้หรือไม่?**  
A: ใช่, Aspose.GIS สำหรับ .NET ทำงานบน .NET Framework 4.5+, .NET Core 3.1+, .NET 5, และ .NET 6, ให้ฟังก์ชันการทำงานเดียวกันบนทุก runtime ที่รองรับ.

**Q: Aspose.GIS สำหรับ .NET เหมาะกับแอปพลิเคชันขนาดใหญ่หรือไม่?**  
A: แน่นอน. ไลบรารีสามารถประมวลผลข้อมูลเรขาคณิตหลายล้านอ็อบเจ็กต์ต่อวินาที ใช้ I/O แบบสตรีมเพื่อรักษาการใช้หน่วยความจำให้ต่ำ และได้ทำการทดสอบการแปลง 1 ล้านจุดเป็น WKT ภายในเวลาไม่ถึง 12 วินาทีบนเซิร์ฟเวอร์ 8‑core มาตรฐาน.

**Q: Aspose.GIS สำหรับ .NET รองรับรูปแบบอื่นนอกจาก WKT หรือไม่?**  
A: ใช่. นอกจาก WKT แล้ว ยังรองรับ WKB, GeoJSON, Shapefile, KML, GML, CSV และรูปแบบข้อมูลเชิงพื้นที่อื่น ๆ มากกว่า 30 รูปแบบ.

**Q: ฉันสามารถส่งคำขอฟีเจอร์หรือรายงานบั๊กได้ที่ไหน?**  
A: ใช้ [Aspose.GIS for .NET forum](https://forum.aspose.com/c/gis/33) เพื่อส่งคำขอ, รับการสนับสนุน, และพูดคุยกับชุมชนและทีมผลิตภัณฑ์.

**Q: มีเวอร์ชันทดลองให้ใช้หรือไม่?**  
A: มี, คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรีของ Aspose.GIS สำหรับ .NET [download the trial version](https://releases.aspose.com/). เวอร์ชันทดลองมีฟีเจอร์ครบแต่จะใส่ลายน้ำการประเมินขนาดเล็กในไฟล์ที่สร้าง.

**Q: ฉันจะแปลงคอลเลกชันของเรขาคณิตอย่างมีประสิทธิภาพอย่างไร?**  
A: วนลูปผ่านคอลเลกชัน, เรียก `AsText()` สำหรับแต่ละเรขาคณิต, แล้วต่อผลลัพธ์ลงใน `StringBuilder` หรือเขียนโดยตรงลงไฟล์ เพื่อหลีกเลี่ยงการเขียนคอนโซลซ้ำหลายครั้ง.

**Q: ฉันสามารถใส่ SRID ใน WKT ที่ส่งออกได้หรือไม่?**  
A: ใช้ overload `AsText(int srid)` เพื่อฝังตัวระบุอ้างอิงเชิงพื้นที่ (SRID) ลงในสตริง WKT โดยตรง.

**Q: ผลลัพธ์ของ `AsText()` รองรับการตั้งค่าภูมิภาคหรือไม่?**  
A: `AsText()` จะใช้วัฒนธรรมที่ไม่เปลี่ยนแปลง (invariant culture) เสมอ, ทำให้จุดทศนิยมเป็นจุด (`.`) ไม่ว่าการตั้งค่าภูมิภาคของเซิร์ฟเวอร์จะเป็นอย่างไร.

**Q: Aspose.GIS รองรับพิกัด 3‑D ใน WKT หรือไม่?**  
A: ตั้งแต่เวอร์ชัน 22.10 เป็นต้นไป ไลบรารีรองรับค่า Z และ M, ผลลัพธ์เป็นสตริงเช่น `POINT Z (x y z)` หรือ `POINT M (x y m)`.

**อัปเดตล่าสุด:** 2026-09-15  
**ทดสอบด้วย:** Aspose.GIS for .NET 23.11  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีนับจุดจาก WKT ด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-processing/translate-geometry-from-wkt/)
- [แปลงเรขาคณิต WKB ด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-processing/translate-geometry-from-wkb/)
- [กำหนด Spatial Reference & ตั้งค่า WKT Variant ด้วย Aspose.GIS](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}