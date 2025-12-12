---
date: 2025-12-12
description: เรียนรู้วิธีสร้างเลเยอร์เวกเตอร์และเพิ่มเรขาคณิตเส้นวงกลมโดยใช้ Aspose.GIS
  สำหรับ .NET – วิธีที่รวดเร็วในการสร้างแอปพลิเคชัน GIS.
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: สร้างชั้นเวกเตอร์และสตริงวงกลมใน Aspose.GIS สำหรับ .NET
url: /th/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง Vector Layer และ Circular String Geometry ด้วย Aspose.GIS สำหรับ .NET

## บทนำ
หากคุณกำลังสร้างแอปพลิเคชัน GIS บนแพลตฟอร์ม .NET ขั้นตอนแรกมักจะเป็น **to create vector layer** ที่เก็บฟีเจอร์เชิงพื้นที่ของคุณ Aspose.GIS สำหรับ .NET ทำให้กระบวนการนี้ง่ายขึ้นและเพิ่มชั้นเหล่านั้นด้วยรูปทรงเรขาคณิตขั้นสูง เช่น circular strings ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีสร้าง vector layer, เพิ่ม circular string geometry, และบันทึกผลลัพธ์เป็น Shapefile — ทั้งหมดด้วยโค้ด C# ที่สะอาดและพร้อมใช้งานในผลิตภัณฑ์

## คำตอบอย่างรวดเร็ว
- **What does “create vector layer” mean?** มันสร้างคอนเทนเนอร์ (layer) ใหม่ที่สามารถเก็บฟีเจอร์เชิงพื้นที่ เช่น จุด, เส้น, หรือโพลิกอน  
- **Which class represents a circular string?** `CircularString` จาก `Aspose.Gis.Geometries`  
- **Can I save the layer as a Shapefile?** ได้ – ใช้ `Drivers.Shapefile` เมื่อสร้าง layer  
- **Do I need a license for development?** ใบอนุญาตชั่วคราวใช้ได้สำหรับการประเมิน; จำเป็นต้องมีใบอนุญาตเต็มสำหรับการใช้งานจริง  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  

## “create vector layer” คืออะไร?
Vector layer คือการจัดกลุ่มเชิงตรรกะของฟีเจอร์เวกเตอร์ (จุด, เส้น, โพลิกอน) ที่เก็บในแหล่งข้อมูลเดียว ใน Aspose.GIS คุณสร้าง layer โดยเรียก `VectorLayer.Create` โดยระบุเส้นทางไฟล์เป้าหมายและไดรเวอร์ที่ต้องการ (เช่น Shapefile) เมื่อ layer มีอยู่แล้ว คุณสามารถเพิ่มฟีเจอร์, กำหนดเรขาคณิต, และทำการดำเนินการเชิงพื้นที่ได้

## ทำไมต้องเพิ่ม circular string?
Circular strings เป็นประเภทของ **linear geometry** ที่ประมาณค่าความโค้งโดยใช้ลำดับของจุด พวกมันมีประโยชน์สำหรับการแสดงเส้นถนนโค้ง, การโค้งของแม่น้ำ, หรือฟีเจอร์ใด ๆ ที่ต้องการเส้นโค้งเรียบโดยไม่ต้องใช้เส้นเล็ก ๆ จำนวนมาก

