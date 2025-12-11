---
date: 2025-12-11
description: เรียนรู้วิธีนับเรขาคณิตและเพิ่มเรขาคณิตลงในคอลเลกชันโดยใช้ Aspose.GIS
  สำหรับ .NET คู่มือทีละขั้นตอนพร้อมตัวอย่างโค้ดสำหรับนักพัฒนา
linktitle: Count Geometries in Geometry
second_title: Aspose.GIS .NET API
title: วิธีนับเรขาคณิตใน Geometry ด้วย Aspose.GIS
url: /th/net/geometry-creation/count-geometries-in-geometry/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีนับเรขาคณิตใน Geometry ด้วย Aspose.GIS

## Introduction
หากคุณต้องการ **how to count geometries** ภายในรูปทรงเชิงซ้อน Aspose.GIS for .NET ทำให้เป็นเรื่องง่าย ไม่ว่าคุณจะกำลังสร้างแอปพลิเคชันแผนที่ บริการตำแหน่ง หรือเครื่องมือวิเคราะห์เชิงพื้นที่ การนับเรขาคณิตแต่ละรายการในคอลเลกชันเป็นงานพื้นฐาน ในบทเรียนนี้เราจะเดินผ่านการสร้างเรขาคณิตง่าย ๆ การเพิ่มเข้าไปในคอลเลกชัน และสุดท้ายใช้ API เพื่อดึงจำนวนเรขาคณิต

## Quick Answers
- **วิธีหลักคืออะไร?** ใช้ property `Count` ของ `GeometryCollection`  
- **ต้องใช้ namespace ใด?** `Aspose.Gis.Geometries`  
- **ต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** การทดลองใช้ฟรีเพียงพอสำหรับการประเมิน; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง  
- **สามารถเพิ่มประเภทเรขาคณิตที่แตกต่างกันได้หรือไม่?** ได้ – จุด, เส้น, โพลิกอน ฯลฯ สามารถเพิ่มลงในคอลเลกชันเดียวกันได้  
- **รองรับ .NET Core หรือไม่?** แน่นอน, Aspose.GIS รองรับ .NET Framework และ .NET Core  

## What is “how to count geometries”?
การนับเรขาคณิตหมายถึงการกำหนดจำนวนวัตถุเรขาคณิตแต่ละตัว (จุด, เส้น, โพลิกอน ฯลฯ) ที่เก็บอยู่ภายในโครงสร้างเชิงซ้อนเช่น `GeometryCollection` API เปิดเผยข้อมูลนี้ผ่าน property จำนวนเต็มแบบง่าย ทำให้ไม่ต้องวนลูปด้วยตนเอง

## Why add geometries to collection?
การเพิ่มเรขาคณิตลงในคอลเลกชัน (`add geometries to collection`) ทำให้คุณสามารถจัดการหลายรูปทรงเป็นเอนทิตีตรรกะเดียว ซึ่งมีประโยชน์สำหรับการประมวลผลแบบแบตช์, คำถามเชิงพื้นที่, และการแสดงผลหลายฟีเจอร์พร้อมกันโดยไม่ต้องจัดการแต่ละรายการแยกกัน

## Prerequisites
ก่อนเริ่ม, ตรวจสอบว่าคุณมี:

1. **Visual Studio** – เวอร์ชันล่าสุดใดก็ได้ (2019, 2022 หรือใหม่กว่า).  
2. **Aspose.GIS for .NET** – ดาวน์โหลดและติดตั้งจาก [download page](https://releases.aspose.com/gis/net/).  
3. **ความรู้พื้นฐานของ C#** – คุณควรคุ้นเคยกับการสร้างแอปพลิเคชันคอนโซลและการเพิ่มแพ็กเกจ NuGet  

## Import Namespaces
แรกเริ่ม, นำเข้า namespace ที่ให้คุณเข้าถึงคลาสเรขาคณิต.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Create a Point Geometry
`Point` แทนพิกัดคู่เดียว (ละติจูด, ลองจิจูด). ที่นี่เราสร้างหนึ่งจุดสำหรับเมืองนิวยอร์ก

```csharp
Point point = new Point(40.7128, -74.006);
```

## Step 2: Create a LineString Geometry
`LineString` คือชุดของจุดที่เชื่อมต่อกัน เราจะเพิ่มสองจุดสุ่มเพื่อเป็นตัวอย่าง.

```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```

## Step 3: Add Geometries to a Collection
ตอนนี้เราจะรวมจุดและเส้นเข้าด้วยกันใน `GeometryCollection` นี่คือที่ที่เราจะ **add geometries to collection**.

```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```

## Step 4: How to Count Geometries
Property `Count` คืนค่าจำนวนรวมของเรขาคณิตที่เก็บในคอลเลกชัน.

```csharp
int geometriesCount = geometryCollection.Count;
```

## Step 5: Display the Count
สุดท้าย, แสดงผลจำนวนบนคอนโซล ในตัวอย่างนี้ผลลัพธ์คือ `2`.

```csharp
Console.WriteLine(geometriesCount); // 2
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **Count คืนค่าเป็น 0 เสมอ** | คอลเลกชันไม่เคยถูกเติมข้อมูล. | ตรวจสอบให้แน่ใจว่าคุณเรียก `Add` สำหรับแต่ละเรขาคณิตก่อนเข้าถึง `Count`. |
| **ลำดับพิกัดไม่ถูกต้อง** | คอนสตรัคเตอร์ของ Point คาดว่าละติจูดมาก่อน, แล้วลองจิจูด. | ตรวจสอบลำดับของพารามิเตอร์เมื่อสร้าง `Point` หรือ `LineString`. |
| **ข้อผิดพลาด namespace หายไป** | `Aspose.Gis.Geometries` ไม่ได้ถูกนำเข้า. | เพิ่ม `using Aspose.Gis.Geometries;` ที่ส่วนหัวของไฟล์. |

## Frequently Asked Questions

**Q: ฉันสามารถผสมประเภทเรขาคณิตที่แตกต่างกันในคอลเลกชันเดียวได้หรือไม่?**  
A: ได้, คุณสามารถเพิ่มจุด, เส้น, โพลิกอน, และแม้กระทั่งคอลเลกชันอื่น ๆ ลงใน `GeometryCollection` เดียวได้.

**Q: Aspose.GIS รองรับการส่งออก GeoJSON สำหรับคอลเลกชันหรือไม่?**  
A: แน่นอน. คุณสามารถใช้ `geometryCollection.ToGeoJson()` เพื่อทำการซีเรียลไลซ์คอลเลกชัน.

**Q: มีวิธีวนลูปแต่ละเรขาคณิตหลังจากนับหรือไม่?**  
A: มี, `foreach (var geom in geometryCollection)` จะให้คุณประมวลผลแต่ละเรขาคณิตแยกกันได้.

**Q: ฉันต้องการไลเซนส์สำหรับการสร้างเวอร์ชันพัฒนาไหม?**  
A: การทดลองใช้ฟรีเพียงพอสำหรับการประเมิน, แต่ต้องใช้เวอร์ชันที่มีไลเซนส์สำหรับการใช้งานจริง.

### Aspose.GIS for .NET เหมาะกับแอปพลิเคชันเดสก์ท็อปและเว็บหรือไม่?  
ใช่, Aspose.GIS for .NET สามารถใช้ได้ทั้งในแอปพลิเคชันเดสก์ท็อปและเว็บอย่างราบรื่น.

### ฉันสามารถทำการค้นหาเชิงพื้นที่โดยใช้ Aspose.GIS for .NET ได้หรือไม่?  
แน่นอน, Aspose.GIS for .NET มีการสนับสนุนที่แข็งแกร่งสำหรับการทำการค้นหาเชิงพื้นที่บนเรขาคณิต.

### Aspose.GIS for .NET รองรับรูปแบบไฟล์ GIS ต่าง ๆ หรือไม่?  
ใช่, Aspose.GIS for .NET รองรับรูปแบบไฟล์ GIS หลากหลายรวมถึง SHP, KML, และ GeoJSON.

### มีการทดลองใช้ฟรีสำหรับ Aspose.GIS for .NET หรือไม่?  
ใช่, คุณสามารถดาวน์โหลดการทดลองใช้ฟรีจาก [website](https://releases.aspose.com/).

### ฉันจะหาแหล่งสนับสนุนสำหรับ Aspose.GIS for .NET ได้จากที่ไหน?  
คุณสามารถหาแหล่งสนับสนุนได้ที่ [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

## Conclusion
ในคู่มือนี้เราได้อธิบาย **how to count geometries** ภายใน `GeometryCollection` และสาธิตขั้นตอนการปฏิบัติในการ **add geometries to collection** ด้วย Aspose.GIS for .NET ด้วยพื้นฐานเหล่านี้คุณสามารถสร้างฟีเจอร์เชิงพื้นที่ที่ซับซ้อนมากขึ้น, ทำการประมวลผลแบบแบตช์, และรวมข้อมูลเชิงภูมิศาสตร์เข้าไปในแอปพลิเคชัน .NET ใดก็ได้.

---

**อัปเดตล่าสุด:** 2025-12-11  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}