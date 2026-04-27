---
date: 2026-01-13
description: เรียนรู้วิธีสร้างไฟล์ shapefile ใหม่ด้วย Aspose.GIS สำหรับ .NET คู่มือแบบขั้นตอนนี้จะแสดงวิธีกำหนดเลเยอร์เวกเตอร์
  เพิ่มแอตทริบิวต์วันที่ และจัดการข้อมูลเชิงพื้นที่
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: สร้างไฟล์ Shapefile ใหม่
url: /th/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างไฟล์ Shapefile ใหม่

## บทนำ
หากคุณกำลังศึกษาการพัฒนาระบบสารสนเทศภูมิศาสตร์ (GIS) ด้วย .NET Aspose.GIS คือโซลูชันที่คุณควรใช้ ไลบรารีอันทรงพลังนี้ช่วยให้นักพัฒนาสามารถทำงานกับข้อมูลเชิงพื้นที่ได้อย่างราบรื่น และในบทช่วยสอนนี้ เราจะแนะนำวิธีการ **สร้างไฟล์ shapefile ใหม่** โดยใช้ Aspose.GIS สำหรับ .NET คุณจะได้เห็นว่าเหตุใดการกำหนดเลเยอร์เวกเตอร์และการเพิ่มแอตทริบิวต์วันที่จึงเป็นขั้นตอนสำคัญสำหรับโครงการ GIS ที่แข็งแกร่ง

## คำตอบโดยย่อ
- **บทช่วยสอนนี้สอนอะไร?** วิธีการสร้างไฟล์ shapefile ใหม่ กำหนดเลเยอร์เวกเตอร์ และเพิ่มแอตทริบิวต์ (รวมถึงฟิลด์วันที่)
- **ต้องใช้ไลบรารีใด?** Aspose.GIS สำหรับ .NET
- **ฉันต้องมีใบอนุญาตหรือไม่?** การทดลองใช้ฟรีเหมาะสำหรับการเรียนรู้ จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานจริง
- **ฉันควรใช้ IDE ใด?** Visual Studio (เวอร์ชันล่าสุดใดก็ได้)
- **การใช้งานใช้เวลานานแค่ไหน?** ประมาณ 10-15 นาทีสำหรับตัวอย่างพื้นฐาน

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มบทเรียน โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- Visual Studio ติดตั้งอยู่ในเครื่องของคุณ
- ไลบรารี Aspose.GIS สำหรับ .NET คุณสามารถดาวน์โหลดได้ [ที่นี่](https://releases.aspose.com/gis/net/)

## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชันการทำงานของ Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: ตั้งค่าโปรเจ็กต์ของคุณ
เริ่มต้นด้วยการสร้างโปรเจ็กต์ C# ใหม่ใน Visual Studio และรวมไลบรารี Aspose.GIS เข้ามา

## ขั้นตอนที่ 2: กำหนดไดเร็กทอรีเอกสาร
```csharp
string dataDir = "Your Document Directory";
```

แทนที่ *Your Document Directory* ด้วยเส้นทางจริงที่คุณต้องการบันทึกไฟล์ shapefile ใหม่ของคุณ

## ขั้นตอนที่ 3: สร้างเลเยอร์เวกเตอร์
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

ส่วนของโค้ดนี้ **กำหนดเลเยอร์เวกเตอร์** และประกาศแอตทริบิวต์สามรายการ ได้แก่ ฟิลด์ข้อความ (`name`), ฟิลด์จำนวนเต็ม (`age`) และฟิลด์วันที่และเวลา (`dob`) การเพิ่มแอตทริบิวต์วันที่มีความสำคัญอย่างยิ่งสำหรับการวิเคราะห์ GIS เชิงเวลา

## ขั้นตอนที่ 4: เพิ่มฟีเจอร์
### กรณีที่ 1: กำหนดค่าทีละรายการ
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

ในที่นี้เราสร้างจุดสองจุด กำหนดค่าแอตทริบิวต์แต่ละรายการแยกกัน และเพิ่มฟีเจอร์ลงในเลเยอร์

### กรณีที่ 2: กำหนดค่าใหม่สำหรับแอตทริบิวต์ทั้งหมด
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
ในวิธีการนี้ เราจะใส่ค่าแอตทริบิวต์ทั้งหมดในการเรียกเพียงครั้งเดียวโดยใช้อาร์เรย์ของออบเจ็กต์ ซึ่งสะดวกเมื่อคุณมีแอตทริบิวต์จำนวนมาก

## เหตุใดจึงสำคัญ
การสร้างไฟล์ shapefile ด้วยโปรแกรมช่วยให้คุณสามารถทำให้กระบวนการจัดการข้อมูลเป็นไปโดยอัตโนมัติ สร้างชุดข้อมูลทดสอบ หรือผสานรวมเอาต์พุต GIS เข้ากับบริการเว็บได้โดยตรง การเรียนรู้ **วิธีการสร้างไฟล์ shapefile** ด้วย Aspose.GIS จะทำให้คุณควบคุมรูปทรงเรขาคณิตของฟีเจอร์ โครงสร้างแอตทริบิวต์ และการปฏิบัติตามรูปแบบไฟล์ได้อย่างเต็มที่

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **ตัวคั่นเส้นทาง:** ใช้ `Path.Combine` เพื่อความเข้ากันได้ข้ามแพลตฟอร์มแทนการต่อสตริง
- **ลำดับแอตทริบิวต์:** ลำดับของค่าใน `SetValues` ต้องตรงกับลำดับที่คุณเพิ่มแอตทริบิวต์
- **การจัดการวันที่:** ใช้ `DateTimeKind.Utc` เสมอหากข้อมูล GIS ของคุณจะถูกแชร์ข้ามเขตเวลา

## สรุป
ขอแสดงความยินดี! คุณได้สร้างไฟล์ shapefile ใหม่โดยใช้ Aspose.GIS สำหรับ .NET สำเร็จแล้ว บทช่วยสอนนี้ครอบคลุมพื้นฐานของการตั้งค่าโปรเจ็กต์ การกำหนดเลเยอร์เวกเตอร์ และการเพิ่มฟีเจอร์ต่างๆ รวมถึงแอตทริบิวต์วันที่ ในขณะที่คุณสำรวจเพิ่มเติม โปรดดู [เอกสารประกอบ](https://reference.aspose.com/gis/net/) สำหรับฟีเจอร์และฟังก์ชันการทำงานขั้นสูง

## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.GIS กับภาษาโปรแกรมอื่นๆ ได้หรือไม่?
Aspose.GIS รองรับ .NET เป็นหลัก แต่ก็มีเวอร์ชันสำหรับ Java ด้วยเช่นกัน

### ถาม: มีการทดลองใช้ฟรีหรือไม่?
ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้ [ที่นี่](https://releases.aspose.com/)

### ถาม: ฉันจะหาการสนับสนุนสำหรับ Aspose.GIS ได้ที่ไหน?
โปรดไปที่ [ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33) สำหรับการสนับสนุนและการสนทนาในชุมชน

### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวได้อย่างไร?
รับใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase.aspose.com/temporary-license/)

### ถาม: ฉันจะซื้อ Aspose.GIS สำหรับ .NET ได้ที่ไหน?
คุณสามารถซื้อไลบรารีได้ [ที่นี่](https://purchase.aspose.com/buy)

---

**อัปเดตล่าสุด:** 2026-01-13
**ทดสอบกับ:** Aspose.GIS 24.11 สำหรับ .NET
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}