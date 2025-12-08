---
date: 2025-12-04
description: เรียนรู้วิธีตรวจสอบการสัมผัสของรูปทรงเรขาคณิตโดยใช้ Aspose.GIS สำหรับ
  .NET ซึ่งเป็นไลบรารีที่มีประสิทธิภาพในการจัดการข้อมูลเชิงพื้นที่และทำการวิเคราะห์เชิงพื้นที่ใน
  .NET.
language: th
linktitle: How to Check Touching Geometries
second_title: Aspose.GIS .NET API
title: วิธีตรวจสอบเรขาคณิตที่สัมผัสกันด้วย Aspose.GIS สำหรับ .NET
url: /net/geometry-analysis/check-geometries-touching/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีตรวจสอบการสัมผัสของเรขาคณิต

## บทนำ
หากคุณต้องการ **วิธีตรวจสอบการสัมผัส** ระหว่างวัตถุเชิงพื้นที่สองชิ้น Aspose.GIS for .NET จะมอบ API ที่สะอาดและปลอดภัยต่อชนิดข้อมูล ทำให้การทำงานเป็นเรื่องง่าย ในบทเรียนนี้คุณจะได้เห็นวิธีสร้าง line string, point แล้วใช้เมธอด `Touches` เพื่อตรวจสอบว่าเรขาคณิตมีเพียงขอบเขตที่ร่วมกันหรือไม่ นี่เป็นการดำเนินการหลักในหลายสถานการณ์การวิเคราะห์เชิงพื้นที่ .NET เช่น การกำหนดเส้นทางเครือข่าย, การตรวจสอบการซ้อนทับของแผนที่, และการตรวจสอบความใกล้เคียง

## คำตอบสั้น
- **“การสัมผัส” หมายถึงอะไร?** เรขาคณิตสองชิ้นมีจุดขอบเขตอย่างน้อยหนึ่งจุดร่วมกัน แต่ภายในของพวกมันไม่ทับกัน  
- **เมธอดใดที่ตรวจสอบได้?** `Geometry.Touches(otherGeometry)`  
- **ต้องมีลิขสิทธิ์สำหรับฟีเจอร์นี้หรือไม่?** รุ่นทดลองใช้ได้สำหรับการพัฒนา; ต้องมีลิขสิทธิ์ถาวรสำหรับการใช้งานจริง  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework, .NET Core, .NET 5/6/7 – ทั้งหมดรองรับโดย Aspose.GIS  
- **ใช้เวลาพัฒนาเท่าไหร่?** ประมาณ 5‑10 นาทีสำหรับตัวอย่างพื้นฐาน

## “การสัมผัส” ในการวิเคราะห์เชิงพื้นที่คืออะไร?
ในศัพท์ GIS, *การสัมผัส* หมายถึงความสัมพันธ์เชิงพื้นที่ที่เรขาคณิตสองชิ้นมาพบกันที่ขอบเขตแต่ไม่ทับซ้อนกัน มันแตกต่างจาก *intersects* (ซึ่งรวมถึงการทับซ้อนของภายใน) และมักใช้เมื่อคุณต้องการตรวจสอบว่าฟีเจอร์มาพบกันเฉพาะที่ขอบเขตเท่านั้น เช่น เส้นถนนที่เชื่อมต่อที่แยกโดยไม่ข้ามกัน

