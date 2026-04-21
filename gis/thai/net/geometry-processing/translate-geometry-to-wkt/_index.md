---
date: 2026-04-13
description: เรียนรู้วิธีแปลงรูปทรงเรขาคณิตเป็น WKT ด้วย Aspose.GIS สำหรับ .NET คู่มือนี้แสดงวิธีแปลงรูปทรงเรขาคณิตเป็น
  WKT และวิธีใช้เมธอด AsText อย่างมีประสิทธิภาพ
keywords:
- how to translate geometry
- convert geometry to wkt
- how to use astext
linktitle: แปลงเรขาคณิตเป็น WKT
second_title: Aspose.GIS .NET API
title: วิธีแปลงเรขาคณิตเป็น WKT ด้วย Aspose.GIS สำหรับ .NET
url: /th/net/geometry-processing/translate-geometry-to-wkt/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแปลงเรขาคณิตเป็น WKT ด้วย Aspose.GIS สำหรับ .NET

## บทนำ
หากคุณทำงานกับข้อมูลเชิงพื้นที่ในแอปพลิเคชัน .NET คุณมักต้อง **แปลงเรขาคณิต** ให้เป็นรูปแบบข้อความที่ระบบอื่น ๆ สามารถใช้ได้ รูปแบบ Well‑Known Text (WKT) เป็นมาตรฐานที่ใช้กันอย่างแพร่หลายสำหรับจุดประสงค์นี้ ในบทเรียนนี้เราจะอธิบาย **วิธีแปลงเรขาคณิต** เป็น WKT ด้วย Aspose.GIS สำหรับ .NET และเราจะยังแสดงวิธีการที่สะดวกของเมธอด `AsText()` ที่ทำให้การแปลงเป็นบรรทัดเดียว

## คำตอบอย่างรวดเร็ว
- **“translate geometry” หมายถึงอะไร?** การแปลงอ็อบเจ็กต์เรขาคณิต (จุด, เส้น, โพลิกอน ฯลฯ) ให้เป็นรูปแบบข้อความเช่น WKT.  
- **เมธอดใดสร้าง WKT?** `AsText()` บนวัตถุเรขาคณิตใด ๆ.  
- **ฉันต้องการไลเซนส์หรือไม่?** รุ่นทดลองฟรีใช้ได้สำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **เวอร์ชัน .NET ที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **ฉันสามารถแปลงรูปแบบอื่นได้หรือไม่?** ใช่ – Aspose.GIS ยังรองรับ WKB, GeoJSON, Shapefile และอื่น ๆ อีกมาก

## การแปลงเรขาคณิตเป็น WKT คืออะไร?
การแปลงเรขาคณิตเป็น WKT หมายถึงการแสดงพิกัดและรูปทรงของวัตถุเชิงพื้นที่เป็นสตริงข้อความธรรมดา เช่น `POINT (23.5732 25.3421)` รูปแบบนี้อ่านง่ายสำหรับมนุษย์และได้รับการยอมรับอย่างกว้างขวางโดยเครื่องมือ GIS, ฐานข้อมูล, และบริการเว็บ

