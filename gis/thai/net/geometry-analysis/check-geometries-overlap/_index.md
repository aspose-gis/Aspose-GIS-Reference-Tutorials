---
date: 2025-12-04
description: เรียนรู้วิธีตรวจสอบการทับซ้อนและวิธีตรวจจับการทับซ้อนของรูปทรงเรขาคณิตโดยใช้
  Aspose.GIS สำหรับ .NET คู่มือขั้นตอนต่อขั้นตอนสำหรับนักพัฒนา
language: th
linktitle: Check Geometries Overlap
second_title: Aspose.GIS .NET API
title: วิธีตรวจสอบการทับซ้อนของรูปทรงเรขาคณิตด้วย Aspose.GIS สำหรับ .NET
url: /net/geometry-analysis/check-geometries-overlap/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตรวจสอบการทับซ้อนของเรขาคณิตด้วย Aspose.GIS

## แนะนำ

หากคุณต้องการ **วิธีตรวจสอบการทับซ้อน** ระหว่างสองฟีเจอร์เชิงพื้นที่, Aspose.GIS for .NET ให้ API ที่สะอาดและปลอดภัยต่อประเภทที่ทำงานหนักให้คุณ ไม่ว่าคุณจะกำลังสร้างเครื่องยนต์การกำหนดเส้นทาง, ตัวตรวจสอบการใช้ที่ดิน, หรือยูทิลิตี้ GIS อย่างง่าย, การตรวจจับเรขาคณิตที่ทับซ้อนเป็นความต้องการทั่วไป ในบทแนะนำนี้เราจะพาคุณผ่านทุกอย่างที่คุณต้องรู้—ข้อกำหนดเบื้องต้น, การเดินผ่านโค้ด, และเคล็ดลับเชิงปฏิบัติ—เพื่อให้คุณตอบคำถาม *วิธีตรวจจับการทับซ้อน* ในโครงการของคุณได้อย่างมั่นใจ

## คำตอบสั้น
- **วิธีหลักคืออะไร?** `Geometry.Overlaps(otherGeometry)`  
- **ต้องการไลเซนส์สำหรับการทดสอบหรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+  
- **การดำเนินการใช้เวลานานเท่าไหร่?** ประมาณ 5‑10 นาทีสำหรับการตรวจสอบการทับซ้อนพื้นฐาน  
- **สามารถใช้ร่วมกับไลบรารี GIS อื่นได้หรือไม่?** ใช่—Aspose.GIS ผสานรวมได้อย่างราบรื่นกับสแตก GIS ของ .NET ส่วนใหญ่  

## “วิธีตรวจสอบการทับซ้อน” คืออะไรใน GIS?

ในการวิเคราะห์เชิงพื้นที่, *การทับซ้อน* หมายถึงเรขาคณิตสองรูปแชร์จุดภายในบางส่วนแต่ไม่มีรูปใดรูปหนึ่งครอบคลุมอีกรูปอย่างสมบูรณ์ ตัวตรวจสอบ `Overlaps` ปฏิบัติตามคำนิยามของ OGC (Open Geospatial Consortium) และจะคืนค่า **true** เฉพาะเมื่อความสัมพันธ์นี้มีอยู่จริง

## ทำไมต้องใช้ Aspose.GIS สำหรับการตรวจจับการทับซ้อน?

- **Zero‑dependency** – ไม่ต้องใช้ไลบรารีเนทีฟหรือบริการภายนอก  
- **Rich geometry model** – รองรับจุด, เส้น, โพลิกอน, และมัลติ‑เรขาคณิตโดยตรง  
- **Performance‑optimized** – ออกแบบมาสำหรับชุดข้อมูลขนาดใหญ่และสถานการณ์เรียลไทม์  
- **Cross‑platform** – ทำงานบน Windows, Linux, และ macOS ด้วย .NET Core  

## ข้อกำหนดเบื้องต้น

