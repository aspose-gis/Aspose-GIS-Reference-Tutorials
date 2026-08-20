---
date: 2026-06-30
description: เรียนรู้วิธีสร้าง vector layer พร้อม spatial reference system ด้วย Aspose.GIS
  สำหรับ .NET คู่มือแบบขั้นตอน คำอธิบายแบบไม่ต้องเขียนโค้ด และคำถามที่พบบ่อย
keywords:
- how to create vector layer
- Aspose.GIS spatial reference
- .NET GIS tutorial
linktitle: วิธีสร้าง Vector Layer พร้อม SRS ด้วย Aspose.GIS สำหรับ .NET
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer with a spatial reference system using
    Aspose.GIS for .NET. Step‑by‑step guide, code‑free explanations, and FAQs.
  headline: How to Create Vector Layer with SRS using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS throws a `GisException`. You must either reproject the geometry
      or ensure it shares the layer’s SRS.
    question: What happens if I try to add a geometry with a different SRS?
  - answer: Yes, you can create a new layer with the desired SRS and copy features
      over, reprojecting them as needed.
    question: Can I change the SRS of an existing layer?
  - answer: Aspose.GIS supports Z‑coordinates; just use geometry constructors that
      accept a Z value.
    question: Is it possible to work with 3D coordinates?
  - answer: When you reproject geometries using `Geometry.Transform`, Aspose.GIS performs
      the necessary datum shift.
    question: Does the library handle datum transformations automatically?
  - answer: The library is tested with .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7.
    question: Which .NET versions are officially tested?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: วิธีสร้าง Vector Layer พร้อม SRS ด้วย Aspose.GIS สำหรับ .NET
url: /th/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้าง Vector Layer พร้อม SRS ด้วย Aspose.GIS สำหรับ .NET

## คำนำ
ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีสร้างวัตถุ vector layer** ที่รวมระบบอ้างอิงเชิงพื้นที่ (SRS) ด้วย Aspose.GIS สำหรับ .NET เราจะอธิบายเหตุผลในการกำหนด SRS แสดงขั้นตอนที่ต้องทำอย่างละเอียด และอธิบายประโยชน์ในโลกจริง เช่น การวัดที่แม่นยำและการซ้อนทับข้อมูล GIS อย่างราบรื่น เมื่ออ่านจบคุณจะพร้อมฝังฟังก์ชัน GIS ที่แข็งแกร่งเข้าไปในแอปพลิเคชัน .NET ใด ๆ

## คำตอบสั้น
- **วัตถุประสงค์หลักของบทแนะนำนี้คืออะไร?** เพื่อสาธิตวิธีสร้าง vector layer พร้อมกำหนด SRS ที่ระบุด้วย Aspose.GIS สำหรับ .NET  
- **การฉายภาพที่ใช้ในตัวอย่างคืออะไร?** World Mercator (EPSG:3395)  
- **ต้องมีลิขสิทธิ์เพื่อรันโค้ดหรือไม่?** สามารถใช้รุ่นทดลองฟรีสำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **สามารถใช้วิธีเดียวกันกับฟอร์แมต GIS อื่นได้หรือไม่?** ใช่, การจัดการ SRS นี้ใช้ได้กับ Shapefile, GeoJSON, KML ฯลฯ  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7

## Vector layer คืออะไรและทำไมต้องกำหนด spatial reference?
**vector layer** จะเก็บคุณลักษณะเชิงเรขาคณิต (จุด, เส้น, พื้นที่) พร้อมข้อมูลแอตทริบิวต์ การกำหนด **ระบบอ้างอิงเชิงพื้นที่** จะบอกซอฟต์แวร์ GIS ว่าจะแมปพิกัดเหล่านั้นบนพื้นผิวโลกอย่างไร เพื่อให้การคำนวณระยะทางแม่นยำ การจัดตำแหน่งเลเยอร์ถูกต้อง และการแสดงแผนที่เชื่อถือได้

## ทำไมต้องกำหนดระบบอ้างอิงเชิงพื้นที่?
การใช้ SRS ที่กำหนดไว้ช่วยลดข้อผิดพลาดการแปลงพิกัดได้ถึง 95 % เมื่อซ้อนเลเยอร์จากแหล่งต่าง ๆ Aspose.GIS รองรับ **กว่า 20** ฟอร์แมตการนำเข้าและส่งออก รวมถึง Shapefile, GeoJSON, KML, และ GML — พร้อมประมวลผลชุดข้อมูลหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมี:

- ความรู้พื้นฐานเกี่ยวกับ C# และการพัฒนา .NET  
- ไลบรารี Aspose.GIS สำหรับ .NET ติดตั้งแล้ว คุณสามารถดาวน์โหลดได้ **[ที่นี่](https://releases.aspose.com/gis/net/)**  
- สภาพแวดล้อมการพัฒนา (Visual Studio, VS Code หรือ IDE C# ใด ๆ)

## นำเข้า Namespaces
ตรวจสอบให้แน่ใจว่าคุณได้นำเข้า namespaces ที่จำเป็นที่ส่วนหัวของไฟล์ C# ของคุณแล้ว:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## วิธีตั้งค่า spatial reference (SRS) – ขั้นตอน 1
โหลด SRS ที่ฉายภาพไว้ในสองบรรทัด: สร้างอินสแตนซ์ `ProjectedSpatialReferenceSystem`, ตั้งค่าพารามิเตอร์การฉาย Mercator, แล้วคุณพร้อมที่จะผูกกับเลเยอร์

`ProjectedSpatialReferenceSystem` เป็นคลาสที่อธิบายระบบอ้างอิงเชิงพิกัดที่ฉายภาพไว้  
`ProjectedSpatialReferenceSystemParameters` เก็บพารามิเตอร์ที่จำเป็นสำหรับกำหนดค่า SRS ที่ฉายภาพ เช่น เมอริดียนศูนย์และสเกลแฟคเตอร์

มาสร้าง **ระบบอ้างอิงเชิงพื้นที่ที่ฉายภาพ** โดยใช้การฉาย World Mercator เป็นตัวอย่าง ซึ่งจะแสดง **วิธีตั้งค่า srs** สำหรับเลเยอร์

```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```

## วิธีสร้างเลเยอร์ – ขั้นตอน 2
สร้างอินสแตนซ์ของเลเยอร์ Shapefile, ส่ง `projectedSrs` ที่กำหนดไว้ก่อนหน้า, แล้วเพิ่มเรขาคณิตที่ `SpatialReferenceSystem` ตรงกับ SRS ของเลเยอร์

`Layer` (เช่น Shapefile) แทนคอลเลกชันของฟีเจอร์ที่เก็บในไฟล์ GIS เดียว  
ต่อไปเราจะ **สร้าง vector layer** (Shapefile) และเพิ่มฟีเจอร์ที่ใช้ SRS ที่เรากำหนดไว้ ส่วนนี้ตอบ **วิธีสร้างเลเยอร์** ด้วย Aspose.GIS

```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

## ตรวจสอบระบบอ้างอิงเชิงพื้นที่ – ขั้นตอน 3
เปิดเลเยอร์ที่สร้างใหม่, ดึง `SpatialReferenceSystem` ของมัน, แล้วเปรียบเทียบกับ `projectedSrs` ดั้งเดิมโดยใช้ `IsEquivalent` ผลลัพธ์ `true` ยืนยันว่า SRS ถูกนำไปใช้อย่างถูกต้อง

`IsEquivalent` ตรวจสอบว่าระบบอ้างอิงเชิงพื้นที่สองระบบแสดงถึงระบบพิกัดเดียวกันหรือไม่  
สุดท้ายเปิดเลเยอร์และยืนยันว่า SRS ถูกนำไปใช้อย่างถูกต้อง

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

หากการเรียก `IsEquivalent` คืนค่า `true` คุณได้ **สร้าง vector layer** พร้อม spatial reference ที่ต้องการสำเร็จแล้ว

## ปัญหาทั่วไป & วิธีแก้
`GisException` คือประเภทข้อยกเว้นที่ Aspose.GIS โยนเมื่อเกิดข้อผิดพลาดเช่น SRS ไม่ตรงกัน  

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|---------|
| `GisException` ขณะเพิ่มฟีเจอร์ | เรขาคณิตใช้ SRS แตกต่างจากเลเยอร์ | ตั้งค่า `feature.Geometry.SpatialReferenceSystem` ให้ตรงกับ SRS ของเลเยอร์ก่อนเพิ่ม |
| เลเยอร์แสดงว่างในซอฟต์แวร์ GIS | ไฟล์ shapefile สร้างโดยไม่มีไฟล์ `.prj` ที่เหมาะสม | ตรวจสอบให้แน่ใจว่าได้ส่งออบเจ็กต์ `projectedSrs` เมื่อสร้างเลเยอร์ |
| ค่าพิกัดไม่คาดคิด | พารามิเตอร์การฉายผิด (เช่น เมอริดียนศูนย์) | ตรวจสอบพารามิเตอร์ที่ส่งให้ `AddProjectionParameter` อีกครั้ง |

## คำถามที่พบบ่อย
### Aspose.GIS รองรับฟอร์แมต GIS ทุกประเภทหรือไม่?
Aspose.GIS รองรับ **กว่า 20** ฟอร์แมต GIS รวมถึง Shapefile, GeoJSON, KML, GML และอื่น ๆ ตรวจสอบ **[เอกสารอ้างอิง](https://reference.aspose.com/gis/net/)** เพื่อดูรายการเต็ม

### สามารถใช้ Aspose.GIS ในเว็บแอปพลิเคชันได้หรือไม่?
ได้แน่นอน! Aspose.GIS สำหรับ .NET ทำงานใน ASP.NET, ASP.NET Core, และสภาพแวดล้อม .NET ฝั่งเซิร์ฟเวอร์ใด ๆ

### จะหาการสนับสนุนสำหรับ Aspose.GIS ได้จากที่ไหน?
คุณสามารถเข้าชุมชนที่เป็นประโยชน์ได้ที่ **[ฟอรั่ม Aspose.GIS](https://forum.aspose.com/c/gis/33)** สำหรับคำถามหรือปัญหาต่าง ๆ

### มีรุ่นทดลองฟรีหรือไม่?
มี, คุณสามารถสำรวจคุณสมบัติของ Aspose.GIS ได้โดยรับรุ่นทดลอง **[ที่นี่](https://releases.aspose.com/)**

### จะซื้อไลเซนส์สำหรับ Aspose.GIS ได้อย่างไร?
เพื่อซื้อไลเซนส์, เยี่ยมชม **[หน้าซื้อสินค้า](https://purchase.aspose.com/buy)**

## คำถามที่พบบ่อย (เพิ่มเติม)

**ถาม: จะเกิดอะไรขึ้นหากฉันพยายามเพิ่มเรขาคณิตที่มี SRS แตกต่าง?**  
ตอบ: Aspose.GIS จะโยน `GisException` คุณต้องทำการรีโปรเจกต์เรขาคณิตหรือให้มันใช้ SRS ของเลเยอร์เดียวกัน

**ถาม: สามารถเปลี่ยน SRS ของเลเยอร์ที่มีอยู่แล้วได้หรือไม่?**  
ตอบ: ได้, คุณสามารถสร้างเลเยอร์ใหม่ด้วย SRS ที่ต้องการและคัดลอกฟีเจอร์ไปยังเลเยอร์ใหม่พร้อมทำการรีโปรเจกต์ตามต้องการ

**ถาม: สามารถทำงานกับพิกัด 3 มิติได้หรือไม่?**  
ตอบ: Aspose.GIS รองรับพิกัด Z; เพียงใช้คอนสตรัคเตอร์ของเรขาคณิตที่รับค่า Z

**ถาม: ไลบรารีจัดการการแปลง datum โดยอัตโนมัติหรือไม่?**  
ตอบ: เมื่อคุณรีโปรเจกต์เรขาคณิตด้วย `Geometry.Transform` Aspose.GIS จะทำการชิฟท์ datum ที่จำเป็นโดยอัตโนมัติ

**ถาม: .NET เวอร์ชันใดที่ผ่านการทดสอบอย่างเป็นทางการ?**  
ตอบ: ไลบรารีผ่านการทดสอบกับ .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6/7

## สรุป
คุณได้เรียนรู้ **วิธีสร้าง vector layer** พร้อมระบบอ้างอิงเชิงพื้นที่ที่กำหนดเองด้วย Aspose.GIS สำหรับ .NET การตั้งค่า SRS ที่ถูกต้อง, การจัดการเรขาคณิตอย่างสอดคล้อง, และการตรวจสอบเมตาดาต้าเลเยอร์ จะช่วยให้คุณสร้างแอปพลิเคชัน GIS ที่แข็งแกร่งและทำงานร่วมกับซอฟต์แวร์ GIS มาตรฐานใด ๆ

---

**อัปเดตล่าสุด:** 2026-06-30  
**ทดสอบด้วย:** Aspose.GIS 24.11 สำหรับ .NET (ล่าสุด ณ เวลาที่เขียน)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [Create Vector Layer and Set Layer Spatial Reference System](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [How to Modify Layer – Aspose.GIS .NET Layer Interaction](/gis/net/layer-interaction-and-data-access/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}