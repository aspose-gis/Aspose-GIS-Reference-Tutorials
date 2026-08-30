---
date: 2026-08-18
description: เรียนรู้วิธีเพิ่มจุดลงใน linestring และแปลง geometry ให้เป็นรูปแบบที่แก้ไขได้อย่างง่ายดายด้วย
  Aspose.GIS สำหรับ .NET ทำตามบทแนะนำขั้นตอนต่อขั้นตอนนี้
keywords:
- add point to linestring
- add vertex to path
- Aspose.GIS editable geometry
lastmod: 2026-08-18
linktitle: แปลง Geometry เป็นแบบที่แก้ไขได้
og_description: เพิ่มจุดลงใน linestring และแปลง geometry ให้เป็นรูปแบบที่แก้ไขได้ด้วย
  Aspose.GIS สำหรับ .NET คู่มือนี้แสดงขั้นตอนการทำงานทั้งหมดภายในไม่กี่นาที
og_image_alt: Screenshot of Aspose.GIS code editing a LineString geometry in a .NET
  console app
og_title: เพิ่มจุดลงใน linestring – แปลง geometry เป็นรูปแบบที่แก้ไขได้ด้วย Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add point to linestring and convert geometry to an editable
    format effortlessly using Aspose.GIS for .NET. Follow this step‑by‑step tutorial.
  headline: How to add point to linestring and convert geometry to editable format
    with Aspose.GIS
  type: TechArticle
