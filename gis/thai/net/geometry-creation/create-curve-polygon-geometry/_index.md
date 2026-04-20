---
date: 2026-02-15
description: เรียนรู้วิธีสร้างเลเยอร์เวกเตอร์และรูปทรงโพลิกอนโค้งโดยใช้ Aspose.GIS
  สำหรับ .NET รวมถึงรูปทรงเส้นวงกลมสำหรับวงแหวนภายใน
linktitle: Create Curve Polygon Geometry
second_title: Aspose.GIS .NET API
title: สร้างเลเยอร์เวกเตอร์และโพลิกอนโค้งด้วย Aspose.GIS
url: /th/net/geometry-creation/create-curve-polygon-geometry/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเลเยอร์เวกเตอร์และโพลิกอนโค้งด้วย Aspose.GIS

## บทนำ
ในโลกของการพัฒนา Geographic Information Systems (GIS) **Aspose.GIS for .NET** โดดเด่นในฐานะไลบรารีที่ทรงพลังสำหรับการสร้าง, แก้ไข, และจัดการข้อมูลเชิงพื้นที่ ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **create vector layer** และ **create curve polygon** geometry อย่างเป็นขั้นตอน เพื่อให้คุณสามารถฝังรูปทรงที่ซับซ้อนได้โดยตรงในแอปพลิเคชัน GIS ของคุณ เมื่อจบคู่มือคุณจะมี Shapefile ที่พร้อมใช้งานซึ่งบรรจุ curve polygon ที่มีทั้งวงแหวนภายนอกและภายใน

## คำตอบด่วน
- **ใช้ไลบรารีอะไร?** Aspose.GIS for .NET  
- **งานหลักคืออะไร?** สร้าง curve polygon geometry, บันทึกเป็น Shapefile, และ **create vector layer** สำหรับข้อมูล  
- **ระยะเวลาในการทำงานโดยทั่วไป?** 5–10 นาทีสำหรับรูปทรงพื้นฐาน  
- **ข้อกำหนดเบื้องต้น?** .NET development environment and Aspose.GIS NuGet package  
- **ฉันสามารถดูผลลัพธ์ได้หรือไม่?** ใช่ – any GIS viewer that supports Shapefile (e.g., QGIS, ArcGIS)

## Curve Polygon คืออะไร?
*curve polygon* คือพอลิกอนที่ขอบของมันสามารถประกอบด้วยส่วนโค้ง (เช่นส่วนโค้งวงกลม) แทนที่จะเป็นเส้นตรงเท่านั้น สิ่งนี้ทำให้การจำลองลักษณะธรรมชาติ เช่น ทะเลสาบ, เกาะ, หรือรูปทรงใด ๆ ที่ได้ประโยชน์จากขอบที่เรียบเนียน มีความสมจริงมากขึ้น

