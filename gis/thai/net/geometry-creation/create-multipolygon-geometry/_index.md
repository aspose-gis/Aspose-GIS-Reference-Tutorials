---
date: 2025-12-17
description: เรียนรู้วิธีสร้างเรขาคณิตมัลติพอลิกอนใน ASP.NET ด้วย Aspose.GIS สำหรับ
  .NET คู่มือขั้นตอนต่อขั้นตอน ทดลองใช้งานฟรีและข้อมูลการให้สิทธิ์ใช้งาน
linktitle: Create MultiPolygon Geometry
second_title: Aspose.GIS .NET API
title: วิธีสร้างเรขาคณิตมัลติโพลิกอนใน asp.net ด้วย Aspose.GIS
url: /th/net/geometry-creation/create-multipolygon-geometry/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างรูปทรง MultiPolygon ด้วย Aspose.GIS

## บทนำ
หากคุณต้องการ **create multipolygon geometry asp.net**, Aspose.GIS for .NET ให้ API ที่สะอาดและปลอดภัยต่อประเภทที่ทำงานบนแพลตฟอร์ม .NET ใดก็ได้ ในบทเรียนนี้เราจะเดินผ่านกระบวนการทั้งหมด—ตั้งแต่การติดตั้งไลบรารีจนถึงการสร้างอ็อบเจ็กต์ MultiPolygon ที่คุณสามารถส่งออกเป็น Shapefile, GeoJSON หรือรูปแบบอื่นที่รองรับ ไม่ว่าคุณจะสร้างบริการเว็บแมพปิ้งหรือเครื่องมือ GIS บนเดสก์ท็อป การเชี่ยวชาญกระบวนการนี้จะช่วยประหยัดเวลาและลดบั๊ก

## คำตอบอย่างรวดเร็ว
- **What can I build with this?** แอปพลิเคชัน GIS ใดก็ได้ที่ต้องการพื้นที่หลายเหลี่ยมที่ซับซ้อน เช่น แผนที่การใช้ที่ดินหรือโซนการจัดส่ง.  
- **Do I need a license?** การทดลองใช้ฟรีทำงานสำหรับการพัฒนา; จำเป็นต้องมีลิขสิทธิ์ถาวรสำหรับการใช้งานจริง.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **How long does the code take to write?** ประมาณ 5‑10 นาทีสำหรับ MultiPolygon พื้นฐาน.  
- **Can I export the result?** ใช่—ใช้เมธอด `Save` ที่มีในตัวเพื่อเขียนเป็น Shapefile, GeoJSON ฯลฯ.

## MultiPolygon Geometry คืออะไร?
A **MultiPolygon** คือการรวบรวมหลายหลายเหลี่ยมที่อาจแยกจากกันหรือมีรูปร่างเป็นรู (holes). ในศัพท์ GIS มันแสดงชุดของฟีเจอร์เชิงพื้นที่ที่มีแอตทริบิวต์เดียวกันแต่แยกกันทางเรขาคณิต—เหมาะสำหรับการแทนประเทศที่ประกอบด้วยเกาะหรือแปลงที่มีหลายส่วน.

