---
date: 2025-12-23
description: เรียนรู้วิธีสร้างเส้นจากโพลิกอนและแปลงโพลิกอนเป็นเส้นโดยใช้ Aspose.GIS
  สำหรับ .NET. เชี่ยวชาญการจัดการข้อมูล GIS อย่างรวดเร็ว.
linktitle: Replace Polygons with Lines
second_title: Aspose.GIS .NET API
title: วิธีสร้างเส้นจากโพลิกอนด้วย Aspose.GIS สำหรับ .NET
url: /th/net/geometry-processing/replace-polygons-with-lines/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเส้นจากโพลิกอนด้วย Aspose.GIS สำหรับ .NET

## Introduction
หากคุณต้องการ **create line from polygon** ในแอปพลิเคชัน GIS, Aspose.GIS สำหรับ .NET มีวิธีง่าย ๆ เพียงบรรทัดเดียวเพื่อทำการแปลงนี้ การแปลงรูปทรงเรขาคณิตโพลิกอนเป็นเส้นเป็นขั้นตอนทั่วไปเมื่อคุณต้องการแสดงขอบเขต, ทำการวิเคราะห์เชิงเส้น, หรือ ลดความซับซ้อนของข้อมูล ในบทแนะนำนี้คุณจะได้เห็นวิธีการแทนที่โพลิกอนด้วยเส้นอย่างละเอียด, เหตุผลที่สำคัญ, และวิธีการผสานโซลูชันนี้เข้ากับโครงการ .NET ของคุณ

## Quick Answers
- **“create line from polygon” หมายถึงอะไร?** มันแปลงรูปทรงโพลิกอนที่ปิดเป็นเส้นขอบเขตที่ประกอบกันเป็นส่วนประกอบ.  
- **วิธีการใดที่ทำการแปลง?** `ReplacePolygonsByLines()` จาก Aspose.GIS Geometry API.  
- **ฉันต้องใช้ไลเซนส์เพื่อรันโค้ดหรือไม่?** การทดลองใช้งานฟรีใช้ได้สำหรับการประเมิน; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **ฉันสามารถใช้กับฟอร์แมต GIS อื่นได้หรือไม่?** ได้ – วิธีเดียวกันทำงานกับ Shapefile, GeoJSON, KML, เป็นต้น.

## “create line from polygon” คืออะไร?
การสร้างเส้นจากโพลิกอนจะดึงขอบของโพลิกอนเป็นคอลเลกชัน `LineString` การดำเนินการนี้มักเรียกว่า *polygon to line* conversion และมีประโยชน์สำหรับงานเช่น การวิเคราะห์เครือข่าย, การแสดงแผนที่, และการทำให้ข้อมูลง่ายขึ้น.

## ทำไมต้องใช้ Aspose.GIS สำหรับการแปลงนี้?
- **Built‑in method** – ไม่จำเป็นต้องเขียนโค้ดการแยกวิเคราะห์เรขาคณิตแบบกำหนดเอง.  
- **High performance** – ปรับให้ทำงานได้อย่างมีประสิทธิภาพกับชุดข้อมูลขนาดใหญ่.  
- **Cross‑format support** – ทำงานกับไฟล์ GIS ประเภทต่าง ๆ มากมาย.  
- **Comprehensive documentation** – เริ่มต้นได้ง่าย.

## Prerequisites
ก่อนเริ่มเขียนโค้ด, ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้พร้อม:

