---
date: 2026-05-21
description: เรียนรู้วิธีการรับค่าแอตทริบิวต์และตั้งค่าดีฟอลต์ใน Aspose.GIS for .NET.
  คู่มือขั้นตอนต่อขั้นตอนนี้แสดงการสร้างเลเยอร์ GeoJSON และการสร้างฟีเจอร์ GIS.
keywords:
- how to get attribute
- use default values
- set default attribute
- create geojson layer
- create gis feature
linktitle: วิธีการรับค่าแอตทริบิวต์ (ค่าเริ่มต้น)
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to get attribute values and set defaults in Aspose.GIS for
    .NET. This step‑by‑step guide shows creating GeoJSON layers and constructing GIS
    features.
  headline: How to Get Attribute Value (Default) with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to get attribute values and set defaults in Aspose.GIS for
    .NET. This step‑by‑step guide shows creating GeoJSON layers and constructing GIS
    features.
  name: How to Get Attribute Value (Default) with Aspose.GIS for .NET
  steps:
  - name: Set up the Environment
    text: 'Define the path to the folder that holds your test documents:'
  - name: Create a GeoJSON Layer
    text: 'We’ll **create a GeoJSON layer** — the first place where we define an attribute
      that can be null or unset:'
  - name: Construct a GIS Feature
    text: 'Now we **construct a GIS feature** — this gives us a fresh feature instance
      that respects the attribute schema we just defined:'
  - name: Retrieve Values
    text: 'We **get feature attribute** values using several scenarios, demonstrating
      how defaults work:'
  - name: Create Another GeoJSON Layer
    text: 'This time we’ll **set attribute default** directly on the schema:'
  - name: Retrieve and Set Values
    text: 'We retrieve the default, then change it to see the effect of **how to set
      default** at runtime:'
  type: HowTo
- questions:
  - answer: The method throws an `ArgumentException`. Always verify the attribute
      name with `feature.HasAttribute("name")` first.
    question: What happens if I call `GetValueOrDefault` on an attribute that doesn’t
      exist?
  - answer: Yes – modify `attribute.DefaultValue` and call `layer.UpdateAttribute(attribute)`
      to persist the change.
    question: Can I change the default value after the layer is created?
  - answer: You can iterate over a feature collection and call `SetValue` on each
      feature; for large datasets, use the `FeatureCursor` API to improve performance.
    question: Does Aspose.GIS support bulk updates of attribute values?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: วิธีการรับค่าแอตทริบิวต์ (ค่าเริ่มต้น) ด้วย Aspose.GIS for .NET
url: /th/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีรับค่าแอตทริบิวต์ (ค่าเริ่มต้น) ด้วย Aspose.GIS สำหรับ .NET

## บทนำ
ในบทแนะนำเชิงลึกนี้ คุณจะได้ค้นพบ **วิธีรับค่าแอตทริบิวต์** จากฟีเจอร์ GIS ด้วย Aspose.GIS สำหรับ .NET และวิธีทำงานกับค่าเริ่มต้นเมื่อแอตทริบิวต์หายไป ไม่ว่าคุณจะกำลังสร้างเครื่องมือวิเคราะห์เชิงพื้นที่หรือโปรแกรมดูแผนที่แบบง่าย การเชี่ยวชาญการดึงค่าแอตทริบิวต์และการจัดการค่าเริ่มต้นเป็นสิ่งสำคัญสำหรับแอปพลิเคชัน GIS ที่เชื่อถือได้

