---
date: 2025-12-09
description: เรียนรู้วิธีตรวจสอบว่าจุดอยู่ภายในรูปหลายเหลี่ยมโดยใช้ Aspose.GIS สำหรับ
  .NET คู่มือแบบขั้นตอนต่อขั้นตอนเพื่อรับจุดบนพื้นผิว สร้างรูปหลายเหลี่ยมด้วย C# และดึงจุดบนรูปหลายเหลี่ยม.
linktitle: Check Point Inside Polygon and Get Point on Surface
second_title: Aspose.GIS .NET API
title: ตรวจสอบจุดอยู่ภายในรูปหลายเหลี่ยมและหาจุดบนพื้นผิว
url: /th/net/geometry-analysis/get-point-on-geometry-surface/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตรวจสอบจุดภายในรูปหลายเหลี่ยมและรับจุดบนพื้นผิว

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **how to check point inside polygon** ด้วย Aspose.GIS for .NET และดูวิธี **get point on surface** ของรูปทรงเราคณิต เราจะเดินผ่านการสร้างรูปหลายเหลี่ยมใน C# การดึงจุดที่อยู่บนพื้นผิวของรูปหลายเหลี่ยม และการตรวจสอบว่าจุดนั้นอยู่ภายในรูปหลายเหลี่ยมจริงหรือไม่ เมื่อเสร็จคุณจะมีโค้ดสแนปช็อตพร้อมใช้งานที่สามารถใส่ลงในแอปพลิเคชันเชิงพื้นที่ .NET ใดก็ได้

## คำตอบสั้น
- **What does “check point inside polygon” mean?** มันตรวจสอบว่าพิกัดที่กำหนดอยู่ภายในขอบเขตของรูปหลายเหลี่ยมหรือไม่  
- **Which method returns a point on a polygon’s interior?** `GetPointOnSurface()` คืนค่าจุดที่รับประกันว่าจะอยู่ภายในรูปหลายเหลี่ยม  
- **Do I need a license to run the example?** การทดลองใช้ฟรีสามารถใช้สำหรับการประเมิน; จำเป็นต้องมีไลเซนส์เต็มสำหรับการใช้งานจริง  
- **Which .NET versions are supported?** .NET Framework, .NET Core, และ .NET Standard ทั้งหมดรองรับ  
- **How long does the implementation take?** ประมาณ 5‑10 นาทีสำหรับการคัดลอก, คอมไพล์, และรัน  

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

