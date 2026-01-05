---
date: 2026-01-05
description: เรียนรู้วิธีดึงค่าคุณลักษณะและตั้งค่าเริ่มต้นใน Aspose.GIS สำหรับ .NET
  คู่มือขั้นตอนต่อขั้นตอนนี้แสดงการสร้างชั้น GeoJSON และการสร้างฟีเจอร์ GIS.
linktitle: How to Get Attribute Value (Default)
second_title: Aspose.GIS .NET API
title: วิธีดึงค่าคุณลักษณะ (ค่าเริ่มต้น) ด้วย Aspose.GIS สำหรับ .NET
url: /th/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีรับค่าแอตทริบิวต์ (ค่าเริ่มต้น) ด้วย Aspose.GIS สำหรับ .NET

## บทนำ
ในบทแนะนำเชิงลึกนี้ คุณจะได้ค้นพบ **วิธีรับค่าแอตทริบิวต์** จากฟีเจอร์ GIS โดยใช้ Aspose.GIS สำหรับ .NET และวิธีการทำงานกับค่าเริ่มต้นเมื่อแอตทริบิวต์หายไป ไม่ว่าคุณจะกำลังสร้างเครื่องมือวิเคราะห์เชิงพื้นที่หรือแอปดูแผนที่แบบง่าย การเชี่ยวชาญการดึงค่าแอตทริบิวต์และการจัดการค่าเริ่มต้นเป็นสิ่งสำคัญสำหรับแอปพลิเคชัน GIS ที่เชื่อถือได้.

## คำตอบสั้น
- **วิธีหลักคืออะไร?** `Feature.GetValueOrDefault<T>()`  
- **ฉันสามารถตั้งค่าเริ่มต้นแบบกำหนดเองได้หรือไม่?** ใช่, ผ่าน overload ที่รับค่าเริ่มต้นหรือโดยการกำหนด `DefaultValue` บนแอตทริบิวต์.  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** การทดลองใช้ฟรีสามารถใช้สำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **รูปแบบเรขาคณิตที่รองรับ?** GeoJSON, Shapefile, GML, และอื่น ๆ อีกหลายรูปแบบผ่านไดรเวอร์ของ Aspose.GIS.  
- **ทำงานกับ .NET Core/.NET 6+ หรือไม่?** แน่นอน – ไลบรารีนี้เป็นแบบข้ามแพลตฟอร์ม.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมี:

