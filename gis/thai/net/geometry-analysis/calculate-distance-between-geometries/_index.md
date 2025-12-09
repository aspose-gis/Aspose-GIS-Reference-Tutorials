---
date: 2025-12-02
description: เรียนรู้วิธีคำนวณระยะทางระหว่างรูปทรงเรขาคณิตโดยใช้ Aspose.GIS สำหรับ
  .NET คู่มือแบบขั้นตอนนี้แสดงวิธีใช้ Aspose.GIS, รับระยะทางถึงรูปทรงเรขาคณิต, และรวมการคำนวณระยะทางเข้ากับแอปพลิเคชันของคุณ.
linktitle: How to Calculate Distance Between Geometries
second_title: Aspose.GIS .NET API
title: วิธีคำนวณระยะทางระหว่างรูปทรงเรขาคณิตด้วย Aspose.GIS
url: /th/net/geometry-analysis/calculate-distance-between-geometries/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีคำนวณระยะห่างระหว่างรูปทรงเรขาคณิตด้วย Aspose.GIS

## Introduction
หากคุณเคยต้องการรู้ **วิธีคำนวณระยะห่าง** ระหว่างสองวัตถุเชิงพื้นที่—ไม่ว่าจะเป็นเครือข่ายถนน, โซนการจัดส่ง, หรือคุณลักษณะสิ่งแวดล้อม—คู่มือนี้เหมาะสำหรับคุณ ใน .NET, Aspose.GIS ทำให้การคำนวณระยะห่างเป็นเรื่องง่าย, แม่นยำ, และมีประสิทธิภาพ เราจะเดินผ่านตัวอย่างจริงที่แสดง **วิธีใช้ Aspose.GIS**, สร้างรูปทรงเรขาคณิตง่าย ๆ, และเรียกเมธอด **GetDistanceTo** เพื่อรับระยะห่างระหว่างพวกมัน.

## Quick Answers
- **การคำนวณระยะห่าง** ใน GIS หมายถึงอะไร? It returns the shortest (Euclidean) distance between two geometries.  
- **คลาสของ Aspose.GIS ที่ให้การคำนวณนี้คืออะไร?** `Geometry.GetDistanceTo(Geometry other)`.  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง.  
- **ฉันสามารถคำนวณระยะห่างสำหรับรูปทรง 3‑D ได้หรือไม่?** ใช่, Aspose.GIS รองรับการคำนวณ 2‑D และ 3‑D.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## What is Distance Calculation in Geospatial Programming?
การคำนวณระยะห่างในโปรแกรมเชิงพื้นที่คืออะไร? การคำนวณระยะห่างวัดเส้นสั้นที่สุดที่เชื่อมต่อสองรูปทรงเรขาคณิต มันเป็นการดำเนินการหลักสำหรับงานเช่น การวิเคราะห์ความใกล้ชิด, การกำหนดเส้นทาง, การจัดกลุ่ม, และการทำดัชนีเชิงพื้นที่.

## Why Use Aspose.GIS to Calculate Distance?
- **ความแม่นยำสูง** – Uses double‑precision arithmetic.  
- **ไม่มีการพึ่งพา** – No native GIS libraries required.  
- **ข้ามแพลตฟอร์ม** – Works on Windows, Linux, and macOS with .NET Core/5+.  
- **โมเดลรูปทรงเรขาคณิตที่หลากหลาย** – Supports points, lines, polygons, and multi‑geometries out of the box.

