---
date: 2025-12-11
description: เรียนรู้วิธีเพิ่มจุดลงในเส้นและแปลงรูปทรงเรขาคณิตเป็นรูปแบบที่แก้ไขได้อย่างง่ายดายโดยใช้
  Aspose.GIS สำหรับ .NET ตามขั้นตอนในบทเรียนนี้.
linktitle: Convert Geometry to Editable
second_title: Aspose.GIS .NET API
title: วิธีเพิ่มจุดลงใน LineString และแปลงรูปทรงเรขาคณิตเป็นรูปแบบที่แก้ไขได้ด้วย
  Aspose.GIS
url: /th/net/geometry-creation/convert-geometry-to-editable/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเพิ่มจุดลงใน LineString และแปลง Geometry ให้เป็นรูปแบบที่แก้ไขได้ด้วย Aspose.GIS

## บทนำ
เมื่อทำงานกับข้อมูลเชิงพื้นที่ ความสามารถในการ **เพิ่มจุดลงใน linestring** แล้วแก้ไขได้อย่างอิสระเป็นความต้องการทั่วไป Aspose.GIS สำหรับ .NET ทำให้กระบวนการนี้ง่ายดาย ด้วย API ที่ชัดเจนสำหรับการแปลง geometry ที่อ่าน‑ได้อย่างเดียวให้เป็นแบบที่แก้ไขได้ ในบทเรียนนี้คุณจะได้เห็นวิธีเพิ่มจุดลงใน `LineString` รับสำเนาที่แก้ไขได้ และตรวจสอบว่า geometry ดั้งเดิมยังคงไม่ถูกเปลี่ยนแปลง

## คำตอบสั้น
- **“เพิ่มจุดลงใน linestring” หมายถึงอะไร?** หมายถึงการแทรกพิกัดใหม่เข้าไปใน geometry `LineString` ที่มีอยู่  
- **ไลบรารีใดสนับสนุนสิ่งนี้?** Aspose.GIS สำหรับ .NET มีเมธอด `ToEditable()` และฟังก์ชัน `AddPoint()`  
- **ต้องมีลิขสิทธิ์สำหรับฟีเจอร์นี้หรือไม่?** สามารถใช้รุ่นทดลองฟรีสำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7  
- **ใช้เวลาพัฒนาเท่าไหร่?** ปกติใช้เวลาน้อยกว่า 10 นาทีสำหรับสถานการณ์พื้นฐาน

## “เพิ่มจุดลงใน linestring” คืออะไร?
การเพิ่มจุดลงใน `LineString` จะใส่เวอร์เท็กซ์ใหม่ที่พิกัดที่ระบุ ทำให้เส้นยืดหรือมีรายละเอียดมากขึ้น การดำเนินการนี้สำคัญสำหรับการแก้ไขเส้นทาง, การแก้ไขแผนที่, หรือการสร้าง geometry แบบไดนามิก

## ทำไมต้องใช้ Aspose.GIS สำหรับงานนี้?
- **ไม่มีการพึ่งพาไลบรารีภายนอก** – API จัดการการแปลง geometry ภายในเอง  
- **ความปลอดภัยแบบอ่าน‑อย่างเดียว** – geometry ดั้งเดิมคงเป็น immutable ป้องกันการเปลี่ยนแปลงโดยบังเอิญ  
- **ไวยากรณ์ง่าย** – เมธอดเช่น `ToEditable()` และ `AddPoint()` เข้าใจง่ายสำหรับนักพัฒนา C#  
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS .NET runtimes

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามขั้นตอนต่อไปนี้ให้แน่ใจว่าคุณมี:

- **สภาพแวดล้อม .NET** – ติดตั้ง .NET framework จาก [website](https://dotnet.microsoft.com/download)  
- **ไลบรารี Aspose.GIS** – ดาวน์โหลดแพ็กเกจล่าสุดจาก [releases page](https://releases.aspose.com/gis/net/)  
- **พื้นฐาน C#** – ความคุ้นเคยกับไวยากรณ์ C# และแอปพลิเคชันคอนโซล

### นำเข้า Namespaces
เพื่อเริ่มต้นกระบวนการ ให้แน่ใจว่าได้นำเข้า namespaces ที่จำเป็นในโค้ด C# ของคุณ ซึ่งจะทำให้คุณเข้าถึงฟังก์ชันของ Aspose.GIS สำหรับ .NET

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

ตอนนี้เราจะเดินผ่านขั้นตอนที่เป็นรูปธรรมสำหรับการแปลง geometry ให้เป็นรูปแบบที่แก้ไขได้และเพิ่มจุดลงใน `LineString`

## ขั้นตอนที่ 1: กำหนด Geometry แบบอ่าน‑อย่างเดียว
แรกสุด สร้างอ็อบเจกต์ geometry แบบอ่าน‑อย่างเดียวที่แทนเส้นง่าย ๆ อ็อบเจกต์นี้ไม่สามารถแก้ไขได้โดยตรง

```csharp
ILineString readOnlyLine = (ILineString)Geometry.FromText("LINESTRING (1 1, 2 2)");
```

## ขั้นตอนที่ 2: รับสำเนาที่แก้ไขได้
เพื่อแก้ไข geometry ให้ใช้เมธอด `ToEditable()` เพื่อสร้างสำเนาที่สามารถแก้ไขได้ ในขณะที่ geometry ดั้งเดิมยังคงไม่ถูกเปลี่ยนแปลง

```csharp
LineString editableLine = readOnlyLine.ToEditable();
```

## ขั้นตอนที่ 3: เพิ่มจุดลงใน LineString
เมื่อคุณมีสำเนาที่แก้ไขได้แล้ว คุณสามารถ **เพิ่มจุดลงใน linestring** ได้ เมธอด `AddPoint` จะเพิ่มเวอร์เท็กซ์ใหม่ที่พิกัดที่ระบุ

```csharp
editableLine.AddPoint(3, 3);
```

## ขั้นตอนที่ 4: แสดง Geometry ที่แก้ไขแล้ว
พิมพ์ geometry ที่แก้ไขแล้วเพื่อยืนยันว่าจุดใหม่ถูกเพิ่มสำเร็จ

```csharp
Console.WriteLine(editableLine.AsText()); // LINESTRING (1 1, 2 2, 3 3)
```

## ขั้นตอนที่ 5: ตรวจสอบว่า Geometry ดั้งเดิมไม่เปลี่ยนแปลง
เป็นแนวปฏิบัติที่ดีในการยืนยันว่า geometry แบบอ่าน‑อย่างเดียวเดิมไม่ได้รับการแก้ไข

```csharp
Console.WriteLine(readOnlyLine.AsText()); // LINESTRING (1 1, 2 2)
```

## ข้อผิดพลาดทั่วไป & เคล็ดลับ
- **ห้ามแก้ไขอ็อบเจกต์แบบอ่าน‑อย่างเดียว** – ต้องเรียก `ToEditable()` ก่อนเสมอ  
- **ลำดับพิกัดสำคัญ** – ตรวจสอบให้แน่ใจว่าคุณส่ง (X, Y) ในลำดับที่ถูกต้อง  
- **Geometry ขนาดใหญ่** – สำหรับ `LineString` ยาวมาก ควรทำการแก้ไขเป็นชุดเพื่อเพิ่มประสิทธิภาพ

## คำถามที่พบบ่อย

**Q: Aspose.GIS รองรับไลบรารี .NET อื่น ๆ หรือไม่?**  
A: ใช่, Aspose.GIS สามารถทำงานร่วมกับไลบรารี GIS .NET ยอดนิยมเช่น NetTopologySuite และ SharpMap ได้อย่างราบรื่น

**Q: ฉันสามารถลองใช้ Aspose.GIS ก่อนซื้อได้หรือไม่?**  
A: แน่นอน! คุณสามารถรับรุ่นทดลองฟรีจาก [releases page](https://releases.aspose.com/) เพื่อสำรวจคุณสมบัติต่าง ๆ

**Q: จะขอรับการสนับสนุนสำหรับ Aspose.GIS ได้อย่างไร?**  
A: เยี่ยมชม [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อรับความช่วยเหลือจากชุมชนและการสนับสนุนอย่างเป็นทางการ

**Q: มีลิขสิทธิ์ชั่วคราวสำหรับการประเมินหรือไม่?**  
A: มี, สามารถขอรับลิขสิทธิ์ชั่วคราวได้ผ่าน [Aspose.GIS purchase page](https://purchase.aspose.com/temporary-license/)

**Q: สามารถซื้อ Aspose.GIS โดยตรงได้หรือไม่?**  
A: ได้เลย! ใช้ [purchase page](https://purchase.aspose.com/buy) เพื่อเลือกซื้อไลเซนส์ที่เหมาะกับความต้องการของคุณ

---

**อัปเดตล่าสุด:** 2025-12-11  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}