## ข้อกำหนดเบื้องต้น
- **.NET Framework หรือ .NET Core** ติดตั้งบนเครื่องของคุณ  
- **Aspose.GIS for .NET** library – ดาวน์โหลดจากเว็บไซต์อย่างเป็นทางการ **[here](https://releases.aspose.com/gis/net/)**.  
- IDE เช่น **Visual Studio** หรือ **JetBrains Rider**.  
- ความคุ้นเคยพื้นฐานกับการเขียนโปรแกรม **C#**.  

## นำเข้า Namespaces
Add the required namespaces to your C# file:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## คู่มือขั้นตอน

### ขั้นตอนที่ 1: กำหนดเส้นทางไฟล์ผลลัพธ์
กำหนดตำแหน่งที่ Shapefile จะถูกเขียน

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

แทนที่ `"Your Document Directory"` ด้วยเส้นทางโฟลเดอร์จริงบนระบบของคุณ

### ขั้นตอนที่ 2: **Create vector layer**
เปิด `VectorLayer` โดยใช้เมธอด `Create` นี่คือแกนหลักของการดำเนินการ **create vector layer**

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### ขั้นตอนที่ 3: สร้างฟีเจอร์ใหม่
ฟีเจอร์เป็นตัวแทนของบันทึกเชิงพื้นที่หนึ่งรายการภายใน layer

```csharp
    var feature = layer.ConstructFeature();
```

### ขั้นตอนที่ 4: สร้าง circular string geometry
เพิ่มจุดที่กำหนดรูปทรงโค้ง ลำดับของจุดสร้างส่วนโค้งที่เริ่มและสิ้นสุดที่ตำแหน่งเดียวกัน ทำให้ได้ circular string ที่ปิด

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### ขั้นตอนที่ 5: กำหนดเรขาคณิตและเพิ่มฟีเจอร์ลงใน layer
เชื่อมโยงเรขาคณิตกับฟีเจอร์และบันทึกลงใน layer

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

เมื่อบล็อก `using` สิ้นสุดลง layer จะถูกเขียนลง Shapefile บนดิสก์โดยอัตโนมัติ

## ปัญหาทั่วไปและวิธีแกัญหา | วิธีแก้ |
|-------|----------|
| **File path invalid** | ตรวจสอบให้แน่ใจว่าไดเรกทอรีมีอยู่และคุณมีสิทธิ์เขียน |
| **CircularString appears as a straight line** | ตรวจสอบว่าจุดถูกเพิ่มตามลำดับที่ถูกต้อง; จุดแรกและจุดสุดท้ายควรเหมือนกันสำหรับรูปแบบที่ปิด |
| **License exception** | ใช้ใบอนุญาตชั่วคราวในระหว่างการพัฒนา หรือซื้อใบอนุญาตเต็มสำหรับการใช้งานในผลิตภัณฑ์ |

## คำถามที่พบบ่อย

### Aspose.GIS for .NET รองรับเวอร์ชันทั้งหมดของ .NET Framework หรือไม่?
ใช่, Aspose.GIS for .NET ถูกออกแบบให้ทำงานกับหลายเวอร์ชันของ .NET ตั้งแต่ Framework 4.5 จนถึงการปล่อย .NET 8 ล่าสุด

### ฉันสามารถรวม Aspose.GIS for .NET กับไลบรารี GIS อื่นได้หรือไม่?
แน่นอน! คุณสามารถอ่านข้อมูลด้วยไลบรารีอื่น, ปรับแต่งด้วย Aspose.GIS, แล้วเขียนกลับได้ ด้วย API ที่ยืดหยุ่นของมัน

### Aspose.GIS for .NET รองรับการแสดงผลข้อมูลเชิงพื้นที่หรือไม่?
ใช่, ไลบรารีนี้มียูทิลิตี้การเรนเดอร์ที่ช่วยให้คุณสร้างแผนที่และการแสดงผลเชิงภาพของเรขาคณิตของคุณ

### มีฟอรั่มชุมชนที่ฉันสามารถขอความช่วยเหลือเกี่ยวกับ Aspose.GIS for .NET ได้หรือไม่?
ใช่, คุณสามารถเยี่ยมชมฟอรั่ม Aspose.GIS **[here](https://forum.aspose.com/c/gis/33)** เพื่อถามคำถามและแบ่งปันประสบการณ์

### ฉันสามารถรับใบอนุญาตประเมิน Aspose.GIS for .NET ได้หรือไม่?
แน่นอน! ใบอนุญาตประเมินชั่วคราวพร้อมให้ดาวน์โหลด **[here](https://purchase.aspose.com/temporary-license/)**.

### ฉันจะเพิ่มเรขาคณิตที่ซับซ้อนมากขึ้น (เช่น MultiLineString) ลงใน layer เดียวได้อย่างไร?
สร้างอ็อบเจกต์เรขาคณิตที่เหมาะสม (เช่น `MultiLineString`), เติมข้อมูลด้วยอ็อบเจกต์ `LineString` แยกแต่ละอัน, กำหนดให้กับ `feature.Geometry`, แล้วเพิ่มฟีเจอร์เช่นเดียวกับที่ทำกับ circular string

## สรุป
โดยทำตามขั้นตอนเหล่านี้ คุณจะรู้วิธี **create vector layer** objects และเพิ่มเรขาคณิต circular string ด้วย Aspose.GIS สำหรับ .NET พื้นฐานนี้ทำให้คุณสร้างโซลูชัน GIS ที่หลากหลายยิ่งขึ้น — ไม่ว่าจะเป็นการทำแผนที่เครือข่ายการขนส่ง, การแสดงผลข้อมูลสิ่งแวดล้อม, หรือการพัฒนาเครื่องมือวิเคราะห์เชิงพื้นที่แบบกำหนดเอง

---

**Last Updated:** 2025-12-12  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}