1. **C# basics** – คุณควรคุ้นเคยกับคลาส, เมธอด, และการแสดงผลบนคอนโซล  
2. **Aspose.GIS for .NET** – ดาวน์โหลดและติดตั้งจากเว็บไซต์อย่างเป็นทางการ [here](https://releases.aspose.com/gis/net/)  
3. **A .NET‑compatible IDE** – Visual Studio, Rider, หรือ VS Code พร้อมส่วนขยาย C#  

## นำเข้า Namespaces

เพิ่มคำสั่ง `using` ที่จำเป็นเพื่อให้โค้ดของคุณเข้าถึงประเภทเรขาคณิตของ Aspose.GIS

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

ตอนนี้เราจะลงลึกในตัวอย่างเชิงปฏิบัติที่แสดง **วิธีตรวจสอบการทับซ้อน** ทีละขั้นตอน

## ขั้นตอนที่ 1: กำหนดเรขาคณิตที่คุณต้องการเปรียบเทียบ

เราจะเริ่มด้วยอ็อบเจกต์ `LineString` สองตัวที่แชร์จุดสิ้นสุดแต่ **ไม่** ทับซ้อนกัน

```csharp
var geometry1 = new LineString();
geometry1.AddPoint(0, 0);
geometry1.AddPoint(0, 2);

var geometry2 = new LineString();
geometry2.AddPoint(0, 2);
geometry2.AddPoint(0, 3);
```

## ขั้นตอนที่ 2: ใช้เมธอด `Overlaps` – การตรวจสอบครั้งแรก

เมธอด `Overlaps` จะคืนค่า `false` เนื่องจากเส้นสองเส้นเพียงแค่สัมผัสกันที่จุดเดียว

```csharp
Console.WriteLine(geometry1.Overlaps(geometry2)); // Output: False
```

## ขั้นตอนที่ 3: สร้างเรขาคณิตอื่นที่ทับซ้อนจริง

ต่อไปเราจะสร้างเส้นที่สามที่วิ่งผ่านภายในของ `geometry1`

```csharp
var geometry3 = new LineString();
geometry3.AddPoint(0, 1);
geometry3.AddPoint(0, 3);
```

## ขั้นตอนที่ 4: ตรวจสอบการทับซ้อนอีกครั้ง – ครั้งนี้ควรเป็น true

```csharp
Console.WriteLine(geometry1.Overlaps(geometry3)); // Output: True
```

### วิธีตรวจจับการทับซ้อนในกรณีที่ซับซ้อนมากขึ้น?

หากคุณทำงานกับโพลิกอน, มัลติ‑เรขาคณิต, หรือจำเป็นต้องพิจารณาความคลาดเคลื่อน, เมธอด `Overlaps` เดียวกันก็ใช้ได้ เพียงเปลี่ยน `LineString` เป็น `Polygon`, `MultiPolygon` ฯลฯ แล้วตัวตรวจสอบจะจัดการกับประเภทเรขาคณิตนั้นโดยอัตโนมัติ

## ปัญหาทั่วไปและวิธีแก้

| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **Always returns `false`** | Geometries are only touching (share a boundary) rather than overlapping. | Use `Intersects` for any shared point, or adjust the coordinates so interiors intersect. |
| **Exception on large datasets** | Memory pressure when loading many geometries at once. | Process geometries in batches or use `GeometryCollection` with streaming. |
| **Unexpected `true` for polygons** | Polygon interiors intersect but share an edge. | Verify that you truly need the OGC *overlaps* definition; otherwise, use `Crosses` or `Touches`. |

## คำถามที่พบบ่อย

**Q1: สามารถใช้ Aspose.GIS for .NET ร่วมกับไลบรารี .NET อื่นได้หรือไม่?**  
A1: ใช่, Aspose.GIS for .NET ผสานรวมได้อย่างราบรื่นกับไลบรารี .NET อื่น ๆ ทำให้ความสามารถของมันเพิ่มขึ้น

**Q2: มีเวอร์ชันทดลองฟรีสำหรับ Aspose.GIS for .NET หรือไม่?**  
A2: มี, คุณสามารถเข้าถึงเวอร์ชันทดลองฟรีของ Aspose.GIS for .NET ได้จาก [here](https://releases.aspose.com/)

**Q3: จะหาเอกสารสำหรับ Aspose.GIS for .NET ได้จากที่ไหน?**  
A3: เอกสารครบถ้วนสำหรับ Aspose.GIS for .NET มีให้บริการที่ [here](https://reference.aspose.com/gis/net/)

**Q4: จะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.GIS for .NET ได้อย่างไร?**  
A4: คุณสามารถรับไลเซนส์ชั่วคราวสำหรับ Aspose.GIS for .NET ได้จาก [here](https://purchase.aspose.com/temporary-license/)

**Q5: จะขอรับการสนับสนุนสำหรับ Aspose.GIS for .NET ได้จากที่ไหน?**  
A5: สำหรับความช่วยเหลือหรือคำถามใด ๆ ให้เยี่ยมชมฟอรั่ม Aspose.GIS ที่ [here](https://forum.aspose.com/c/gis/33)

---

**อัปเดตล่าสุด:** 2025-12-04  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}