- ความคุ้นเคยพื้นฐานกับ C# และระบบนิเวศของ .NET.  
- ติดตั้ง Aspose.GIS สำหรับ .NET หากคุณยังไม่ได้ทำ, ดาวน์โหลดได้จาก [here](https://releases.aspose.com/gis/net/).  
- โปรแกรมแก้ไขโค้ด เช่น Visual Studio หรือ Visual Studio Code.

## นำเข้า Namespaces
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

ตอนนี้เราจะเดินผ่านแต่ละตัวอย่างทีละขั้นตอน.

## วิธีรับค่าแอตทริบิวต์ (ค่าเริ่มต้น)

### ขั้นตอนที่ 1: ตั้งค่าสภาพแวดล้อม
กำหนดเส้นทางไปยังโฟลเดอร์ที่เก็บเอกสารทดสอบของคุณ:

```csharp
string dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 2: สร้างเลเยอร์ GeoJSON
เราจะ **สร้างเลเยอร์ geojson** — เป็นที่แรกที่เรากำหนดแอตทริบิวต์ที่อาจเป็น null หรือไม่ได้ตั้งค่า:

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```

### ขั้นตอนที่ 3: สร้างฟีเจอร์ GIS
ตอนนี้เราจะ **สร้างฟีเจอร์ GIS** — ซึ่งจะให้ตัวอย่างฟีเจอร์ใหม่ที่สอดคล้องกับสคีม่าแอตทริบิวต์ที่เรากำหนดไว้:

```csharp
    Feature feature = layer.ConstructFeature();
```

### ขั้นตอนที่ 4: ดึงค่าต่าง ๆ
สุดท้าย, เรา **ดึงค่าแอตทริบิวต์ของฟีเจอร์** โดยใช้หลายสถานการณ์เพื่อแสดงวิธีการทำงานของค่าเริ่มต้น:

```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // value == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // value == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // value == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```

## วิธีตั้งค่าค่าเริ่มต้น

### ขั้นตอนที่ 1: สร้างเลเยอร์ GeoJSON อีกอัน
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
เราดึงค่าตั้งต้น, จากนั้นเปลี่ยนค่าเพื่อดูผลของ **วิธีตั้งค่าตั้งต้น** ในขณะทำงาน:

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
- **เมื่อ `CanBeNull` เป็น false, `GetValueOrDefault` จะคืนค่าตลอดเวลา** (ไม่ว่าจะเป็นค่าที่เก็บไว้หรือค่าตั้งต้นที่กำหนด).  
- **ใช้ overload แบบ generic** (`GetValueOrDefault<T>`) เพื่อหลีกเลี่ยงการ boxing/unboxing สำหรับประเภทค่าพื้นฐาน.  
- **เคล็ดลับมืออาชีพ:** หากต้องการตรวจสอบว่าแอตทริบิวต์ถูกตั้งค่าจริงหรือไม่, ใช้ `feature.IsAttributeSet("attribute")` ก่อนเรียก `GetValueOrDefault`.

## คำถามที่พบบ่อย

### Aspose.GIS รองรับ .NET Core หรือไม่?
ใช่, Aspose.GIS รองรับ .NET Core อย่างเต็มที่, ให้การสนับสนุนข้ามแพลตฟอร์ม.

### ฉันสามารถใช้ Aspose.GIS ในโครงการเชิงพาณิชย์ได้หรือไม่?
แน่นอน! Aspose.GIS มาพร้อมไลเซนส์เชิงพาณิชย์ที่อนุญาตให้คุณใช้ในแอปพลิเคชันเชิงพาณิชย์โดยไม่มีข้อจำกัดใด ๆ.

### ฉันจะหาแหล่งสนับสนุนและทรัพยากรเพิ่มเติมได้จากที่ไหน?
เยี่ยมชม [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อรับการสนับสนุนจากชุมชนและสำรวจ [documentation](https://reference.aspose.com/gis/net/) เพื่อข้อมูลเชิงลึก.

### มีการทดลองใช้ฟรีหรือไม่?
ใช่, คุณสามารถสำรวจ Aspose.GIS ด้วยการทดลองใช้ฟรี ดาวน์โหลดได้จาก [here](https://releases.aspose.com/).

### ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับการทดสอบได้อย่างไร?
สำหรับไลเซนส์ชั่วคราว, เยี่ยมชม [here](https://purchase.aspose.com/temporary-license/).

## FAQ เพิ่มเติม
**ถาม: จะเกิดอะไรขึ้นหากฉันเรียก `GetValueOrDefault` บนแอตทริบิวต์ที่ไม่มีอยู่?**  
ตอบ: เมธอดจะโยน `ArgumentException`. ควรตรวจสอบชื่อแอตทริบิวต์หรือใช้ `feature.HasAttribute("name")` ก่อนเสมอ.

**ถาม: ฉันสามารถเปลี่ยนค่าเริ่มต้นหลังจากสร้างเลเยอร์แล้วได้หรือไม่?**  
ตอบ: ใช่, คุณสามารถแก้ไข `attribute.DefaultValue` แล้วเรียก `layer.UpdateAttribute(attribute)` เพื่อบันทึกการเปลี่ยนแปลง.

**ถาม: Aspose.GIS รองรับการอัปเดตค่าแอตทริบิวต์เป็นกลุ่มหรือไม่?**  
ตอบ: คุณสามารถวนลูปผ่านคอลเลกชันของฟีเจอร์และเรียก `SetValue` บนแต่ละฟีเจอร์; สำหรับชุดข้อมูลขนาดใหญ่, พิจารณาใช้ API `FeatureCursor` เพื่อประสิทธิภาพที่ดีกว่า.

## สรุป
ในคู่มือนี้ เราได้ครอบคลุม **วิธีรับค่าแอตทริบิวต์** การกำหนดและการแทนที่ค่าเริ่มต้น, และวิธี **สร้างสคีม่าเลเยอร์ GeoJSON** ที่ตรงกับความต้องการของแอปพลิเคชันของคุณ ด้วยเทคนิคเหล่านี้คุณสามารถสร้างโซลูชัน GIS ที่แข็งแรงและจัดการกับข้อมูลที่หายไปหรือเป็นตัวเลือกได้อย่างราบรื่น.

---

**อัปเดตล่าสุด:** 2026-01-05  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}