- description: Learn how to add point to linestring and convert geometry to an editable
    format effortlessly using Aspose.GIS for .NET. Follow this step‑by‑step tutorial.
  name: How to add point to linestring and convert geometry to editable format with
    Aspose.GIS
  steps:
  - name: Define a read‑only geometry
    text: First, create a read‑only geometry object that represents a simple line.
      This object cannot be modified directly. **Definition:** A read‑only geometry
      is an immutable object that represents spatial data without allowing modifications.
  - name: Obtain an editable copy
    text: To edit the geometry, obtain an editable version using the `ToEditable()`
      method. This creates a mutable copy while leaving the original untouched. **Definition:**
      The `ToEditable()` method creates a mutable copy of a geometry, enabling changes
      while preserving the original.
  - name: Add point to LineString
    text: Now that you have an editable copy, you can **add point to linestring**.
      The `AddPoint` method appends a new vertex at the specified coordinates. **Definition:**
      The `AddPoint()` method appends a new coordinate to a `LineString` or inserts
      it at a specific index when you provide an index argument.
  - name: Output edited geometry
    text: Print the edited geometry to verify that the new point was added successfully.
  - name: Verify original geometry remains unchanged
    text: It’s good practice to confirm that the original read‑only geometry has not
      been altered.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS integrates smoothly with popular .NET GIS libraries such
      as NetTopologySuite and SharpMap.
    question: Is Aspose.GIS compatible with other .NET libraries?
  - answer: Certainly! You can obtain a free trial from the [releases page](https://releases.aspose.com/)
      to explore its features.
    question: Can I try Aspose.GIS before purchasing?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      assistance and official support.
    question: How can I get support for Aspose.GIS?
  - answer: Yes, a temporary license can be requested via the [Aspose.GIS purchase
      page](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for evaluation?
  - answer: Absolutely! Use the [purchase page](https://purchase.aspose.com/buy) to
      acquire a license that fits your needs.
    question: Can I purchase Aspose.GIS directly?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- GIS editing
- Aspose.GIS
- .NET geometry manipulation
title: วิธีเพิ่มจุดลงใน linestring และแปลง geometry เป็นรูปแบบที่แก้ไขได้ด้วย Aspose.GIS
url: /th/net/geometry-creation/convert-geometry-to-editable/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มจุดลงใน LineString และแปลงเรขาคณิตเป็นรูปแบบที่แก้ไขได้ด้วย Aspose.GIS

## บทนำ
เมื่อคุณทำงานกับข้อมูลเชิงพื้นที่, **add point to linestring** เป็นการดำเนินการที่พบบ่อย—ไม่ว่าจะเป็นการแก้ไขเส้นทาง, ขยายเส้นทาง, หรือสร้างเรขาคณิตแบบไดนามิก Aspose.GIS สำหรับ .NET ทำให้ภารกิจนี้ง่ายดายโดยให้ API ที่สะอาดตาซึ่งช่วยให้คุณแปลงเรขาคณิตแบบอ่านอย่างเดียวให้เป็นแบบที่แก้ไขได้, เพิ่มจุดยอดใหม่, และรักษาเรขาคณิตต้นฉบับให้ปลอดภัยจากการเปลี่ยนแปลงโดยไม่ได้ตั้งใจ ในบทเรียนนี้คุณจะได้เห็นวิธีเพิ่มจุดลงใน `LineString`, รับสำเนาที่แก้ไขได้, และตรวจสอบว่าเรขาคณิตต้นฉบับยังคงไม่ถูกเปลี่ยนแปลง

## คำตอบอย่างรวดเร็ว
- **“add point to linestring” หมายถึงอะไร?** หมายถึงการแทรกพิกัดใหม่เข้าไปในเรขาคณิต `LineString` ที่มีอยู่แล้ว.  
- **ไลบรารีใดสนับสนุนสิ่งนี้?** Aspose.GIS สำหรับ .NET มีเมธอด `ToEditable()` และฟังก์ชัน `AddPoint()` ให้ใช้งาน.  
- **ฉันต้องใช้ใบอนุญาตสำหรับฟีเจอร์นี้หรือไม่?** การทดลองใช้ฟรีทำงานได้สำหรับการพัฒนา; จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานจริง.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **การดำเนินการใช้เวลานานเท่าไหร่?** โดยทั่วไปใช้เวลาน้อยกว่า 10 นาทีสำหรับสถานการณ์พื้นฐาน.

## “add point to linestring” คืออะไร?
`LineString` เป็นประเภทเรขาคณิตที่แสดงชุดของจุดที่เชื่อมต่อกันเป็นเส้น.  
การเพิ่มจุดลงใน `LineString` จะใส่เวอร์เท็กซ์ใหม่ที่พิกัดที่ระบุ, ขยายเส้นหรือสร้างเส้นทางที่ละเอียดมากขึ้น การดำเนินการนี้สำคัญสำหรับงานเช่นการแก้ไขเส้นทาง, การแก้ไขแผนที่, หรือการสร้างเรขาคณิตแบบไดนามิก, และช่วยให้คุณเพิ่มคุณค่าข้อมูลเชิงพื้นที่โดยไม่ต้องสร้างฟีเจอร์ใหม่ทั้งหมด

## ทำไมต้องใช้ Aspose.GIS สำหรับงานนี้?
Aspose.GIS ถูกออกแบบมาสำหรับนักพัฒนาที่ต้องการไลบรารีที่เชื่อถือได้, ไม่มีการพึ่งพาอื่นใด, ทำงานได้บน .NET runtime หลักทั้งหมด มันทำให้เรขาคณิตต้นฉบับเป็นแบบไม่เปลี่ยนแปลง, ป้องกันการแก้ไขโดยไม่ได้ตั้งใจ, พร้อมกับให้เมธอดที่เรียบง่ายและเชื่อมต่อกันเช่น `ToEditable()` และ `AddPoint()` ที่ทำให้การแก้ไขง่ายดาย API ยังรองรับรูปแบบ GIS มากกว่า 50 รูปแบบและสามารถจัดการชุดข้อมูลขนาดใหญ่ได้อย่างมีประสิทธิภาพโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ
- **ไม่มีการพึ่งพาภายนอก** – API จัดการการแปลงเรขาคณิตภายใน  
- **ความปลอดภัยแบบอ่าน‑อย่างเดียว** – เรขาคณิตต้นฉบับยังคงเป็นแบบไม่เปลี่ยนแปลง, ป้องกันการแก้ไขโดยไม่ได้ตั้งใจ  
- **ไวยากรณ์ที่เข้าใจง่าย** – เมธอดเช่น `ToEditable()` และ `AddPoint()` เป็นธรรมชาติสำหรับนักพัฒนา C#  
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS .NET runtimes  
- **รองรับรูปแบบการนำเข้าและส่งออกกว่า 50 รูปแบบ** และสามารถประมวลผลเรขาคณิตหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ

## เมื่อใดที่คุณต้องการเพิ่มจุดลงใน LineString?
การเพิ่มเวอร์เท็กซ์ลงในเส้นที่มีอยู่เป็นประโยชน์เมื่อใดก็ตามที่ข้อมูลพื้นฐานต้องการการปรับปรุงหรือขยาย มันช่วยให้คุณแก้ไขความไม่แม่นยำ, รวมโครงสร้างพื้นฐานใหม่, หรือเพิ่มระดับความละเอียดสำหรับการวิเคราะห์ สถานการณ์ทั่วไปรวมถึงการอัปเดตเครือข่ายถนนหลังการก่อสร้าง, การแก้ไขจุดทางที่หายไปในรอย GPS, การสร้างเส้นทางที่ผู้ใช้วาดเอง, และการเตรียมชุดข้อมูลที่ต้องมีจำนวนเวอร์เท็กซ์ขั้นต่ำสำหรับอัลกอริทึมเชิงพื้นที่

## ข้อกำหนดเบื้องต้น
- **.NET environment** – ติดตั้ง .NET framework จาก [website](https://dotnet.microsoft.com/download).  
- **Aspose.GIS library** – ดาวน์โหลดแพคเกจล่าสุดจาก [releases page](https://releases.aspose.com/gis/net/).  
- **C# basics** – มีความคุ้นเคยกับไวยากรณ์ C# และแอปพลิเคชันคอนโซล

### นำเข้า namespace
เพื่อเริ่มกระบวนการ, ตรวจสอบให้แน่ใจว่าได้นำเข้า namespace ที่จำเป็นเข้าสู่โค้ด C# ของคุณ ซึ่งจะทำให้คุณเข้าถึงฟังก์ชันที่ Aspose.GIS สำหรับ .NET ให้มา

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

ต่อไปนี้เราจะเดินผ่านขั้นตอนที่เป็นรูปธรรมสำหรับการแปลงเรขาคณิตเป็นรูปแบบที่แก้ไขได้และการเพิ่มจุดลงใน `LineString`.

## วิธีเพิ่มจุดลงใน LineString ด้วย Aspose.GIS
`ToEditable()` สร้างสำเนาที่สามารถแก้ไขได้ของเรขาคณิต, ทำให้สามารถแก้ไขได้ `AddPoint()` แทรกเวอร์เท็กซ์ใหม่ลงใน `LineString` โหลดเรขาคณิตแบบอ่าน‑อย่างเดียวของคุณ, เรียก `ToEditable()` เพื่อรับสำเนาที่แก้ไขได้, แล้วใช้ `AddPoint()` เพื่อแทรกพิกัดใหม่ กระบวนการสี่ขั้นตอนนี้ทำให้คุณแก้ไขได้อย่างปลอดภัยและตรวจสอบผลลัพธ์ได้ทันที

### ขั้นตอนที่ 1: กำหนดเรขาคณิตแบบอ่าน‑อย่างเดียว
แรกเริ่ม, สร้างอ็อบเจ็กต์เรขาคณิตแบบอ่าน‑อย่างเดียวที่แสดงเส้นง่าย ๆ อ็อบเจ็กต์นี้ไม่สามารถแก้ไขโดยตรงได้  
**Definition:** เรขาคณิตแบบอ่าน‑อย่างเดียวคืออ็อบเจ็กต์ที่ไม่เปลี่ยนแปลงซึ่งแสดงข้อมูลเชิงพื้นที่โดยไม่อนุญาตให้แก้ไข

```csharp
ILineString readOnlyLine = (ILineString)Geometry.FromText("LINESTRING (1 1, 2 2)");
```

### ขั้นตอนที่ 2: รับสำเนาที่แก้ไขได้
เพื่อแก้ไขเรขาคณิต, รับเวอร์ชันที่แก้ไขได้โดยใช้เมธอด `ToEditable()` ซึ่งสร้างสำเนาที่สามารถแก้ไขได้ในขณะที่ทำให้ต้นฉบับไม่ถูกเปลี่ยนแปลง  
**Definition:** เมธอด `ToEditable()` สร้างสำเนาที่สามารถแก้ไขได้ของเรขาคณิต, ทำให้สามารถเปลี่ยนแปลงได้ขณะยังคงรักษาต้นฉบับไว้

```csharp
LineString editableLine = readOnlyLine.ToEditable();
```

### ขั้นตอนที่ 3: เพิ่มจุดลงใน LineString
เมื่อคุณมีสำเนาที่แก้ไขได้แล้ว, คุณสามารถ **add point to linestring** ได้ เมธอด `AddPoint` เพิ่มเวอร์เท็กซ์ใหม่ที่พิกัดที่ระบุ  
**Definition:** เมธอด `AddPoint()` เพิ่มพิกัดใหม่ลงใน `LineString` หรือแทรกที่ตำแหน่งเฉพาะเมื่อคุณระบุอาร์กิวเมนต์ดัชนี

```csharp
editableLine.AddPoint(3, 3);
```

### ขั้นตอนที่ 4: แสดงผลเรขาคณิตที่แก้ไขแล้ว
พิมพ์เรขาคณิตที่แก้ไขเพื่อยืนยันว่าจุดใหม่ถูกเพิ่มสำเร็จ

```csharp
Console.WriteLine(editableLine.AsText()); // LINESTRING (1 1, 2 2, 3 3)
```

### ขั้นตอนที่ 5: ตรวจสอบว่าเรขาคณิตต้นฉบับยังคงไม่เปลี่ยนแปลง
เป็นแนวปฏิบัติที่ดีในการยืนยันว่าเรขาคณิตแบบอ่าน‑อย่างเดียวต้นฉบับไม่ได้ถูกเปลี่ยนแปลง

```csharp
Console.WriteLine(readOnlyLine.AsText()); // LINESTRING (1 1, 2 2)
```

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ห้ามแก้ไขอ็อบเจ็กต์แบบอ่าน‑อย่างเดียว** – ต้องเรียก `ToEditable()` ก่อนเสมอ  
- **ลำดับพิกัดสำคัญ** – ตรวจสอบว่าคุณส่ง (X, Y) ตามลำดับที่ถูกต้อง  
- **เรขาคณิตขนาดใหญ่** – สำหรับอ็อบเจ็กต์ `LineString` ที่ยาวมาก, พิจารณาแก้ไขเป็นชุดเพื่อปรับปรุงประสิทธิภาพ  
- **ความปลอดภัยของเธรด** – เรขาคณิตที่แก้ไขได้ไม่ปลอดภัยต่อการทำงานหลายเธรด; แก้ไขบนเธรดเดียวหรือใช้การซิงโครไนซ์ที่เหมาะสม

## คำถามที่พบบ่อย

**Q: Aspose.GIS เข้ากันได้กับไลบรารี .NET อื่นหรือไม่?**  
A: ใช่, Aspose.GIS ผสานรวมอย่างราบรื่นกับไลบรารี GIS .NET ยอดนิยมเช่น NetTopologySuite และ SharpMap.

**Q: ฉันสามารถทดลองใช้ Aspose.GIS ก่อนซื้อได้หรือไม่?**  
A: แน่นอน! คุณสามารถรับการทดลองใช้ฟรีจาก [releases page](https://releases.aspose.com/) เพื่อสำรวจคุณสมบัติต่าง ๆ

**Q: ฉันจะรับการสนับสนุนสำหรับ Aspose.GIS อย่างไร?**  
A: เยี่ยมชม [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อรับความช่วยเหลือจากชุมชนและการสนับสนุนอย่างเป็นทางการ

**Q: มีใบอนุญาตชั่วคราวสำหรับการประเมินหรือไม่?**  
A: ใช่, สามารถขอใบอนุญาตชั่วคราวได้ผ่าน [Aspose.GIS purchase page](https://purchase.aspose.com/temporary-license/)

**Q: ฉันสามารถซื้อ Aspose.GIS โดยตรงได้หรือไม่?**  
A: แน่นอน! ใช้ [purchase page](https://purchase.aspose.com/buy) เพื่อซื้อใบอนุญาตที่ตรงกับความต้องการของคุณ

### คำถามที่พบบ่อยเพิ่มเติม
**Q: จะเกิดอะไรขึ้นหากฉันพยายามเพิ่มจุดลงในเรขาคณิตแบบอ่าน‑อย่างเดียวโดยไม่เรียก `ToEditable()`?**  
A: `InvalidOperationException` จะถูกโยนขึ้นเนื่องจากเรขาคณิตเป็นแบบไม่เปลี่ยนแปลง

**Q: ฉันสามารถแทรกจุดที่ตำแหน่งเฉพาะแทนการเพิ่มที่ท้ายได้หรือไม่?**  
A: ได้, ใช้ overload `AddPoint(int index, double x, double y)` เพื่อแทรกที่ดัชนีที่กำหนด

**Q: `ToEditable()` สร้างสำเนาลึกของเรขาคณิตหรือไม่?**  
A: มันสร้างสำเนาที่สามารถแก้ไขได้ซึ่งใช้ข้อมูลพิกัดเดียวกัน; การเปลี่ยนแปลงในสำเนาที่แก้ไขไม่ได้ส่งผลต่อต้นฉบับ

## สรุป
ตอนนี้คุณรู้วิธี **add point to linestring** และแปลงเรขาคณิตแบบอ่าน‑อย่างเดียวให้เป็นรูปแบบที่แก้ไขได้โดยใช้ Aspose.GIS สำหรับ .NET วิธีนี้ทำให้ข้อมูลต้นฉบับของคุณปลอดภัยในขณะที่ให้การควบคุมเต็มที่ต่อการจัดการเรขาคณิต—เหมาะสำหรับการแก้ไขเส้นทาง, การแก้ไขแผนที่, หรือสถานการณ์ใด ๆ ที่ต้องการการอัปเดตเรขาคณิตแบบไดนามิก สำรวจต่อไปโดยเชื่อมต่อหลายการเรียก `AddPoint`, แทรกจุดที่ดัชนีเฉพาะ, หรือผสานเทคนิคนี้กับการดำเนินการเชิงพื้นที่อื่น ๆ ของ Aspose.GIS

---

**อัปเดตล่าสุด:** 2026-08-18  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [เรียนรู้วิธีสร้างเรขาคณิต LineString ด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [วิธีนับเวอร์เท็กซ์ในเรขาคณิตด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-creation/count-points-in-geometry/)
- [สร้าง Geometry Collection ด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-creation/create-geometry-collection/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}