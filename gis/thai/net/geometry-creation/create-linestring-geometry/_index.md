---
date: 2026-03-29
description: เรียนรู้วิธีสร้างเรขาคณิต LineString ใน .NET ด้วย Aspose.GIS คู่มือนี้ครอบคลุมการเพิ่มจุดลงใน
  LineString และการจัดการข้อมูลเชิงพื้นที่ใน .NET อย่างมีประสิทธิภาพ
linktitle: Create LineString Geometry
second_title: Aspose.GIS .NET API
title: วิธีสร้างเรขาคณิต LineString ด้วย Aspose.GIS สำหรับ .NET
url: /th/net/geometry-creation/create-linestring-geometry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างเรขาคณิต LineString ด้วย Aspose.GIS สำหรับ .NET

## บทนำ
หากคุณกำลังมองหา **how to create linestring** objects ในสภาพแวดล้อม .NET คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะอธิบายการสร้างเรขาคณิต `LineString` ด้วย Aspose.GIS, เพิ่มจุดเข้าไป, และอธิบายว่าทำไมวิธีนี้จึงเหมาะสำหรับการทำงานกับ **geospatial data .net** ในตอนท้ายคุณจะได้ตัวอย่างที่ชัดเจนและสามารถรันได้ซึ่งสามารถนำไปใช้ในโครงการแผนที่หรือการวิเคราะห์เชิงพื้นที่ใด ๆ

## คำตอบสั้น
- **ต้องการไลบรารีอะไร?** Aspose.GIS for .NET  
- **ต้องใช้บรรทัดโค้ดกี่บรรทัด?** Only three concise statements to create and populate a LineString  
- **ต้องการไลเซนส์สำหรับการทดสอบหรือไม่?** A free trial works for development; a commercial license is required for production  
- **รุ่น .NET ที่รองรับ?** .NET Framework, .NET Core, .NET 5+ and .NET 6+  
- **สามารถเพิ่มจุดเพิ่มเติมในภายหลังได้หรือไม่?** Yes – call `AddPoint` as many times as required  

## LineString คืออะไร?
`LineString` เป็นรูปทรงเรขาคณิตแบบง่ายที่ประกอบด้วยชุดจุดที่เรียงลำดับกันโดยเชื่อมต่อด้วยเส้นตรง มักใช้แทนถนน, แม่น้ำ, หรือคุณลักษณะเชิงเส้นใด ๆ บนแผนที่

## ทำไมต้องใช้ Aspose.GIS สำหรับ .NET?
Aspose.GIS มี API ที่จัดการเต็มรูปแบบและมีประสิทธิภาพสูง ซึ่งทำให้ซับซ้อนของการจัดการข้อมูลเชิงพื้นที่ถูกซ่อนอยู่ มันรองรับรูปแบบไฟล์หลากหลาย (Shapefile, GeoJSON, KML, ฯลฯ) และให้คุณจัดการเรขาคณิตได้โดยไม่ต้องทำงานกับไลบรารี GIS ระดับต่ำ

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน ให้ตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:

1. **.NET Environment** – ติดตั้ง .NET SDK ล่าสุดจาก Microsoft.  
2. **Aspose.GIS for .NET Library** – ดาวน์โหลดไบนารีจาก [download page](https://releases.aspose.com/gis/net/) แล้วเพิ่มอ้างอิงไปยังโปรเจกต์ของคุณ.  
3. **Development IDE** – Visual Studio, Rider, หรือเครื่องมือแก้ไขใด ๆ ที่รองรับการพัฒนา .NET.

## นำเข้า Namespaces
ในแอปพลิเคชัน .NET ของคุณ ให้นำเข้า namespaces ที่จำเป็นเพื่อเข้าถึงฟังก์ชันที่ Aspose.GIS ให้มา

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## วิธีสร้างเรขาคณิต LineString
ด้านล่างเป็นโค้ดขั้นตอนต่อขั้นตอนที่คุณต้องการ **how to create linestring** และ **add points linestring**.

### ขั้นตอนที่ 1: สร้างอ็อบเจ็กต์ LineString
```csharp
LineString line = new LineString();
```
ที่นี่เราจะสร้างอ็อบเจ็กต์ `LineString` ใหม่ซึ่งจะเก็บชุดจุดที่กำหนดเส้น

### ขั้นตอนที่ 2: เพิ่มจุดเข้าไปใน LineString
```csharp
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```
เราเพิ่มจุดตัวอย่างสองจุดโดยใช้เมธอด `AddPoint` แต่ละจุดจะกำหนดด้วยพิกัด X (longitude) และ Y (latitude) คุณสามารถเรียก `AddPoint` ซ้ำได้เพื่อขยายเส้นตามต้องการ

## ปัญหาทั่วไปและวิธีแก้
- **Points appear in the wrong order** – Ensure you add them in the sequence you want them connected.  
- **Coordinate system mismatch** – Aspose.GIS works in the coordinate system you provide; convert coordinates to the same CRS if mixing sources.  
- **NullReferenceException** – Verify that the `LineString` instance is created before calling `AddPoint`.

## คำถามที่พบบ่อย
### Q: Aspose.GIS สำหรับ .NET รองรับทุกเฟรมเวิร์กของ .NET หรือไม่?
A: Yes, Aspose.GIS for .NET is compatible with .NET Framework, .NET Core, and .NET 5+.

### Q: สามารถใช้ Aspose.GIS ในโครงการเชิงพาณิชย์ได้หรือไม่?
A: Yes, you can use Aspose.GIS for both personal and commercial projects. Check out the licensing options on the Aspose website.

### Q: Aspose.GIS รองรับรูปแบบข้อมูลเชิงพื้นที่อื่น ๆ นอกจาก GeoJSON หรือไม่?
A: Yes, Aspose.GIS supports a wide range of spatial data formats, including Shapefile, KML, GML, and many more.

### Q: Aspose.GIS มีการอัปเดตบ่อยแค่ไหน?
A: Aspose.GIS releases updates regularly to improve performance, add new features, and fix any reported issues.

### Q: มีฟอรั่มชุมชนที่สามารถขอความช่วยเหลือเกี่ยวกับ Aspose.GIS ได้หรือไม่?
A: Yes, you can visit the Aspose.GIS forum for community support and to connect with other users: [Aspose.GIS Forum](https://forum.aspose.com/c/gis/33).

**Additional Q&A**

**Q: สามารถส่งออก LineString เป็น GeoJSON ได้หรือไม่?**  
A: Absolutely. Use `line.Save("output.geojson", ExportFormat.GeoJson);` after adding all points.

**Q: วิธีคำนวณความยาวของ LineString คืออะไร?**  
A: Call `double length = line.Length;` – the API returns the length in the units of your coordinate system.

## สรุป
การสร้างและจัดการ `LineString` ใน .NET ทำได้อย่างง่ายดายด้วย Aspose.GIS โดยทำตามขั้นตอนข้างต้นคุณสามารถ **add points linestring** อย่างรวดเร็วและผสานเรขาคณิตนี้เข้าสู่เวิร์กโฟลว์ GIS ขนาดใหญ่ได้ สำรวจเอกสาร Aspose.GIS เพิ่มเติมเพื่อค้นหาการดำเนินการขั้นสูงเช่นการสืบค้นเชิงพื้นที่, การแปลงเรขาคณิต, และการแปลงรูปแบบไฟล์

---

**อัปเดตล่าสุด:** 2026-03-29  
**ทดสอบกับ:** Aspose.GIS for .NET 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}