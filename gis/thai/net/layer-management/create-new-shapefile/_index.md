---
date: 2026-06-30
description: เรียนรู้วิธีสร้าง shapefile ด้วย Aspose.GIS for .NET คู่มือขั้นตอนต่อขั้นตอนนี้จะแสดงวิธีกำหนด
  vector layer, เพิ่ม date attribute, และจัดการ spatial data อย่างมีประสิทธิภาพ
keywords:
- how to create shapefile
- temporal gis shapefile
- Aspose.GIS vector layer
- GIS data automation
linktitle: สร้าง Shapefile ใหม่
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create shapefile using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to define a vector layer, add a date attribute, and manage
    spatial data efficiently.
  headline: How to Create Shapefile with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS primarily supports .NET, but there are versions available for
      Java as well.
    question: Can I use Aspose.GIS with other programming languages?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I find support for Aspose.GIS?
  - answer: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license?
  - answer: You can buy the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: วิธีสร้าง Shapefile ด้วย Aspose.GIS for .NET
url: /th/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง Shapefile ใหม่

## บทนำ
หากคุณกำลังสำรวจการพัฒนาระบบสารสนเทศภูมิศาสตร์ (GIS) ด้วย .NET, Aspose.GIS คือโซลูชันที่คุณควรเลือกสำหรับ **how to create shapefile** อย่างเป็นโปรแกรมเมติก ไลบรารีนี้ให้คุณควบคุมเลเยอร์เวกเตอร์, สคีมาของแอตทริบิวต์, และการปฏิบัติตามรูปแบบไฟล์ได้อย่างเต็มที่, ทำให้คุณสามารถอัตโนมัติการไหลของข้อมูลหรือสร้างชุดข้อมูลทดสอบได้ในเวลาไม่กี่นาที

## คำตอบด่วน
- **บทเรียนนี้สอนอะไร?** วิธีสร้าง shapefile ใหม่, กำหนดเลเยอร์เวกเตอร์, และเพิ่มแอตทริบิวต์ (รวมถึงฟิลด์วันที่)  
- **ไลบรารีที่ต้องการคืออะไร?** Aspose.GIS สำหรับ .NET  
- **ฉันต้องการไลเซนส์หรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการเรียนรู้; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **IDE ที่ควรใช้คืออะไร?** Visual Studio (เวอร์ชันล่าสุดใดก็ได้)  
- **การดำเนินการใช้เวลานานเท่าใด?** ประมาณ 10‑15 นาทีสำหรับตัวอย่างพื้นฐาน

## วิธีสร้าง shapefile ด้วย Aspose.GIS สำหรับ .NET?
โหลดไลบรารี Aspose.GIS, ตั้งค่าโฟลเดอร์ผลลัพธ์, สร้าง `VectorLayer`, กำหนดแอตทริบิวต์, และเพิ่มฟีเจอร์—กระบวนการทั้งหมดนี้สามารถเขียนได้ภายในไม่เกิน 30 บรรทัดของ C# ไลบรารีจะจัดการการสร้างเรขาคณิต, การกำหนดประเภทแอตทริบิวต์, และการเขียนไฟล์โดยอัตโนมัติ, ดังนั้นคุณไม่จำเป็นต้องจัดการสเปค Shapefile ระดับล่างด้วยตนเอง

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มบทเรียน, โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:
- ความเข้าใจพื้นฐานของภาษาโปรแกรม C#  
- ติดตั้ง Visual Studio บนเครื่องของคุณ  
- ไลบรารี Aspose.GIS สำหรับ .NET คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/gis/net/)

## นำเข้า Namespaces
เริ่มต้นโดยการนำเข้า namespaces ที่จำเป็นเพื่อใช้ฟังก์ชันของ Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์ของคุณ
เริ่มด้วยการสร้างโปรเจกต์ C# ใหม่ใน Visual Studio และเพิ่มไลบรารี Aspose.GIS เข้าไป

## ขั้นตอนที่ 2: กำหนดไดเรกทอรีเอกสาร
```csharp
string dataDir = "Your Document Directory";
```
แทนที่ *Your Document Directory* ด้วยเส้นทางจริงที่คุณต้องการบันทึก shapefile ใหม่ของคุณ

## ขั้นตอนที่ 3: สร้าง VectorLayer
คลาส `VectorLayer` แทนเลเยอร์ shapefile เดียวที่เก็บข้อมูลเรขาคณิตและแอตทริบิวต์ ในขั้นตอนนี้เราจะกำหนดเลเยอร์เวกเตอร์และประกาศแอตทริบิวต์สามรายการ: ฟิลด์ข้อความ (`name`), ฟิลด์จำนวนเต็ม (`age`), และฟิลด์วันที่‑เวลา (`dob`). การเพิ่มแอตทริบิวต์วันที่เป็นสิ่งสำคัญสำหรับการวิเคราะห์ **temporal GIS shapefile**  

