---
date: 2026-02-08
description: เรียนรู้วิธีสร้างบัฟเฟอร์รูปทรงเรขาคณิตด้วย Aspose.GIS สำหรับ .NET และทำการวิเคราะห์เชิงพื้นที่ด้วยบัฟเฟอร์
  รวมถึงการติดตั้ง การนำเข้าเนมสเปซ และการตรวจสอบการครอบคลุม
linktitle: How to Create Buffer Using Aspose.GIS for .NET
second_title: Aspose.GIS .NET API
title: วิธีบัฟเฟอร์เรขาคณิตโดยใช้ Aspose.GIS สำหรับ .NET
url: /th/net/geometry-analysis/create-geometry-buffer/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการทำ Buffer รูปทรงเรขาคณิตด้วย Aspose.GIS สำหรับ .NET

## บทนำ
หากคุณทำงานกับข้อมูลเชิงพื้นที่ในสภาพแวดล้อม .NET การ **ทำ Buffer รูปทรงเรขาคณิต** เป็นสิ่งสำคัญสำหรับการวิเคราะห์ความใกล้ชิด การจัดโซน และการสรุปลักษณะของฟีเจอร์ ในบทแนะนำนี้เราจะพาคุณผ่านกระบวนการทั้งหมดด้วย Aspose.GIS สำหรับ .NET—ตั้งแต่การติดตั้ง การนำเข้า namespace ที่จำเป็น การสร้าง Buffer สำหรับเส้นและโพลิกอน และสุดท้ายการตรวจสอบการครอบคลุมเชิงพื้นที่ เมื่อเสร็จสิ้นคุณจะสามารถใช้ **buffer การวิเคราะห์เชิงพื้นที่** ในแอปพลิเคชันของคุณได้อย่างมั่นใจ

## คำตอบสั้น
- **Buffer ของรูปทรงเรขาคณิตคืออะไร?** โพลิกอนที่ล้อมรอบทุกจุดภายในระยะที่กำหนดจากรูปทรงต้นทาง  
- **ทำไมต้องใช้ Aspose.GIS สำหรับการทำ Buffer?** ให้ API ที่ง่ายและมีประสิทธิภาพสูง ทำงานได้บน .NET Framework, .NET Core, และ .NET 5/6+  
- **จะติดตั้ง Aspose.GIS อย่างไร?** ดาวน์โหลดไลบรารีจากเว็บไซต์ทางการและเพิ่มเป็นอ้างอิงใน Visual Studio  
- **จะตรวจสอบการครอบคลุมอย่างไร?** ใช้เมธอด `SpatiallyContains` เพื่อตรวจสอบว่าจุดอยู่ภายใน Buffer ที่สร้างหรือไม่  
- **สามารถทำการวิเคราะห์เชิงพื้นที่อื่น ๆ นอกเหนือจาก Buffer ได้หรือไม่?** ได้—รองรับการทำ intersect, union, และการคำนวณระยะทางด้วย

## Buffer ของรูปทรงเรขาคณิตคืออะไร?
Buffer ของรูปทรงเรขาคณิตสร้างโซนรอบฟีเจอร์ (จุด, เส้น, หรือโพลิกอน) ที่กำหนดโดยผู้ใช้ ระยะนี้มีประโยชน์สำหรับการระบุฟีเจอร์ใกล้เคียง การสร้างพื้นที่ผลกระทบ หรือการทำให้รูปร่างซับซ้อนง่ายขึ้น

