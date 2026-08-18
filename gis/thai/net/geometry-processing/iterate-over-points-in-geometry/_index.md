---
date: 2026-06-10
description: เรียนรู้วิธีเพิ่มจุดและเพิ่มพิกัดให้กับรูปทรงขณะวนซ้ำกับ geometry โดยใช้
  Aspose.GIS for .NET ซึ่งเป็นชุดเครื่องมือ GIS ที่ทรงพลังสำหรับนักพัฒนา .NET
keywords:
- how to add points
- add coordinates to shape
- Aspose.GIS geometry
linktitle: วิธีเพิ่มจุดและทำการวนซ้ำกับ Geometry ใน .NET
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  headline: How to Add Points and Iterate Over Geometry in .NET
  type: TechArticle
- description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  name: How to Add Points and Iterate Over Geometry in .NET
  steps:
  - name: Create a `LineString` object
    text: '`LineString` is Aspose.GIS''s geometry type that represents an ordered
      collection of points forming a polyline.'
  - name: Add points to the `LineString`
    text: The `AddPoint` method inserts a new vertex (longitude, latitude) at the
      end of the line. Call it repeatedly to **add coordinates to shape** objects.
  - name: Iterate over the points
    text: '`LineString` implements `IEnumerable<IPoint>`, allowing you to loop through
      each point with a `foreach` statement. This makes extracting X (longitude) and
      Y (latitude) values trivial. The loop prints each point’s X (longitude) and
      Y (latitude) values to the console, allowing you to verify that the p'
  type: HowTo
- questions:
  - answer: '`LineString`'
    question: What is the primary class for point collections?
  - answer: Use `AddPoint(longitude, latitude)`
    question: How do you add a point?
  - answer: Yes, `LineString` implements `IEnumerable<IPoint>`
    question: Can you iterate with a foreach loop?
  - answer: .NET 6+ (or .NET Core 3.1/Framework 4.6+) and Aspose.GIS for .NET library
    question: Prerequisites?
  - answer: Building routes, visualizing tracks, or preprocessing data for spatial
      analysis
    question: Typical use case?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: วิธีเพิ่มจุดและทำการวนซ้ำกับ Geometry ใน .NET
url: /th/net/geometry-processing/iterate-over-points-in-geometry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มจุดและวนซ้ำผ่าน Geometry ใน .NET

## บทนำ

หากคุณกำลังทำงานกับข้อมูล GIS ในสภาพแวดล้อม .NET หนึ่งในสิ่งแรกที่คุณต้องรู้คือ **วิธีเพิ่มจุด** ลงใน geometry แล้วทำงานกับจุดเหล่านั้น Aspose.GIS for .NET มี API แบบวัตถุ‑เชิงวัตถุที่สะอาดและง่ายต่อการใช้งาน ในบทเรียนนี้เราจะสร้าง `LineString` เพิ่มจุดลงไป และวนซ้ำผ่านจุดเหล่านั้นเพื่อดึงพิกัดหรือทำการวิเคราะห์ต่อไป คุณยังจะได้เห็นวิธี **เพิ่มพิกัดลงในวัตถุ shape** อย่างมีประสิทธิภาพ

## คำตอบสั้น
- **คลาสหลักสำหรับคอลเลกชันของจุดคืออะไร?** `LineString`
- **เพิ่มจุดอย่างไร?** ใช้ `AddPoint(longitude, latitude)`
- **สามารถวนซ้ำด้วย foreach loop ได้หรือไม่?** ได้, `LineString` implements `IEnumerable<IPoint>`
- **ข้อกำหนดเบื้องต้น?** .NET 6+ (หรือ .NET Core 3.1/Framework 4.6+) และไลบรารี Aspose.GIS for .NET
- **กรณีการใช้งานทั่วไป?** สร้างเส้นทาง, แสดงแทร็ก, หรือทำการเตรียมข้อมูลสำหรับการวิเคราะห์เชิงพื้นที่  
- **IPoint** แทนจุด geometry หนึ่งจุดที่มีพิกัด X (longitude) และ Y (latitude)

