---
date: 2026-06-05
description: เรียนรู้วิธีเปรียบเทียบ geometries ใน .NET ด้วย Aspose.GIS, ตรวจจับ geometries
  ที่ซ้ำกัน, และตรวจสอบความเท่าเทียมของ geometry ในแอปพลิเคชันของคุณ
keywords:
- how to compare geometries
- detect duplicate geometries
- Aspose.GIS geometry equality
linktitle: วิธีเปรียบเทียบ Geometries เพื่อความเท่าเทียม
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to compare geometries in .NET using Aspose.GIS, detect duplicate
    geometries, and check geometry equality in your applications.
  headline: How to Compare Geometries for Equality using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard
      projects.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. Download a trial from the [Aspose.GIS releases page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Detailed docs are on the [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).
    question: Where can I find the full API documentation?
  - answer: Post your question on the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How do I get help if I run into an issue?
  - answer: Yes, temporary licenses are available on the [purchase page](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: วิธีเปรียบเทียบ Geometries เพื่อความเท่าเทียมโดยใช้ Aspose.GIS สำหรับ .NET
url: /th/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเปรียบเทียบรูปทรงเรขาคณิตเพื่อความเท่ากันโดยใช้ Aspose.GIS สำหรับ .NET

## บทนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีเปรียบเทียบรูปทรงเรขาคณิต** ด้วย Aspose.GIS สำหรับ .NET ซึ่งเป็นงานที่สำคัญเมื่อคุณต้องการตรวจจับรูปทรงที่ซ้ำกัน, ตรวจสอบความถูกต้องของข้อมูลเชิงพื้นที่, หรือบังคับใช้กฎทอพอโลยี ไม่ว่าคุณจะกำลังสร้างบริการแผนที่, รันการวิเคราะห์เชิงพื้นที่แบบชุด, หรือเพียงแค่ตรวจสอบว่ารูปทรงสองรูปครอบคลุมตำแหน่งเดียวกัน, คู่มือนี้จะพาคุณผ่านการสร้าง, แก้ไข, และทดสอบความเท่ากันของรูปทรงด้วยโค้ด C# ที่สะอาดและพร้อมสำหรับการผลิต

## คำตอบสั้น
- **“compare geometries” หมายถึงอะไร?** It checks whether two geometric objects occupy the same space, regardless of how they are constructed.  
- **ใช้เมธอดใด?** `SpatiallyEquals` from the Aspose.GIS API.  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** A free trial works for testing; a commercial license is required for production.  
- **เวอร์ชัน .NET ที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **ระยะเวลาการทำงานโดยประมาณ?** About 5‑10 minutes for a basic equality check.

## ความเท่ากันของรูปทรงเรขาคณิตคืออะไร?
ความเท่ากันของรูปทรงเรขาคณิต หรือที่เรียกว่า spatial equality หมายถึงรูปทรงสองรูปแสดงชุดจุดเดียวกันบนพื้นผิวของโลกอย่างแม่นยำ แม้ว่าหนึ่งรูปจะสร้างเป็น `MultiLineString` และอีกหนึ่งเป็น `LineString` เดียว, พวกมันจะถือว่าเท่ากันเมื่อทุกพิกัดตรงกันภายในค่าความคลาดเคลื่อนที่กำหนด คำจำกัดความนี้ทำให้นักพัฒนาสามารถตรวจจับรูปทรงที่ซ้ำกันจากแหล่งข้อมูลที่หลากหลายได้อย่างเชื่อถือ

## ทำไมต้องใช้ Aspose.GIS เพื่อเปรียบเทียบรูปทรงเรขาคณิต?
Aspose.GIS มีเอนจิ้นรูปทรงที่มีประสิทธิภาพสูงและทำงานแบบออฟไลน์ซึ่งลบความจำเป็นในการใช้บริการภายนอกออกไป มัน **รองรับรูปแบบเวกเตอร์และเรสเตอร์กว่า 30 แบบ** (รวมถึง WKT, GeoJSON, Shapefile, KML, GML) และสามารถประมวลผลไฟล์ที่มี **จำนวนจุดหลายแสนจุด** พร้อมควบคุมการใช้หน่วยความจำให้อยู่ต่ำกว่า 50 MB เมธอด `SpatiallyEquals` ของไลบรารีนี้รับรู้ความแม่นยำ ทำให้ได้ผลลัพธ์ที่แน่นอนแม้กับพิกัดแบบ floating‑point

### ทำไมเรื่องนี้ถึงสำคัญสำหรับนักพัฒนา
เมื่อคุณต้องการ **ตรวจจับรูปทรงที่ซ้ำกัน** ในกระบวนการแบบชุด, สายการตรวจสอบแบบเรียลไทม์, หรือการย้ายข้อมูล GIS, ไลบรารีที่พิสูจน์แล้วจะลบการคาดเดาและรับประกันผลลัพธ์ที่สอดคล้องกันระหว่างผู้ให้ข้อมูลที่ต่างกัน

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่ม, ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- **.NET Framework หรือ .NET Core ที่ติดตั้ง** – เวอร์ชันใดก็ได้ที่รองรับโดย Aspose.GIS.  
- **ไลบรารี Aspose.GIS สำหรับ .NET** – ดาวน์โหลดจาก [Aspose.GIS download page](https://releases.aspose.com/gis/net/).  
- **IDE สำหรับการพัฒนา** – Visual Studio, Rider, หรือ VS Code พร้อมส่วนขยาย C#.

## นำเข้า Namespaces
ในโครงการ .NET ของคุณ, เพิ่มคำสั่ง `using` ที่จำเป็นเพื่อให้คอมไพเลอร์รู้ว่าจะหาคลาส GIS จากที่ไหน:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: กำหนดรูปทรงเรขาคณิต
`MultiLineString` แสดงถึงการรวบรวมส่วนของเส้น, ในขณะที่ `LineString` กำหนดเส้นต่อเนื่องเดียว ทั้งสองคลาสสืบทอดจากประเภทพื้นฐาน `Geometry`.

แรกสุด, เราจะสร้างรูปทรงสองรูปเพื่อเปรียบเทียบ ในตัวอย่างนี้ `geometry1` เป็น `MultiLineString` ที่ประกอบด้วยสองส่วนของเส้น, ส่วน `geometry2` เป็น `LineString` เดียวที่ครอบคลุมจุดเริ่มต้นและจุดสิ้นสุดเดียวกัน.

```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```

## ขั้นตอนที่ 2: ตรวจสอบความเท่ากันของรูปทรง
`SpatiallyEquals` ประเมินว่ารูปทรงสองรูปครอบคลุมชุดจุดเดียวกันหรือไม่, โดยสามารถรับค่าความคลาดเคลื่อนสำหรับความไม่แม่นยำของ floating‑point ได้ตามต้องการ.

ตอนนี้เราจะใช้เมธอด `SpatiallyEquals` เพื่อตรวจสอบว่ารูปทรงสองรูปถือว่าเท่ากันโดยเอนจิ้น GIS หรือไม่.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

คอนโซลจะแสดงค่า `True` เนื่องจากแม้โครงสร้างจะแตกต่างกัน, ทั้งสองรูปทรงยังคงครอบคลุมเส้นเดียวกันจาก (0,0) ถึง (2,2).

## ขั้นตอนที่ 3: แก้ไขรูปทรงหนึ่ง
เพื่อแสดงให้เห็นว่าการเปลี่ยนแปลงส่งผลต่อความเท่ากันอย่างไร, เราจะเพิ่มจุดเพิ่มเติมลงใน `geometry2`.

```csharp
geometry2.AddPoint(3, 3);
```

## ขั้นตอนที่ 4: ตรวจสอบความเท่ากันอีกครั้งหลังการแก้ไข
หลังจากการแก้ไข, รูปทรงไม่เหมือนเดิมอีกต่อไป, ดังนั้น `SpatiallyEquals` จะคืนค่า `False`.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

ผลลัพธ์ `False` ยืนยันว่าจุดเพิ่มเติมทำให้ความเท่ากันเชิงพื้นที่ถูกทำลาย.

## วิธีตรวจจับรูปทรงที่ซ้ำกัน?
โหลดรูปทรงแต่ละรูป, เรียก `SpatiallyEquals` พร้อมค่าความคลาดเคลื่อนที่เหมาะสม, แล้วกรองรูปทรงที่คืนค่า `True` รูปแบบนี้ทำงานได้ดีเมื่อใช้กับ LINQ, ช่วยให้คุณระบุรูปทรงที่ซ้ำกันในคอลเลกชันขนาดใหญ่ด้วยเพียงไม่กี่บรรทัดของโค้ด คุณยังสามารถรวมกับ `GroupBy` เพื่อรวมรูปทรงที่เหมือนกันและลดค่าใช้จ่ายในการจัดเก็บได้อีกด้วย.

## ปัญหาที่พบบ่อยและเคล็ดลับ
- **ปัญหาความแม่นยำ** – หากคุณทำงานกับพิกัดที่มีความแม่นยำสูงมาก, พิจารณาการปัดเศษหรือใช้ overload ของ `SpatiallyEquals` ที่รับค่าความคลาดเคลื่อน.  
- **SRID ที่แตกต่าง** – ตรวจสอบให้แน่ใจว่ารูปทรงทั้งสองมี Spatial Reference System Identifier (SRID) เดียวกันก่อนทำการเปรียบเทียบ.  
- **ประสิทธิภาพ** – สำหรับคอลเลกชันขนาดใหญ่, การเปรียบเทียบแบบชุดโดยใช้ LINQ หรือลูปขนานสามารถลดภาระงานได้อย่างมาก.

## คำถามที่พบบ่อย
**Q: ฉันสามารถใช้ Aspose.GIS สำหรับ .NET กับเฟรมเวิร์ก .NET อื่น ๆ ได้หรือไม่?**  
A: ใช่, Aspose.GIS ทำงานกับโครงการ .NET Framework, .NET Core, และ .NET Standard  

**Q: มีรุ่นทดลองฟรีหรือไม่?**  
A: มีแน่นอน. ดาวน์โหลดรุ่นทดลองจาก [Aspose.GIS releases page](https://releases.aspose.com/).  

**Q: ฉันจะหาเอกสาร API ฉบับเต็มได้จากที่ไหน?**  
A: เอกสารโดยละเอียดอยู่ที่ [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).  

**Q: ฉันจะขอความช่วยเหลือเมื่อเจอปัญหาได้อย่างไร?**  
A: โพสต์คำถามของคุณในฟอรั่มชุมชน Aspose.GIS [ที่นี่](https://forum.aspose.com/c/gis/33).  

**Q: ฉันสามารถซื้อไลเซนส์ชั่วคราวเพื่อการประเมินผลได้หรือไม่?**  
A: ได้, ไลเซนส์ชั่วคราวมีให้ซื้อที่ [purchase page](https://purchase.aspose.com/temporary-license/).  

## สรุป
คุณได้เรียนรู้ **วิธีเปรียบเทียบรูปทรงเรขาคณิต** ด้วย Aspose.GIS สำหรับ .NET ตั้งแต่การสร้างอ็อบเจ็กต์จนถึงการตรวจสอบความเท่ากันเชิงพื้นที่และการจัดการการแก้ไข ความสามารถนี้เป็นพื้นฐานสำหรับการวิเคราะห์เชิงพื้นที่ขั้นสูงเช่นการตรวจสอบทอพอโลยี, การตรวจจับซ้ำ, และการกรองตามรูปทรง.

---

**อัปเดตล่าสุด:** 2026-06-05  
**ทดสอบด้วย:** Aspose.GIS for .NET 24.11  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [สร้างรูปหลายเหลี่ยม Geometry C# และตรวจสอบการตัดกันด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [วิธีทำการวิเคราะห์การทับซ้อนเชิงพื้นที่ของรูปทรงด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-analysis/check-geometries-overlap/)
- [ตรวจสอบการเชื่อมต่อเครือข่าย: รูปทรงที่สัมผัสกันด้วย Aspose.GIS](/gis/net/geometry-analysis/check-geometries-touching/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}