---
date: 2025-12-07
description: เรียนรู้วิธีทำการโอเวอร์เลย์ในบทแนะนำการโอเวอร์เลย์เชิงพื้นที่นี้โดยใช้
  Aspose.GIS สำหรับ .NET. เชี่ยวชาญการตัดกัน, การรวม, ความแตกต่าง, และความแตกต่างสมมาตร.
language: th
linktitle: Find Geometry Overlays
second_title: Aspose.GIS .NET API
title: วิธีทำการดำเนินการโอเวอร์เลย์ด้วย Aspose.GIS สำหรับ .NET
url: /net/geometry-analysis/find-geometry-overlays/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการทำการดำเนินการ Overlay ด้วย Aspose.GIS for .NET

## บทนำ
การวิเคราะห์ overlay เป็นเทคนิคหลักใน **บทแนะนำการ overlay เชิงพื้นที่**—มันช่วยให้คุณรวม, เปรียบเทียบ, และสกัดข้อมูลเชิงลึกจากหลายชั้นภูมิศาสตร์ ในคู่มือนี้คุณจะได้เรียนรู้ **วิธีการทำการดำเนินการ overlay** เช่น Intersection, Union, Difference, และ Symmetric Difference ด้วยไลบรารี Aspose.GIS for .NET ที่ทรงพลัง เมื่อจบบทเรียนคุณจะสามารถนำวิธีเหล่านี้ไปใช้กับปัญหา GIS ในโลกจริง เช่น การวางแผนการใช้ที่ดิน, การศึกษาผลกระทบต่อสิ่งแวดล้อม, และการเพิ่มประสิทธิภาพเส้นทาง

## คำตอบสั้น
- **Overlay operation คืออะไร?** วิธีเชิงพื้นที่ที่รวมรูปทรงสองรูปเพื่อสร้างรูปทรงใหม่ (intersection, union ฯลฯ)  
- **ไลบรารีใดจัดการ overlay ใน .NET?** Aspose.GIS for .NET  
- **ใช้เวลานานเท่าไหร่ในการทำตัวอย่างพื้นฐาน?** ประมาณ 10‑15 นาที  
- **ต้องมีลิขสิทธิ์หรือไม่?** มีรุ่นทดลองฟรี; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **สามารถรันบน .NET Core / .NET 6+ ได้หรือไม่?** ได้—Aspose.GIS รองรับ .NET runtime สมัยใหม่ทั้งหมด

## Overlay Operation คืออะไร?
การดำเนินการ overlay จะรับรูปทรงเรขาคณิตสองรูปและคำนวณรูปใหม่ตามความสัมพันธ์เชิงพื้นที่ของพวกมัน  
- **Intersection** คืนพื้นที่ที่เป็นส่วนร่วมของทั้งสองรูป  
- **Union** รวมรูปทั้งสองเป็นรูปทรงเดียว  
- **Difference** ลบรูปหนึ่งออกจากอีกรูปหนึ่ง  
- **Symmetric Difference** คืนส่วนที่เป็นของรูปใดรูปหนึ่งแต่ไม่ใช่ของทั้งสองพร้อมกัน

## ทำไมต้องใช้ Aspose.GIS สำหรับ Overlay?
Aspose.GIS มี API ที่สะอาดและจัดการทั้งหมดในระดับ Managed ทำให้คุณไม่ต้องกังวลเรื่องคณิตศาสตร์ระดับล่าง สามารถทำงานข้ามแพลตฟอร์ม, จัดการชุดข้อมูลขนาดใหญ่ได้อย่างมีประสิทธิภาพ, และผสานรวมกับคอมโพเนนต์ .NET อื่น ๆ ได้อย่างราบรื่น

