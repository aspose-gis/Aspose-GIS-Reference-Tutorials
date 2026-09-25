---
date: 2026-09-25
description: เรียนรู้วิธีสร้างเรขาคณิต multilinestring อย่างรวดเร็วด้วย Aspose.GIS
  for .NET. บทเรียน multilinestring C# นี้แสดงขั้นตอนการสร้างเรขาคณิตเส้นซับซ้อนแบบทีละขั้นตอน.
keywords:
- create multilinestring geometry
- how to create multilinestring
- multilinestring example c#
lastmod: 2026-09-25
linktitle: สร้างเรขาคณิต MultiLineString
og_description: สร้างเรขาคณิต MultiLineString ด้วย Aspose.GIS for .NET ภายในไม่กี่นาที.
  ทำตามบทเรียน C# นี้เพื่อสร้างเรขาคณิตเส้นซับซ้อนสำหรับการทำแผนที่และการวิเคราะห์.
og_image_alt: Code example showing creation of MultiLineString geometry with Aspose.GIS
  in C#
og_title: สร้างเรขาคณิต MultiLineString ด้วย Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to quickly create multilinestring geometry with Aspose.GIS
    for .NET. This multilinestring tutorial C# shows step‑by‑step creation of complex
    line geometries.
  headline: Create MultiLineString geometry using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can call `multiLineString.Save("output.geojson", new GeoJsonOptions());`
      after adding the necessary using directives.
    question: Can I export the MultiLineString to GeoJSON?
  - answer: Use `multiLineString.SpatialReference = new SpatialReference(4326);` to
      assign WGS 84 (EPSG:4326).
    question: How do I set a spatial reference (SRID) for the MultiLineString?
  - answer: Absolutely. Use `FeatureReader` to iterate over features and cast the
      geometry to `MultiLineString`.
    question: Is it possible to read a MultiLineString from a Shapefile?
  - answer: Duplicate points are allowed but may affect length calculations and rendering;
      consider cleaning the data if duplicates are unintended.
    question: What happens if I add duplicate points to a LineString?
  - answer: Yes, you can add a Z value with `AddPoint(x, y, z);` and the geometry
      will be stored as 3‑dimensional.
    question: Does Aspose.GIS support 3D coordinates for MultiLineString?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create multilinestring
- Aspose.GIS
- .NET GIS development
title: สร้างเรขาคณิต MultiLineString ด้วย Aspose.GIS for .NET
url: /th/net/geometry-creation/create-multilinestring-geometry/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเรขาคณิต multilinestring ด้วย Aspose.GIS สำหรับ .NET

## บทนำ
ในบทแนะนำนี้คุณจะ **สร้างเรขาคณิต multilinestring** ด้วย Aspose.GIS สำหรับ .NET ซึ่งเป็นความต้องการทั่วไปเมื่อคุณต้องการแสดงชุดของฟีเจอร์เส้น เช่น ถนน, แม่น้ำ หรือเครือข่ายสาธารณูปโภค ไม่ว่าคุณจะสร้างแอปพลิเคชันแผนที่, ทำการวิเคราะห์เชิงพื้นที่, หรือส่งออกข้อมูลเส้นที่ซับซ้อน คู่มือนี้จะพาคุณผ่านกระบวนการแบบทีละขั้นตอน

Aspose.GIS สำหรับ .NET เป็นไลบรารีที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถทำงานกับข้อมูลเชิงพื้นที่ได้อย่างราบรื่นภายในแอปพลิเคชัน .NET ของพวกเขา มันรองรับทั้งสถานการณ์บนเดสก์ท็อปและเซิร์ฟเวอร์ ทำให้คุณมี API ที่สอดคล้องกันใน .NET Framework, .NET Core, และ .NET 5/6/7

## คำตอบสั้น
- **สร้างเรขาคณิต “multilinestring” หมายถึงอะไร?** หมายถึงการสร้างอ็อบเจ็กต์เรขาคณิตเดียวที่ประกอบด้วยหลายส่วน `LineString`  
- **ไลบรารีที่ใช้คืออะไร?** Aspose.GIS สำหรับ .NET  
- **ฉันต้องการใบอนุญาตหรือไม่?** ใช่, จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานจริง; มีรุ่นทดลองฟรีให้ใช้  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **การดำเนินการใช้เวลานานเท่าไหร่?** ปกติใช้เวลาน้อยกว่า 10 นาทีสำหรับตัวอย่างพื้นฐานที่แสดงในที่นี้

## MultiLineString คืออะไร?
**MultiLineString** คือการรวบรวมของอ็อบเจ็กต์ `LineString` สองหรือมากกว่าที่จัดกลุ่มเป็นเอนทิตีเชิงพื้นที่เดียว  
คุณสร้างมันเมื่อมีหลายเส้นที่เกี่ยวข้อง—เช่นเครือข่ายแม่น้ำหรือชุดของส่วนถนน—ต้องการจัดการเป็นฟีเจอร์เดียวในขณะที่แต่ละเส้นยังคงลำดับพิกัดของตนเอง คลาสนี้อยู่ในเนมสเปซ `Aspose.GIS.Geometry` และสามารถทำการซีเรียลไลซ์เป็นรูปแบบต่าง ๆ เช่น Shapefile, GeoJSON, และ KML

