---
date: 2026-04-03
description: เรียนรู้วิธีสร้างรูปหลายเหลี่ยมที่มีรู (hole) ด้วย Aspose.GIS สำหรับ
  .NET คู่มือนี้จะแสดงวิธีสร้างรูในรูปหลายเหลี่ยมและทำงานกับข้อมูลเชิงพื้นที่
keywords:
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
linktitle: สร้างรูปหลายเหลี่ยมที่มีรู
second_title: Aspose.GIS .NET API
title: สร้างรูปหลายเหลี่ยมที่มีรูภายในโดยใช้ Aspose.GIS
url: /th/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างรูปหลายเหลี่ยมที่มีรูโดยใช้ Aspose.GIS

## บทนำ
ในบทแนะนำนี้ คุณจะ **create polygon with hole** geometry โดยใช้ Aspose.GIS สำหรับ .NET ไม่ว่าคุณจะกำลังสร้างแอปพลิเคชันแผนที่, ทำการวิเคราะห์เชิงพื้นที่, หรือเตรียมข้อมูลสำหรับบริการ GIS การรู้วิธีใส่รูภายในรูปหลายเหลี่ยมเป็นสิ่งสำคัญ เราจะเดินผ่านกระบวนการทั้งหมดทีละขั้นตอน ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการสร้างอ็อบเจ็กต์รูปหลายเหลี่ยมขั้นสุดท้าย

## คำตอบด่วน
- **What does “create polygon with hole” mean?** หมายถึงการสร้างรูปหลายเหลี่ยมที่มีหนึ่งหรือหลายวงแหวนภายใน (รู) ซึ่งไม่ได้รวมอยู่ในพื้นที่  
- **Which library handles this?** Aspose.GIS for .NET ให้การสนับสนุนเต็มรูปแบบสำหรับวงแหวนภายนอกและภายใน  
- **Do I need a license?** การทดลองใช้ฟรีทำงานได้สำหรับการพัฒนา; จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **How long does it take?** โดยทั่วไปใช้เวลาน้อยกว่า 10 นาทีในการดำเนินการและทดสอบ  

## วิธีเพิ่มรูในรูปหลายเหลี่ยมโดยใช้ Aspose.GIS
การเพิ่มรูเป็นเรื่องง่ายเพียงการกำหนด **interior ring** แล้วผูกเข้ากับรูปหลายเหลี่ยม ไลบรารีจะจัดการเรื่องการกำหนดทิศทางและความถูกต้องให้คุณ จึงสามารถมุ่งเน้นที่พิกัดที่แทนช่องว่างที่ต้องการได้

## “create polygon with hole” คืออะไร?
การสร้างรูปหลายเหลี่ยมที่มีรูเกี่ยวข้องกับการกำหนด **exterior ring** ที่ร่างขอบเขตภายนอกและหนึ่งหรือหลาย **interior rings** ที่ตัดส่วนว่างออกออกไป วงแหวนภายในมักเรียกว่า *holes* เนื่องจากเป็นพื้นที่ที่ไม่เป็นส่วนหนึ่งของพื้นผิวรูปหลายเหลี่ยม

## ทำไมต้องสร้างรูในรูปหลายเหลี่ยมโดยใช้ Aspose.GIS?
- **Accurate spatial modeling:** คุณลักษณะจริงเช่นทะเลสาบภายในแปลงที่ดินหรือลานกลางภายในอาคารต้องการรู  
- **Interoperability:** รูปแบบเช่น Shapefile, GeoJSON, และ GML รองรับวงแหวนภายในโดยธรรมชาติ; Aspose.GIS รักษาไว้  
- **Performance:** ไลบรารีจัดการความถูกต้องของเรขาคณิต ทำให้คุณไม่ต้องเขียนโค้ดตรวจสอบความถูกต้องเอง  

## กรณีการใช้งานจริงสำหรับรูปหลายเหลี่ยมที่มีรู
1. **Land parcel with an internal lake** – ทะเลสาบถูกจำลองเป็นรูจึงไม่ถูกรวมในพื้นที่ของแปลง  
2. **Building footprints with courtyards** – ลานกลางถูกตัดออกจากรอยเท้าอาคาร  
3. **Protected zones inside a larger conservation area** – คุณสามารถตัดส่วนที่จำกัดออกโดยไม่ต้องสร้างเลเยอร์แยก  

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้:
1. Aspose.GIS for .NET Library: คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/gis/net/).  
2. Development Environment: ตรวจสอบว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาพร้อม Visual Studio หรือ IDE .NET อื่นใดที่ติดตั้งแล้ว  

## นำเข้า Namespaces
ก่อนอื่น คุณต้องนำเข้า namespaces ที่จำเป็นเพื่อทำงานกับฟังก์ชันของ Aspose.GIS ต่อไปนี้คือวิธีทำ:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

ต่อไป เราจะดำเนินการสร้างรูปหลายเหลี่ยมที่มีรูโดยใช้ Aspose.GIS สำหรับ .NET

## ขั้นตอนที่ 1: สร้างอ็อบเจ็กต์ Polygon
เราเริ่มโดยสร้างอ็อบเจ็กต์ `Polygon` ว่างที่หลังจากนี้จะเก็บทั้งวงแหวนภายนอกและภายใน

```csharp
Polygon polygon = new Polygon();
```

## ขั้นตอนที่ 2: กำหนด Exterior Ring
Exterior Ring กำหนดขอบเขตภายนอกของรูปหลายเหลี่ยม เพิ่มจุดตามลำดับตามเข็มนาฬิกาเพื่อสร้างรูปแบบที่ปิด

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## ขั้นตอนที่ 3: กำหนด Interior Ring (รู)
ต่อไป เราจะสร้าง interior ring—ซึ่งเป็น **hole** ที่จะถูกตัดออกจากพื้นที่ของรูปหลายเหลี่ยม จุดมักจะเพิ่มตามลำดับทวนเข็มนาฬิกา แต่ Aspose.GIS จะจัดการทิศทางโดยอัตโนมัติ

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## ขั้นตอนที่ 4: กำหนด Exterior Ring และเพิ่ม Interior Ring ไปยัง Polygon
สุดท้าย ผูก exterior ring เข้ากับ polygon แล้วเพิ่ม interior ring (รู) วิธี `AddInteriorRing` สามารถเรียกหลายครั้งหากต้องการหลายรู

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## เคล็ดลับและแนวปฏิบัติที่ดีที่สุด
- **Orientation matters for readability** – แม้ว่า Aspose.GIS จะปรับทิศทางอัตโนมัติ การรักษา exterior rings ให้เป็นตามเข็มนาฬิกาและ interior rings ให้เป็นทวนเข็มนาฬิกาจะทำให้เรขาคณิตตรวจสอบง่ายขึ้นใน GIS viewer  
- **Close each ring** – ควรทำซ้ำพิกัดแรกเป็นจุดสุดท้ายเสมอ เพื่อรับประกันรูปแบบที่ปิดและถูกต้อง  
- **Validate after creation** – คุณสามารถเรียก `polygon.IsValid` เพื่อตรวจสอบว่าเรขาคณิตสอดคล้องกับมาตรฐาน OGC ก่อนบันทึก  

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|-----|
| รูไม่แสดงใน GIS viewer | การกำหนดทิศทางของ interior ring ผกผัน | ตรวจสอบให้เพิ่มจุดในทิศทางตรงกันข้ามกับ exterior ring (ทวนเข็มนาฬิกา). |
| ข้อผิดพลาด Polygon ไม่ถูกต้อง | วงแหวนไม่ปิด (จุดแรก ≠ จุดสุดท้าย) | ทำซ้ำจุดแรกเป็นจุดสุดท้ายในแต่ละวงแหวน (ตามที่แสดงด้านบน). |
| เรขาคณิตว่างที่ไม่คาดคิด | ลืมกำหนด `ExteriorRing` ก่อนเพิ่ม interior rings | กำหนด `polygon.ExteriorRing` ก่อน แล้วจึงเรียก `AddInteriorRing`. |

## คำถามที่พบบ่อย
### 1. Aspose.GIS คืออะไร?
Aspose.GIS เป็นไลบรารี .NET ที่ช่วยให้นักพัฒนาสามารถทำงานกับข้อมูลเชิงพื้นที่ได้ โดยสามารถสร้าง อ่าน และจัดการรูปแบบไฟล์เชิงพื้นที่ต่าง ๆ

### 2. ฉันสามารถใช้ Aspose.GIS สำหรับโครงการเชิงพาณิชย์ได้หรือไม่?
ได้ คุณสามารถใช้ Aspose.GIS สำหรับโครงการส่วนบุคคลและเชิงพาณิชย์ได้โดยการซื้อไลเซนส์ เยี่ยมชม [here](https://purchase.aspose.com/buy) เพื่อดูรายละเอียดเพิ่มเติม

### 3. มีการทดลองใช้ฟรีสำหรับ Aspose.GIS หรือไม่?
ได้ คุณสามารถใช้การทดลองฟรีของ Aspose.GIS ได้จาก [here](https://releases.aspose.com/).

### 4. ฉันสามารถหาการสนับสนุนสำหรับ Aspose.GIS ได้ที่ไหน?
คุณสามารถหาการสนับสนุนสำหรับ Aspose.GIS ได้ที่ [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### 5. ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.GIS อย่างไร?
คุณสามารถขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.GIS ได้จาก [here](https://purchase.aspose.com/temporary-license/).

---

**อัปเดตล่าสุด:** 2026-04-03  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}