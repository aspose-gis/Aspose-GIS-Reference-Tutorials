---
date: 2026-02-10
description: เรียนรู้วิธีคำนวณศูนย์กลางของรูปทรงเรขาคณิตโดยใช้ Aspose.GIS สำหรับ .NET,
  ดึงจุดศูนย์กลางของโพลิกอนและคำนวณศูนย์กลางของมัลติพอลิกอนสำหรับการวิเคราะห์เชิงพื้นที่.
linktitle: Get Geometry Centroid
second_title: Aspose.GIS .NET API
title: วิธีคำนวณจุดศูนย์กลางของรูปทรงเรขาคณิตด้วย Aspose.GIS สำหรับ .NET
url: /th/net/geometry-analysis/get-geometry-centroid/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีคำนวณศูนย์กลางของเรขาคณิตด้วย Aspose.GIS สำหรับ .NET

## บทนำ
หากคุณกำลังทำ **C# spatial analysis** และต้องการทราบ **how to compute centroid** ของรูปทรงใด ๆ คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะพาคุณผ่านการใช้ Aspose.GIS สำหรับ .NET เพื่อ **calculate polygon centroid**, ดึงศูนย์กลางนั้นออกมา และดูว่าชิ้นส่วนเล็ก ๆ ของเรขาคณิตนี้สามารถเปิดใช้งานสถานการณ์ **integrated spatial analysis** ที่ทรงพลัง เช่น การวางป้าย, การจัดกลุ่ม, และการคำนวณระยะทางได้อย่างไร

## คำตอบสั้น
- **What is the primary method?** `GetCentroid()` บนวัตถุ `IGeometry`  
- **Which library provides it?** Aspose.GIS สำหรับ .NET  
- **How many lines of code?** น้อยกว่า 15 บรรทัดทั้งหมด (ไม่รวมคำสั่ง using)  
- **Do I need a license?** ใบอนุญาตชั่วคราวใช้ได้สำหรับการทดสอบ; ต้องมีใบอนุญาตเต็มสำหรับการใช้งานจริง  
- **Can it run on .NET 6+?** ใช่ – API รองรับอย่างเต็มที่กับ .NET Core และ .NET 5/6  

## ศูนย์กลางคืออะไรและทำไมจึงสำคัญ?
ศูนย์กลางคือจุดกึ่งกลางเชิงเรขาคณิตของรูปทรง – คิดว่าเป็น “จุดสมดุล” สำหรับ polygon, ศูนย์กลาง (หรือ **center point of polygon**) มักใช้เพื่อวางป้าย, คำนวณตำแหน่งเฉลี่ย, หรือเป็นจุดอ้างอิงในคำค้นเชิงพื้นที่ การรู้ **how to compute centroid** อย่างรวดเร็วทำให้คุณสามารถรวมคุณลักษณะการวิเคราะห์เชิงพื้นที่ได้โดยไม่ต้องเขียนสูตรคณิตศาสตร์ซับซ้อนเอง

## ทำไมต้องคำนวณศูนย์กลางของ Multipolygon?
เมื่อทำงานกับชุดของ polygon (เช่น พรมแดนประเทศที่ประกอบด้วยเกาะหลายเกาะ) คุณอาจต้อง **compute centroid of multipolygon** Aspose.GIS ให้คุณเรียก `GetCentroid()` บน `MultiPolygon` และจะคืนค่าศูนย์กลางของรูปทรงรวม ทำให้การประมวลผลแบบชุดและการแสดงแผนที่ง่ายขึ้น

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