## “การเพิ่มจุด” ใน GIS คืออะไร?

การเพิ่มจุดหมายถึงการใส่คู่พิกัด (longitude, latitude) แต่ละคู่ลงในคอนเทนเนอร์เชิงเรขาคณิต เช่น `LineString`, `Polygon` หรือ `MultiPoint` จุดแต่ละจุดจะกลายเป็นเวอร์เท็กซ์ที่กำหนดรูปทรงหรือเส้นทางที่คุณกำลังสร้าง ทำให้สามารถทำการดำเนินการเชิงพื้นที่และการแสดงผลได้ เวอร์เท็กซ์เหล่านี้สามารถเข้าถึงเพื่อการวิเคราะห์, ส่งออกเป็นฟอร์แมต GIS ต่าง ๆ, หรือใช้ในคำนวณเชิงพื้นที่เช่นการวัดระยะทางหรือการทดสอบการตัดกัน

## ทำไมต้องเพิ่มจุดด้วย Aspose.GIS?

คุณเพิ่มจุดด้วย Aspose.GIS เพราะไลบรารีรับประกัน **การจัดการ geometry แบบ type‑safe**, รองรับ **ฟอร์แมตเวกเตอร์และเรสเตอร์กว่า 30 แบบ**, และสามารถประมวลผล **ชุดข้อมูลหลายร้อยหน้า** ได้โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ API ยังมีการวนซ้ำในตัว, การดำเนินการเชิงพื้นที่, และการแปลงฟอร์แมต (Shapefile, GeoJSON, KML ฯลฯ) บนทุกแพลตฟอร์มที่รองรับ

## ข้อกำหนดเบื้องต้น