## ข้อกำหนดเบื้องต้น
- สภาพแวดล้อมการพัฒนา .NET ที่ทำงานได้ (Visual Studio, VS Code, หรือ .NET CLI)  
- ไลบรารี Aspose.GIS for .NET – ดาวน์โหลดเวอร์ชันล่าสุดจาก [official site](https://releases.aspose.com/gis/net/)  

### นำเข้า Namespaces
ก่อนที่คุณจะเริ่มใช้ Aspose.GIS for .NET คุณต้องนำเข้า namespaces ที่จำเป็นเข้าสู่โปรเจกต์ของคุณ

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## วิธีการทำการดำเนินการ Overlay ใน .NET
ต่อไปนี้เป็นขั้นตอนแบบละเอียดในการสร้างสองโพลิกอนและใช้แต่ละวิธี overlay

### ขั้นตอนที่ 1: สร้างอ็อบเจ็กต์ Polygon
แรกเริ่ม เรากำหนดโพลิกอนสี่เหลี่ยมจัตุรัสสองรูปที่ทับกันบางส่วน ซึ่งจะเป็นข้อมูลทดสอบของเรา

```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```

### ขั้นตอนที่ 2: ทำการดำเนินการ Intersection
**Intersection** ให้เราพื้นที่ที่ทับซ้อนของสองโพลิกอน

```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Polygon
```

### ขั้นตอนที่ 3: พิมพ์จุด Intersection
เราใช้เมธอดช่วย (`PrintRing`) เพื่อแสดงพิกัดของโพลิกอนผลลัพธ์

```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```

### ขั้นตอนที่ 4: ทำการดำเนินการ Union
**Union** รวมโพลิกอนทั้งสองเป็นรูปทรงเดียวที่ครอบคลุมพื้นที่ทั้งหมดของโพลิกอนใดโพลิกอนหนึ่ง

```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Polygon
```

### ขั้นตอนที่ 5: พิมพ์จุด Union
แสดงพิกัดของเรขาคณิตที่รวมกันแล้ว

```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```

### ขั้นตอนที่ 6: ทำการดำเนินการ Difference
**Difference** ลบ `polygon2` ออกจาก `polygon1` ทำให้เหลือเฉพาะส่วนของ `polygon1` ที่ไม่ทับกับ `polygon2`

```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Polygon
```

### ขั้นตอนที่ 7: พิมพ์จุด Difference
แสดงจุดยอดที่เหลือหลังการลบ

```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```

### ขั้นตอนที่ 8: ทำการดำเนินการ Symmetric Difference
**Symmetric Difference** คืนพื้นที่ที่เป็นของโพลิกอนใดโพลิกอนหนึ่งแต่ไม่เป็นของทั้งสองพร้อมกัน ผลลัพธ์คือ `MultiPolygon`

```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // MultiPolygon
```

### ขั้นตอนที่ 9: พิมพ์ Polygons ของ Symmetric Difference
วนลูปผ่านแต่ละโพลิกอนใน `MultiPolygon` แล้วพิมพ์จุดของมัน

```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| ผลลัพธ์ `null` จาก `Intersection` | โพลิกอนไม่ทับกันจริง | ตรวจสอบพิกัดหรือใช้การตรวจสอบ `Intersects` ก่อนเรียก `Intersection` |
| ได้ `MultiPolygon` ที่ไม่คาดคิดจาก `SymDifference` | Symmetric Difference อาจสร้างส่วนที่แยกจากกัน | แคสต์เป็น `IMultiPolygon` แล้ววนลูปตามตัวอย่าง |
| ชะลอตัวเมื่อทำงานกับชุดข้อมูลขนาดใหญ่ | ทุกการดำเนินการคำนวณเรขาคณิตใหม่ทั้งหมด | ใช้ผลลัพธ์กลางซ้ำหรือทำให้รูปทรงง่ายลงด้วย `Simplify()` ก่อนทำ overlay |

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถใช้ Aspose.GIS for .NET ในโครงการเชิงพาณิชย์ได้หรือไม่?**  
ตอบ: ได้, Aspose.GIS for .NET สามารถใช้ได้ทั้งในโครงการเชิงพาณิชย์และไม่เชิงพาณิชย์โดยมีลิขสิทธิ์ที่ถูกต้อง

**ถาม: มีเวอร์ชันทดลองของ Aspose.GIS for .NET หรือไม่?**  
ตอบ: มี, คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรีได้จาก [ที่นี่](https://releases.aspose.com/)

**ถาม: จะขอรับการสนับสนุนสำหรับ Aspose.GIS for .NET ได้อย่างไร?**  
ตอบ: คุณสามารถรับการสนับสนุนจากฟอรั่มชุมชน Aspose.GIS [ที่นี่](https://forum.aspose.com/c/gis/33)

**ถาม: มีลิขสิทธิ์ชั่วคราวสำหรับ Aspose.GIS for .NET หรือไม่?**  
ตอบ: มี, ลิขสิทธิ์ชั่วคราวพร้อมให้ใช้สำหรับการทดสอบและประเมินผล คุณสามารถรับได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/)

**ถาม: สามารถซื้อ Aspose.GIS for .NET ได้โดยตรงหรือไม่?**  
ตอบ: ได้, คุณสามารถสั่งซื้อ Aspose.GIS for .NET ได้จากเว็บไซต์ [ที่นี่](https://purchase.aspose.com/buy)

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}