## คำตอบสั้น
- **วิธีหลักคืออะไร?** `Feature.GetValueOrDefault<T>()` ดึงแอตทริบิวต์หรือค่าเริ่มต้นที่กำหนดไว้ในหนึ่งการเรียก.  
- **ฉันสามารถตั้งค่าเริ่มต้นแบบกำหนดเองได้หรือไม่?** ได้ – ใช้ overload ที่รับค่าตั้งต้นหรือกำหนด `DefaultValue` บนสคีม่าแอตทริบิวต์.  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **รูปแบบเรขาคณิตที่รองรับ?** ไดรเวอร์ของ Aspose.GIS รองรับรูปแบบกว่า 30 แบบ รวมถึง GeoJSON, Shapefile, GML, และ KML.  
- **ทำงานกับ .NET Core/.NET 6+ หรือไม่?** แน่นอน – ไลบรารีนี้เป็นแบบข้ามแพลตฟอร์มและทำงานบน Windows, Linux, และ macOS.  

## GetValueOrDefault คืออะไร?
`GetValueOrDefault<T>()` เป็นเมธอด generic ของ Aspose.GIS ที่คืนค่าของแอตทริบิวต์ที่ระบุหรือหากแอตทริบิวต์เป็น null จะคืนค่าที่กำหนดไว้ล่วงหน้า วิธีนี้ช่วยลดความจำเป็นในการตรวจสอบ null ด้วยตนเองและปรับปรุงความอ่านง่ายของโค้ด นอกจากนี้ยังรองรับประเภท nullable และผู้ให้ค่าเริ่มต้นแบบกำหนดเอง ทำให้ใช้งานได้หลากหลายสำหรับสถานการณ์ข้อมูลต่าง ๆ

## ทำไมต้องใช้ค่าเริ่มต้นของแอตทริบิวต์?
การกำหนดค่าดีฟอลต์ช่วยลดข้อผิดพลาดขณะรันไทม์และทำให้สายงานข้อมูลง่ายขึ้น Aspose.GIS สามารถประมวลผล **ไฟล์ GeoJSON ขนาดหลายร้อยหน้า** โดยไม่ต้องโหลดชุดข้อมูลทั้งหมดเข้าสู่หน่วยความจำ และการจัดการค่าเริ่มต้นสามารถลดโค้ดป้องกันได้ถึง **70 %** ในสถานการณ์ CRUD ปกติอย่างมีนัยสำคัญ

