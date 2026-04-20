---
date: 2026-02-15
description: เรียนรู้วิธีสร้างเลเยอร์เวกเตอร์และเพิ่มเรขาคณิตเส้นวงกลมโดยใช้ Aspose.GIS
  สำหรับ .NET – วิธีที่รวดเร็วในการสร้างแอปพลิเคชัน GIS.
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: สร้างเลเยอร์เวกเตอร์และสายวงกลมใน Aspose.GIS สำหรับ .NET
url: /th/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง Vector Layer และ Circular String Geometry ด้วย Aspose.GIS สำหรับ .NET

## บทนำ
หากคุณกำลังสร้างแอปพลิเคชัน GIS บนแพลตฟอร์ม .NET ขั้นตอนแรกมักจะเป็น **to create vector layer** ที่เก็บฟีเจอร์เชิงพื้นที่ของคุณ Aspose.GIS สำหรับ .NET ทำให้กระบวนการนี้ง่ายขึ้นและให้คุณเพิ่มเรขาคณิตขั้นสูงเช่น circular strings ให้กับเลเยอร์เหล่านั้น ในบทเรียนนี้คุณจะได้เรียนรู้อย่างละเอียดว่า **create vector layer**, **add circular string** geometry ทำอย่างไรและบันทึกผลเป็น Shapefile — ทั้งหมดด้วยโค้ด C# ที่สะอาดและพร้อมใช้งานในสภาพแวดล้อมการผลิต

## คำตอบสั้น
- **What does “create vector layer” mean?** มันสร้างคอนเทนเนอร์ (เลเยอร์) ใหม่ที่สามารถเก็บฟีเจอร์เชิงพื้นที่เช่น จุด, เส้น, หรือโพลิกอน  
- **Which class represents a circular string?** `CircularString` จาก `Aspose.Gis.Geometries`  
- **Can I save the layer as a Shapefile?** ได้ – ใช้ `Drivers.Shapefile` เมื่อสร้างเลเยอร์  
- **Do I need a license for development?** ใบอนุญาตชั่วคราวใช้ได้สำหรับการประเมิน; ต้องมีใบอนุญาตเต็มสำหรับการผลิต  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7

## “create vector layer” คืออะไร?
Vector layer คือการจัดกลุ่มเชิงตรรกะของฟีเจอร์เวกเตอร์ (จุด, เส้น, โพลิกอน) ที่เก็บไว้ในแหล่งข้อมูลเดียว ใน Aspose.GIS คุณสร้างเลเยอร์โดยเรียก `VectorLayer.Create` พร้อมระบุเส้นทางไฟล์เป้าหมายและไดรเวอร์ที่ต้องการ (เช่น Shapefile) เมื่อเลเยอร์มีอยู่แล้ว คุณสามารถเพิ่มฟีเจอร์, กำหนดเรขาคณิต, และทำการดำเนินการเชิงพื้นที่ต่าง ๆ ได้

## ทำไมต้องเพิ่ม circular string?
Circular strings เป็นประเภท **linear geometry** ที่ประมาณเส้นโค้งโดยใช้ลำดับของจุด พวกมันมีประโยชน์สำหรับการแสดงเส้นทางโค้ง, การโค้งของแม่น้ำ, หรือฟีเจอร์ใด ๆ ที่ต้องการเส้นโค้งเรียบโดยไม่ต้องใช้เส้นส่วนเล็ก ๆ จำนวนมาก