## วิธีทำ Buffer รูปทรงเรขาคณิตด้วย Aspose.GIS
### ทำไมต้องใช้ Aspose.GIS สำหรับ Buffer การวิเคราะห์เชิงพื้นที่?
- **รองรับหลายแพลตฟอร์ม:** ทำงานบน Windows, Linux, และ macOS  
- **ไม่มีการพึ่งพาไลบรารีภายนอก:** ไม่ต้องใช้ GIS library แบบเนทีฟ  
- **API ครบถ้วน:** มีฟังก์ชัน Buffer, spatial predicates, และการแปลงระบบพิกัด  
- **ปรับประสิทธิภาพสูง:** จัดการชุดข้อมูลขนาดใหญ่ได้อย่างมีประสิทธิภาพ เหมาะกับการทำ Buffer การวิเคราะห์เชิงพื้นที่ระดับหนัก

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- **Visual Studio 2019 หรือใหม่กว่า** (หรือ IDE .NET ที่เข้ากันได้)  
- **.NET 6 SDK** (หรือ .NET Core 3.1 ขึ้นไป)  
- **Aspose.GIS for .NET library** – ดูขั้นตอนการติดตั้งด้านล่าง  

### วิธีติดตั้ง Aspose.GIS สำหรับ .NET
1. ดาวน์โหลดไลบรารี Aspose.GIS สำหรับ .NET จาก [ลิงก์ดาวน์โหลด](https://releases.aspose.com/gis/net/)  
2. ใน Visual Studio คลิกขวาที่โครงการของคุณ → **Add** → **Reference…** → เรียกดูไปยังไฟล์ DLL ที่ดาวน์โหลดและเพิ่มเข้ามา  
3. รับไลเซนส์จาก [Aspose](https://purchase.aspose.com/buy) หรือใช้ [ไลเซนส์ชั่วคราว](https://purchase.aspose.com/temporary-license/) เพื่อประเมินผล

## การนำเข้า Namespace
เพื่อเริ่มใช้ API ให้นำเข้า namespace ที่จำเป็นในไฟล์ C# ของคุณ

### วิธีนำเข้า Aspose.GIS
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

ตอนนี้เราจะอธิบายกระบวนการสร้าง Buffer ทีละขั้นตอน

## คู่มือแบบขั้นตอน

### ขั้นตอนที่ 1: สร้าง Buffer ของรูปทรงเรขาคณิต
ก่อนอื่นเรากำหนดรูปทรง `LineString` ง่าย ๆ ที่จะเป็นแหล่งข้อมูลสำหรับ Buffer

```csharp
// Define a LineString geometry
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(3, 3);
```

ในโค้ดนี้เราสร้าง `LineString` และเพิ่มสองจุด เพื่อสร้างเส้นทแยงมุมจาก (0,0) ไปยัง (3,3)

### ขั้นตอนที่ 2: สร้าง Buffer สำหรับ LineString
ต่อไปเราจะสร้าง Buffer รอบเส้นด้วย **ระยะบวก** 1 หน่วย

```csharp
// Generate a buffer for the LineString with a positive distance
var lineBuffer = line.GetBuffer(distance: 1);
```

เมธอด `GetBuffer` จะคืนค่าเป็นโพลิกอนที่รวมทุกจุดที่อยู่ภายใน 1 หน่วยจากเส้นต้นฉบับ

### ขั้นตอนที่ 3: ตรวจสอบการครอบคลุมเชิงพื้นที่
ต่อไปเราจะแสดง **วิธีตรวจสอบการครอบคลุม** โดยทดสอบว่าจุดบางจุดอยู่ภายใน Buffer หรือไม่

```csharp
// Check spatial containment of points within the buffer
Console.WriteLine(lineBuffer.SpatiallyContains(new Point(1, 2)));     // True
Console.WriteLine(lineBuffer.SpatiallyContains(new Point(3.1, 3.1))); // True
```

พรีดิเกต `SpatiallyContains` จะคืนค่า `true` หากจุดนั้นอยู่ภายในโพลิกอน Buffer

### ขั้นตอนที่ 4: กำหนดรูปทรงโพลิกอน
เราจะสร้างรูปทรง `Polygon` เพื่อสาธิตการทำ Buffer ด้วย **ระยะลบ** ซึ่งจะทำให้รูปทรงหดลง

```csharp
// Define a Polygon geometry
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 3),
    new Point(3, 3),
    new Point(3, 0),
    new Point(0, 0),
});
```

โพลิกอนนี้เป็นสี่เหลี่ยมจัตุรัสที่มีจุดยอดที่ (0,0), (0,3), (3,3) และ (3,0)

### ขั้นตอนที่ 5: สร้าง Buffer สำหรับโพลิกอน
ใช้ระยะลบ –1 หน่วยเพื่อทำให้โพลิกอนหดเข้าไปด้านใน

```csharp
// Generate a buffer for the Polygon with a negative distance
var polygonBuffer = (IPolygon)polygon.GetBuffer(distance: -1);
```

ผลลัพธ์ `polygonBuffer` จะเป็นสี่เหลี่ยมจัตุรัสที่เล็กลง เหมาะสำหรับการสร้างโซนภายใน

### ขั้นตอนที่ 6: เข้าถึงจุดของวงแหวนภายนอก Buffer
สุดท้ายเราจะดึงและแสดงพิกัดของวงแหวนภายนอกของ Buffer

```csharp
// Access points of the exterior ring of the buffer Polygon
var ring = polygonBuffer.ExteriorRing;
for (int i = 0; i < ring.Count; ++i)
{
    Console.WriteLine("[{0}] = ({1} {2})", i, ring[i].X, ring[i].Y);
}
```

ลูปนี้พิมพ์จุดยอดแต่ละจุดของโพลิกอนที่หดลง เพื่อยืนยันรูปทรง Buffer

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **Buffer คืนค่า `null`** | ตรวจสอบให้แน่ใจว่าค่าระยะห่างเหมาะสมกับระบบพิกัดของรูปทรง |
| **`SpatiallyContains` คืนค่า `false` เสมอ** | ยืนยันว่าทั้งสองรูปทรงใช้ระบบอ้างอิงเชิงพื้นที่เดียวกัน (CRS) |
| **ประสิทธิภาพช้ากับชุดข้อมูลขนาดใหญ่** | ประมวลผลรูปทรงเป็นชุดและใช้ instance ของ `GeometryFactory` เดียวกันซ้ำ |

## คำถามที่พบบ่อย

**ถาม: Aspose.GIS สำหรับ .NET รองรับเฟรมเวิร์ก .NET อื่น ๆ หรือไม่?**  
ตอบ: รองรับ .NET Framework, .NET Core, .NET 5, และ .NET 6

**ถาม: สามารถทำการวิเคราะห์เชิงพื้นที่ด้วย Aspose.GIS สำหรับ .NET ได้หรือไม่?**  
ตอบ: ทำได้แน่นอน ไลบรารีรองรับ Buffer, intersect, การคำนวณระยะทาง และอื่น ๆ

**ถาม: มีขีดจำกัดขนาดชุดข้อมูลหรือไม่?**  
ตอบ: API ถูกออกแบบให้ทำงานกับชุดข้อมูลขนาดใหญ่ได้ แต่การใช้หน่วยความจำขึ้นอยู่กับขนาดของรูปทรงที่โหลด

**ถาม: Aspose.GIS รองรับระบบอ้างอิงเชิงพื้นที่หลายประเภทหรือไม่?**  
ตอบ: รองรับระบบพิกัดหลากหลายและสามารถแปลงได้แบบเรียลไทม์

**ถาม: จะขอรับการสนับสนุนทางเทคนิคได้จากที่ไหน?**  
ตอบ: เยี่ยมชมฟอรั่มชุมชน Aspose.GIS ที่ [https://forum.aspose.com/c/gis/33](https://forum.aspose.com/c/gis/33) เพื่อขอความช่วยเหลือ

---

**อัปเดตล่าสุด:** 2026-02-08  
**ทดสอบด้วย:** Aspose.GIS for .NET (เวอร์ชันล่าสุด)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}