## ทำไมต้องใช้ Aspose.GIS สำหรับ .NET?
- **Full‑featured API** – ไม่มีการพึ่งพาเนทีฟภายนอก, โค้ดที่จัดการทั้งหมด.  
- **Cross‑platform** – ทำงานบน Windows, Linux, และ macOS.  
- **Rich format support** – อ่าน/เขียนหลายสิบรูปแบบเวกเตอร์โดยไม่ต้องตั้งค่าเพิ่มเติม.  
- **Performance‑optimized** – จัดการชุดข้อมูลขนาดใหญ่ด้วยการใช้หน่วยความจำน้อย.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **Visual Studio 2022** (หรือ IDE C# ใดก็ได้) ที่ติดตั้ง .NET 6 SDK แล้ว.  
2. แพคเกจ **Aspose.GIS for .NET** – ดาวน์โหลดจาก [download page](https://releases.aspose.com/gis/net/) และทำตามคู่มือการติดตั้งในเอกสาร.

## การนำเข้า Namespaces
เพิ่มคำสั่ง `using` ที่จำเป็นในโปรเจกต์ของคุณเพื่อให้คอมไพเลอร์รู้ว่าชนิด GIS อยู่ที่ไหน:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: สร้าง Linear Rings
A **LinearRing** คือ `LineString` ปิดที่กำหนดขอบเขตภายนอกหรือภายในของหลายเหลี่ยม ที่นี่เราจะสร้างสองวงที่ง่าย:

```csharp
LinearRing firstRing = new LinearRing();
firstRing.AddPoint(8.5, -2.5);
firstRing.AddPoint(-8.5, 2.5);
firstRing.AddPoint(8.5, -2.5);
LinearRing secondRing = new LinearRing();
secondRing.AddPoint(7.6, -3.6);
secondRing.AddPoint(-9.6, 1.5);
secondRing.AddPoint(7.6, -3.6);
```

> **Pro tip:** จุดแรกและจุดสุดท้ายต้องเหมือนกันเพื่อปิดวง; Aspose.GIS จะปิดอัตโนมัติหากคุณละเว้นจุดสุดท้าย, แต่การระบุอย่างชัดเจนจะช่วยหลีกเลี่ยงความสับสน.

## ขั้นตอนที่ 2: สร้าง Polygons
แต่ละ `Polygon` สร้างจาก `LinearRing`. คุณสามารถเพิ่มวงใน (holes) ต่อมาได้หากต้องการ.

```csharp
Polygon firstPolygon = new Polygon(firstRing);
Polygon secondPolygon = new Polygon(secondRing);
```

## ขั้นตอนที่ 3: สร้าง MultiPolygon
ตอนนี้เราจะรวมสองหลายเหลี่ยมเป็นอ็อบเจ็กต์ `MultiPolygon` เดียว—นี่คือขั้นตอนที่ทำให้คุณ **create multipolygon geometry asp.net**.

```csharp
MultiPolygon multiPolygon = new MultiPolygon();
multiPolygon.Add(firstPolygon);
multiPolygon.Add(secondPolygon);
```

ตอนนี้คุณมี `MultiPolygon` ที่ทำงานเต็มรูปแบบที่คุณสามารถจัดการ, คิวรี, หรือทำการซีเรียลไลซ์.

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| **Ring not closed** | ไม่มีการทำซ้ำของจุดแรก | ตรวจสอบให้แน่ใจว่าจุดแรกและจุดสุดท้ายเหมือนกัน, หรือเรียก `LinearRing.Close()` อย่างชัดเจน. |
| **Incorrect coordinate order** | ละ/ลองจิจูดสลับกัน | Aspose.GIS คาดหวัง **X = longitude**, **Y = latitude**. ตรวจสอบแหล่งข้อมูลของคุณ. |
| **Exception on `Add`** | เพิ่มหลายเหลี่ยมที่เป็น null | ตรวจสอบว่าแต่ละอินสแตนซ์ของ `Polygon` ถูกสร้างก่อนเพิ่มเข้า `MultiPolygon`. |

## สรุป
โดยทำตามขั้นตอนเหล่านี้คุณได้เรียนรู้วิธี **create multipolygon geometry asp.net** ด้วย Aspose.GIS สำหรับ .NET พื้นฐานนี้ทำให้คุณสร้างโมเดลเชิงพื้นที่ที่ซับซ้อนขึ้น, ทำการคิวรีเชิงพื้นที่, และส่งออกข้อมูลไปยังรูปแบบ GIS ที่รองรับทั้งหมด ต่อไปสำรวจเมธอดเช่น `Contains`, `Intersects`, หรือ `Transform` เพื่อเพิ่มพลังการวิเคราะห์ให้กับแอปพลิเคชันของคุณ.

## คำถามที่พบบ่อย
### Aspose.GIS สำหรับ .NET เหมาะกับผู้เริ่มต้นหรือไม่?
แน่นอน! Aspose.GIS มีเอกสารและบทเรียนที่ครอบคลุมเพื่อช่วยนักพัฒนาทุกระดับเริ่มต้น.

### ฉันสามารถลอง Aspose.GIS ก่อนซื้อได้หรือไม่?
ได้, คุณสามารถดาวน์โหลดเวอร์ชันทดลองฟรีจาก [here](https://releases.aspose.com/) เพื่อสำรวจคุณสมบัติก่อนทำการซื้อ.

### ฉันจะหา support สำหรับ Aspose.GIS ได้จากที่ไหน?
คุณสามารถเยี่ยมชมฟอรั่ม Aspose.GIS [here](https://forum.aspose.com/c/gis/33) เพื่อถามคำถามและรับความช่วยเหลือจากชุมชน.

### มีใบอนุญาตชั่วคราวสำหรับ Aspose.GIS หรือไม่?
ได้, คุณสามารถรับใบอนุญาตชั่วคราวจาก [here](https://purchase.aspose.com/temporary-license/) เพื่อการประเมิน.

### ฉันสามารถซื้อ Aspose.GIS โดยตรงได้หรือไม่?
ได้, คุณสามารถซื้อ Aspose.GIS จากเว็บไซต์ [here](https://purchase.aspose.com/buy).

## คำถามที่พบบ่อย
**Q: ฉันจะบันทึก MultiPolygon ไปยังไฟล์ได้อย่างไร?**  
A: ใช้คลาส `Feature` เพื่อห่อหุ้ม geometry และเรียก `feature.Save("output.shp", Drivers.Shapefile);`.

**Q: ฉันสามารถเพิ่มวงใน (holes) ให้กับหลายเหลี่ยมได้หรือไม่?**  
A: ได้—สร้าง `LinearRing` ที่สองและส่งเป็นอาร์กิวเมนต์ที่สองให้กับคอนสตรัคเตอร์ `Polygon`.

**Q: สามารถแปลงพิกัดไปยังระบบอ้างอิงเชิงพื้นที่อื่นได้หรือไม่?**  
A: แน่นอน. เรียก `multiPolygon.Transform(sourceCRS, targetCRS);` โดยที่วัตถุ CRS ถูกกำหนดผ่านรหัส EPSG.

---

**อัปเดตล่าสุด:** 2025-12-17  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}