### การตั้งค่าสภาพแวดล้อม
1. ติดตั้ง Aspose.GIS for .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.GIS for .NET จาก [here](https://releases.aspose.com/gis/net/).  
2. ตั้งค่าสภาพแวดล้อมการพัฒนา: ตรวจสอบว่าคุณมีสภาพแวดล้อมการพัฒนา .NET ที่ทำงานได้ หากไม่มี คุณสามารถตั้งค่า Visual Studio หรือสภาพแวดล้อมการพัฒนา .NET อื่น ๆ ที่คุณเลือกได้  
3. ความรู้พื้นฐานของ C#: ทำความคุ้นเคยกับพื้นฐานของภาษาโปรแกรม C# หากคุณยังไม่คุ้นเคย  
4. เข้าถึงเอกสารอ้างอิง: เก็บ [documentation](https://reference.aspose.com/gis/net/) ไว้ใกล้มือเพื่อใช้เป็นอ้างอิงตลอดบทแนะนำ  

## นำเข้า Namespaces
ก่อนที่เราจะดำดิ่งสู่การทำงาน, ให้เริ่มต้นด้วยการนำเข้า Namespaces ที่จำเป็น:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

เมื่อเราตั้งค่าสภาพแวดล้อมและนำเข้า Namespaces ที่จำเป็นแล้ว, เราจะแบ่งตัวอย่างออกเป็นหลายขั้นตอนเพื่อทำความเข้าใจให้ดียิ่งขึ้น

## วิธีสร้าง Polygon ด้วย C#  
ขั้นแรก, เราต้อง **create a polygon** geometry. เรากำหนดวงแหวนภายนอกของรูปหลายเหลี่ยมโดยระบุจุดยอดของมัน

```csharp
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(0, 0),
});
```

## วิธีดึง Point บนพื้นผิว  
ต่อไป, เราจะดึงจุดบนพื้นผิวของรูปหลายเหลี่ยมโดยใช้เมธอด `GetPointOnSurface()` ขั้นตอนนี้คือ **get point on surface**

```csharp
IPoint pointOnSurface = polygon.GetPointOnSurface();
```

## วิธีตรวจสอบ Point ภายใน Polygon  
เราสามารถตรวจสอบว่าจุดที่ดึงมานั้นอยู่ภายในรูปหลายเหลี่ยมหรือไม่โดยใช้เมธอด `SpatiallyContains()` ซึ่งแสดงให้เห็นการ **retrieving point on polygon** แล้วทำการตรวจสอบ

```csharp
Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // True
```

## ปัญหาทั่วไปและวิธีแก้
- **Empty polygon** – ตรวจสอบให้แน่ใจว่าวงแหวนภายนอกมีจุดยอดที่แตกต่างอย่างน้อยสามจุด; หากไม่เช่นนั้น `GetPointOnSurface()` อาจคืนค่าจุดที่ไม่ได้กำหนด  
- **Clockwise vs. Counter‑clockwise** – การวางแนวของวงแหวนไม่ส่งผลต่อการตรวจสอบการบรรจุ, แต่การรักษาลำดับการวนที่สม่ำเสมอช่วยในปฏิบัติการเชิงพื้นที่อื่น ๆ  
- **Coordinate System** – ตัวอย่างนี้ใช้ระบบพิกัดคาร์ทีเซียนแบบง่าย; เมื่อทำงานกับพิกัดโลกจริง, ตรวจสอบให้แน่ใจว่า CRS (coordinate reference system) ถูกกำหนดอย่างถูกต้อง  

## สรุป
ในบทแนะนำนี้, เราได้เรียนรู้วิธี **check point inside polygon** ด้วย Aspose.GIS for .NET, รับ **point on surface**, และตรวจสอบการบรรจุของมัน ด้วย Aspose.GIS การจัดการข้อมูลเชิงพื้นที่จึงเป็นเรื่องมีประสิทธิภาพและตรงไปตรงมา ทำให้ผู้พัฒนาสามารถสร้างแอปพลิเคชันเชิงพื้นที่ที่แข็งแกร่งได้

## คำถามที่พบบ่อย
### Aspose.GIS รองรับกับเฟรมเวิร์ก .NET อื่น ๆ หรือไม่?
ใช่, Aspose.GIS รองรับเฟรมเวิร์ก .NET ต่าง ๆ รวมถึง .NET Framework, .NET Core, และ .NET Standard.

### ฉันสามารถลอง Aspose.GIS ก่อนซื้อได้หรือไม่?
ได้, คุณสามารถดาวน์โหลดการทดลองใช้ฟรีของ Aspose.GIS จาก [here](https://releases.aspose.com/).

### ฉันจะขอรับการสนับสนุนสำหรับ Aspose.GIS ได้อย่างไร?
คุณสามารถเยี่ยมชมฟอรั่ม Aspose.GIS [here](https://forum.aspose.com/c/gis/33) เพื่อขอความช่วยเหลือและโต้ตอบกับผู้ใช้และนักพัฒนาคนอื่น ๆ

### Aspose.GIS มีไลเซนส์ชั่วคราวหรือไม่?
ใช่, คุณสามารถรับไลเซนส์ชั่วคราวสำหรับ Aspose.GIS จาก [here](https://purchase.aspose.com/temporary-license/).

### ฉันสามารถซื้อ Aspose.GIS ได้จากที่ไหน?
คุณสามารถซื้อ Aspose.GIS ได้จากหน้าการสั่งซื้อ [here](https://purchase.aspose.com/buy).

**Additional Q&A**

**Q:** วิธีที่ดีที่สุดในการจัดการชุดข้อมูลรูปหลายเหลี่ยมขนาดใหญ่คืออะไร?  
**A:** โหลดเรขาคณิตแบบ lazy และใช้ instance ของ `GeometryFactory` เพียงหนึ่งตัวเพื่อ ลดการใช้หน่วยความจำ  

**Q:** ฉันสามารถดึงหลายจุดบนพื้นผิวได้หรือไม่?  
**A:** `GetPointOnSurface()` คืนค่าจุดภายในหนึ่งจุด เพื่อสร้างหลายจุดภายใน, คุณสามารถใช้ตัวสร้างจุดสุ่มภายในกล่องขอบเขตของรูปหลายเหลี่ยมและทดสอบแต่ละจุดด้วย `SpatiallyContains()`  

**Q:** สามารถส่งออกรูปหลายเหลี่ยมเป็น shapefile หลังจากสร้างได้หรือไม่?  
**A:** ได้, Aspose.GIS มีคลาส `FeatureSet` และ `ShapefileWriter` เพื่อเขียนเรขาคณิตเป็นรูปแบบ Shapefile  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2025-12-09  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose