---
date: 2026-01-15
description: สำรวจ Aspose.GIS สำหรับ .NET เพื่อสร้างเลเยอร์เวกเตอร์พร้อมระบบอ้างอิงเชิงพื้นที่
  เรียนรู้วิธีตั้งค่า SRS สร้างเลเยอร์ และจัดการข้อมูล GIS ดาวน์โหลดเลย!
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: สร้างเลเยอร์เวกเตอร์ด้วย SRS
url: /th/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง Vector Layer ด้วย SRS

## บทนำ
Aspose.GIS for .NET เป็นไลบรารีที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถ **สร้าง vector layer** และทำงานกับข้อมูลระบบสารสนเทศภูมิศาสตร์ (GIS) ได้อย่างราบรื่นในแอปพลิเคชัน .NET ในบทเรียนนี้ เราจะอธิบายขั้นตอนการสร้าง vector layer ด้วยระบบอ้างอิงเชิงพื้นที่ (SRS) เหตุผลที่คุณควรตั้งค่า spatial reference และประโยชน์ที่ได้จากการนำไปใช้ในโครงการจริง เมื่ออ่านจบคุณจะสามารถบูรณาการความสามารถ GIS เข้าไปในโซลูชัน .NET ของคุณได้อย่างมั่นใจ

## คำตอบสั้น
- **วัตถุประสงค์หลักของบทเรียนนี้คืออะไร?** เพื่อแสดงวิธีการสร้าง vector layer ด้วย SRS ที่ระบุโดยใช้ Aspose.GIS for .NET.  
- **การฉายภาพใดที่ใช้ในตัวอย่าง?** World Mercator (EPSG:3395).  
- **ฉันต้องมีลิขสิทธิ์เพื่อรันโค้ดหรือไม่?** การทดลองใช้ฟรีสามารถใช้สำหรับการพัฒนาได้; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **ฉันสามารถใช้วิธีเดียวกันกับรูปแบบ GIS อื่นได้หรือไม่?** ใช่ การจัดการ SRS เดียวกันใช้ได้กับ Shapefile, GeoJSON, KML ฯลฯ.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Vector layer คืออะไรและทำไมต้องตั้งค่า spatial reference?
A **vector layer** เก็บข้อมูลคุณลักษณะเชิงเรขาคณิต (จุด, เส้น, พื้นที่) พร้อมกับข้อมูลแอตทริบิวต์ การกำหนด **spatial reference** (SRS) บอกซอฟต์แวร์ GIS ว่าจะตีความพิกัดเหล่านั้นบนพื้นผิวโลกอย่างไร การตั้งค่า SRS ที่ถูกต้องทำให้ได้การวัดที่แม่นยำ การซ้อนทับกับเลเยอร์อื่นอย่างเหมาะสม และการแสดงแผนที่ที่เชื่อถือได้