## ทำไมต้องใช้ Aspose.GIS สำหรับ .NET เพื่อสร้าง MultiLineString?
Aspose.GIS ช่วยให้คุณสร้าง MultiLineString ด้วยการเรียกใช้แบบ fluent เพียงไม่กี่ครั้ง ลดความจำเป็นในการจัดการบัฟเฟอร์เรขาคณิตระดับต่ำ มันสามารถประมวลผล **ข้อมูลเวกเตอร์ขนาดสูงสุด 500 MB ในโหมดสตรีมที่ใช้หน่วยความจำน้อย** รองรับ **รูปแบบเข้าและออกกว่า 50 รูปแบบ** และทำงานบน **.NET runtime หลักทั้งหมด** โดยไม่ต้องพึ่งพาไลบรารีเนทีฟภายนอก การผสมผสานของความเร็ว ความหลากหลายของรูปแบบ และความเสถียรข้ามแพลตฟอร์มทำให้เป็นตัวเลือกที่ดีที่สุดสำหรับโครงการ GIS ระดับองค์กร

## ข้อกำหนดเบื้องต้น
ก่อนที่จะลงลึกในโค้ด โปรดตรวจสอบว่าคุณมี:

### สภาพแวดล้อมการพัฒนา .NET
1. Visual Studio 2022 (หรือ IDE ใดก็ได้ที่รองรับ .NET 6+) ติดตั้งแล้ว.  
2. โปรเจกต์คอนโซล .NET 6 พร้อมสำหรับแพ็กเกจ NuGet.

