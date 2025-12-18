---
date: 2025-12-18
description: Learn how to add latitude longitude to geospatial data in .NET applications
  using Aspose.GIS for .NET. Create, analyze, and visualize maps effortlessly.
linktitle: Create LineString Geometry
second_title: Aspose.GIS .NET API
title: Add Latitude Longitude with Aspose.GIS for .NET
url: /th/net/geometry-creation/create-linestring-geometry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มละติจูดและลองจิจูดด้วย Aspose.GIS สำหรับ .NET

## บทนำ
Aspose.GIS for .NET เป็นไลบรารีที่ทรงพลังที่ช่วยให้นักพัฒนาสามารถ **เพิ่มละติจูดและลองจิจูด** และทำงานกับข้อมูลเชิงพื้นที่ในแอปพลิเคชัน .NET ของพวกเขาได้อย่างราบรื่น ไม่ว่าคุณจะกำลังสร้างแอปพลิเคชันแผนที่, วิเคราะห์ข้อมูลเชิงพื้นที่, หรือรวมบริการที่อิงตำแหน่ง, Aspose.GIS มีเครื่องมือที่คุณต้องการเพื่อ **จัดการข้อมูลเชิงพื้นที่** อย่างมีประสิทธิภาพและจัดการข้อมูลทางภูมิศาสตร์

## คำตอบอย่างรวดเร็ว
- **“add latitude longitude” หมายถึงอะไร?** หมายถึงการแทรกคู่พิกัดทางภูมิศาสตร์ (latitude, longitude) ลงในอ็อบเจ็กต์ geometry.  
- **ไลบรารีใดช่วยคุณเพิ่มละติจูดและลองจิจูดใน .NET?** Aspose.GIS for .NET.  
- **ฉันต้องการไลเซนส์สำหรับการใช้งานในสภาพแวดล้อมการผลิตหรือไม่?** ใช่, จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานในสภาพแวดล้อมการผลิต.  
- **ฉันสามารถใช้กับ .NET 6 หรือเวอร์ชันใหม่กว่าได้หรือไม่?** ได้แน่นอน – ไลบรารีรองรับ .NET 5+, .NET 6, และ .NET 7.  
- **มีเมธอดในตัวที่ใช้เพิ่มจุดลงในเส้นหรือไม่?** ใช่, เมธอด `AddPoint` ของ `LineString` จะเพิ่มคู่ latitude‑longitude ลงในเส้น.

## “add latitude longitude” หมายถึงอะไรใน Aspose.GIS?
การเพิ่มละติจูดและลองจิจูดหมายถึงการแทรกคู่พิกัดลงใน geometry เช่น `LineString` พิกัดเหล่านี้กำหนดรูปทรงและตำแหน่งของ geometry บนพื้นผิวของโลก.