## ข้อกำหนดเบื้องต้น
- ความรู้พื้นฐานเกี่ยวกับ C# และการพัฒนา .NET  
- ไลบรารี Aspose.GIS for .NET ติดตั้งแล้ว คุณสามารถดาวน์โหลดได้ **[ที่นี่](https://releases.aspose.com/gis/net/)**.  
- สภาพแวดล้อมการพัฒนา (Visual Studio, VS Code หรือ IDE ของ C# ใดก็ได้)

## นำเข้า Namespaces
Ensure you have the necessary namespaces imported at the top of your C# file:

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
Let's create a **projected spatial reference system** using the World Mercator projection as an example. This demonstrates **how to set srs** for a layer.

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
Now we’ll **create a vector layer** (a Shapefile) and add features that use the SRS we just defined. This part answers **how to create layer** with Aspose.GIS.

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

> **เคล็ดลับ:** ตรวจสอบให้แน่ใจว่า `SpatialReferenceSystem` ของ geometry ตรงกับ SRS ของเลเยอร์ก่อนทำการเพิ่ม หากค่า SRS ไม่ตรงจะทำให้เกิด `GisException` ตามที่แสดงด้านบน.

## ตรวจสอบ Spatial Reference System – ขั้นตอน 3
Finally, open the layer and confirm that the SRS was correctly applied.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

If the `IsEquivalent` call returns `true`, you’ve successfully **create vector layer** with the desired spatial reference.

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| `GisException` เมื่อเพิ่มฟีเจอร์ | Geometry ใช้ SRS ที่แตกต่างจากเลเยอร์ | ตั้งค่า `feature.Geometry.SpatialReferenceSystem` ให้ตรงกับ SRS ของเลเยอร์ก่อนทำการเพิ่ม |
| เลเยอร์แสดงว่าเป็นค่าว่างในซอฟต์แวร์ GIS | Shapefile ถูกสร้างโดยไม่มีไฟล์ `.prj` ที่เหมาะสม | ตรวจสอบให้แน่ใจว่าออบเจกต์ `projectedSrs` ถูกส่งเมื่อสร้างเลเยอร์ |
| ค่าพิกัดที่ไม่คาดคิด | พารามิเตอร์การฉายภาพผิด (เช่น เมอร์ดิอันศูนย์) | ตรวจสอบพารามิเตอร์ที่ส่งให้ `AddProjectionParameter` อีกครั้ง |

## คำถามที่พบบ่อย
### Aspose.GIS รองรับรูปแบบไฟล์ GIS ทั้งหมดหรือไม่?
Aspose.GIS supports various GIS formats, including Shapefile, GeoJSON, KML, and more. Check the **[documentation](https://reference.aspose.com/gis/net/)** for the complete list.

### ฉันสามารถใช้ Aspose.GIS ในเว็บแอปพลิเคชันได้หรือไม่?
Absolutely! Aspose.GIS for .NET is versatile and can be used in web applications, desktop applications, and even mobile apps.

### ฉันจะหาการสนับสนุนสำหรับ Aspose.GIS ได้จากที่ไหน?
You can find a helpful community at the **[Aspose.GIS forum](https://forum.aspose.com/c/gis/33)** for any queries or issues you may encounter.

### มีการทดลองใช้ฟรีหรือไม่?
Yes, you can explore the features of Aspose.GIS by obtaining a free trial **[here](https://releases.aspose.com/)**.

### ฉันจะซื้อไลเซนส์สำหรับ Aspose.GIS ได้อย่างไร?
To purchase a license, visit the **[purchase page](https://purchase.aspose.com/buy)**.

## คำถามที่พบบ่อย (เพิ่มเติม)

**Q: จะเกิดอะไรขึ้นหากฉันพยายามเพิ่ม geometry ที่มี SRS แตกต่าง?**  
A: Aspose.GIS จะโยน `GisException`. คุณต้องทำการรีโปรเจกต์ geometry หรือให้แน่ใจว่าใช้ SRS เดียวกับเลเยอร์

**Q: ฉันสามารถเปลี่ยน SRS ของเลเยอร์ที่มีอยู่ได้หรือไม่?**  
A: Yes, you can create a new layer with the desired SRS and copy features over, reprojecting them as needed.

**Q: สามารถทำงานกับพิกัด 3 มิติได้หรือไม่?**  
A: Aspose.GIS supports Z‑coordinates; just use geometry constructors that accept a Z value.

**Q: ไลบรารีจัดการการแปลง datum อัตโนมัติหรือไม่?**  
A: When you reproject geometries using `Geometry.Transform`, Aspose.GIS performs the necessary datum shift.

**Q: .NET เวอร์ชันใดที่ทดสอบอย่างเป็นทางการ?**  
A: The library is tested with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.

## สรุป
You’ve now learned how to **create vector layer** with a custom spatial reference system using Aspose.GIS for .NET. By setting the correct SRS, handling geometry consistently, and verifying the layer’s metadata, you can build robust GIS-enabled applications that interoperate with any standard GIS software.

---

**Last Updated:** 2026-01-15  
**ทดสอบกับ:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}