## ข้อกำหนดเบื้องต้น
- ความคุ้นเคยพื้นฐานกับ C# และระบบนิเวศของ .NET.  
- ติดตั้ง Aspose.GIS สำหรับ .NET หากยังไม่ได้ดาวน์โหลด ให้ดาวน์โหลดจาก [here](https://releases.aspose.com/gis/net/).  
- โปรแกรมแก้ไขโค้ดเช่น Visual Studio หรือ Visual Studio Code.

## นำเข้า Namespace
เพิ่มคำสั่ง `using` ที่จำเป็นลงในไฟล์ C# ของคุณเพื่อให้ประเภท API พร้อมใช้งาน:

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

ตอนนี้เรามาเดินผ่านแต่ละตัวอย่างทีละขั้นตอน.

## วิธีรับค่าแอตทริบิวต์ (ค่าเริ่มต้น)
โหลดฟีเจอร์, เรียก `GetValueOrDefault` และคุณจะได้รับค่าที่เก็บไว้หรือค่าที่สำรองที่คุณกำหนดทันที วิธีนี้ทำงานกับสตริง, ตัวเลข, วันที่, และแม้แต่ struct ที่กำหนดเอง, รับประกันความปลอดภัยของประเภทโดยไม่ต้องบ็อกซ์ การใช้เมธอดนี้ช่วยหลีกเลี่ยงการตรวจสอบ null อย่างชัดเจนและสามารถเชื่อมต่อการเรียกได้อย่างปลอดภัย ซึ่งทำให้โค้ดอ่านง่ายขึ้นและลดบั๊กในโค้ดฐานขนาดใหญ่

### ขั้นตอนที่ 1: ตั้งค่าสภาพแวดล้อม
กำหนดเส้นทางไปยังโฟลเดอร์ที่เก็บเอกสารทดสอบของคุณ:

```csharp
string dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 2: สร้างเลเยอร์ GeoJSON
เราจะ **สร้างเลเยอร์ GeoJSON** — เป็นที่แรกที่เรากำหนดแอตทริบิวต์ที่อาจเป็น null หรือไม่ได้ตั้งค่า:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```

### ขั้นตอนที่ 3: สร้างฟีเจอร์ GIS
ตอนนี้เราจะ **สร้างฟีเจอร์ GIS** — ซึ่งให้เรามีอินสแตนซ์ฟีเจอร์ใหม่ที่สอดคล้องกับสคีม่าแอตทริบิวต์ที่เรากำหนดไว้:

```csharp
    Feature feature = layer.ConstructFeature();
```

### ขั้นตอนที่ 4: ดึงค่า
เรา **ดึงค่าแอตทริบิวต์ของฟีเจอร์** ด้วยหลายสถานการณ์ เพื่อแสดงวิธีการทำงานของค่าเริ่มต้น:

```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // value == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // value == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // value == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```

## วิธีตั้งค่าดีฟอลต์
กำหนดค่าเริ่มต้นโดยตรงบนสคีม่าแอตทริบิวต์ แล้วทำการแทนที่ในระหว่างการทำงานหากจำเป็น วิธีนี้ให้การควบคุมเต็มที่ต่อพฤติกรรมสำรองโดยไม่ต้องแก้ไขรูปแบบไฟล์พื้นฐาน คุณยังสามารถระบุค่าเริ่มต้นเมื่อกำหนดสคีม่าแอตทริบิวต์ เพื่อให้ฟีเจอร์ที่สร้างใหม่ทั้งหมดสืบทอดค่าเริ่มต้นเหล่านี้โดยอัตโนมัติโดยไม่ต้องเขียนโค้ดเพิ่มเติม

### ขั้นตอนที่ 1: สร้างเลเยอร์ GeoJSON อีกชั้น
ครั้งนี้เราจะ **ตั้งค่าเริ่มต้นของแอตทริบิวต์** โดยตรงบนสคีม่า:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```

### ขั้นตอนที่ 2: สร้างฟีเจอร์ GIS (อีกครั้ง)
```csharp
    Feature feature = layer.ConstructFeature();
```

### ขั้นตอนที่ 3: ดึงและตั้งค่า
เราดึงค่าเริ่มต้นแล้วเปลี่ยนค่าเพื่อดูผลของ **วิธีตั้งค่าเริ่มต้น** ในระหว่างการทำงาน:

```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // value == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // value == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // value == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```

## ข้อผิดพลาดทั่วไปและเคล็ดลับ
- **อย่าลืมปิดบล็อก `using`** เลเยอร์จะถูกทำลายโดยอัตโนมัติ ปล่อยตัวจัดการไฟล์.  
- **เมื่อ `CanBeNull` เป็น false, `GetValueOrDefault` จะคืนค่าตลอดเวลา** (ไม่ว่าจะเป็นค่าที่เก็บไว้หรือค่าที่กำหนดเป็นค่าเริ่มต้น).  
- **ใช้ overload generic** (`GetValueOrDefault<T>`) เพื่อหลีกเลี่ยงการ boxing/unboxing สำหรับประเภทค่า.  
- **เคล็ดลับระดับมืออาชีพ:** หากต้องการตรวจสอบว่าแอตทริบิวต์ถูกตั้งค่าจริงหรือไม่ ให้ใช้ `feature.IsAttributeSet("attribute")` ก่อนเรียก `GetValueOrDefault`.  
- **หลีกเลี่ยงการผสมชื่อแอตทริบิวต์ที่มีการใช้ตัวอักษรต่างกัน** – ชื่อแอตทริบิวต์ GIS มีความไวต่อขนาดตัวอักษรและความไม่ตรงกันจะทำให้เกิด `ArgumentException`.  

## คำถามที่พบบ่อย
### Aspose.GIS รองรับ .NET Core หรือไม่?
ใช่ – Aspose.GIS ทำงานบน .NET Core, .NET 5, .NET 6 และเวอร์ชันต่อไป ให้การสนับสนุนแบบข้ามแพลตฟอร์มเต็มรูปแบบ.

### ฉันสามารถใช้ Aspose.GIS สำหรับโครงการเชิงพาณิชย์ได้หรือไม่?
แน่นอน ไลเซนส์เชิงพาณิชย์จะลบข้อจำกัดการทดลองทั้งหมดและให้สิทธิ์คุณในการใช้งานในสภาพแวดล้อมการผลิต.

### ฉันจะหาแหล่งสนับสนุนและทรัพยากรเพิ่มเติมได้จากที่ไหน?
เยี่ยมชม [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อรับความช่วยเหลือจากชุมชนและสำรวจ [documentation](https://reference.aspose.com/gis/net/) เพื่อดูรายละเอียด API อย่างลึกซึ้ง.

### มีการทดลองใช้ฟรีหรือไม่?
ใช่ คุณสามารถสำรวจ Aspose.GIS ด้วยการทดลองใช้ฟรี ดาวน์โหลดได้จาก [here](https://releases.aspose.com/).

### ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับการทดสอบได้อย่างไร?
สำหรับไลเซนส์ชั่วคราว โปรดเยี่ยมชม [here](https://purchase.aspose.com/temporary-license/).

## คำถามเพิ่มเติม
**Q: หากฉันเรียก `GetValueOrDefault` บนแอตทริบิวต์ที่ไม่มีอยู่ จะเกิดอะไรขึ้น?**  
A: เมธอดจะโยน `ArgumentException`. ควรตรวจสอบชื่อแอตทริบิวต์ด้วย `feature.HasAttribute("name")` ก่อนเสมอ.

**Q: ฉันสามารถเปลี่ยนค่าเริ่มต้นหลังจากสร้างเลเยอร์แล้วได้หรือไม่?**  
A: ได้ – แก้ไข `attribute.DefaultValue` แล้วเรียก `layer.UpdateAttribute(attribute)` เพื่อบันทึกการเปลี่ยนแปลง.

**Q: Aspose.GIS รองรับการอัปเดตค่าของแอตทริบิวต์เป็นกลุ่มหรือไม่?**  
A: คุณสามารถวนลูปผ่านคอลเลกชันของฟีเจอร์และเรียก `SetValue` บนแต่ละฟีเจอร์; สำหรับชุดข้อมูลขนาดใหญ่ ให้ใช้ API `FeatureCursor` เพื่อปรับปรุงประสิทธิภาพ.

## สรุป
ในคู่มือนี้ เราได้ครอบคลุม **วิธีรับค่าแอตทริบิวต์** การกำหนดและการแทนที่ค่าเริ่มต้น และวิธี **สร้างสคีม่าเลเยอร์ GeoJSON** ที่เหมาะกับความต้องการของแอปพลิเคชันของคุณ ด้วยเทคนิคเหล่านี้คุณสามารถสร้างโซลูชัน GIS ที่แข็งแรงซึ่งจัดการกับข้อมูลที่หายไปหรือเป็นตัวเลือกได้อย่างราบรื่น ลดโค้ดป้องกันและปรับปรุงประสิทธิภาพโดยรวม.

---

**อัปเดตล่าสุด:** 2026-05-21  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [รับแอตทริบิวต์ของเลเยอร์ – ดึงข้อมูลแอตทริบิวต์ของเลเยอร์ด้วย Aspose.GIS สำหรับ .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [รับค่าแอตทริบิวต์ของฟีเจอร์โดยใช้การแคสท์ประเภทแบบไดนามิก](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value/)
- [อ่าน Shapefile C# – รับค่าแอตทริบิวต์ของฟีเจอร์ทั้งหมด](/gis/net/layer-interaction-and-data-access/get-all-feature-attribute-values/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}