## Prerequisites
- **Aspose.GIS for .NET** installed (download from the [Aspose.GIS for .NET releases page](https://releases.aspose.com/gis/net/)).  
- ความรู้พื้นฐานเกี่ยวกับ C# และโครงสร้างโปรเจกต์ .NET.  
- สภาพแวดล้อมการพัฒนา เช่น Visual Studio 2022 หรือ VS Code.

## Import Namespaces
Before you can start using Aspose.GIS, add the required namespaces to your C# file:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Step 1: Create a Polygon Geometry
```csharp
var polygon = new Polygon();
```
We start with an empty polygon that will later represent a rectangular area.

เราเริ่มด้วยโพลิกอนว่างเปล่าที่ต่อไปจะเป็นตัวแทนของพื้นที่สี่เหลี่ยม.

### Step 2: Define the Polygon Exterior Ring
```csharp
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
});
```
The exterior ring is a closed loop of points that defines the polygon’s boundary. In this example we create a 1 × 1 square.

วงแหวนภายนอกคือวงปิดของจุดที่กำหนดขอบเขตของโพลิกอน ในตัวอย่างนี้เราสร้างสี่เหลี่ยม 1 × 1.

### Step 3: Create a LineString Geometry
```csharp
var line = new LineString();
```
A `LineString` is a series of connected line segments. We’ll use it to represent a road or a path.

`LineString` คือชุดของส่วนเส้นที่เชื่อมต่อกัน เราจะใช้มันเพื่อแทนถนนหรือเส้นทาง.

### Step 4: Add Points to the LineString
```csharp
line.AddPoint(2, 0);
line.AddPoint(1, 3);
```
These two points give the line a slanted shape that does not intersect the polygon, which makes the distance calculation interesting.

สองจุดนี้ทำให้เส้นมีรูปแบบเอียงที่ไม่ตัดกับโพลิกอน ซึ่งทำให้การคำนวณระยะห่างน่าสนใจ.

### Step 5: Calculate the Distance
```csharp
double distance = polygon.GetDistanceTo(line);
```
Here we **get distance to geometry** by calling `GetDistanceTo`. Aspose.GIS computes the shortest distance between the polygon’s edge and the line.

ที่นี่เรา **รับระยะห่างถึงรูปทรงเรขาคณิต** โดยเรียก `GetDistanceTo`. Aspose.GIS คำนวณระยะสั้นที่สุดระหว่างขอบของโพลิกอนและเส้น.

### Step 6: Output the Result
```csharp
Console.WriteLine(distance.ToString("F")); // 0.63
```
The result is printed with two decimal places (`0.63`). This value represents the minimum Euclidean distance between the square and the line.

ผลลัพธ์จะพิมพ์ด้วยทศนิยมสองตำแหน่ง (`0.63`). ค่านี้แสดงระยะ Euclidean ขั้นต่ำระหว่างสี่เหลี่ยมและเส้น.

## Common Use Cases
- **โลจิสติกส์:** ค้นหาคลังสินค้าที่ใกล้ที่สุดกับเส้นทางการจัดส่ง.  
- **การเฝ้าระวังสิ่งแวดล้อม:** วัดระยะห่างของควันมลพิษจากพื้นที่คุ้มครอง.  
- **การวางผังเมือง:** กำหนดระยะห่างระหว่างโครงสร้างพื้นฐานที่เสนอและสถานที่สำคัญที่มีอยู่.

## Troubleshooting & Tips
- **ระบบพิกัดสำคัญ:** Ensure both geometries use the same CRS (coordinate reference system) before calculating distance.  
- **ประสิทธิภาพ:** For large datasets, consider spatial indexing (R‑tree) to avoid O(N²) comparisons.  
- **ความแม่นยำ:** If you need geodesic (great‑circle) distances, transform coordinates to a suitable projection first.

## FAQ's
### Is Aspose.GIS for .NET compatible with all .NET frameworks?
ใช่, Aspose.GIS for .NET เข้ากันได้กับ .NET Framework 4.6 ขึ้นไป.

### Can I use Aspose.GIS for .NET to perform complex spatial analyses?
แน่นอน! Aspose.GIS for .NET มีฟังก์ชันหลากหลายสำหรับงานวิเคราะห์เชิงพื้นที่ขั้นสูง.

### Does Aspose.GIS for .NET support both 2D and 3D geometries?
ใช่, คุณสามารถทำงานกับรูปทรง 2D และ 3D ด้วย Aspose.GIS for .NET.

### Can I integrate Aspose.GIS for .NET with other GIS libraries?
Aspose.GIS for .NET ให้การทำงานร่วมกับไลบรารี GIS อื่น ๆ ทำให้คุณสามารถใช้ฟังก์ชันเพิ่มเติมได้.

### Is technical support available for Aspose.GIS for .NET users?
ใช่, ผู้ใช้ Aspose.GIS for .NET สามารถเข้าถึงการสนับสนุนทางเทคนิคผ่าน [forums](https://forum.aspose.com/c/gis/33) ของ Aspose.

## Frequently Asked Questions

**Q: How accurate is the distance returned by `GetDistanceTo`?**  
A: The method uses double‑precision arithmetic and follows the OGC Simple Features Specification, providing sub‑meter accuracy for typical planar coordinates.

**ถาม:** ระยะทางที่ `GetDistanceTo` คืนค่ามีความแม่นยำแค่ไหน?  
**ตอบ:** เมธอดใช้การคำนวณแบบ double‑precision และสอดคล้องกับ OGC Simple Features Specification, ให้ความแม่นยำระดับใต้เมตรสำหรับพิกัดระนาบทั่วไป.

**Q: Can I calculate distance between a `Point` and a `Polygon`?**  
A: Yes—simply call `point.GetDistanceTo(polygon)` (or the reverse) and Aspose.GIS will return the shortest distance from the point to the polygon’s edge.

**ถาม:** ฉันสามารถคำนวณระยะห่างระหว่าง `Point` กับ `Polygon` ได้หรือไม่?  
**ตอบ:** ได้—เพียงเรียก `point.GetDistanceTo(polygon)` (หรือกลับกัน) แล้ว Aspose.GIS จะคืนค่าระยะสั้นที่สุดจากจุดถึงขอบของโพลิกอน.

**Q: Does the API support batch distance calculations?**  
A: While there isn’t a single batch method, you can loop over collections of geometries and reuse the same `GetDistanceTo` call efficiently.

**ถาม:** API รองรับการคำนวณระยะห่างแบบแบตช์หรือไม่?  
**ตอบ:** แม้ว่าจะไม่มีเมธอดแบตช์เดียว, คุณสามารถวนลูปผ่านคอลเลกชันของรูปทรงและใช้การเรียก `GetDistanceTo` เดียวกันอย่างมีประสิทธิภาพ.

**Q: What happens if the geometries intersect?**  
A: The method returns `0.0` because the shortest distance between intersecting geometries is zero.

**ถาม:** จะเกิดอะไรขึ้นหากรูปทรงตัดกัน?  
**ตอบ:** เมธอดจะคืนค่า `0.0` เนื่องจากระยะสั้นที่สุดระหว่างรูปทรงที่ตัดกันคือศูนย์.

**Q: Is there a way to get the nearest points on each geometry?**  
A: Yes—use `Geometry.GetNearestPoints(Geometry other)` which returns a tuple containing the closest points on both geometries.

**ถาม:** มีวิธีใดบ้างที่จะได้จุดที่ใกล้ที่สุดบนแต่ละรูปทรงหรือไม่?  
**ตอบ:** มี—ใช้ `Geometry.GetNearestPoints(Geometry other)` ซึ่งจะคืนค่า tuple ที่มีจุดที่ใกล้ที่สุดบนทั้งสองรูปทรง.

## Conclusion
การคำนวณระยะห่างระหว่างรูปทรงเป็นการดำเนินการพื้นฐานในแอปพลิเคชัน .NET ที่เปิดใช้ GIS ใด ๆ ด้วยการทำตามขั้นตอนข้างต้น คุณจะรู้ **วิธีคำนวณระยะห่าง** ด้วย Aspose.GIS, **วิธีใช้ Aspose** เพื่อสร้างและจัดการรูปทรง, และวิธีดึง **ระยะห่างถึงรูปทรง** ด้วยการเรียกเมธอดเดียว ลองทดลองกับรูปทรงต่าง ๆ, ระบบพิกัด, และชุดข้อมูลขนาดใหญ่เพื่อดูว่าความสามารถนี้สามารถขับเคลื่อนโครงการวิเคราะห์เชิงพื้นที่ต่อไปของคุณได้อย่างไร.

---

**อัปเดตล่าสุด:** 2025-12-02  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}