### 1. การติดตั้ง Aspose.GIS สำหรับ .NET
ดาวน์โหลดไลบรารีจาก [Aspose.GIS for .NET website](https://releases.aspose.com/gis/net/). ทำตามคำแนะนำการติดตั้งเพื่อเพิ่มแพ็กเกจ NuGet ไปยังโปรเจกต์ของคุณ

### 2. ความคุ้นเคยกับการเขียนโปรแกรม C#
คุณควรจะคุ้นเคยกับการเขียนโค้ด C# เบื้องต้น หากคุณใหม่, ควรทบทวนสั้น ๆ เกี่ยวกับตัวแปร, คลาส, และการแสดงผลบนคอนโซล

### 3. ความเข้าใจพื้นฐานเกี่ยวกับแนวคิดทางภูมิศาสตร์
แม้ไม่จำเป็นต้องมี, การรู้ความแตกต่างระหว่าง point, line, และ polygon จะช่วยให้คุณตามตัวอย่างได้ง่ายขึ้น

## นำเข้า Namespaces
เราต้องนำคลาสของ Aspose.GIS เข้ามาในสโคป เพิ่มคำสั่ง `using` ด้านล่างนี้ที่ส่วนหัวของไฟล์ C# ของคุณ:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Namespaces เหล่านี้ทำให้คุณเข้าถึงประเภท geometry, วิธี `GetCentroid()`, และยูทิลิตี้มาตรฐานของ .NET

## วิธีคำนวณศูนย์กลางของเรขาคณิต
ด้านล่างเป็นคำแนะนำแบบขั้นตอนที่แสดงวิธี **create polygon geometry**, คำนวณศูนย์กลาง, และแสดงผลลัพธ์

### ขั้นตอนที่ 1: กำหนด Polygon
แรกเริ่ม, เรา **create polygon geometry** โดยระบุจุดยอด ตัวอย่างนี้สร้าง polygon ง่าย ๆ ที่ไม่ตัดกันเอง:

```csharp
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(1, 0),
    new Point(2, 2),
    new Point(0, 4),
    new Point(5, 5),
    new Point(6, 1),
    new Point(1, 0),
});
```

### ขั้นตอนที่ 2: ดึงศูนย์กลาง Polygon (center point of polygon)
เมื่อกำหนด polygon แล้ว, เรียก `GetCentroid()` เพื่อ **retrieve polygon centroid**:

```csharp
IPoint centroid = polygon.GetCentroid();
```

### ขั้นตอนที่ 3: แสดงพิกัดศูนย์กลาง
สุดท้าย, แสดงค่าพิกัด X และ Y ของศูนย์กลาง สตริงรูปแบบจะปัดค่าให้เหลือสองตำแหน่งทศนิยม:

```csharp
Console.WriteLine("{0:F} {1:F}", centroid.X, centroid.Y); // Output: 3.33 2.58
```

การรันโปรแกรมจะพิมพ์พิกัดศูนย์กลางลงคอนโซล, ยืนยันว่าเรขาคณิตถูกประมวลผลอย่างถูกต้อง

## ข้อผิดพลาดทั่วไป & เคล็ดลับระดับมืออาชีพ
- **Pitfall:** การให้ polygon ที่ตัดกันเองอาจทำให้ได้ศูนย์กลางที่ไม่คาดคิด  
  **Tip:** ตรวจสอบความถูกต้องของ polygon (เช่น ใช้ `IsValid` หากมี) ก่อนเรียก `GetCentroid()`
- **Pitfall:** ลืมปิดวงแหวน (จุดแรกและจุดสุดท้ายต้องเหมือนกัน)  
  **Tip:** ควรทำซ้ำจุดแรกเป็นจุดสุดท้ายเมื่อสร้าง `LinearRing`
- **Pro Tip:** สำหรับชุดข้อมูลขนาดใหญ่, คำนวณศูนย์กลางแบบขนานด้วย `Parallel.ForEach` เพื่อเร่งการประมวลผลแบบชุด
- **Pro Tip:** เมื่อทำงานกับ `MultiPolygon`, เรียก `GetCentroid()` บนคอลเลกชันโดยตรงเพื่อ **compute centroid of multipolygon** ในการเรียกเดียว

## คำถามที่พบบ่อย
### ถาม: Aspose.GIS สำหรับ .NET เข้ากันได้กับทุกเวอร์ชันของ .NET Framework หรือไม่?
**ตอบ:** Aspose.GIS สำหรับ .NET เข้ากันได้กับ .NET Framework 4.6 ขึ้นไป, ทำให้รองรับหลายเวอร์ชันอย่างกว้างขวาง

### ถาม: ฉันสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS สำหรับ .NET ได้หรือไม่?
**ตอบ:** ได้, ใบอนุญาตชั่วคราวสำหรับ Aspose.GIS สำหรับ .NET มีให้สำหรับการทดสอบ คุณสามารถรับได้จาก [temporary license page](https://purchase.aspose.com/temporary-license/)

### ถาม: Aspose.GIS สำหรับ .NET เหมาะสำหรับทั้งแอปพลิเคชันเดสก์ท็อปและเว็บหรือไม่?
**ตอบ:** แน่นอน! Aspose.GIS สำหรับ .NET สามารถผสานรวมได้อย่างราบรื่นทั้งในแอปพลิเคชันเดสก์ท็อปและเว็บ, ให้ความยืดหยุ่นในการพัฒนา

### ถาม: Aspose.GIS สำหรับ .NET มีเอกสารที่ครอบคลุมหรือไม่?
**ตอบ:** มี, เอกสารครบถ้วนสำหรับ Aspose.GIS สำหรับ .NET มีให้บน [documentation page](https://reference.aspose.com/gis/net/), ให้ข้อมูลเชิงลึกเกี่ยวกับการใช้งานและฟังก์ชันต่าง ๆ

### ถาม: ฉันจะขอความช่วยเหลือหรือเข้าร่วมชุมชนเกี่ยวกับ Aspose.GIS สำหรับ .NET อย่างไร?
**ตอบ:** สำหรับคำถาม, การสนับสนุน, หรือการมีส่วนร่วมในชุมชน, คุณสามารถเยี่ยมชมฟอรั่มเฉพาะของ Aspose.GIS [ที่นี่](https://forum.aspose.com/c/gis/33)

## คำถามที่พบบ่อย

**Q: Can I calculate the centroid of a MultiPolygon?**  
**A:** ใช่. เรียก `GetCentroid()` บนแต่ละ polygon แยกหรือบนวัตถุ `MultiPolygon`; API จะคืนค่าศูนย์กลางของรูปทรงรวม

**Q: Does the centroid calculation consider the Earth's curvature?**  
**A:** `GetCentroid()` ที่มีอยู่ทำงานในพื้นที่พิกัดของเรขาคณิต (แผนที่) สำหรับข้อมูลเชิงภูมิศาสตร์, ควรทำการแปลงเป็น CRS แผนที่ที่เหมาะสมก่อนคำนวณศูนย์กลาง

**Q: Is there a way to get the centroid of a geometry collection in one call?**  
**A:** คุณสามารถวนลูปคอลเลกชันเพื่อคำนวณศูนย์กลางแต่ละอัน, หรือใช้ `GeometryFactory` เพื่อรวมเรขาคณิตแล้วเรียก `GetCentroid()` บนผลลัพธ์ที่รวมกัน

**Q: How accurate is the centroid for very large polygons?**  
**A:** ความแม่นยำขึ้นอยู่กับความละเอียดของพิกัดและการฉายภาพ สำหรับ polygon ที่ใหญ่มากหรือซับซ้อน, ควรทำการทำให้เรขาคณิตง่ายลงก่อนเพื่อเพิ่มประสิทธิภาพ

**Q: Can I format the centroid output as GeoJSON?**  
**A:** ได้. หลังจากได้ `IPoint`, คุณสามารถทำการ serialize ด้วย `GeoJsonWriter` ของ Aspose.GIS หรือ serializer JSON ใด ๆ ที่คุณเลือก

---

**Last Updated:** 2026-02-10  
**Tested With:** Aspose.GIS 24.11 สำหรับ .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}