---
date: 2026-05-16
description: ตัวอย่าง Vector layer แสดงวิธีตั้งค่า field width, กำหนด attribute width,
  และเพิ่ม attribute length ใน Aspose.GIS for .NET – คู่มือขั้นตอนเต็มรูปแบบ
keywords:
- vector layer example
- how to set width
- set field width
- define attribute width
- add attribute length
linktitle: วิธีตั้งค่า Field Width
schemas:
- author: Aspose
  dateModified: '2026-05-16'
  description: Vector layer example showing how to set field width, define attribute
    width, and add attribute length in Aspose.GIS for .NET – a complete step‑by‑step
    guide.
  headline: Vector Layer Example – How to Set Field Width in Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for peer‑to‑peer
      help and official responses.
    question: Where can I find community support for Aspose.GIS for .NET?
  - answer: Yes, explore the [free trial](https://releases.aspose.com/) to experience
      the full feature set without cost.
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Purchase your license [here](https://purchase.aspose.com/buy).
    question: How do I purchase a license for Aspose.GIS for .NET?
  - answer: Refer to the [documentation](https://reference.aspose.com/gis/net/) for
      comprehensive API details.
    question: Where can I access the documentation for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: ตัวอย่าง Vector Layer – วิธีตั้งค่า Field Width ใน Aspose.GIS for .NET
url: /th/net/layer-data-operations/specify-attribute-value-length/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตัวอย่างเลเยอร์เวกเตอร์ – วิธีตั้งความกว้างของฟิลด์ใน Aspose.GIS สำหรับ .NET

ใน **ตัวอย่างเลเยอร์เวกเตอร์** นี้ คุณจะได้เรียนรู้วิธีตั้งความกว้างของฟิลด์สำหรับแอตทริบิวต์เมื่อสร้าง Shapefile ด้วย Aspose.GIS สำหรับ .NET เราจะเดินผ่านทุกขั้นตอน ตั้งแต่การนำเข้าเนมสเปซจนถึงการเพิ่มฟีเจอร์ และอธิบายว่าทำไมการควบคุมความยาวของแอตทริบิวต์จึงสำคัญต่อความสมบูรณ์ของข้อมูลและการทำงานร่วมกับเครื่องมือ GIS อื่น ๆ

## คำตอบอย่างรวดเร็ว
- **What is the primary purpose of this guide?** เพื่อแสดงวิธีตั้งความกว้างของฟิลด์สำหรับแอตทริบิวต์ใน shapefile ด้วย Aspose.GIS สำหรับ .NET.  
- **Which class defines the field width?** `FeatureAttribute.Width`.  
- **Do I need a license to run the code?** ใบอนุญาตชั่วคราวใช้ได้สำหรับการประเมิน; จำเป็นต้องมีใบอนุญาตเต็มสำหรับการใช้งานจริง.  
- **What file format is used in the example?** ESRI Shapefile (`.shp`).  
- **Can I change the width after the layer is created?** ไม่ – ความกว้างต้องกำหนดก่อนเพิ่มฟีเจอร์.

## ความกว้างของฟิลด์คืออะไรและทำไมจึงสำคัญ?
ความกว้างของฟิลด์ (หรือที่เรียกว่าความยาวของแอตทริบิวต์) คือจำนวนอักขระสูงสุดที่ฟิลด์ประเภทสตริงสามารถเก็บได้ในส่วน DBF ของ Shapefile การตั้งค่าความกว้างที่ถูกต้องช่วยป้องกันการตัดข้อความโดยไม่แจ้งเตือน, รับประกันว่าแอปพลิเคชัน GIS อื่น ๆ จะอ่านข้อมูลได้ตรงตามที่คุณป้อน, และทำให้ขนาดไฟล์คาดเดาได้—แต่ละอักขระเพิ่มหนึ่งไบต์ต่อเรคคอร์ด

## ข้อกำหนดเบื้องต้น
- **Aspose.GIS for .NET Library** – ดาวน์โหลดจาก [ลิงก์ดาวน์โหลด](https://releases.aspose.com/gis/net/).  
- **Development Environment** – Visual Studio 2022, Visual Studio Code, หรือ IDE ใด ๆ ที่รองรับ .NET 6+.  
- **Write Access** – โฟลเดอร์บนดิสก์ที่ไฟล์ shapefile ที่สร้างขึ้นจะถูกบันทึก

## ทำไมต้องใช้ตัวอย่างเลเยอร์เวกเตอร์พร้อมความกว้างที่กำหนด?
Aspose.GIS รองรับ **มากกว่า 30 รูปแบบไฟล์ GIS** รวมถึง Shapefile, GeoJSON, KML, และ GML เมื่อคุณกำหนดความกว้างของฟิลด์อย่างชัดเจน คุณจะหลีกเลี่ยงขีดจำกัดเริ่มต้น 255 ตัวอักษร ซึ่งอาจทำให้ไฟล์ `.dbf` บวมโดยเพิ่มขนาดถึง 255 × จำนวนเรคคอร์ดไบต์ ในชุดข้อมูลขนาดใหญ่ สิ่งนี้แปลเป็นการประหยัดพื้นที่จัดเก็บที่เห็นได้ชัด

## วิธีตั้งความกว้างของฟิลด์สำหรับแอตทริบิวต์?
ในส่วนนี้เราจะโหลดหรือสร้าง `VectorLayer` ที่ชี้ไปยังไฟล์ `.shp` เป้าหมาย, กำหนดแอตทริบิวต์ประเภทสตริงด้วยความกว้างที่แม่นยำ, แล้วเพิ่มฟีเจอร์—ทั้งหมดในไม่กี่บรรทัดสั้น ๆ `VectorLayer` แทนชุดข้อมูลเวกเตอร์เช่น Shapefile และให้การเข้าถึงเรขาคณิตและตารางแอตทริบิวต์ ด้านล่างเป็นสูตรโดยตรงที่คุณสามารถทำตามขั้นตอนได้

โหลดหรือสร้าง `VectorLayer` ที่ชี้ไปยังไฟล์ `.shp` เป้าหมาย, ประกาศแอตทริบิวต์สตริงชื่อ **wide** ด้วย `Width = 120`, แล้วเพิ่มฟีเจอร์ที่ค่าตรงตามขีดจำกัด 120 ตัวอักษร Aspose.GIS จะตัดสตริงที่ยาวเกินให้โดยอัตโนมัติตามความกว้างที่กำหนด, รักษาความสอดคล้องของข้อมูลโดยไม่เกิดข้อยกเว้น

### นำเข้าเนมสเปซ
`FeatureAttribute`, `VectorLayer` และประเภทที่เกี่ยวข้องอยู่ในเนมสเปซ `Aspose.Gis` ให้นำเข้าที่ส่วนหัวของไฟล์ของคุณ:

เนมสเปซ `Aspose.Gis` ให้วัตถุ GIS แกนหลักที่คุณจะทำงานด้วย เช่น `VectorLayer`, `Feature` และ `FeatureAttribute` การนำเข้าช่วยให้คลาสเหล่านี้ใช้ได้โดยไม่ต้องระบุชื่อเต็ม

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### สร้าง VectorLayer
คลาส `VectorLayer` แทนแหล่งข้อมูลเวกเตอร์ (เช่น Shapefile) เป็นคอนเทนเนอร์ที่เก็บฟีเจอร์และแอตทริบิวต์ของพวกมัน

คลาส `VectorLayer` เป็นการแสดงผลของชุดข้อมูลเวกเตอร์ใน Aspose.GIS, จัดการเรขาคณิตและตารางแอตทริบิวต์ในหน่วยความจำ สร้างอินสแตนซ์ที่ชี้ไปยังไฟล์ `.shp` ใหม่หรือที่มีอยู่

```csharp
string dataDir = "Your Document Directory";
using (VectorLayer layer = VectorLayer.Create(dataDir + "SpecifyAttributeValueLength_out.shp", Drivers.Shapefile))
{
    // Your code for the next steps will go here.
}
```

### เพิ่มแอตทริบิวต์ด้วยความยาวที่กำหนด
กำหนดแอตทริบิวต์สตริงชื่อ **wide** และตั้งค่า `Width` เป็น 120 ตัวอักษร นี่คือขั้นตอนสำคัญของ **ตัวอย่างเลเยอร์เวกเตอร์**

อ็อบเจ็กต์ `FeatureAttribute` อธิบายคอลัมน์ในตารางแอตทริบิวต์; การตั้งค่า `Width = 120` บอกตัวเขียน Shapefile ให้จองพื้นที่ 120 ไบต์สำหรับแต่ละเรคคอร์ดของฟิลด์นี้

```csharp
FeatureAttribute attribute = new FeatureAttribute("wide", AttributeDataType.String);
attribute.Width = 120;
layer.Attributes.Add(attribute);
```

> **Pro tip:** คุณสมบัติ `Width` ใช้ได้เฉพาะกับแอตทริบิวต์ประเภทสตริงเท่านั้น ฟิลด์ประเภทตัวเลข, วันที่ หรือ Boolean จะละเว้น `Width` เนื่องจากขนาดถูกกำหนดโดยประเภทข้อมูล

### สร้างและเพิ่ม Feature
สร้าง `Feature`, กำหนดค่าที่อยู่ภายในขีดจำกัด 120 ตัวอักษร, แล้วเพิ่มลงในเลเยอร์ หากสตริงยาวเกินขีดจำกัด Aspose.GIS จะตัดโดยเงียบ ๆ ให้ตรงกับความกว้างที่กำหนด, รักษาความสมบูรณ์ของข้อมูล

คลาส `Feature` รวมเรขาคณิตและค่าของแอตทริบิวต์; หลังจากตั้งค่าแอตทริบิวต์แล้ว การเรียก `layer.Add(feature)` จะเขียนเรคคอร์ดลงใน Shapefile

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("wide", "this string can be up to 120 characters long now.");
layer.Add(feature);
```

หากคุณพยายามกำหนดสตริงที่ยาวกว่า Aspose.GIS จะตัดให้ตรงกับความกว้างที่กำหนด, รักษาความสมบูรณ์ของข้อมูล

## ข้อผิดพลาดทั่วไปและการแก้ไขปัญหา
- **Forgot to set `Width` before adding the attribute?** ความกว้างเริ่มต้นคือ 255 ตัวอักษร; การเปลี่ยนแปลงภายหลังจะไม่ส่งผลต่อฟิลด์ที่สร้างแล้ว ควรกำหนดความกว้างก่อนเสมอ  
- **Using a non‑string data type?** `Width` จะถูกละเว้นสำหรับฟิลด์ตัวเลขหรือวันที่; ตรวจสอบให้แน่ใจว่า `AttributeDataType` ของแอตทริบิวต์เป็น `String`  
- **“Field not found” error?** ชื่อแอตทริบิวต์แยกแยะตามตัวพิมพ์ใหญ่‑เล็ก ตรวจสอบให้ชื่อที่ใช้ใน `SetValue` ตรงกับชื่อที่กำหนดในสคีม่าอย่างแม่นยำ  
- **Unexpected increase in file size?** ความกว้างที่ใหญ่ขึ้นทำให้ขนาดไฟล์ `.dbf` เพิ่มขึ้นแบบเชิงเส้น สำหรับ 10 000 เรคคอร์ด การเพิ่มความกว้างจาก 50 ไปเป็น 120 จะเพิ่มประมาณ 700 KB

## คำถามที่พบบ่อย
**Q: How can I obtain a temporary license for Aspose.GIS for .NET?**  
A: คุณสามารถรับใบอนุญาตชั่วคราวได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/).

**Q: Where can I find community support for Aspose.GIS for .NET?**  
A: เยี่ยมชม [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อรับความช่วยเหลือจากผู้ใช้และการตอบจากทีมงานอย่างเป็นทางการ

**Q: Is there a free trial available for Aspose.GIS for .NET?**  
A: มี, สำรวจ [free trial](https://releases.aspose.com/) เพื่อทดลองใช้คุณสมบัติเต็มชุดโดยไม่มีค่าใช้จ่าย

**Q: How do I purchase a license for Aspose.GIS for .NET?**  
A: ซื้อใบอนุญาตของคุณได้จาก [ที่นี่](https://purchase.aspose.com/buy)

**Q: Where can I access the documentation for Aspose.GIS for .NET?**  
A: ดูรายละเอียดใน [documentation](https://reference.aspose.com/gis/net/) สำหรับข้อมูล API อย่างครบถ้วน

**Q: Can I change the field width after the layer has been created?**  
A: ไม่. ความกว้างของฟิลด์ต้องกำหนดก่อนเพิ่มแอตทริบิวต์; หากต้องการเปลี่ยนต้องสร้างเลเยอร์ใหม่พร้อมสคีม่าใหม่

**Q: Does setting a larger width affect file size?**  
A: Shapefile เก็บฟิลด์สตริงด้วยความยาวคงที่, ดังนั้นการเพิ่มความกว้างจะทำให้ขนาดไฟล์ `.dbf` เพิ่มขึ้นโดยตรงตามจำนวนเรคคอร์ด

## สรุป
**ตัวอย่างเลเยอร์เวกเตอร์** นี้ได้สาธิตวิธีตั้งความกว้างของฟิลด์สำหรับแอตทริบิวต์ใน Shapefile ด้วย Aspose.GIS สำหรับ .NET และแสดงวิธีเพิ่มแอตทริบิวต์ที่มีความยาวเฉพาะอย่างมีประสิทธิภาพ ด้วยการควบคุมความกว้างของแอตทริบิวต์คุณจะหลีกเลี่ยงการตัดข้อมูล, ทำให้ขนาดไฟล์เหมาะสม, และรับประกันการทำงานร่วมกับแพลตฟอร์ม GIS อื่น ๆ ทดลองใช้ความกว้างต่าง ๆ, สำรวจ [documentation](https://reference.aspose.com/gis/net/), และเปิดศักยภาพเต็มของการพัฒนาทางภูมิศาสตร์ด้วย Aspose.GIS

---

**อัปเดตล่าสุด:** 2026-05-16  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [รับแอตทริบิวต์ของเลเยอร์ – ดึงข้อมูลแอตทริบิวต์ของเลเยอร์ด้วย Aspose.GIS สำหรับ .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [วิธีรับค่าแอตทริบิวต์ (ค่าเริ่มต้น) ด้วย Aspose.GIS สำหรับ .NET](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [สร้าง Vector Layer ใน File GDB – บทแนะนำ Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}