## ทำไมต้องใช้ Aspose.GIS สำหรับการวิเคราะห์เชิงพื้นที่ .NET?
Aspose.GIS ให้ไลบรารี .NET ที่จัดการทั้งหมดซึ่งทำให้คุณ **จัดการข้อมูลเชิงพื้นที่** ได้โดยไม่ต้องติดตั้ง GIS แบบดั้งเดิม รองรับรูปแบบหลากหลาย (Shapefile, GeoJSON, KML ฯลฯ) และมีการดำเนินการเรขาคณิตที่มีประสิทธิภาพสูง เช่น `Touches`, `Intersects`, `Contains` เป็นต้น เนื่องจากเป็น .NET แท้ คุณสามารถฝังมันลงในเว็บเซอร์วิส, แอปเดสก์ท็อป หรือฟังก์ชันคลาวด์ได้โดยตรง

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **Visual Studio** (เวอร์ชันล่าสุดใดก็ได้) ติดตั้งบนเครื่องของคุณ  
2. **Aspose.GIS for .NET** – ดาวน์โหลดแพคเกจล่าสุดจาก [official download page](https://releases.aspose.com/gis/net/)  
3. **ลิขสิทธิ์ที่ถูกต้อง** (หรือรุ่นทดลองฟรี) – รับได้จาก [here](https://releases.aspose.com/)

### การตั้งค่าสภาพแวดล้อมของคุณ
1. ติดตั้ง Visual Studio หากยังไม่ได้ทำ  
2. ดาวน์โหลด Aspose.GIS for .NET จากลิงก์ข้างต้นและเพิ่มแพคเกจ NuGet ไปยังโปรเจกต์ของคุณ  
3. ใส่ไฟล์ลิขสิทธิ์ของคุณในโค้ด (หรือใช้ลิขสิทธิ์ชั่วคราวสำหรับการทดสอบ)

## นำเข้า Namespaces
เพื่อเริ่มใช้ API ให้นำเข้า namespaces ที่จำเป็น:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: สร้าง Line Strings (และ Point)
ด้านล่างเราจะ **สร้างอ็อบเจ็กต์ line string** และจุดที่จะใช้ทดสอบความสัมพันธ์การสัมผัส

```csharp
var geometry1 = new LineString();
geometry1.AddPoint(0, 0);
geometry1.AddPoint(2, 2);
var geometry2 = new LineString();
geometry2.AddPoint(2, 2);
geometry2.AddPoint(3, 3);
var geometry3 = new Point(2, 2);
var geometry4 = new LineString();
geometry4.AddPoint(1, 1);
geometry4.AddPoint(4, 4);
```

*คำอธิบาย*:  
- `geometry1` และ `geometry2` มีจุดสิ้นสุดร่วมกันที่ `(2, 2)`  
- `geometry3` เป็นจุดที่ตั้งอยู่ตรงที่จุดร่วมนั้น  
- `geometry4` ข้ามพื้นที่เดียวกันแต่ **ไม่** มีขอบเขตร่วมกับ `geometry1`

## ขั้นตอนที่ 2: ตรวจสอบความสัมพันธ์การสัมผัส
ต่อไปเราจะเรียกเมธอด `Touches` เพื่อดูว่าคู่ใดบ้างถือว่าเป็นการสัมผัส

```csharp
Console.WriteLine(geometry1.Touches(geometry2)); // True
Console.WriteLine(geometry2.Touches(geometry1)); // True
Console.WriteLine(geometry1.Touches(geometry3)); // True
Console.WriteLine(geometry1.Touches(geometry4)); // False
```

*ผลลัพธ์*:  
- การตรวจสอบสามครั้งแรกคืนค่า **True** เนื่องจากเรขาคณิตมาพบกันที่จุดเดียวโดยไม่มีการทับซ้อนของภายใน  
- การตรวจสอบครั้งสุดท้ายคืนค่า **False** เนื่องจากสอง line string ทับกันเป็นส่วนของเส้น ไม่ใช่เพียงจุดขอบเขตเดียว

## ปัญหาที่พบบ่อย & เคล็ดลับ
- **ปัญหาเรื่องความแม่นยำ** – การคำนวณ GIS ใช้เลขทศนิยม หากคุณเจอผลลัพธ์ `False` ที่ไม่คาดคิด ให้ลองทำการทำให้พิกัดเป็นมาตรฐานหรือใช้ tolerance กับ `Geometry.EqualsExact(other, tolerance)`  
- **ประเภทเรขาคณิตผสม** – `Touches` ทำงานได้กับ point, line, polygon แต่ความหมายอาจแตกต่าง; ตรวจสอบความสัมพันธ์ที่คาดหวังสำหรับโมเดลข้อมูลของคุณเสมอ  
- **ประสิทธิภาพ** – สำหรับชุดข้อมูลขนาดใหญ่ ควรทำการตรวจสอบเป็นชุดหรือใช้ spatial indexes (เช่น R‑tree) ที่ Aspose.GIS มีให้เพื่อหลีกเลี่ยงการเปรียบเทียบ O(N²)

## คำถามที่พบบ่อย

**Q: Aspose.GIS รองรับทุกเฟรมเวิร์กของ .NET หรือไม่?**  
A: รองรับ .NET Framework, .NET Core, .NET 5+, และ .NET 6+ ให้ความยืดหยุ่นสำหรับโปรเจกต์เดสก์ท็อป, เว็บ, และคลาวด์

**Q: สามารถทดลองใช้ Aspose.GIS ก่อนซื้อไลเซนส์ได้หรือไม่?**  
A: แน่นอน คุณสามารถรับรุ่นทดลองฟรีจากเว็บไซต์ Aspose [here](https://purchase.aspose.com/temporary-license/) เพื่อสำรวจฟีเจอร์ทั้งหมดรวมถึงการดำเนินการ `Touches`

**Q: จะหาแหล่งสนับสนุนสำหรับคำถามเกี่ยวกับ Aspose.GIS ได้จากที่ไหน?**  
A: เยี่ยมชม [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อถามคำถาม, แชร์ตัวอย่าง, และรับความช่วยเหลือจากชุมชนและวิศวกรของ Aspose

**Q: การอัปเดตของ Aspose.GIS มีความถี่แค่ไหน?**  
A: Aspose ปล่อยอัปเดตเป็นประจำเพื่อเพิ่มการสนับสนุนรูปแบบใหม่, ปรับปรุงประสิทธิภาพ, และแก้ไขบั๊ก ทำให้เข้ากันได้กับ .NET เวอร์ชันล่าสุด

**Q: สามารถขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.GIS ได้หรือไม่?**  
A: ได้, ลิขสิทธิ์ชั่วคราวมีให้ [here](https://purchase.aspose.com/temporary-license/) สำหรับการประเมินผล

---

**อัปเดตล่าสุด:** 2025-12-04  
**ทดสอบด้วย:** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
