---
date: 2026-09-25
description: เรียนรู้วิธีสร้างเรขาคณิต linestring อย่างรวดเร็วใน .NET ด้วย Aspose.GIS
  คู่มือนี้ครอบคลุมการเพิ่ม points ไปยัง linestring และการจัดการข้อมูล geospatial
  อย่างมีประสิทธิภาพ
keywords:
- create linestring geometry
- add points to linestring
- Aspose.GIS .NET
lastmod: 2026-09-25
linktitle: สร้างเรขาคณิต LineString
og_description: เรียนรู้วิธีสร้างเรขาคณิต linestring ใน .NET ด้วย Aspose.GIS เพิ่ม
  points ไปยัง linestring อย่างรวดเร็วและจัดการข้อมูล geospatial อย่างมีประสิทธิภาพ
og_image_alt: Screenshot of Aspose.GIS code creating a LineString geometry in .NET
og_title: สร้างเรขาคณิต linestring ด้วย Aspose.GIS สำหรับ .NET
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to quickly create linestring geometry in .NET using Aspose.GIS.
    This guide covers adding points to a linestring and handling geospatial data efficiently.
  headline: How to create linestring geometry with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Absolutely. Use `line.Save("output.geojson", ExportFormat.GeoJson);` after
      adding all points.
    question: Can I export the LineString to GeoJSON?
  - answer: Call `double length = line.Length;` – the API returns the length in the
      units of your coordinate system.
    question: How do I calculate the length of the LineString?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geospatial data
- Aspose.GIS
- .NET GIS
- geometry creation
title: วิธีสร้างเรขาคณิต linestring ด้วย Aspose.GIS สำหรับ .NET
url: /th/net/geometry-creation/create-linestring-geometry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างเรขาคณิต linestring ด้วย Aspose.GIS สำหรับ .NET

## บทนำ
หากคุณกำลังมองหา **การสร้างเรขาคณิต linestring** ในสภาพแวดล้อม .NET คุณมาถูกที่แล้ว ในบทเรียนนี้เราจะอธิบายการสร้างเรขาคณิต `LineString` ด้วย Aspose.GIS, เพิ่มจุดลงไป, และอธิบายว่าทำไมวิธีนี้จึงเหมาะสำหรับการทำงานกับ **ข้อมูลเชิงพื้นที่ .NET** ในตอนท้ายคุณจะได้ตัวอย่างที่ชัดเจนและสามารถรันได้ซึ่งคุณสามารถนำไปใช้ในโครงการแมปปิ้งหรือการวิเคราะห์เชิงพื้นที่ใด ๆ

## คำตอบอย่างรวดเร็ว
- **ต้องการไลบรารีอะไร?** Aspose.GIS for .NET  
- **ต้องใช้โค้ดกี่บรรทัด?** มีเพียงสามคำสั่งสั้น ๆ เพื่อสร้างและเติมข้อมูลให้ LineString  
- **ต้องมีลิขสิทธิ์สำหรับการทดสอบหรือไม่?** รุ่นทดลองฟรีใช้ได้สำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework, .NET Core, .NET 5+ และ .NET 6+  
- **สามารถเพิ่มจุดเพิ่มเติมในภายหลังได้หรือไม่?** ได้ – เรียก `AddPoint` ตามจำนวนที่ต้องการ  

## LineString คืออะไร?
LineString คือรูปทรงเรขาคณิตแบบง่ายที่ประกอบด้วยรายการจุดที่เรียงลำดับกันโดยเชื่อมต่อด้วยเส้นตรง มันเหมาะสำหรับการจำลองลักษณะเชิงเส้นเช่น ถนน, แม่น้ำ, ท่อส่ง, หรือเส้นทางใด ๆ บนแผนที่ แต่ละจุดเป็นเวอร์เท็กซ์และลำดับของจุดกำหนดรูปทรงของเส้น

