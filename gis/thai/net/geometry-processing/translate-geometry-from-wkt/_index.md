---
date: 2025-12-23
description: เรียนรู้วิธีแปลง WKT เป็นเรขาคณิตและวิธีนับจุดโดยใช้ Aspose.GIS สำหรับ
  .NET คู่มือขั้นตอนต่อขั้นตอนสำหรับนักพัฒนา
linktitle: Translate Geometry from WKT
second_title: Aspose.GIS .NET API
title: วิธีแปลง WKT เป็น Geometry ด้วย Aspose.GIS ใน .NET
url: /th/net/geometry-processing/translate-geometry-from-wkt/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง WKT เป็น Geometry ด้วย Aspose.GIS ใน .NET

## บทนำ
ในบทเรียนนี้คุณจะได้ค้นพบ **วิธีแปลง WKT เป็น geometry** ด้วย Aspose.GIS สำหรับ .NET และดูตัวอย่างการ **นับจุด** ในรูปทรงที่ได้ ไม่ว่าคุณจะกำลังสร้างบริการแผนที่, ประมวลผลข้อมูล GIS, หรือเพียงต้องการอ่าน Well‑Known Text ในแอปพลิเคชัน .NET ขั้นตอนเหล่านี้จะช่วยให้คุณเริ่มต้นได้อย่างรวดเร็ว

## คำตอบเร็ว
- **Aspose.GIS สามารถอ่าน WKT ได้หรือไม่?** ใช่ – เมธอด `Geometry.FromText` จะทำการแยกวิเคราะห์สตริง WKT โดยตรง.  
- **ต้องใช้บรรทัดของโค้ดกี่บรรทัด?** ประมาณ 5‑6 บรรทัดสำหรับการแปลงพื้นฐานและการนับจุด.  
- **ต้องการไลเซนส์สำหรับการใช้งานจริงหรือไม่?** ใช่, จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานที่ไม่ใช่แบบทดลอง.  
- **เวอร์ชัน .NET ที่รองรับ?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6+.  
- **การนับจุดมีอยู่ในตัวหรือไม่?** แน่นอน – วัตถุ geometry มีคุณสมบัติ `Count`.

## “การแปลง WKT เป็น geometry” คืออะไร?
Well‑Known Text (WKT) เป็นรูปแบบข้อความธรรมดาที่ใช้แทนวัตถุเชิงเรขาคณิต การแปลง WKT เป็น geometry หมายถึงการเปลี่ยนข้อความนั้นให้เป็นโมเดลวัตถุ (เช่น `ILineString`, `IPolygon`) ที่คุณสามารถจัดการได้โดยโปรแกรม

## ทำไมต้องใช้ Aspose.GIS สำหรับการแปลงนี้?
- **การแยกวิเคราะห์แบบไม่มีการพึ่งพา** – ไม่ต้องใช้ไลบรารีภายนอก.  
- **ชุดฟีเจอร์ GIS ครบถ้วน** – รองรับพิกัด 2D/3D, การจัดการ SRID, และหลายรูปแบบไฟล์.  
- **ประสิทธิภาพสูง** – ปรับให้เหมาะกับชุดข้อมูลขนาดใหญ่และสถานการณ์แบบหลายเธรด.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมี:

