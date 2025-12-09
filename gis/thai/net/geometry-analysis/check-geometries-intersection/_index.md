---
date: 2025-12-03
description: เรียนรู้วิธีสร้างรูปหลายเหลี่ยมใน C# และตรวจจับรูปหลายเหลี่ยมที่ทับซ้อนโดยใช้เมธอด
  Intersects ของ Aspose.GIS สำหรับ .NET
linktitle: Create Polygon Geometry C#
second_title: Aspose.GIS .NET API
title: สร้างรูปทรงหลายเหลี่ยมใน C# และตรวจสอบการตัดกันด้วย Aspose.GIS สำหรับ .NET
url: /th/net/geometry-analysis/check-geometries-intersection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง Polygon Geometry C# และตรวจสอบการตัดกันด้วย Aspose.GIS สำหรับ .NET

## Introduction
หากคุณต้องการ **สร้าง polygon geometry C#** และต้องการตรวจสอบอย่างรวดเร็วว่ารูปสองรูปทับกันหรือไม่ Aspose.GIS สำหรับ .NET จะมอบ API ที่สะอาดและมีประสิทธิภาพสูง ในคู่มือนี้เราจะเดินผ่านกระบวนการทั้งหมด—from การตั้งค่าห้องสมุดไปจนถึงการใช้เมธอด `Intersects` เพื่อ **ตรวจจับ polygon ที่ทับกัน** เมื่อเสร็จสิ้น คุณจะสามารถผสานการตรวจสอบการตัดกันของ polygon เข้าไปในแอปพลิเคชัน .NET ใด ๆ เพียงไม่กี่บรรทัดของโค้ด

## Quick Answers
- **เมธอด Intersects ทำอะไร?** คืนค่า `true` เมื่อสอง geometry มีพื้นที่ร่วมกันใด ๆ  
- **เนมสเปซใดที่มีคลาส polygon?** `Aspose.Gis.Geometries`  
- **ต้องใช้ไลเซนส์สำหรับการพัฒนาหรือไม่?** รุ่นทดลองฟรีใช้ได้สำหรับการทดสอบ; ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **สามารถใช้กับ .NET Core / .NET 6+ ได้หรือไม่?** ใช่, Aspose.GIS รองรับ .NET runtime สมัยใหม่ทั้งหมด  
- **ตัวอย่างใช้เวลารันเท่าไหร่?** น้อยกว่าวินาทีหนึ่งบนเครื่องพัฒนาปกติ

## What is “create polygon geometry C#”?
การสร้าง polygon geometry ใน C# หมายถึงการสร้างอินสแตนซ์ของคลาส `Polygon` (หรือประเภท geometry อื่น) ที่จัดทำโดย Aspose.GIS และให้ชุด `Point` ปิดวงที่กำหนดจุดยอดของรูปทรง เมื่อสร้างเสร็จ geometry นี้สามารถทำงานร่วมกับการดำเนินการเชิงพื้นที่ต่าง ๆ เช่น การตัดกัน, การบรรจุ, และการคำนวณระยะทาง

## Why use Aspose.GIS to detect overlapping polygons?
- **Zero external dependencies** – ไลบรารี .NET แท้ ๆ ไม่ต้องติดตั้ง GIS แบบเนทีฟ  
- **Rich spatial operations** – `Intersects`, `Disjoint`, `Contains` ฯลฯ พร้อมใช้  
- **High accuracy** – จัดการกรณีขอบอย่างแข็งแรง เช่น ขอบหรือจุดยอดที่แชร์กัน  
- **Cross‑platform** – ทำงานบน Windows, Linux, และ macOS ด้วย .NET Core/5/6

## Prerequisites
ก่อนเริ่มทำงาน ให้ตรวจสอบว่าคุณมี:

1. **Aspose.GIS for .NET** ที่ติดตั้งแล้ว (ดูขั้นตอนด้านล่าง)  
2. สภาพแวดล้อมการพัฒนา .NET (Visual Studio, VS Code, หรือ Rider)  
3. .NET Framework 4.6+ หรือ .NET Core 3.1+