## ทำไมต้องใช้ Aspose.GIS สำหรับ .NET?
Aspose.GIS for .NET ให้ API ที่จัดการเต็มรูปแบบและมีประสิทธิภาพสูงซึ่งทำให้ไม่ต้องพึ่งพาไลบรารี GIS แบบดั้งเดิม รองรับรูปแบบไฟล์เข้าและออกมากกว่า 30 รูปแบบ รวมถึง Shapefile, GeoJSON, KML, GML, และ CSV และสามารถประมวลผลไฟล์ที่ใหญ่กว่า 500 MB โดยไม่ต้องโหลดชุดข้อมูลทั้งหมดเข้าสู่หน่วยความจำ สิ่งนี้ช่วยลดเวลาในการพัฒนาและการใช้หน่วยความจำอย่างมาก

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:
1. **สภาพแวดล้อม .NET** – ติดตั้ง .NET SDK ล่าสุดจาก Microsoft.  
2. **ไลบรารี Aspose.GIS for .NET** – ดาวน์โหลดไบนารีจาก [download page](https://releases.aspose.com/gis/net/) แล้วเพิ่มการอ้างอิงไปยังโปรเจคของคุณ.  
3. **IDE สำหรับการพัฒนา** – Visual Studio, Rider หรือเครื่องมือแก้ไขใด ๆ ที่รองรับการพัฒนา .NET.

## นำเข้า namespace
ในแอปพลิเคชัน .NET ของคุณ ให้นำเข้า namespace ที่จำเป็นเพื่อเข้าถึงฟังก์ชันที่ Aspose.GIS ให้มา

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## วิธีสร้างเรขาคณิต LineString
`LineString` คือคลาส polyline ที่สามารถแก้ไขได้ซึ่งเก็บชุดจุดพิกัดที่เรียงลำดับกัน  
เพื่อสร้างเรขาคณิต LineString ใน .NET ด้วย Aspose.GIS ให้สร้างอ็อบเจ็กต์ `LineString` ใหม่แล้วเพิ่มเวอร์เท็กซ์แต่ละจุดโดยใช้เมธอด `AddPoint` พร้อมค่าลองจิจูดและละติจูด เมื่อเพิ่มจุดทั้งหมดแล้วอ็อบเจ็กต์จะเป็น polyline ที่สมบูรณ์พร้อมสำหรับการส่งออกหรือการวิเคราะห์เชิงพื้นที่

### ขั้นตอนที่ 1: สร้างอ็อบเจ็กต์ LineString
คลาส `LineString` แสดงถึง polyline ที่สามารถแก้ไขได้ซึ่งเก็บชุดจุดพิกัดที่เรียงลำดับกัน.  
```csharp
LineString line = new LineString();
```
ที่นี่เราสร้างอ็อบเจ็กต์ `LineString` ใหม่ซึ่งจะเก็บชุดของจุดที่กำหนดเส้น.

### ขั้นตอนที่ 2: เพิ่มจุดลงใน LineString
เมธอด `AddPoint` จะเพิ่มเวอร์เท็กซ์ใหม่ลงใน LineString โดยใช้พิกัด X (ลองจิจูด) และ Y (ละติจูด).  
```csharp
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```
เราจะเพิ่มจุดตัวอย่างสองจุดโดยใช้เมธอด `AddPoint`. แต่ละจุดถูกกำหนดด้วยพิกัด X (ลองจิจูด) และ Y (ละติจูด). คุณสามารถเรียก `AddPoint` ซ้ำหลายครั้งเพื่อขยายเส้นตามต้องการ.

## ปัญหาทั่วไปและวิธีแก้
- **จุดปรากฏในลำดับที่ผิด** – ตรวจสอบให้แน่ใจว่าคุณเพิ่มจุดตามลำดับที่ต้องการให้เชื่อมต่อ.  
- **ระบบพิกัดไม่ตรงกัน** – Aspose.GIS ทำงานในระบบพิกัดที่คุณระบุ; แปลงพิกัดให้เป็น CRS เดียวกันหากใช้แหล่งข้อมูลหลายแหล่ง.  
- **NullReferenceException** – ตรวจสอบว่าอ็อบเจ็กต์ `LineString` ถูกสร้างก่อนเรียก `AddPoint`.

## คำถามที่พบบ่อย
### ถ: Aspose.GIS for .NET รองรับทุกเฟรมเวิร์กของ .NET หรือไม่?
ใช่, Aspose.GIS for .NET รองรับ .NET Framework, .NET Core, และ .NET 5+.

### ถ: ฉันสามารถใช้ Aspose.GIS สำหรับโครงการเชิงพาณิชย์ได้หรือไม่?
ใช่, คุณสามารถใช้ Aspose.GIS ทั้งในโครงการส่วนบุคคลและเชิงพาณิชย์ได้ ตรวจสอบตัวเลือกการให้ลิขสิทธิ์บนเว็บไซต์ของ Aspose.

### ถ: Aspose.GIS มีการสนับสนุนรูปแบบข้อมูลเชิงพื้นที่อื่น ๆ นอกจาก GeoJSON หรือไม่?
ใช่, Aspose.GIS รองรับรูปแบบข้อมูลเชิงพื้นที่หลากหลายรวมถึง Shapefile, KML, GML, และอื่น ๆ อีกมาก.

### ถ: Aspose.GIS มีการอัปเดตบ่อยแค่ไหน?
Aspose.GIS ปล่อยอัปเดตเป็นประจำเพื่อปรับปรุงประสิทธิภาพ, เพิ่มฟีเจอร์ใหม่, และแก้ไขปัญหาที่รายงาน.

### ถ: มีฟอรั่มชุมชนที่ฉันสามารถขอความช่วยเหลือเกี่ยวกับ Aspose.GIS ได้หรือไม่?
ใช่, คุณสามารถเยี่ยมชมฟอรั่ม Aspose.GIS เพื่อรับการสนับสนุนจากชุมชนและเชื่อมต่อกับผู้ใช้คนอื่น: [Aspose.GIS Forum](https://forum.aspose.com/c/gis/33).

**คำถามเพิ่มเติม**
**ถาม: ฉันสามารถส่งออก LineString เป็น GeoJSON ได้หรือไม่?**  
ตอบ: แน่นอน ใช้ `line.Save("output.geojson", ExportFormat.GeoJson);` หลังจากเพิ่มจุดทั้งหมด.

**ถาม: ฉันจะคำนวณความยาวของ LineString ได้อย่างไร?**  
ตอบ: เรียก `double length = line.Length;` – API จะคืนค่าความยาวในหน่วยของระบบพิกัดของคุณ.

## สรุป
การสร้างและจัดการ `LineString` ใน .NET ทำได้ง่ายด้วย Aspose.GIS ด้วยการทำตามขั้นตอนข้างต้นคุณสามารถ **เพิ่มจุดลงใน linestring** อย่างรวดเร็วและผสานรวมเรขาคณิตนี้เข้าสู่กระบวนการ GIS ที่ใหญ่ขึ้น ค้นหาเอกสาร Aspose.GIS เพิ่มเติมเพื่อเรียนรู้การดำเนินการขั้นสูงเช่นการสอบถามเชิงพื้นที่, การแปลงเรขาคณิต, และการแปลงรูปแบบ.

---

**อัปเดตล่าสุด:** 2026-09-25  
**ทดสอบด้วย:** Aspose.GIS for .NET 24.11  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [วิธีเพิ่มจุดและวนซ้ำผ่านเรขาคณิตใน .NET](/gis/net/geometry-processing/iterate-over-points-in-geometry/)
- [ใช้ Aspose.GIS สำหรับ .NET เพื่อสร้างบัฟเฟอร์เรขาคณิต](/gis/net/geometry-analysis/create-geometry-buffer/)
- [สร้างเรขาคณิต MultiLineString ด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}