## ข้อกำหนดเบื้องต้น
- **.NET Framework หรือ .NET Core** ที่ติดตั้งบนเครื่องของคุณ  
- **Aspose.GIS for .NET** library – ดาวน์โหลดจากเว็บไซต์อย่างเป็นทางการ **[here](https://releases.aspose.com/gis/net/)**  
- IDE เช่น **Visual Studio** หรือ **JetBrains Rider**  
- ความคุ้นเคยพื้นฐานกับการเขียนโปรแกรม **C#**

## นำเข้า Namespaces
เพิ่ม Namespaces ที่จำเป็นลงในไฟล์ C# ของคุณ:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: กำหนดเส้นทางไฟล์ผลลัพธ์
กำหนดตำแหน่งที่ Shapefile จะถูกเขียนออกไป

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

แทนที่ `"Your Document Directory"` ด้วยเส้นทางโฟลเดอร์จริงบนระบบของคุณ

### ขั้นตอนที่ 2: **Create vector layer**
เปิด `VectorLayer` ด้วยเมธอด `Create` นี่คือหัวใจของการ **create vector layer** 

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### ขั้นตอนที่ 3: สร้างฟีเจอร์ใหม่
ฟีเจอร์เป็นบันทึกเชิงพื้นที่หนึ่งรายการภายในเลเยอร์

```csharp
    var feature = layer.ConstructFeature();
```

### ขั้นตอนที่ 4: สร้าง circular string geometry
เพิ่มจุดที่กำหนดรูปทรงโค้ง ลำดับของจุดจะสร้างส่วนโค้งที่เริ่มและจบที่ตำแหน่งเดียวกัน ทำให้เป็น circular string ปิด

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### ขั้นตอนที่ 5: กำหนดเรขาคณิตและเพิ่มฟีเจอร์ลงในเลเยอร์
เชื่อมโยงเรขาคณิตกับฟีเจอร์และบันทึกลงในเลเยอร์

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

เมื่อบล็อก `using` สิ้นสุดลง เลเยอร์จะถูก flush ไปยัง Shapefile บนดิสก์โดยอัตโนมัติ

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **File path invalid** | ตรวจสอบให้แน่ใจว่าไดเรกทอรีมีอยู่และคุณมีสิทธิ์เขียน |
| **CircularString appears as a straight line** | ตรวจสอบว่าจุดถูกเพิ่มตามลำดับที่ถูกต้อง; จุดแรกและจุดสุดท้ายควรเหมือนกันสำหรับรูปแบบปิด |
| **License exception** | ใช้ใบอนุญาตชั่วคราวระหว่างการพัฒนา หรือซื้อใบอนุญาตเต็มสำหรับการใช้งานในสภาพแวดล้อมการผลิต |

## คำถามที่พบบ่อย

### Aspose.GIS for .NET รองรับทุกเวอร์ชันของ .NET Framework หรือไม่?
ใช่, Aspose.GIS for .NET ถูกออกแบบให้ทำงานกับหลายเวอร์ชันของ .NET ตั้งแต่ Framework 4.5 จนถึง .NET 8 ล่าสุด

### สามารถรวม Aspose.GIS for .NET กับไลบรารี GIS อื่นได้หรือไม่?
ได้แน่นอน! คุณสามารถอ่านข้อมูลด้วยไลบรารีอื่น, ปรับแต่งด้วย Aspose.GIS, แล้วเขียนกลับได้ด้วย API ที่ยืดหยุ่นของมัน

### Aspose.GIS for .NET รองรับการแสดงผลข้อมูลเชิงพื้นที่หรือไม่?
ใช่, ไลบรารีมียูทิลิตี้การเรนเดอร์ที่ช่วยให้คุณสร้างแผนที่และการแสดงผลของเรขาคณิตต่าง ๆ

### มีฟอรั่มชุมชนที่สามารถขอความช่วยเหลือเกี่ยวกับ Aspose.GIS for .NET ได้หรือไม่?
มี, คุณสามารถเยี่ยมชมฟอรั่ม Aspose.GIS **[here](https://forum.aspose.com/c/gis/33)** เพื่อถามคำถามและแชร์ประสบการณ์

### สามารถขอใบอนุญาตชั่วคราวเพื่อประเมิน Aspose.GIS for .NET ได้หรือไม่?
ได้เลย! ใบอนุญาตชั่วคราวสำหรับการประเมินมีให้ **[here](https://purchase.aspose.com/temporary-license/)**

### จะเพิ่มเรขาคณิตที่ซับซ้อนกว่า (เช่น MultiLineString) ลงในเลเยอร์เดียวได้อย่างไร?
สร้างอ็อบเจกต์เรขาคณิตที่เหมาะสม (เช่น `MultiLineString`), เติมด้วย `LineString` แต่ละอัน, กำหนดให้กับ `feature.Geometry`, แล้วเพิ่มฟีเจอร์ด้วย `layer.Add(feature)` เช่นเดียวกับ circular string

## FAQ (อ้างอิงอย่างรวดเร็ว)

**Q:** How do I **create vector layer** programmatically?  
**A:** เรียก `VectorLayer.Create(path, Drivers.Shapefile)` (หรือไดรเวอร์อื่น) ภายในบล็อก `using`

**Q:** What method adds points to a circular string?  
**A:** ใช้ `circularString.AddPoint(x, y)` สำหรับแต่ละพิกัด

**Q:** Can I store multiple geometries in the same layer?  
**A:** ได้, สร้างฟีเจอร์ใหม่สำหรับแต่ละเรขาคณิตและเพิ่มด้วย `layer.Add(feature)`

**Q:** What should I do if the Shapefile is not created?  
**A:** ตรวจสอบว่าไดเรกทอรีผลลัพธ์มีอยู่, คุณมีสิทธิ์เขียน, และไดรเวอร์ (`Drivers.Shapefile`) ถูกอ้างอิงอย่างถูกต้อง

**Q:** Is a license required for the evaluation build?  
**A:** ใบอนุญาตชั่วคราวเพียงพอสำหรับการพัฒนาและทดสอบ; ต้องมีใบอนุญาตเต็มสำหรับการใช้งานในสภาพแวดล้อมการผลิต

## สรุป
โดยทำตามขั้นตอนเหล่านี้ คุณจะรู้วิธี **create vector layer** และเพิ่มเรขาคณิต **circular string** ด้วย Aspose.GIS สำหรับ .NET พื้นฐานนี้ช่วยให้คุณสร้างโซลูชัน GIS ที่มีความหลากหลายมากขึ้น—ไม่ว่าจะเป็นการทำแผนที่เครือข่ายการขนส่ง, การแสดงผลข้อมูลสิ่งแวดล้อม, หรือการพัฒนาเครื่องมือวิเคราะห์เชิงพื้นที่แบบกำหนดเอง

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}