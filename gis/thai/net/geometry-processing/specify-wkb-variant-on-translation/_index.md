---
date: 2025-12-21
description: เรียนรู้วิธีสร้างเรขาคณิตแบบ linestring และแปลงเรขาคณิตเป็น WKB ด้วย
  Aspose.GIS สำหรับ .NET โดยใช้รุ่น ExtendedPostGis
linktitle: Specify WKB Variant on Translation
second_title: Aspose.GIS .NET API
title: สร้างเรขาคณิต Linestring และรูปแบบ WKB ใน Aspose.GIS .NET
url: /th/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ระบุ WKB Variant ในการแปลงใน Aspose.GIS สำหรับ .NET

## บทนำ
ในโลกของการพัฒนา Geographic Information Systems (GIS) Aspose.GIS สำหรับ .NET โดดเด่นในฐานะชุดเครื่องมือที่ทรงพลัง หากคุณต้องการ **สร้างเรขาคณิต linestring** แล้ว **แปลงเรขาคณิตเป็น WKB** คุณมาถูกที่แล้ว ความหลากหลายและประสิทธิภาพของมันทำให้เป็นตัวเลือกที่หลายคนนิยมใช้สำหรับนักพัฒนาที่ต้องการบูรณาการฟังก์ชัน GIS เข้าในแอปพลิเคชัน .NET ของตนอย่างราบรื่น บทความนี้เป็นคู่มือฉบับสมบูรณ์ในการใช้ Aspose.GIS สำหรับ .NET โดยมุ่งเน้นที่การระบุ WKB (Well‑Known Binary) variant ในกระบวนการแปลง

## คำตอบสั้น
- **WKB ย่อมาจากอะไร?** Well‑Known Binary, การแทนค่าดิจิทัลแบบกะทัดรัดของวัตถุเรขาคณิต  
- **WKB variant ใดที่บันทึกข้อมูล SRID ได้?** variant `ExtendedPostGis` (EWKB)  
- **ต้องมีลิขสิทธิ์เพื่อรันโค้ดหรือไม่?** จำเป็นต้องมีลิขสิทธิ์ชั่วคราวหรือเต็มสำหรับการใช้งานในสภาพแวดล้อมการผลิต  
- **รองรับ .NET เวอร์ชันใดบ้าง?** .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6+  
- **การทำงานใช้เวลานานเท่าไหร่?** ปกติใช้เวลาน้อยกว่า 10 นาทีสำหรับตัวอย่างพื้นฐาน

## Linestring Geometry คืออะไร?
Linestring คือรูปทรงเรขาคณิตแบบง่ายที่ประกอบด้วยลำดับจุดที่เชื่อมต่อด้วยเส้นตรง มักใช้แทนถนน แม่น้ำ หรือคุณลักษณะเชิงเส้นใด ๆ ในข้อมูล GIS

## ทำไมต้องระบุ WKB Variant?
การเลือก WKB variant ที่เหมาะสมช่วยให้เมตาดาต้าที่สำคัญ—เช่น Spatial Reference System Identifier (SRID)—ถูกเก็บรักษาไว้เมื่อคุณบันทึกหรือแลกเปลี่ยนข้อมูลเรขาคณิต variant `ExtendedPostGis` (EWKB) มีประโยชน์เป็นพิเศษเมื่อทำงานกับ PostgreSQL/PostGIS หรือระบบใด ๆ ที่คาดหวังข้อมูล SRID ฝังอยู่ในไบนารี

## ข้อกำหนดเบื้องต้น
ก่อนจะเจาะลึกการระบุ WKB variant ใน Aspose.GIS สำหรับ .NET ให้ตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งานแล้ว:

### การติดตั้ง Aspose.GIS สำหรับ .NET
1. ดาวน์โหลด Aspose.GIS: ไปที่ [download link](https://releases.aspose.com/gis/net/) เพื่อรับแพคเกจ Aspose.GIS สำหรับ .NET  
2. ติดตั้งแพคเกจ: ปฏิบัติตามคำแนะนำการติดตั้งในเอกสารเพื่อผสาน Aspose.GIS เข้ากับสภาพแวดล้อม .NET ของคุณอย่างราบรื่น

### ความคุ้นเคยกับการเขียนโปรแกรม C#
1. ความรู้พื้นฐาน C#: ตรวจสอบว่าคุณมีความเข้าใจพื้นฐานเกี่ยวกับไวยากรณ์และแนวคิดของภาษา C#  

## นำเข้า Namespaces
เพื่อเริ่มต้นการทำงานกับ Aspose.GIS สำหรับ .NET และใช้ฟังก์ชันต่าง ๆ อย่างมีประสิทธิภาพ คุณต้องนำเข้า namespaces ที่จำเป็นเข้าสู่โปรเจกต์ของคุณ ด้านล่างเป็นขั้นตอนแบบทีละขั้นตอน:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Namespaces เหล่านี้ให้การเข้าถึงฟังก์ชันของ Aspose.GIS ทำให้คุณสามารถทำงานกับข้อมูลเชิงพื้นที่ได้อย่างง่ายดาย

## วิธีสร้าง linestring geometry?
เราจะวิเคราะห์ตัวอย่างที่ให้ไว้เป็นหลายขั้นตอน เพื่อทำความเข้าใจกระบวนการระบุ WKB variant ในการแปลงอย่างละเอียด

### ขั้นตอนที่ 1: สร้าง Geometry Object
```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
ในขั้นตอนนี้ เรา **สร้างเรขาคณิต linestring** ที่แทนคุณลักษณะเชิงเส้นด้วยพิกัดที่ระบุ

### ขั้นตอนที่ 2: สร้างการแทนค่า WKB
```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
ที่นี่ เรา **แปลงเรขาคณิตเป็น WKB** โดยใช้ variant `ExtendedPostGis` ซึ่งฝังข้อมูล SRID ไว้ด้วย

### ขั้นตอนที่ 3: เขียนลงไฟล์
```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
สุดท้าย เราเขียนข้อมูลไบนารี WKB ที่สร้างขึ้นลงไฟล์ชื่อ `EWkbFile.ewkb` ในไดเรกทอรีที่คุณเลือก

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| **ไฟล์ว่าง** | `Path.Combine` ชี้ไปยังไดเรกทอรีที่ไม่มีอยู่ | ตรวจสอบให้แน่ใจว่าไดเรกทอรีเป้าหมายมีอยู่หรือสร้างด้วย `Directory.CreateDirectory` |
| **SRID ไม่ถูกต้อง** | ใช้ `WkbVariant.Standard` เริ่มต้นทำให้สูญเสีย SRID | ใช้ `WkbVariant.ExtendedPostGis` เสมอเมื่อจำเป็นต้องเก็บ SRID |
| **License exception** | รันโดยไม่มีลิขสิทธิ์ที่ถูกต้องในสภาพแวดล้อมการผลิต | ใส่ลิขสิทธิ์ชั่วคราวหรือเต็มก่อนรันโค้ดในสภาพแวดล้อมการผลิต |

## คำถามที่พบบ่อย
### Aspose.GIS สำหรับ .NET รองรับทุกเวอร์ชันของ .NET หรือไม่?
Aspose.GIS สำหรับ .NET ถูกออกแบบให้เข้ากันได้กับหลายเวอร์ชันของ .NET เพื่อให้มีความยืดหยุ่นและเข้าถึงได้สำหรับนักพัฒนา

### สามารถขอรับการสนับสนุนหรือความช่วยเหลือขณะใช้ Aspose.GIS สำหรับ .NET ได้หรือไม่?
ได้ คุณสามารถขอรับการสนับสนุนและความช่วยเหลือผ่าน [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) ซึ่งผู้เชี่ยวชาญและนักพัฒนาคนอื่น ๆ จะตอบคำถามของคุณ

### Aspose.GIS สำหรับ .NET มีรุ่นทดลองฟรีหรือไม่?
มี คุณสามารถสำรวจคุณลักษณะและความสามารถของ Aspose.GIS สำหรับ .NET ผ่านรุ่นทดลองฟรีที่ [this link](https://releases.aspose.com/)

### จะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.GIS สำหรับ .NET ได้อย่างไร?
คุณสามารถขอรับลิขสิทธิ์ชั่วคราวได้โดยไปที่ [temporary license page](https://purchase.aspose.com/temporary-license/) แล้วทำตามคำแนะนำที่ให้ไว้

### จะซื้อลิขสิทธิ์สำหรับ Aspose.GIS สำหรับ .NET ได้จากที่ไหน?
คุณสามารถซื้อลิขสิทธิ์สำหรับ Aspose.GIS สำหรับ .NET ได้จากหน้าการซื้อที่ [this link](https://purchase.aspose.com/buy)

## Frequently Asked Questions
**Q: สามารถใช้ไฟล์ EWKB กับ PostGIS ได้หรือไม่?**  
A: ใช่, variant `ExtendedPostGis` จะสร้าง EWKB ที่รวม SRID ซึ่ง PostGIS สามารถอ่านได้โดยตรง

**Q: สามารถอ่านไฟล์ WKB กลับมาเป็น Geometry Object ได้หรือไม่?**  
A: แน่นอน ใช้ `Geometry.FromBinary(byteArray)` เพื่อสร้างเรขาคณิตใหม่จากไบนารี

**Q: ไลบรารีสนับสนุนประเภทเรขาคณิตอื่น ๆ เช่น polygons หรือไม่?**  
A: รองรับ Aspose.GIS จัดการกับ points, linestrings, polygons, multipolygons และอื่น ๆ อีกมาก

**Q: จะระบุ SRID ที่แตกต่างเมื่อสร้างเรขาคณิตได้อย่างไร?**  
A: ตั้งค่า SRID บนวัตถุเรขาคณิตก่อนเรียก `AsBinary` เช่น `geometry.SRID = 4326;`

**Q: โค้ดนี้ทำงานบน .NET Core ได้หรือไม่?**  
A: ได้, API เดียวกันทำงานได้บน .NET Framework, .NET Core, และ .NET 5/6  

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.GIS สำหรับ .NET 23.9 (ล่าสุด ณ เวลาที่เขียน)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}