1. Aspose.GIS for .NET API – ดาวน์โหลดได้จาก [here](https://releases.aspose.com/gis/net/).  
2. ความรู้พื้นฐานของ C# และสภาพแวดล้อมการพัฒนา .NET (Visual Studio, VS Code, ฯลฯ).

## นำเข้า Namespaces
ขั้นแรก, เพิ่ม namespaces ที่จำเป็นลงในไฟล์ C# ของคุณ:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: สร้าง LineString จาก WKT
ตอนนี้เราจะ **แปลง WKT เป็น geometry** โดยสร้างอ็อบเจกต์ `LineString` จากสตริง WKT ที่รวมพิกัด Z:

```csharp
ILineString line = (ILineString)Geometry.FromText("LINESTRING Z (0.1 0.2 0.3, 1 2 1, 12 23 2)");
```

> *เคล็ดลับ:* เมธอด `FromText` จะตรวจจับประเภทของ geometry โดยอัตโนมัติ, ดังนั้นคุณสามารถแคสท์เป็นอินเทอร์เฟซที่เหมาะสม (`ILineString`, `IPolygon`, ฯลฯ) ได้

## วิธีนับจุดใน LineString?
เพื่อตอบคีย์เวิร์ดรอง **วิธีนับจุด**, เพียงอ่านคุณสมบัติ `Count` ของอินสแตนซ์ `ILineString`:

```csharp
Console.WriteLine(line.Count); // Output: 3
```

ผลลัพธ์แสดงว่าเส้นนี้มีจุดยอดสามจุด, ยืนยันว่าการแปลงสำเร็จและจำนวนจุดถูกต้อง.

## สรุป
ตอนนี้คุณรู้ **วิธีแปลง WKT เป็น geometry** ด้วย Aspose.GIS สำหรับ .NET และวิธีดึงจำนวนจุดด้วยการเรียกคุณสมบัติเดียว พื้นฐานเหล่านี้ทำให้คุณสามารถรวมการประมวลผลข้อมูล GIS เข้าไปในแอปพลิเคชัน .NET ใดก็ได้, ตั้งแต่เครื่องมือเดสก์ท็อปจนถึงบริการคลาวด์.

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.GIS สำหรับ .NET ในโครงการเชิงพาณิชย์ของฉันได้หรือไม่?
ได้, คุณสามารถใช้ได้ Aspose.GIS สำหรับ .NET มีไลเซนส์ต่อผู้พัฒนา, ทำให้คุณใช้ในโครงการเชิงพาณิชย์ได้โดยไม่มีข้อจำกัดใดๆ

### Aspose.GIS สำหรับ .NET รองรับรูปแบบเรขาคณิตอื่น ๆ นอกจาก WKT หรือไม่?
ใช่, Aspose.GIS สำหรับ .NET รองรับรูปแบบเรขาคณิตหลายประเภท, รวมถึง WKB, GeoJSON, และ Shapefile.

### มีการทดลองใช้ฟรีสำหรับ Aspose.GIS สำหรับ .NET หรือไม่?
ใช่, คุณสามารถรับการทดลองใช้ฟรีได้จาก [here](https://releases.aspose.com/).

### ฉันจะหาเอกสารสำหรับ Aspose.GIS สำหรับ .NET ได้จากที่ไหน?
คุณสามารถหาเอกสารได้ที่ [here](https://reference.aspose.com/gis/net/).

### ฉันจะรับการสนับสนุนสำหรับ Aspose.GIS สำหรับ .NET อย่างไร?
คุณสามารถรับการสนับสนุนจากฟอรั่ม Aspose.GIS ได้ที่ [here](https://forum.aspose.com/c/gis/33).

## คำถามที่พบบ่อย (เพิ่มเติม)

**Q: ถ้าสตริง WKT ของฉันมีไวยากรณ์ที่ไม่ถูกต้องจะทำอย่างไร?**  
A: `Geometry.FromText` จะโยน `FormatException`. ให้ห่อการเรียกในบล็อก try‑catch เพื่อจัดการ WKT ที่ผิดรูปแบบอย่างราบรื่น.

**Q: ฉันสามารถแปลงคอลเลกชันของสตริง WKT ได้ในครั้งเดียวหรือไม่?**  
A: ได้ – ทำการวนลูปผ่านรายการสตริงของคุณ, เรียก `Geometry.FromText` สำหรับแต่ละรายการ, และเก็บผลลัพธ์ใน `List<IGeometry>`.

**Q: Aspose.GIS รักษาค่า Z‑values ไว้เมื่อทำการแปลงหรือไม่?**  
A: แน่นอน. เมื่อ WKT มีพิกัด Z (เช่นในตัวอย่าง) geometry ที่ได้จะคงค่าดังกล่าวไว้.

**Q: สามารถส่งออก geometry กลับเป็น WKT หลังจากการปรับแต่งได้หรือไม่?**  
A: ใช้เมธอด `ToText()` บนอินสแตนซ์ `IGeometry` ใดก็ได้เพื่อรับการแสดงผล WKT.

---

**อัปเดตล่าสุด:** 2025-12-23  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}