### Installing Aspose.GIS for .NET
1. ไปที่หน้า Download: เยี่ยมชม [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/) เพื่อรับเวอร์ชันล่าสุดของเครื่องมือ  
2. ดาวน์โหลด Toolkit: เลือกเวอร์ชันที่เข้ากันกับสภาพแวดล้อมการพัฒนาของคุณและดาวน์โหลด  
3. ติดตั้ง Toolkit: ทำตามคำแนะนำการติดตั้งที่ให้มาเพื่อทำการติดตั้ง Aspose.GIS for .NET บนเครื่องของคุณ

## Importing Namespaces
เพื่อเริ่มทำงานกับ Aspose.GIS for .NET คุณต้องนำเข้าเนมสเปซที่จำเป็นเข้าสู่โปรเจกต์ของคุณ

1. เพิ่ม References: ในโปรเจกต์ของคุณ ให้เพิ่มการอ้างอิงไปยัง assembly ของ Aspose.GIS  
2. Import Namespaces: นำเข้าเนมสเปซที่ต้องการในไฟล์โค้ดของคุณ สำหรับตัวอย่างนี้ ให้แน่ใจว่าคุณได้นำเข้าดังต่อไปนี้:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## How to create polygon geometry C# with Aspose.GIS?
ตอนนี้สภาพแวดล้อมพร้อมแล้ว เรามาสร้าง polygon geometry สองรูปแบบง่าย ๆ ที่เราจะทดสอบการทับกันต่อไป

### Step 1: Define Geometries
ในขั้นตอนนี้ คุณจะสร้าง polygon ที่แทนพื้นที่สี่เหลี่ยมผืนผ้าสองรูป จุดยอดจะถูกกำหนดตามลำดับตามเข็มนาฬิกา และจุดแรกจะทำซ้ำที่ท้ายเพื่อปิดวง

```csharp
var geometry1 = new Polygon(new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 3),
    new Point(3, 3),
    new Point(3, 0),
    new Point(0, 0),
}));
var geometry2 = new Polygon(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 4),
    new Point(4, 4),
    new Point(4, 1),
    new Point(1, 1),
}));
```

### Step 2: Use Intersects method to detect overlapping polygons
เมื่อกำหนด geometry แล้ว เราสามารถเรียกเมธอด `Intersects` ได้ เมธอดนี้ **ใช้ algorithm Intersects** เพื่อตรวจสอบว่ามีส่วนใดของสอง polygon แชร์พื้นที่เดียวกันหรือไม่

```csharp
Console.WriteLine(geometry1.Intersects(geometry2)); // True
Console.WriteLine(geometry2.Intersects(geometry1)); // True
```

### Step 3: Check for disjoint geometries (the opposite of intersect)
หากคุณต้องการยืนยันว่ารูปสองรูป **ไม่** ทับกัน เมธอด `Disjoint` จะให้ผลลัพธ์ตรงกันข้าม

```csharp
// 'Disjoint' is opposite to 'Intersects'
Console.WriteLine(geometry1.Disjoint(geometry2)); // False
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **Always returns `false`** | Polygon ไม่ได้ปิด (first point ≠ last point) | ตรวจสอบให้จุดแรกทำซ้ำที่ท้ายของอาร์เรย์พิกัด |
| **Unexpected `true` for touching edges** | `Intersects` ถือว่าเส้นขอบที่แชร์กันเป็นการตัดกัน | ใช้เมธอด `Touches` หากต้องการตรวจจับเฉพาะการสัมผัสขอบ |
| **Performance slowdown with many polygons** | แต่ละการเรียกตรวจสอบทุกคู่จุดยอด | ทำการประมวลผลเป็นชุดโดยใช้ `GeometryCollection` หรือดัชนีเชิงพื้นที่ (R‑tree) หากรองรับ |

## Frequently Asked Questions

**Q: Can I use Aspose.GIS for .NET with other .NET frameworks?**  
A: Yes, Aspose.GIS for .NET is compatible with various .NET frameworks, including .NET Core and .NET Framework.

**Q: Is there a free trial available for Aspose.GIS for .NET?**  
A: Yes, you can access a free trial of Aspose.GIS for .NET from [here](https://releases.aspose.com/).

**Q: Where can I find support for Aspose.GIS for .NET?**  
A: You can seek assistance and engage with the community on the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

**Q: Can I obtain a temporary license for Aspose.GIS for .NET?**  
A: Yes, you can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/).

**Q: Where can I purchase a licensed version of Aspose.GIS for .NET?**  
A: You can purchase a licensed version of Aspose.GIS for .NET from [here](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose