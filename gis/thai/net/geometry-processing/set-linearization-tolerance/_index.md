---
date: 2025-12-21
description: เรียนรู้วิธีสร้างเลเยอร์เวกเตอร์ ตั้งค่าความทนต่อการทำเส้นตรง (linearization
  tolerance) และเพิ่มฟีเจอร์ลงในเลเยอร์โดยใช้ Aspose.GIS สำหรับ .NET. ปฏิบัติตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อส่งออกไฟล์
  GeoJSON.
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: สร้างเลเยอร์เวกเตอร์และตั้งค่าความทนทานต่อการทำเชิงเส้นโดยใช้ Aspose.GIS สำหรับ
  .NET
url: /th/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง Vector Layer และตั้งค่า Linearization Tolerance ด้วย Aspose.GIS for .NET

## บทนำ
หากคุณต้องการ **สร้าง vector layer** ไฟล์, ควบคุมความแม่นยำของเส้นโค้ง, และส่งออกผลลัพธ์เป็นเอกสาร GeoJSON, Aspose.GIS for .NET ทำให้ขั้นตอนเหล่านี้เป็นเรื่องง่าย ในบทเรียนนี้คุณจะได้เรียนรู้วิธีกำหนดค่า GeoJSON options, ตั้งค่า linearization tolerance, และ **เพิ่ม feature ไปยัง layer** ทั้งหมดนี้โดยรักษาโค้ดให้สะอาดและพร้อมใช้งานในสภาพแวดล้อมการผลิต

## คำตอบอย่างรวดเร็ว
- **“สร้าง vector layer” หมายถึงอะไร?** มันสร้างชุดข้อมูล GIS เวกเตอร์ใหม่ (เช่น ไฟล์ GeoJSON) ที่สามารถเก็บเรขาคณิตและแอตทริบิวต์ได้  
- **จะตั้งค่าความทนทานอย่างไร?** ใช้ property `LinearizationTolerance` ของ `GeoJsonOptions`  
- **ฉันสามารถส่งออกไฟล์ GeoJSON ได้หรือไม่?** ได้ — เพียงสร้าง `VectorLayer` ด้วย driver `Drivers.GeoJson`  
- **ต้องมีลิขสิทธิ์หรือไม่?** ลิขสิทธิ์ Aspose.GIS ที่ถูกต้องจะเปิดใช้งานคุณสมบัติทั้งหมด; ลิขสิทธิ์ชั่วคราวใช้สำหรับการประเมินผลได้  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7

## “สร้าง vector layer” คืออะไร?
การสร้าง vector layer หมายถึงการเริ่มต้นคอนเทนเนอร์ GIS ใหม่ (เช่น ไฟล์ GeoJSON) ที่สามารถเก็บฟีเจอร์เรขาคณิตต่าง ๆ เช่น จุด, เส้น, และโพลิกอน Layer นี้จะเป็นเป้าหมายสำหรับเรขาคณิตใด ๆ ที่คุณสร้างและแอตทริบิวต์ใด ๆ ที่คุณแนบ

## ทำไมต้องกำหนดค่า GeoJSON options?
การกำหนดค่า GeoJSON options — โดยเฉพาะ **linearization tolerance** — ทำให้แน่ใจว่าเรขาคณิตโค้ง (เช่น `CircularString`) ถูกประมาณด้วยความแม่นยำที่ตรงตามความต้องการของแอปพลิเคชันของคุณ ขั้นตอนนี้สำคัญเมื่อคุณต้อง **ส่งออกไฟล์ GeoJSON** เพื่อใช้ในเว็บแมพหรือการวิเคราะห์เชิงพื้นที่ต่อไป

## ข้อกำหนดเบื้องต้น
ก่อนเริ่ม, โปรดตรวจสอบว่าคุณมี:

1. **Visual Studio** ที่ติดตั้งแล้ว (เวอร์ชันล่าสุดใดก็ได้)  
2. **ลิขสิทธิ์ Aspose.GIS** (หรือคีย์ประเมินผลชั่วคราว)  
3. ไลบรารี **Aspose.GIS for .NET** ที่ดาวน์โหลดและอ้างอิงในโปรเจกต์ของคุณ  
4. ความคุ้นเคยพื้นฐานกับ **C#**

## นำเข้า Namespaces
ก่อนอื่นให้นำเข้า namespaces ที่จำเป็นเพื่อให้คอมไพเลอร์รู้ว่าจะหาคลาส GIS จากที่ไหน:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: กำหนดค่า GeoJSON Options (วิธีตั้ง tolerance)
เราจะสร้างอ็อบเจกต์ `GeoJsonOptions` และบอก Aspose.GIS ว่าเราต้องการให้เรขาคณิตที่ทำ linearization มีความใกล้เคียงกับเส้นโค้งต้นฉบับเท่าใด

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### ขั้นตอนที่ 2: กำหนดเส้นทางออก (วิธีส่งออก GeoJSON)
ระบุที่ที่ไฟล์ผลลัพธ์จะถูกบันทึก แทนที่ placeholder ด้วยโฟลเดอร์จริงของคุณ

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### ขั้นตอนที่ 3: **สร้าง Vector Layer** ด้วยตัวเลือกที่กำหนดไว้
ตอนนี้เราจะ **สร้าง vector layer** จริง ๆ ด้วยเมธอด `VectorLayer.Create` บล็อก `using` จะรับประกันว่าทรัพยากรจะถูกปล่อยอย่างถูกต้อง

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### ขั้นตอนที่ 4: สร้าง Geometry (เช่น circular string)
ที่นี่เราจะสร้างเรขาคณิตตัวอย่าง — `CircularString` คุณสามารถเปลี่ยนเป็น WKT ที่ถูกต้องใด ๆ ก็ได้

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### ขั้นตอนที่ 5: **เพิ่ม Feature ไปยัง Layer** และบันทึก
สุดท้ายเราจะสร้างฟีเจอร์, กำหนดเรขาคณิตให้, แล้วเพิ่มเข้าไปใน layer นี่คือหัวใจของการทำ **add feature to layer**

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

เมื่อบล็อก `using` สิ้นสุดลง, layer จะถูกเขียนลงไฟล์ที่กำหนดใน `path` โดยอัตโนมัติ ทำให้คุณได้ไฟล์ GeoJSON พร้อมใช้งาน

## ปัญหาที่พบบ่อยและเคล็ดลับ
- **เส้นทางไม่ถูกต้อง** — ตรวจสอบให้แน่ใจว่าไดเรกทอรีมีอยู่และคุณมีสิทธิ์เขียน  
- **Tolerance ต่ำเกินไป** — การตั้งค่า `LinearizationTolerance` เป็นค่าที่เล็กมากอาจทำให้ขนาดไฟล์เพิ่มขึ้นอย่างมหาศาล ปรับตามความต้องการความแม่นยำของคุณ  
- **ข้อผิดพลาดลิขสิทธิ์** — หากเห็นคำเตือนเกี่ยวกับลิขสิทธิ์, ตรวจสอบว่าไฟล์ลิขสิทธิ์ถูกโหลดอย่างถูกต้องก่อนเรียกใช้ Aspose.GIS ใด ๆ

## คำถามที่พบบ่อย

**ถาม: Aspose.GIS for .NET รองรับเฟรมเวิร์ก .NET อื่น ๆ หรือไม่?**  
ตอบ: ใช่, ทำงานกับ .NET Framework, .NET Core, และ .NET 5/6/7  

**ถาม: ฉันสามารถใช้ Aspose.GIS ในโครงการเชิงพาณิชย์ได้หรือไม่?**  
ตอบ: แน่นอน. ลิขสิทธิ์เชิงพาณิชย์จะลบข้อจำกัดการประเมินผลทั้งหมด  

**ถาม: Aspose.GIS รองรับฟอร์แมต GIS อื่น ๆ นอกจาก GeoJSON หรือไม่?**  
ตอบ: ใช่, รองรับ Shapefile, KML, GML, และอื่น ๆ อีกมากมาย  

**ถาม: มีเวอร์ชันทดลองให้ดาวน์โหลดหรือไม่?**  
ตอบ: คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรีจากเว็บไซต์ Aspose  

**ถาม: จะหาการสนับสนุนได้จากที่ไหน?**  
ตอบ: ใช้ฟอรั่มของ Aspose หรือลิงก์สนับสนุนในส่วนทรัพยากร  

## สรุป
โดยทำตามขั้นตอนเหล่านี้คุณจะรู้วิธี **สร้าง vector layer**, ตั้งค่า linearization tolerance, และ **เพิ่ม feature ไปยัง layer** เพื่อสร้าง **ส่งออกไฟล์ GeoJSON** อย่างราบรื่น สำรวจประเภทเรขาคณิตและการจัดการแอตทริบิวต์เพิ่มเติมเพื่อใช้ประโยชน์จาก Aspose.GIS อย่างเต็มที่ในโครงการ GIS บน .NET ของคุณ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2025-12-21  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

---