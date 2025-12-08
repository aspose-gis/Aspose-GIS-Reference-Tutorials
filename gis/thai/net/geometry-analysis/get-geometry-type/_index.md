---
date: 2025-12-08
description: เรียนรู้วิธี **รับประเภทเรขาคณิต** จากจุดโดยใช้ Aspose.GIS สำหรับ .NET
  คู่มือขั้นตอนนี้ครอบคลุมข้อกำหนดเบื้องต้นของ GIS การสร้างวัตถุจุด และการทำงานกับข้อมูลเชิงพื้นที่ใน
  C#
language: th
linktitle: Get Geometry Type
second_title: Aspose.GIS .NET API
title: รับประเภทเรขาคณิตด้วย Aspose.GIS สำหรับ .NET
url: /net/geometry-analysis/get-geometry-type/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# รับประเภทเรขาคณิตด้วย Aspose.GIS สำหรับ .NET

## บทนำ
หากคุณต้องการ **รับประเภทเรขาคณิต** ของฟีเจอร์เชิงพื้นที่ในแอปพลิเคชัน .NET, Aspose.GIS ทำให้เป็นเรื่องง่าย ในบทเรียนนี้เราจะเดินผ่านกระบวนการทั้งหมด—ตั้งแต่การตั้งค่า environment GIS ของคุณจนถึงการสร้างอ็อบเจ็กต์จุดและการดึงประเภทเรขาคณิตของมัน เมื่อเสร็จคุณจะเข้าใจวิธี **ทำงานกับข้อมูลเชิงพื้นที่** อย่างมีประสิทธิภาพและพร้อมขยายตัวอย่างไปยังเส้น, โพลิกอน, และอื่น ๆ

## คำตอบอย่างรวดเร็ว
- **“รับประเภทเรขาคณิต” หมายถึงอะไร?** มันคืนค่า enum (เช่น Point, LineString) ที่ระบุรูปทรงของอ็อบเจ็กต์เรขาคณิต  
- **ไลบรารีใดที่ให้ความสามารถนี้?** Aspose.GIS for .NET.  
- **ฉันต้องมีลิขสิทธิ์เพื่อรันตัวอย่างหรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการพัฒนา; จำเป็นต้องมีลิขสิทธิ์สำหรับการใช้งานในผลิตภัณฑ์  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET 5, .NET 6, .NET Core 3.1 และต่อไป  
- **การตั้งค่าสามารถใช้เวลาเท่าไหร่?** โดยปกติใช้เวลาน้อยกว่า 10 นาทีสำหรับตัวอย่างจุดพื้นฐาน  

## “รับประเภทเรขาคณิต” ใน Aspose.GIS คืออะไร?
`GeometryType` คือการนับจำนวน (enumeration) ที่อธิบายประเภทของเรขาคณิตที่คุณกำลังทำงานด้วย—Point, LineString, Polygon ฯลฯ การเข้าถึงคุณสมบัตินี้ทำให้คุณสามารถตัดสินใจในโค้ดของคุณตามรูปทรงของข้อมูลที่กำลังประมวลผล

## ทำไมต้องใช้ Aspose.GIS สำหรับ .NET?
- **เครื่องยนต์ GIS ที่ครบคุณสมบัติ** – ไม่ต้องพึ่งพาไลบรารีเนทีฟภายนอก  
- **API ที่ครอบคลุม** – สร้าง, แก้ไข, และวิเคราะห์ข้อมูลเชิงพื้นที่โดยตรงจาก C#  
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS  
- **เอกสารที่ยอดเยี่ยม** – อ้างอิงอย่างรวดเร็วและตัวอย่างสำหรับทุกคลาส  

## ข้อกำหนดเบื้องต้นของ GIS สำหรับ .NET (gis prerequisites .net)
ก่อนเริ่ม, ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:

1. **.NET SDK** – เวอร์ชันล่าสุด (ดาวน์โหลดจากเว็บไซต์ .NET อย่างเป็นทางการ)  
2. **IDE** – Visual Studio, Rider หรือ VS Code พร้อมส่วนขยาย C#  
3. **Aspose.GIS for .NET** – รับไลบรารีจาก [download link](https://releases.aspose.com/gis/net/) อย่างเป็นทางการ  
4. **API Documentation** – เก็บ [Aspose.GIS for .NET docs](https://reference.aspose.com/gis/net/) ไว้ใกล้มือสำหรับอ้างอิง  

## นำเข้า Namespaces
ในโครงการ .NET ใด ๆ ที่ใช้ Aspose.GIS, คุณต้องนำเข้า namespaces ที่จำเป็น ซึ่งจะทำให้คุณเข้าถึงคลาสเรขาคณิต, คอลเลกชัน, และเมธอดยูทิลิตี้  

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## วิธีรับประเภทเรขาคณิตจากจุด
ด้านล่างเป็น **ตัวอย่างจุด .net** ที่แสดงกระบวนการเต็มรูปแบบ—ตั้งแต่การสร้างจุดจนถึงการดึงประเภทเรขาคณิตของมัน  

### ขั้นตอนที่ 1: สร้างอ็อบเจ็กต์ Point
```csharp
Point point = new Point(40.7128, -74.006);
```
*เคล็ดลับ:* ตัวสร้าง `Point` คาดหวัง **ละติจูด** ก่อนและ **ลองจิจูด** หลัง, ตรงกับลำดับ GIS ที่เป็นมาตรฐาน  

### ขั้นตอนที่ 2: ดึง Geometry Type
```csharp
GeometryType geometryType = point.GeometryType;
```
ที่นี่เราเข้าถึงคุณสมบัติ `GeometryType` ซึ่งคืนค่า enum `GeometryType.Point`  

### ขั้นตอนที่ 3: แสดง Geometry Type
```csharp
Console.WriteLine(geometryType); // Point
```
ผลลัพธ์ในคอนโซลยืนยันว่าอ็อบเจ็กต์เป็น **point** จริง ๆ และคุณได้ **รับประเภทเรขาคณิต** จากมันสำเร็จ  

## ปัญหาและวิธีแก้ไขทั่วไป
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| **`GeometryType` returns `Unknown`** | เรขาคณิตไม่ได้รับการเริ่มต้นอย่างถูกต้อง. | ตรวจสอบให้แน่ใจว่าคุณใช้คอนสตรัคเตอร์ที่ถูกต้อง (`new Point(lat, lon)`). |
| **ข้อผิดพลาดการคอมไพล์** | ไม่มีการอ้างอิง Aspose.GIS. | เพิ่มแพคเกจ NuGet `Aspose.GIS` ไปยังโปรเจกต์ของคุณ. |
| **Runtime exception on Linux** | ไลบรารีเนทีฟไม่เข้ากัน. | ใช้เวอร์ชัน .NET Core ของ Aspose.GIS ซึ่งเป็นแบบข้ามแพลตฟอร์มอย่างเต็มที่. |

## คำถามที่พบบ่อย

**Q: Aspose.GIS รองรับทุกเวอร์ชันของ .NET หรือ?**  
A: ใช่, Aspose.GIS รองรับ .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 และเวอร์ชันต่อไป  

**Q: ฉันสามารถทดลองใช้ Aspose.GIS ก่อนซื้อได้หรือไม่?**  
A: แน่นอน. มีการทดลองใช้ฟรีที่ [download link](https://releases.aspose.com/).  

**Q: ฉันจะหาแหล่งสนับสนุนสำหรับคำถามที่เกี่ยวกับ Aspose.GIS ได้จากที่ไหน?**  
A: เยี่ยมชม [support forum](https://forum.aspose.com/c/gis/33) ของ Aspose.GIS เพื่อรับความช่วยเหลือจากชุมชนและการสนับสนุนอย่างเป็นทางการ  

**Q: ฉันจะขอรับลิขสิทธิ์ชั่วคราวสำหรับการพัฒนาได้อย่างไร?**  
A: ลิขสิทธิ์ชั่วคราวจะมีให้บนหน้า [temporary license](https://purchase.aspose.com/temporary-license/)  

**Q: ฉันสามารถซื้อไลเซนส์เต็มรูปแบบสำหรับการใช้งานในผลิตภัณฑ์ได้จากที่ไหน?**  
A: คุณสามารถซื้อไลเซนส์ได้โดยตรงจากหน้า Aspose.GIS purchase [here](https://purchase.aspose.com/buy).  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2025-12-08  
**ทดสอบด้วย:** Aspose.GIS for .NET (latest release)  
**ผู้เขียน:** Aspose