## ทำไมต้องสร้าง geometry ของ curve polygon ด้วย Aspose.GIS?
- **ความแม่นยำ** – ขอบโค้งถูกจัดเก็บเป็นคณิตศาสตร์ ทำให้คงสภาพ geometry อย่างแม่นยำ  
- **การทำงานร่วมกัน** – Shapefile ที่สร้างขึ้นทำงานได้กับแพลตฟอร์ม GIS หลักทั้งหมด  
- **ประสิทธิภาพการทำงาน** – ต้องใช้โค้ดเพียงเล็กน้อยในการกำหนดรูปทรงซับซ้อน ช่วยเร่งกระบวนการพัฒนา  
- **ความยืดหยุ่น** – คุณสามารถ **create vector layer** วัตถุได้ทันทีและแนบ geometry ใดก็ได้ที่คุณต้องการ  

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. **Aspose.GIS for .NET** installed. Download it from the [Aspose.GIS for .NET releases page](https://releases.aspose.com/gis/net/).  
2. ความรู้พื้นฐานเกี่ยวกับ C# และระบบ .NET  
3. IDE เช่น Visual Studio (เวอร์ชันล่าสุดใดก็ได้) หรือ Visual Studio Code  

## นำเข้า Namespaces
ในขั้นตอนนี้ เราจะนำเข้า namespaces ที่จำเป็นเพื่อใช้ฟังก์ชันของ Aspose.GIS ในโค้ดของเรา.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: กำหนดเส้นทางไฟล์
แรกสุด ให้ระบุว่าตำแหน่งที่ Shapefile ของ Curve Polygon ที่สร้างขึ้นจะถูกบันทึกไว้ที่ไหน

```csharp
string path = "Your Document Directory" + "CreateCurvePolygon_out.shp";
```

แทนที่ `"Your Document Directory"` ด้วยเส้นทางโฟลเดอร์จริงบนเครื่องของคุณ

### ขั้นตอนที่ 2: สร้าง Vector Layer
สร้างอินสแตนซ์ของ vector layer ใหม่โดยใช้ Shapefile driver นี่คือขั้นตอน **create vector layer** ที่เตรียมคอนเทนเนอร์สำหรับ geometry ของเรา

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Your code for creating the Curve Polygon Geometry will go here
}
```

คำสั่ง `using` รับประกันว่าทรัพยากรจะถูกปล่อยอย่างถูกต้อง

### ขั้นตอนที่ 3: สร้าง Feature
สร้างอ็อบเจ็กต์ Feature ที่จะเก็บ geometry และข้อมูลแอตทริบิวต์ใด ๆ

```csharp
var feature = layer.ConstructFeature();
```

### ขั้นตอนที่ 4: สร้าง Curve Polygon Geometry
ตอนนี้เราจะสร้างอ็อบเจ็กต์ `CurvePolygon` ว่าง

```csharp
var curvePolygon = new CurvePolygon();
```

### ขั้นตอนที่ 5: กำหนด Exterior Ring
เพิ่ม circular string ที่เป็นขอบนอกของพอลิกอน

```csharp
var exterior = new CircularString();
exterior.AddPoint(-2, 0);
exterior.AddPoint(0, 2);
exterior.AddPoint(2, 0);
exterior.AddPoint(0, -2);
exterior.AddPoint(-2, 0);
curvePolygon.ExteriorRing = exterior;
```

พิกัดด้านบนสร้างรูปทรงคล้ายโค้งวงแหวน

### ขั้นตอนที่ 6: กำหนด Interior Ring (ไม่บังคับ)
หากคุณต้องการรูในพอลิกอน ให้กำหนดเป็น circular string อีกอันหนึ่ง นี่เป็นการสาธิตวิธีเพิ่ม **interior ring polygon** ด้วย **circular string geometry**

```csharp
var interior = new CircularString();
interior.AddPoint(-1, 0);
interior.AddPoint(0, 1);
interior.AddPoint(1, 0);
interior.AddPoint(0, -1);
interior.AddPoint(-1, 0);
curvePolygon.AddInteriorRing(interior);
```

### ขั้นตอนที่ 7: กำหนด Geometry ให้กับ Feature
เชื่อมต่อ curve polygon กับ feature ที่คุณสร้างไว้ก่อนหน้า

```csharp
feature.Geometry = curvePolygon;
```

### ขั้นตอนที่ 8: เพิ่ม Feature ไปยัง Layer
สุดท้าย เพิ่ม feature ไปยัง vector layer เพื่อให้เป็นส่วนหนึ่งของชุดข้อมูล

```csharp
layer.Add(feature);
```

เมื่อบล็อก `using` สิ้นสุด Shapefile จะถูกเขียนลงดิสก์

## ปัญหาที่พบบ่อยและวิธีแก้ไข
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| **ไฟล์ไม่ถูกสร้าง** | เส้นทางไม่ถูกต้องหรือไม่มีสิทธิ์การเขียน | ตรวจสอบว่าไดเรกทอรีมีอยู่และแอปพลิเคชันมีสิทธิ์การเขียน |
| **ขอบโค้งแสดงเป็นเส้นตรงในบางโปรแกรมดู** | โปรแกรมดูไม่รองรับ circular strings | ใช้แอปพลิเคชัน GIS ที่รองรับสเปค Shapefile อย่างเต็มที่ (เช่น QGIS 3.28+) |
| **ข้อยกเว้น `ArgumentException` ที่ `AddPoint`** | จุดอยู่เกินช่วงพิกัดที่ถูกต้องสำหรับ CRS ที่เลือก | ตรวจสอบให้แน่ใจว่าพิกัดอยู่ในระบบอ้างอิงพิกัด (CRS) ที่คุณตั้งใจใช้ |

## คำถามที่พบบ่อย

**Q: Aspose.GIS for .NET เข้ากันได้กับไลบรารี GIS อื่นหรือไม่?**  
A: ใช่, Aspose.GIS for .NET รองรับการทำงานร่วมกับรูปแบบ GIS ที่นิยมหลายรูปแบบ ทำให้คุณสามารถแลกเปลี่ยนข้อมูลกับไลบรารีเช่น GDAL/OGR หรือ Proj.NET.

**Q: ฉันสามารถแสดงผล Curve Polygon Geometry ที่สร้างขึ้นในซอฟต์แวร์ GIS ได้หรือไม่?**  
A: แน่นอน! Shapefile ที่สร้างขึ้นสามารถเปิดได้ใน QGIS, ArcGIS หรือเครื่องมือ GIS ใด ๆ ที่อ่านรูปแบบ Shapefile

**Q: Aspose.GIS for .NET มีความสามารถในการวิเคราะห์เชิงพื้นที่หรือไม่?**  
A: มี, มันรวมฟังก์ชันสำหรับการสอบถามเชิงพื้นที่, การบัฟเฟอร์, การตัดกัน, และอื่น ๆ ทำให้สามารถทำการวิเคราะห์ขั้นสูงโดยตรงใน .NET

**Q: ฉันสามารถขอความช่วยเหลือหรือแลกเปลี่ยนแนวคิดกับผู้ใช้คนอื่นได้ที่ไหน?**  
A: เข้าร่วมฟอรั่มชุมชน Aspose.GIS [ที่นี่](https://forum.aspose.com/c/gis/33) เพื่อเชื่อมต่อกับนักพัฒนาคนอื่น

**Q: มีการทดลองใช้ฟรีก่อนการซื้อหรือไม่?**  
A: แน่นอน! คุณสามารถดาวน์โหลดการทดลองใช้ฟรีจาก [หน้า releases](https://releases.aspose.com/) และประเมินคุณสมบัติทั้งหมด

## สรุป
คุณได้เรียนรู้วิธี **create vector layer** และ **create curve polygon** geometry ด้วย Aspose.GIS for .NET, บันทึกเป็น Shapefile, และสำรวจปัญหาที่พบบ่อยและคำถามที่พบบ่อยแล้ว อย่าลังเลที่จะทดลองชุดพิกัดต่าง ๆ, เพิ่มข้อมูลแอตทริบิวต์, หรือรวมเลเยอร์นี้เข้าไปในกระบวนการทำงาน GIS ที่ใหญ่ขึ้น

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.GIS for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}