- Visual Studio 2022 (หรือ IDE สำหรับ C# ใดก็ได้)  
- ติดตั้งแพ็กเกจ NuGet Aspose.GIS for .NET  
- มีความเข้าใจพื้นฐานเกี่ยวกับไวยากรณ์ C#  

## นำเข้า Namespaces

เริ่มต้นด้วยการนำเข้า namespaces ที่จำเป็นเพื่อให้เข้าถึงฟังก์ชันของ Aspose.GIS ในแอปพลิเคชัน .NET ของคุณ:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## วิธีเพิ่มจุดลงใน Geometry?

คุณเพิ่มจุดโดยการสร้างอินสแตนซ์ของ `LineString`, เรียกเมธอด `AddPoint` สำหรับแต่ละคู่พิกัด, แล้ววนซ้ำคอลเลกชันเมื่อจำเป็น รูปแบบสามขั้นตอนนี้ครอบคลุมการสร้าง, การเติมข้อมูล, และการเดินทางผ่านข้อมูลในแบบที่กระชับและอ่านง่าย **LineString คือประเภท geometry ที่แสดงคอลเลกชันของจุดที่เรียงลำดับกันเป็น polyline** วิธีนี้ทำให้ geometry ยังคงเป็นที่ถูกต้องและพร้อมสำหรับการดำเนินการเชิงพื้นที่ต่อไป เช่นการคำนวณความยาวหรือการส่งออก

### ขั้นตอน 1: สร้างอ็อบเจ็กต์ `LineString`  

`LineString` คือประเภท geometry ของ Aspose.GIS ที่แสดงคอลเลกชันของจุดที่เรียงลำดับกันเป็น polyline

```csharp
LineString line = new LineString();
```

### ขั้นตอน 2: เพิ่มจุดลงใน `LineString`  

เมธอด `AddPoint` จะใส่เวอร์เท็กซ์ใหม่ (longitude, latitude) ที่ท้ายเส้น เรียกใช้ซ้ำเพื่อ **เพิ่มพิกัดลงในวัตถุ shape** ตามต้องการ

```csharp
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```

### ขั้นตอน 3: วนซ้ำผ่านจุด  

`LineString` implements `IEnumerable<IPoint>` ทำให้คุณสามารถวนลูปผ่านแต่ละจุดด้วยคำสั่ง `foreach` ได้ การดึงค่า X (longitude) และ Y (latitude) จึงทำได้อย่างง่ายดาย

```csharp
foreach (IPoint point in line)
{
    Console.WriteLine(point.X + "," + point.Y);
}
```

ลูปนี้จะแสดงค่าพิกัด X (longitude) และ Y (latitude) ของแต่ละจุดบนคอนโซล เพื่อให้คุณตรวจสอบว่าจุดถูกเพิ่มอย่างถูกต้องหรือไม่

## กรณีการใช้งานทั่วไป

- **การวางแผนเส้นทาง** – สร้างเส้นทางจากบันทึก GPS แล้ววิเคราะห์ระยะทางระหว่าง waypoint  
- **การตรวจสอบข้อมูล** – วนซ้ำผ่านจุดเพื่อยืนยันว่าตรงตามขอบเขตที่คาดหวัง (เช่น อยู่ภายในพรมแดนของประเทศ)  
- **การแสดงผล** – ส่งออก `LineString` ไปเป็น GeoJSON หรือ Shapefile เพื่อใช้ในเครื่องมือแผนที่ต่าง ๆ  

## คำถามที่พบบ่อย

**Q1: Aspose.GIS for .NET รองรับรูปทรงเรขาคณิตอื่น ๆ นอกจาก `LineString` หรือไม่?**  
A: ใช่, Aspose.GIS รองรับ `Point`, `Polygon`, `MultiLineString`, `MultiPolygon` และประเภท geometry อื่น ๆ อีกมากมาย

**Q2: Aspose.GIS เหมาะกับโครงการเชิงพาณิชย์และส่วนบุคคลหรือไม่?**  
A: แน่นอน. ตัวเลือกการให้ลิขสิทธิ์ครอบคลุมการใช้งานเชิงพาณิชย์, ส่วนบุคคล, และการศึกษา

**Q3: Aspose.GIS for .NET มีเอกสารที่ครอบคลุมสำหรับผู้เริ่มต้นหรือไม่?**  
A: มี, ผลิตภัณฑ์มาพร้อมกับเอกสารละเอียด, API reference, และตัวอย่างโค้ดหลายสิบชุดเพื่อช่วยให้คุณเริ่มต้นได้อย่างรวดเร็ว

**Q4: ฉันสามารถขยายฟังก์ชันของ Aspose.GIS for .NET ผ่านการพัฒนาที่กำหนดเองได้หรือไม่?**  
A: คุณสามารถสร้าง extension methods หรือห่อหุ้มคลาสของ Aspose.GIS เพื่อให้สอดคล้องกับ workflow เฉพาะของคุณ, ให้คุณควบคุมโซลูชันเชิงพื้นที่ได้เต็มที่

**Q5: มีการสนับสนุนทางเทคนิคสำหรับผู้ใช้ Aspose.GIS หรือไม่?**  
A: มีการสนับสนุนทางเทคนิคผ่านฟอรั่มของ Aspose และระบบ ticketing เพื่อให้คุณได้รับความช่วยเหลืออย่างรวดเร็ว

---

**อัปเดตล่าสุด:** 2026-06-10  
**ทดสอบกับ:** Aspose.GIS for .NET 24.5 (รุ่นล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## บทเรียนที่เกี่ยวข้อง

- [How to Count Points in Geometry with Aspose.GIS for .NET](/gis/net/geometry-creation/count-points-in-geometry/)
- [How to Add Point to LineString and Convert Geometry to Editable Format with Aspose.GIS](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [Create MultiPoint Geometry with Aspose.GIS for .NET](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}