```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

## ขั้นตอนที่ 4: เพิ่ม Features
### กรณีที่ 1: ตั้งค่าค่าแยกแต่ละรายการ
เมธอด `SetValues` จะกำหนดค่าของแอตทริบิวต์ให้กับฟีเจอร์ตามลำดับที่ได้กำหนดไว้  

```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
ที่นี่เราสร้างจุดสองจุด, ตั้งค่าแต่ละแอตทริบิวต์แยกกัน, และเพิ่มฟีเจอร์เหล่านั้นลงในเลเยอร์

### กรณีที่ 2: ตั้งค่าค่าใหม่สำหรับทุก Attribute
อีกวิธีหนึ่งคือการให้ค่าของแอตทริบิวต์ทั้งหมดพร้อมกันโดยใช้ `SetValues` พร้อมอาเรย์ของอ็อบเจ็กต์  

```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
วิธีนี้เราจะเติมค่าของแอตทริบิวต์ทั้งหมดในหนึ่งคำสั่งโดยใช้อาเรย์ของอ็อบเจ็กต์—สะดวกเมื่อมีแอตทริบิวต์จำนวนมาก

## ทำไมเรื่องนี้ถึงสำคัญ?
การสร้าง shapefile อย่างเป็นโปรแกรมเมติกช่วยให้คุณอัตโนมัติการไหลของข้อมูล, สร้างชุดข้อมูลทดสอบ, หรือฝังผลลัพธ์ GIS ลงในบริการเว็บโดยตรง Aspose.GIS รองรับ **30+ รูปแบบเวกเตอร์และราสเตอร์** และสามารถเขียน shapefile หลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ, ให้ความเร็วและความสามารถในการขยายตัว

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ตัวคั่นเส้นทาง:** ใช้ `Path.Combine` เพื่อความเข้ากันได้ข้ามแพลตฟอร์มแทนการต่อสตริง  
- **ลำดับแอตทริบิวต์:** ลำดับของค่าที่ส่งให้ `SetValues` ต้องตรงกับลำดับที่คุณเพิ่มแอตทริบิวต์ไว้  
- **การจัดการวันที่:** ควรใช้ `DateTimeKind.Utc` เสมอหากข้อมูล GIS ของคุณจะถูกแชร์ข้ามโซนเวลา

## สรุป
ยินดีด้วย! คุณได้สร้าง shapefile ใหม่สำเร็จโดยใช้ Aspose.GIS สำหรับ .NET บทเรียนนี้ครอบคลุมพื้นฐานของการตั้งค่าโปรเจกต์, การกำหนด VectorLayer, และการเพิ่มฟีเจอร์รวมถึงแอตทริบิวต์วันที่ เมื่อคุณต้องการสำรวจต่อไป, โปรดดู [documentation](https://reference.aspose.com/gis/net/) สำหรับคุณลักษณะและฟังก์ชันขั้นสูง

## คำถามที่พบบ่อย
**Q: ฉันสามารถใช้ Aspose.GIS กับภาษาโปรแกรมอื่นได้หรือไม่?**  
**A:** Aspose.GIS รองรับหลัก ๆ สำหรับ .NET, แต่ก็มีเวอร์ชันสำหรับ Java ด้วย  

**Q: มีเวอร์ชันทดลองฟรีหรือไม่?**  
**A:** มี, คุณสามารถเข้าถึงเวอร์ชันทดลองได้จาก [ที่นี่](https://releases.aspose.com/)  

**Q: ฉันจะหาแหล่งสนับสนุนสำหรับ Aspose.GIS ได้จากที่ไหน?**  
**A:** เยี่ยมชม [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อรับการสนับสนุนจากชุมชนและการสนทนาต่าง ๆ  

**Q: ฉันจะขอรับไลเซนส์ชั่วคราวได้อย่างไร?**  
**A:** รับไลเซนส์ชั่วคราวของคุณได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/)  

**Q: ฉันจะซื้อ Aspose.GIS สำหรับ .NET ได้จากที่ไหน?**  
**A:** คุณสามารถซื้อไลบรารีได้จาก [ที่นี่](https://purchase.aspose.com/buy)  

**Last Updated:** 2026-06-30  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [Get Layer Attributes – Retrieve Layer Attribute Information with Aspose.GIS for .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Create Vector Layer and Set Layer Spatial Reference System](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}