### Aspose.GIS สำหรับ .NET
1. รับใบอนุญาตสำหรับ Aspose.GIS สำหรับ .NET จาก [purchase.aspose.com](https://purchase.aspose.com/buy).  
2. ดาวน์โหลดไลบรารีจาก [releases.aspose.com](https://releases.aspose.com/gis/net/).  
3. เพิ่มแพ็กเกจผ่าน NuGet (`Install-Package Aspose.GIS`) หรืออ้างอิง DLL ด้วยตนเอง.

## นำเข้าเนมสเปซ
เนมสเปซต่อไปนี้ให้คุณเข้าถึงฟังก์ชันหลักของ GIS:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
เนมสเปซนี้ให้การเข้าถึงฟังก์ชันหลักของ Aspose.GIS ทำให้คุณสามารถทำงานกับข้อมูลเชิงพื้นที่หลายประเภทได้.

ต่อไปนี้ เราจะแบ่งตัวอย่างที่ให้ไว้เป็นหลายขั้นตอน:

## วิธีสร้างเรขาคณิต multilinestring
สร้างอ็อบเจ็กต์ `LineString` สองอัน, เพิ่มจุด, แล้วรวมเข้าด้วยกันเป็น `MultiLineString`. การดำเนินการทั้งหมดต้องใช้เพียงสามการเรียกเมธอด: สร้างอ็อบเจ็กต์เส้น, เพิ่มพิกัด, และเพิ่มเส้นลงในคอลเลกชัน `LineString` แต่ละอันแสดงถึงเรขาคณิตเส้นเดียวที่กำหนดโดยรายการจุดที่เรียงลำดับ, และ `MultiLineString` คือคอลเลกชันของอ็อบเจ็กต์ `LineString` ที่แสดงหลายเส้นเป็นเรขาคณิตเดียว

### ขั้นตอนที่ 1: สร้างอ็อบเจ็กต์ LineString
```csharp
LineString firstLine = new LineString();
firstLine.AddPoint(7.5, -3.5);
firstLine.AddPoint(-9.6, 12.6);
LineString secondLine = new LineString();
secondLine.AddPoint(8.5, -2.6);
secondLine.AddPoint(-8.6, 1.5);
```
ในขั้นตอนนี้ เราจะสร้างอ็อบเจ็กต์ `LineString` สองอัน ซึ่งแสดงถึงเส้นแต่ละเส้น จุดจะถูกเพิ่มเข้าไปในแต่ละ `LineString` เพื่อกำหนดเรขาคณิตของมัน.

### ขั้นตอนที่ 2: สร้างอ็อบเจ็กต์ MultiLineString
```csharp
MultiLineString multiLineString = new MultiLineString();
multiLineString.Add(firstLine);
multiLineString.Add(secondLine);
```
ที่นี่ เราจะสร้างอ็อบเจ็กต์ `MultiLineString` และเพิ่มอ็อบเจ็กต์ `LineString` ที่สร้างไว้ก่อนหน้านี้เข้าไป ซึ่งทำให้ได้คอลเลกชันของเส้นที่จัดกลุ่มเป็นเอนทิตีเดียว

## ปัญหาและเคล็ดลับทั่วไป
- **ลำดับพิกัด:** Aspose.GIS คาดหวังพิกัดในลำดับ **(X, Y)** (ลองจิจูด, ละติจูด) การสลับลำดับอาจทำให้เรขาคณิตกลับด้าน.  
- **เรขาคณิตว่าง:** การพยายามเพิ่ม `LineString` ที่ว่างเปล่าจะทำให้เกิดข้อยกเว้น; ควรตรวจสอบว่าแต่ละเส้นมีจุดอย่างน้อยสองจุดเสมอ.  
- **การจัดการการฉายภาพ:** หากข้อมูลของคุณใช้ CRS เฉพาะ, ให้ตั้งค่า spatial reference บนเรขาคณิตก่อนทำการส่งออก.

## สรุป
Aspose.GIS สำหรับ .NET มอบ API ที่กระชับและประสิทธิภาพสูงสำหรับการสร้างและจัดการเรขาคณิตเส้นที่ซับซ้อน ด้วยการทำตามขั้นตอนข้างต้น คุณสามารถ **สร้างเรขาคณิต multilinestring** ได้อย่างรวดเร็วและส่งออกเป็นรูปแบบ GIS ที่รองรับใด ๆ

## คำถามที่พบบ่อย
### Aspose.GIS สำหรับ .NET รองรับทุกเฟรมเวิร์ก .NET หรือไม่?
ใช่, Aspose.GIS สำหรับ .NET รองรับเวอร์ชันต่าง ๆ ของ .NET framework, ทำให้มีความยืดหยุ่นสำหรับนักพัฒนา.

### ฉันสามารถทดลองใช้ Aspose.GIS สำหรับ .NET ก่อนซื้อได้หรือไม่?
แน่นอน! คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรีจาก [releases.aspose.com](https://releases.aspose.com/) เพื่อสำรวจคุณลักษณะและความสามารถของมัน.

### ฉันจะรับการสนับสนุนสำหรับ Aspose.GIS สำหรับ .NET ได้อย่างไร?
สำหรับการสนับสนุนและความช่วยเหลือ คุณสามารถเยี่ยมชม [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อถามคำถามและติดต่อกับผู้ใช้และผู้เชี่ยวชาญคนอื่น ๆ.

### ฉันต้องการใบอนุญาตชั่วคราวสำหรับการทดสอบหรือไม่?
แม้ว่าเวอร์ชันทดลองจะพร้อมสำหรับการทดสอบ, หากคุณต้องการคุณลักษณะเพิ่มเติมหรือประเมินฟังก์ชันเต็มรูปแบบ, คุณสามารถรับใบอนุญาตชั่วคราวจาก [purchase.aspose.com](https://purchase.aspose.com/temporary-license/).

### Aspose.GIS สำหรับ .NET เหมาะกับแอปพลิเคชันเดสก์ท็อปและเว็บหรือไม่?
ใช่, Aspose.GIS สำหรับ .NET สามารถใช้ได้ในแอปพลิเคชันหลากหลาย รวมถึงเดสก์ท็อป, เว็บ, และสถานการณ์ฝั่งเซิร์ฟเวอร์, ให้ความหลากหลายในการพัฒนาตามสภาพแวดล้อมต่าง ๆ.

## คำถามที่พบบ่อยบ่อยครั้ง
**ถาม: ฉันสามารถส่งออก MultiLineString เป็น GeoJSON ได้หรือไม่?**  
**ตอบ:** ใช่, คุณสามารถเรียก `multiLineString.Save("output.geojson", new GeoJsonOptions());` หลังจากเพิ่ม using directives ที่จำเป็น

**ถาม: ฉันจะตั้งค่า spatial reference (SRID) สำหรับ MultiLineString อย่างไร?**  
**ตอบ:** ใช้ `multiLineString.SpatialReference = new SpatialReference(4326);` เพื่อกำหนด WGS 84 (EPSG:4326).

**ถาม: สามารถอ่าน MultiLineString จาก Shapefile ได้หรือไม่?**  
**ตอบ:** แน่นอน. ใช้ `FeatureReader` เพื่อวนลูปฟีเจอร์และแคสต์เรขาคณิตเป็น `MultiLineString`.

**ถาม: จะเกิดอะไรขึ้นหากฉันเพิ่มจุดซ้ำใน LineString?**  
**ตอบ:** จุดซ้ำได้รับอนุญาตแต่อาจส่งผลต่อการคำนวณความยาวและการแสดงผล; ควรทำความสะอาดข้อมูลหากจุดซ้ำไม่ได้ตั้งใจ.

**ถาม: Aspose.GIS รองรับพิกัด 3 มิติสำหรับ MultiLineString หรือไม่?**  
**ตอบ:** ใช่, คุณสามารถเพิ่มค่า Z ด้วย `AddPoint(x, y, z);` และเรขาคณิตจะถูกเก็บเป็น 3‑มิติ.

---

**อัปเดตล่าสุด:** 2026-09-25  
**ทดสอบด้วย:** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [เรียนรู้วิธีสร้างเรขาคณิต MultiPolygon ด้วย Aspose.GIS](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [วิธีสร้างเรขาคณิต Polygon ด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [แปลง WKT เป็นเรขาคณิต: MultiCurve ด้วย Aspose.GIS .NET](/gis/net/geometry-creation/create-multicurve-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}