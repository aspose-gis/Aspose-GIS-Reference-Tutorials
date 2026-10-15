---
date: 2026-10-15
description: สร้างความกว้างของแอตทริบิวต์ shapefile ด้วย Aspose.GIS สำหรับ .NET –
  คู่มือขั้นตอนโดยละเอียดแสดงวิธีตั้งค่าความกว้างของฟิลด์, กำหนดความยาวของแอตทริบิวต์,
  และเพิ่มแอตทริบิวต์อย่างมีประสิทธิภาพ
keywords:
- create shapefile attribute width
- set field width shapefile
- Aspose.GIS attribute width
- vector layer example
- define attribute length
lastmod: 2026-10-15
linktitle: วิธีตั้งค่าความกว้างของฟิลด์
og_description: สร้างความกว้างของแอตทริบิวต์ shapefile ด้วย Aspose.GIS สำหรับ .NET.
  เรียนรู้วิธีตั้งค่าความกว้างของฟิลด์, กำหนดความยาวของแอตทริบิวต์, และทำให้ข้อมูล
  GIS ของคุณสอดคล้องกัน
og_image_alt: Guide showing how to create shapefile attribute width using Aspose.GIS
  for .NET
og_title: สร้างความกว้างของแอตทริบิวต์ shapefile ด้วย Aspose.GIS สำหรับ .NET
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create shapefile attribute width with Aspose.GIS for .NET – step‑by‑step
    guide showing how to set field width, define attribute length, and add attributes
    efficiently.
  headline: Create shapefile attribute width using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: You can acquire a temporary license [temporary license](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for peer‑to‑peer
      help and official responses.
    question: Where can I find community support for Aspose.GIS for .NET?
  - answer: Yes, explore the [free trial](https://releases.aspose.com/) to experience
      the full feature set without cost.
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Purchase your license [purchase a license](https://purchase.aspose.com/buy).
    question: How do I purchase a license for Aspose.GIS for .NET?
  - answer: Refer to the [documentation](https://reference.aspose.com/gis/net/) for
      comprehensive API details.
    question: Where can I access the documentation for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- shapefile
- Aspose.GIS
- .NET GIS
- attribute width
- vector layer
- author: Aspose
  dateModified: '2026-10-15'
  description: Create shapefile attribute width with Aspose.GIS for .NET – step‑by‑step
    guide showing how to set field width, define attribute length, and add attributes
    efficiently.
  headline: Create shapefile attribute width using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: You can acquire a temporary license [temporary license](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for peer‑to‑peer
      help and official responses.
    question: Where can I find community support for Aspose.GIS for .NET?
  - answer: Yes, explore the [free trial](https://releases.aspose.com/) to experience
      the full feature set without cost.
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Purchase your license [purchase a license](https://purchase.aspose.com/buy).
    question: How do I purchase a license for Aspose.GIS for .NET?
  - answer: Refer to the [documentation](https://reference.aspose.com/gis/net/) for
      comprehensive API details.
    question: Where can I access the documentation for Aspose.GIS for .NET?
  type: FAQPage
title: สร้างความกว้างของแอตทริบิวต์ shapefile ด้วย Aspose.GIS สำหรับ .NET
url: /th/net/layer-data-operations/specify-attribute-value-length/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างความกว้างของแอตทริบิวต์ shapefile ด้วย Aspose.GIS สำหรับ .NET

ในตัวอย่างเลเยอร์เวกเตอร์นี้คุณจะได้เรียนรู้วิธี **สร้างความกว้างของแอตทริบิวต์ shapefile** เมื่อสร้าง Shapefile ด้วย Aspose.GIS สำหรับ .NET การควบคุมความยาวของแอตทริบิวต์เป็นสิ่งสำคัญสำหรับความสมบูรณ์ของข้อมูล โดยเฉพาะเมื่อแชร์ไฟล์กับเครื่องมือ GIS อื่นที่คาดหวังคอลัมน์ DBF ขนาดคงที่

## คำตอบอย่างรวดเร็ว
- **วัตถุประสงค์หลักของคู่มือนี้คืออะไร?** เพื่อแสดงวิธีตั้งค่าความกว้างของฟิลด์สำหรับแอตทริบิวต์ใน shapefile โดยใช้ Aspose.GIS สำหรับ .NET.  
- **คลาสใดกำหนดความกว้างของฟิลด์?** `FeatureAttribute.Width`.  
- **ฉันต้องมีใบอนุญาตเพื่อรันโค้ดหรือไม่?** ใบอนุญาตชั่วคราวใช้ได้สำหรับการประเมิน; จำเป็นต้องมีใบอนุญาตเต็มสำหรับการใช้งานจริง.  
- **รูปแบบไฟล์ที่ใช้ในตัวอย่างคืออะไร?** ESRI Shapefile (`.shp`).  
- **ฉันสามารถเปลี่ยนความกว้างหลังจากสร้างเลเยอร์ได้หรือไม่?** ไม่ – ความกว้างต้องกำหนดก่อนเพิ่มฟีเจอร์.

## ความกว้างของฟิลด์คืออะไรและทำไมจึงสำคัญ?
ความกว้างของฟิลด์คือจำนวนอักขระสูงสุดที่คอลัมน์สตริงสามารถเก็บได้ในส่วน DBF ของ Shapefile การตั้งค่าอย่างถูกต้องช่วยป้องกันการตัดข้อความโดยไม่มีการแจ้งเตือน, รับประกันว่าแอปพลิเคชัน GIS อื่นจะอ่านข้อมูลได้ตรงตามที่คุณป้อน, และทำให้ขนาดไฟล์คาดเดาได้—แต่ละอักขระเพิ่มหนึ่งไบต์ต่อเรคคอร์ด

ความกว้างของฟิลด์ (หรือที่เรียกว่าความยาวของแอตทริบิวต์) คือจำนวนอักขระสูงสุดที่ฟิลด์สตริงสามารถเก็บได้ในส่วน DBF ของ Shapefile การตั้งค่าความกว้างที่ถูกต้องช่วยป้องกันการตัดข้อความโดยไม่มีการแจ้งเตือน, รับประกันว่าแอปพลิเคชัน GIS อื่นจะอ่านข้อมูลได้ตรงตามที่คุณป้อน, และทำให้ขนาดไฟล์คาดเดาได้—แต่ละอักขระเพิ่มหนึ่งไบต์ต่อเรคคอร์ด

## ทำไมต้องใช้ตัวอย่างเลเยอร์เวกเตอร์ที่กำหนดความกว้าง?
การกำหนดความกว้างล่วงหน้าช่วยขจัดการจัดสรรค่าเริ่มต้น 255 ตัวอักษร, ซึ่งอาจเพิ่มขนาดเป็น 255 × จำนวนเรคคอร์ดไบต์ สำหรับชุดข้อมูลที่มี 10 000 เรคคอร์ด พื้นที่เพิ่มนี้จะอยู่ประมาณ **2.5 MB**—เป็นภาระที่สังเกตได้สำหรับโครงการขนาดใหญ่ การใช้ความกว้างที่แม่นยำยังช่วยให้เข้ากันได้กับเครื่องมือ GIS รุ่นเก่าที่บังคับใช้สคีม่า DBF อย่างเคร่งครัด

การใช้ความกว้างที่แม่นยำยังช่วยให้เข้ากันได้กับเครื่องมือ GIS รุ่นเก่าที่บังคับใช้สคีม่า DBF อย่างเคร่งครัด สำหรับชุดข้อมูลที่มี 10 000 เรคคอร์ด การจัดสรรค่าเริ่มต้น 255 ตัวอักษรจะเพิ่มข้อมูลที่ไม่จำเป็นประมาณ 2.5 MB, ในขณะที่ฟิลด์ 50 ตัวอักษรจะประหยัดประมาณ 2 MB

## วิธีตั้งค่าความกว้างของฟิลด์สำหรับแอตทริบิวต์?
โหลดหรือสร้าง `VectorLayer` ที่ชี้ไปยังไฟล์ `.shp` เป้าหมาย, ประกาศแอตทริบิวต์สตริงชื่อ **wide** ด้วย `Width = 120`, จากนั้นเพิ่มฟีเจอร์ที่ค่าของมันอยู่ภายในขีดจำกัด 120 ตัวอักษร Aspose.GIS จะตัดสตริงที่ยาวเกินไปโดยอัตโนมัติตามความกว้างที่กำหนด, รักษาความสอดคล้องของข้อมูลโดยไม่เกิดข้อยกเว้น

### นำเข้าเนมสเปซ
`FeatureAttribute`, `VectorLayer`, และประเภทที่เกี่ยวข้องเป็นส่วนหนึ่งของไลบรารี Aspose.GIS นำเข้าพวกมันที่ส่วนหัวของไฟล์ของคุณ:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### สร้าง VectorLayer
คลาส `VectorLayer` แสดงถึงแหล่งข้อมูลเวกเตอร์ (เช่น Shapefile) เป็นคอนเทนเนอร์ที่เก็บฟีเจอร์และแอตทริบิวต์ของพวกมัน

```csharp
string dataDir = "Your Document Directory";
using (VectorLayer layer = VectorLayer.Create(dataDir + "SpecifyAttributeValueLength_out.shp", Drivers.Shapefile))
{
    // Your code for the next steps will go here.
}
```

### เพิ่มแอตทริบิวต์ด้วยความยาวที่กำหนด
อ็อบเจกต์ `FeatureAttribute` อธิบายคอลัมน์ในตารางแอตทริบิวต์; การตั้งค่า `Width = 120` บอกให้ตัวเขียน Shapefile จัดสรร 120 ไบต์อย่างแม่นยำสำหรับแต่ละเรคคอร์ดของฟิลด์นี้

```csharp
FeatureAttribute attribute = new FeatureAttribute("wide", AttributeDataType.String);
attribute.Width = 120;
layer.Attributes.Add(attribute);
```

> **Pro tip:** คุณสมบัติ `Width` ใช้ได้เฉพาะกับแอตทริบิวต์สตริงเท่านั้น ฟิลด์ประเภทตัวเลข, วันที่ หรือ Boolean จะละเว้น `Width` เนื่องจากขนาดของพวกมันถูกกำหนดโดยประเภทข้อมูล

### สร้างและเพิ่มฟีเจอร์
คลาส `Feature` รวมเรขาคณิตและค่าของแอตทริบิวต์; หลังจากตั้งค่าแอตทริบิวต์แล้ว, การเรียก `layer.Add(feature)` จะเขียนเรคคอร์ดลงใน Shapefile

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("wide", "this string can be up to 120 characters long now.");
layer.Add(feature);
```

หากคุณพยายามกำหนดสตริงที่ยาวเกินไป, Aspose.GIS จะตัดสตริงนั้นให้ตรงกับความกว้างที่กำหนด, รักษาความสมบูรณ์ของข้อมูล

## ปัญหาที่พบบ่อยและการแก้ไขปัญหา
- **ลืมตั้งค่า `Width` ก่อนเพิ่มแอตทริบิวต์?** ความกว้างเริ่มต้นคือ 255 ตัวอักษร; การเปลี่ยนแปลงภายหลังจะไม่ส่งผลต่อฟิลด์ที่สร้างแล้ว. ควรกำหนดความกว้างก่อนเสมอ.  
- **ใช้ประเภทข้อมูลที่ไม่ใช่สตริง?** `Width` จะถูกละเว้นสำหรับฟิลด์ตัวเลขหรือวันที่; ตรวจสอบให้แน่ใจว่า `AttributeDataType` ของแอตทริบิวต์เป็น `String`.  
- **ข้อผิดพลาด “Field not found”?** ชื่อแอตทริบิวต์แยกแยะตามตัวพิมพ์ใหญ่‑เล็ก. ตรวจสอบให้แน่ใจว่าชื่อที่ใช้ใน `SetValue` ตรงกับชื่อที่กำหนดในสคีม่า.  
- **ขนาดไฟล์เพิ่มโดยไม่คาดคิด?** ความกว้างที่ใหญ่ขึ้นจะเพิ่มขนาดไฟล์ `.dbf` อย่างเชิงเส้น. สำหรับ 10 000 เรคคอร์ด, การเพิ่มความกว้างจาก 50 ไปเป็น 120 จะเพิ่มประมาณ 700 KB.

## คำถามที่พบบ่อย
**Q: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS สำหรับ .NET ได้อย่างไร?**  
A: คุณสามารถรับใบอนุญาตชั่วคราวได้จาก [temporary license](https://purchase.aspose.com/temporary-license/).

**Q: ฉันจะหาชุมชนสนับสนุนสำหรับ Aspose.GIS สำหรับ .NET ได้ที่ไหน?**  
A: เยี่ยมชม [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อรับความช่วยเหลือจากผู้ใช้และการตอบจากทีมอย่างเป็นทางการ.

**Q: มีการทดลองใช้ฟรีสำหรับ Aspose.GIS สำหรับ .NET หรือไม่?**  
A: มี, สำรวจ [free trial](https://releases.aspose.com/) เพื่อทดลองคุณสมบัติทั้งหมดโดยไม่มีค่าใช้จ่าย.

**Q: ฉันจะซื้อใบอนุญาตสำหรับ Aspose.GIS สำหรับ .NET ได้อย่างไร?**  
A: ซื้อใบอนุญาตของคุณได้จาก [purchase a license](https://purchase.aspose.com/buy).

**Q: ฉันจะเข้าถึงเอกสารสำหรับ Aspose.GIS สำหรับ .NET ได้จากที่ไหน?**  
A: ดูรายละเอียด API อย่างครบถ้วนได้ที่ [documentation](https://reference.aspose.com/gis/net/).

**Q: ฉันสามารถเปลี่ยนความกว้างของฟิลด์หลังจากสร้างเลเยอร์ได้หรือไม่?**  
A: ไม่. ความกว้างของฟิลด์ต้องกำหนดก่อนเพิ่มแอตทริบิวต์; หากต้องการเปลี่ยนต้องสร้างเลเยอร์ใหม่พร้อมสคีม่าใหม่.

**Q: การตั้งค่าความกว้างที่ใหญ่ขึ้นส่งผลต่อขนาดไฟล์หรือไม่?**  
A: Shapefile เก็บฟิลด์สตริงด้วยความยาวคงที่, ดังนั้นการเพิ่มความกว้างจะทำให้ขนาดไฟล์ `.dbf` เพิ่มขึ้นตามจำนวนเรคคอร์ดโดยตรง.

## สรุป
ตัวอย่างเลเยอร์เวกเตอร์นี้ได้สาธิตวิธี **สร้างความกว้างของแอตทริบิวต์ shapefile** สำหรับแอตทริบิวต์ใน Shapefile ด้วย Aspose.GIS สำหรับ .NET, และแสดงวิธีเพิ่มแอตทริบิวต์ด้วยความยาวที่กำหนดอย่างมีประสิทธิภาพ โดยการควบคุมความกว้างของแอตทริบิวต์คุณจะหลีกเลี่ยงการตัดข้อมูล, ทำให้ขนาดไฟล์เหมาะสม, และรับประกันการทำงานร่วมกันอย่างราบรื่นกับแพลตฟอร์ม GIS อื่น ๆ ทดลองใช้ความกว้างต่าง ๆ, สำรวจ [documentation](https://reference.aspose.com/gis/net/), และเปิดศักยภาพเต็มที่ของการพัฒนาทางภูมิสารสนเทศด้วย Aspose.GIS.

---

**Last Updated:** 2026-10-15  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  
Download the latest Aspose.GIS for .NET from the [download link](https://releases.aspose.com/gis/net/).

## บทเรียนที่เกี่ยวข้อง

- [รับแอตทริบิวต์ของเลเยอร์ – ดึงข้อมูลแอตทริบิวต์ของเลเยอร์ด้วย Aspose.GIS สำหรับ .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [วิธีรับค่าแอตทริบิวต์ (ค่าเริ่มต้น) ด้วย Aspose.GIS สำหรับ .NET](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [สร้าง Vector Layer ใน File GDB – บทเรียน Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}