## ทำไมต้องใช้ Aspose.GIS สำหรับโครงการ .NET ที่เกี่ยวกับข้อมูลเชิงพื้นที่?
- **Full‑featured API** – รองรับรูปแบบข้อมูลเชิงพื้นที่หลายประเภท (Shapefile, GeoJSON, KML, เป็นต้น).  
- **High performance** – ปรับให้เหมาะกับชุดข้อมูลขนาดใหญ่.  
- **Cross‑platform** – ทำงานบน Windows, Linux, และ macOS ด้วย .NET Core/5/6+.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน, ตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **.NET Environment** – ติดตั้ง .NET SDK ล่าสุดจาก Microsoft.  
2. **Aspose.GIS for .NET Library** – ดาวน์โหลดและติดตั้งจาก [download page](https://releases.aspose.com/gis/net/). ทำตามคำแนะนำที่ให้มาเพื่อเพิ่มแพ็กเกจ NuGet ไปยังโปรเจกต์ของคุณ.  
3. **Development IDE** – Visual Studio, Rider, หรือเครื่องมือแก้ไขใด ๆ ที่รองรับการพัฒนา .NET.

## นำเข้า Namespaces
ในแอปพลิเคชัน .NET ของคุณ, ให้นำเข้า namespaces ที่จำเป็นเพื่อเข้าถึงฟังก์ชันที่ Aspose.GIS ให้มา.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## วิธีเพิ่มละติจูดและลองจิจูดไปยัง LineString
ด้านล่างเป็นคู่มือขั้นตอนต่อขั้นตอนที่แสดง **วิธีสร้าง geometry linestring** และ **เพิ่มจุดลงในเส้น** ด้วย Aspose.GIS.

### ขั้นตอนที่ 1: สร้างอ็อบเจ็กต์ LineString
```csharp
LineString line = new LineString();
```
ที่นี่, เราสร้างอ็อบเจ็กต์ `LineString` ใหม่ซึ่งเป็นตัวแทนของ **geometry เส้น**.

### ขั้นตอนที่ 2: เพิ่มจุดลงใน LineString
```csharp
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```
เรา **เพิ่มจุดลงในเส้น** โดยใช้เมธอด `AddPoint`. แต่ละครั้งที่เรียกจะให้คู่ latitude และ longitude, ทำให้ **เพิ่มละติจูดและลองจิจูด** ลงใน geometry.

## สร้าง geometry เส้น – สรุปสั้น ๆ
- **LineString** เป็นวิธีที่พบบ่อยที่สุดในการแสดงชุดของจุดที่เชื่อมต่อกัน.  
- เมธอด `AddPoint` ให้คุณ **เพิ่มละติจูดและลองจิจูด** ทีละคู่.  
- เมื่อเพิ่มจุดแล้ว, คุณสามารถส่งออก, วิเคราะห์, หรือแสดงผล geometry ด้วยฟีเจอร์อื่นของ Aspose.GIS.

## ปัญหาที่พบบ่อยและวิธีแก้ไข
| Issue | Solution |
|-------|----------|
| **ลำดับพิกัดไม่ถูกต้อง** | Aspose.GIS ต้องการ `longitude, latitude`. ตรวจสอบลำดับของค่าของคุณอีกครั้ง. |
| **อ้างอิงเป็น Null ขณะเพิ่มจุด** | ตรวจสอบให้แน่ใจว่าอ็อบเจ็กต์ `LineString` ถูกสร้างก่อนเรียก `AddPoint`. |
| **ระบบพิกัดที่ไม่รองรับ** | ใช้ `SpatialReference` เพื่อกำหนด CRS หากคุณต้องการระบบอื่นที่ไม่ใช่ WGS‑84. |

## คำถามที่พบบ่อย (เพิ่มเติม)

**Q: ฉันสามารถใช้ Aspose.GIS สำหรับโครงการเชิงพาณิชย์ได้หรือไม่?**  
A: ใช่, จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานในสภาพแวดล้อมการผลิต.

**Q: Aspose.GIS รองรับรูปแบบข้อมูลเชิงพื้นที่อื่น ๆ นอกจาก GeoJSON หรือไม่?**  
A: แน่นอน – รองรับ Shapefile, KML, GML, CSV, และอื่น ๆ อีกมาก.

**Q: ไลบรารีมีการอัปเดตบ่อยแค่ไหน?**  
A: การอัปเดตจะออกเป็นประจำเพื่อเพิ่มฟีเจอร์, ปรับปรุงประสิทธิภาพ, และแก้ไขบั๊ก.

**Q: มีฟอรั่มชุมชนสำหรับขอความช่วยเหลือหรือไม่?**  
A: มี, คุณสามารถเยี่ยมชมฟอรั่ม Aspose.GIS เพื่อรับการสนับสนุนจากชุมชนและเชื่อมต่อกับผู้ใช้คนอื่น: [Aspose.GIS Forum](https://forum.aspose.com/c/gis/33).

## สรุป
Aspose.GIS for .NET ทำให้การ **เพิ่มละติจูดและลองจิจูด**, **สร้าง geometry เส้น**, และ **จัดการข้อมูลเชิงพื้นที่** ในแอปพลิเคชันของคุณเป็นเรื่องง่าย. ด้วยการทำตามขั้นตอนข้างต้น, คุณสามารถสร้างโซลูชันเชิงพื้นที่ที่แข็งแรงได้อย่างรวดเร็ว. สำรวจเอกสารเพิ่มเติมเพื่อค้นพบการวิเคราะห์ขั้นสูง, การแปลง, และความสามารถในการเรนเดอร์.

---

**อัปเดตล่าสุด:** 2025-12-18  
**ทดสอบด้วย:** Aspose.GIS for .NET 24.10  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}