## ทำไมต้องใช้ Aspose.GIS สำหรับงานนี้?
* **Zero‑dependency API** – ไม่ต้องติดตั้งไลบรารีเนทีฟ  
* **Consistent behavior** ครอบคลุม .NET Framework, .NET Core, และ .NET 5/6.  
* **Rich format support** – นอกเหนือจาก WKT คุณยังได้รับ WKB, GeoJSON, Shapefile ฯลฯ  
* **Thread‑safe and high‑performance** – เหมาะสำหรับสคริปต์ขนาดเล็กและบริการขนาดใหญ่

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะดำเนินการต่อ โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **Install Aspose.GIS for .NET** – ทำตามคำแนะนำใน [Aspose.GIS for .NET documentation](https://reference.aspose.com/gis/net/) อย่างเป็นทางการ.  
2. **Set up a .NET development environment** – Visual Studio, Rider หรือ VS Code พร้อมส่วนขยาย C# จะทำงานได้ดี.  
3. **Basic C# knowledge** – ตัวอย่างใช้ไวยากรณ์ C# อย่างง่าย.

## วิธีแปลงเรขาคณิตเป็น WKT ด้วย Aspose.GIS สำหรับ .NET
ในส่วนต่อไปนี้ เราจะแบ่งกระบวนการเป็นขั้นตอนที่ชัดเจนและเป็นลำดับ ตัวอย่างแต่ละขั้นตอนจะมีคำอธิบายสั้น ๆ ตามด้วยโค้ดที่ต้องใช้

### ขั้นตอนที่ 1: นำเข้าเนมสเปซที่จำเป็น
ก่อนอื่น นำคลาสเรขาคณิตของ Aspose.GIS เข้ามาในสโคป.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### ขั้นตอนที่ 2: สร้างอ็อบเจ็กต์เรขาคณิต (ตัวอย่าง Point)
สร้างเรขาคณิตที่คุณต้องการแปลง ที่นี่เราใช้ `Point` แต่รูปแบบเดียวกันทำงานได้กับ `LineString`, `Polygon` เป็นต้น.

```csharp
Point point = new Point(23.5732, 25.3421);
```

### ขั้นตอนที่ 3: แปลงเรขาคณิตเป็น WKT ด้วย `AsText()`
`AsText()` เป็นเมธอดส่วนขยายที่ส่งคืนการแสดงผล WKT ของเรขาคณิต พิมพ์ผลลัพธ์ไปยังคอนโซลหรือเก็บไว้ตามต้องการ.

```csharp
Console.WriteLine(point.AsText()); // POINT (23.5732, 25.3421)
```

> **เคล็ดลับ:** หากคุณต้องการ WKT ที่ไม่มีวงเล็บรอบพิกัด ให้ใช้ `point.AsText().Replace(",", " ")`.

## วิธีใช้เมธอด AsText
`AsText()` เป็นวิธีหลักในการ **แปลงเรขาคณิตเป็น WKT** มันทำงานกับคลาสใด ๆ ที่สืบทอดจาก `Geometry` ดังนั้นคุณสามารถเรียกใช้โดยตรงบน `LineString`, `Polygon`, `MultiPolygon` เป็นต้น โดยไม่ต้องทำขั้นตอนการแปลงเพิ่มเติม.

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| `AsText()` คืนค่า `null` | เรขาคณิตยังไม่ได้กำหนดค่า | ตรวจสอบให้แน่ใจว่าอ็อบเจ็กต์เรขาคณิตถูกสร้างด้วยพิกัดที่ถูกต้องก่อนเรียก `AsText()`. |
| รูปแบบไม่คาดคิด (คอมม่า vs ช่องว่าง) | เครื่องมือ GIS ต่าง ๆ คาดหวังตัวคั่นที่แตกต่างกัน | ใช้การจัดการสตริง (`Replace`) หรือคลาส `WktWriter` สำหรับการจัดรูปแบบแบบกำหนดเอง. |
| คอขวดด้านประสิทธิภาพเมื่อแปลงคอลเลกชันขนาดใหญ่ | การทำ I/O กับคอนโซลซ้ำหลายครั้ง | ทำการแปลงเป็นชุดและเขียนลงไฟล์หรือ `StringBuilder` แทนการใช้ `Console.WriteLine`. |

## สรุป
การแปลงเรขาคณิตเป็น WKT ด้วย Aspose.GIS สำหรับ .NET นั้นง่ายดาย: นำเข้าเนมสเปซ, สร้างเรขาคณิตของคุณ, แล้วเรียก `AsText()` วิธีนี้ทำให้คุณสามารถฝังความสามารถ GIS ลงในแอปพลิเคชัน .NET ของคุณโดยไม่ต้องพึ่งพาไลบรารีภายนอก.

## คำถามที่พบบ่อย
### Q: ฉันสามารถใช้ Aspose.GIS สำหรับ .NET กับเฟรมเวิร์ก .NET อื่น ๆ ได้หรือไม่?
A: ใช่, Aspose.GIS สำหรับ .NET เข้ากันได้กับหลายเฟรมเวิร์กของ .NET รวมถึง .NET Core และ .NET Framework.

### Q: Aspose.GIS สำหรับ .NET เหมาะกับแอปพลิเคชันขนาดใหญ่หรือไม่?
A: แน่นอน, Aspose.GIS สำหรับ .NET ถูกออกแบบให้จัดการแอปพลิเคชัน GIS ขนาดใหญ่ได้อย่างมีประสิทธิภาพ ให้ประสิทธิภาพสูงและความน่าเชื่อถือ

### Q: Aspose.GIS สำหรับ .NET รองรับรูปแบบเชิงพื้นที่อื่น ๆ นอกจาก WKT หรือไม่?
A: ใช่, Aspose.GIS สำหรับ .NET รองรับรูปแบบเชิงพื้นที่หลายรูปแบบ รวมถึง WKB, GeoJSON, และ Shapefile เป็นต้น

### Q: ฉันสามารถขอคุณลักษณะเพิ่มเติมหรือรายงานปัญหากับ Aspose.GIS สำหรับ .NET ได้หรือไม่?
A: ใช่, คุณสามารถติดต่อ [Aspose.GIS for .NET forum](https://forum.aspose.com/c/gis/33) เพื่อขอรับการสนับสนุน, ขอคุณลักษณะเพิ่มเติม, หรือรายงานปัญหา

### Q: มีเวอร์ชันทดลองของ Aspose.GIS สำหรับ .NET หรือไม่?
A: ใช่, คุณสามารถเข้าถึงเวอร์ชันทดลองฟรีของ Aspose.GIS สำหรับ .NET [ที่นี่](https://releases.aspose.com/)

## คำถามที่พบบ่อย

**Q: How do I convert a collection of geometries to WKT efficiently?**  
A: Loop through the collection and call `AsText()` on each item, storing the results in a `StringBuilder` or writing directly to a file to avoid console overhead.

**Q: What if I need to export WKT with a specific SRID?**  
A: Use the overload `AsText(Srid)` where you provide the desired spatial reference identifier.

**Q: Is the `AsText()` method locale‑aware?**  
A: `AsText()` always uses the invariant culture, ensuring consistent decimal separators regardless of system locale.

**Q: Can I parse WKT back into a geometry object?**  
A: Yes, use `Geometry.FromText(string wkt)` to create a geometry instance from a WKT string.

**Q: Does Aspose.GIS handle 3D coordinates in WKT?**  
A: Starting from version 22.10, the library supports Z and M values in WKT (e.g., `POINT Z (x y z)`).

---

**อัปเดตล่าสุด:** 2026-04-13  
**ทดสอบด้วย:** Aspose.GIS for .NET 23.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}