### Installing Aspose.GIS for .NET
1. ดาวน์โหลด Aspose.GIS สำหรับ .NET: เยี่ยมชม [this link](https://releases.aspose.com/gis/net/) เพื่อดาวน์โหลดเวอร์ชันล่าสุด.  
2. ติดตั้ง Aspose.GIS สำหรับ .NET: ทำตามคำแนะนำการติดตั้งในแพคเกจหรือดูที่ [documentation](https://reference.aspose.com/gis/net/) สำหรับขั้นตอนโดยละเอียด.

## Import Namespaces
ในโครงการ .NET ของคุณ, นำเข้า namespaces ที่จำเป็นเพื่อให้คุณสามารถทำงานกับคลาสเรขาคณิตของ Aspose.GIS

```csharp
using System;
using Aspose.Gis.Geometries;
```

## Step‑by‑step guide to replace polygons with lines

### ขั้นตอนที่ 1: กำหนดเรขาคณิตต้นทาง
สร้างคอลเลกชันเรขาคณิตที่ประกอบด้วยโพลิกอนที่คุณต้องการแปลง.

```csharp
var srcGeometry = Geometry.FromText(@"GeometryCollection (POLYGON((1 2, 1 4, 3 4, 3 2)), Point (5 1))");
```

### ขั้นตอนที่ 2: แปลงโพลิกอนเป็นเส้น
ใช้เมธอด `ReplacePolygonsByLines()` เพื่อ **convert polygon to lines**. นี่คือหัวใจของการดำเนินการ *create line from polygon*.

```csharp
var dstGeometry = srcGeometry.ReplacePolygonsByLines();
```

### ขั้นตอนที่ 3: แสดงผลลัพธ์
พิมพ์เรขาคณิตต้นฉบับและเรขาคณิตที่แปลงแล้วเพื่อยืนยันการแปลง.

```csharp
Console.WriteLine($"source: {srcGeometry.AsText()}");
Console.WriteLine($"result: {dstGeometry.AsText()}");
```

## Common pitfalls and troubleshooting
- **Empty geometry collection** – ตรวจสอบให้แน่ใจว่าเรขาคณิตต้นทางของคุณมีโพลิกอนจริง ๆ; หากไม่เช่นนั้น `ReplacePolygonsByLines()` จะคืนค่าเรขาคณิตต้นฉบับโดยไม่เปลี่ยนแปลง.  
- **Mixed geometry types** – เมธอดนี้มีผลต่อโพลิกอนเท่านั้น; ประเภทเรขาคณิตอื่น (เช่น จุด) จะถูกส่งต่อโดยไม่เปลี่ยนแปลง.  
- **Version compatibility** – ใช้แพคเกจ Aspose.GIS NuGet เวอร์ชันล่าสุดเพื่อหลีกเลี่ยงปัญหา API ที่เลิกใช้.

## Frequently Asked Questions

**Q: Aspose.GIS สำหรับ .NET สามารถทำงานกับฟอร์แมตไฟล์ GIS ต่าง ๆ ได้หรือไม่?**  
A: ใช่, Aspose.GIS สำหรับ .NET รองรับการอ่านและเขียนฟอร์แมตเช่น Shapefile, GeoJSON, KML, และอื่น ๆ.

**Q: มีการทดลองใช้งานฟรีสำหรับ Aspose.GIS สำหรับ .NET หรือไม่?**  
A: ใช่, คุณสามารถเข้าถึงการทดลองใช้งานฟรีของ Aspose.GIS สำหรับ .NET [here](https://releases.aspose.com/).

**Q: Aspose.GIS สำหรับ .NET มีการสนับสนุนสำหรับนักพัฒนาหรือไม่?**  
A: ใช่, นักพัฒนาสามารถรับการสนับสนุนและความช่วยเหลือจากฟอรั่มชุมชน Aspose.GIS [here](https://forum.aspose.com/c/gis/33).

**Q: ฉันสามารถซื้อไลเซนส์ชั่วคราวสำหรับ Aspose.GIS สำหรับ .NET ได้หรือไม่?**  
A: ใช่, คุณสามารถรับไลเซนส์ชั่วคราวจาก [here](https://purchase.aspose.com/temporary-license/).

**Q: Aspose.GIS สำหรับ .NET เหมาะสำหรับทั้งผู้เริ่มต้นและนักพัฒนาที่มีประสบการณ์หรือไม่?**  
A: แน่นอน, Aspose.GIS สำหรับ .NET รองรับนักพัฒนาทุกระดับ, มีเอกสารและการสนับสนุนที่ครบถ้วน.

---

**อัปเดตล่าสุด:** 2025-12-23  
**ทดสอบด้วย:** Aspose.GIS for .NET 24.12 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}