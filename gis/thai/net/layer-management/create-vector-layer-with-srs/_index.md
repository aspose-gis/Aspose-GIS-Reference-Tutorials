---
title: สร้างเลเยอร์เวกเตอร์ด้วย SRS
linktitle: สร้างเลเยอร์เวกเตอร์ด้วย SRS
second_title: Aspose.GIS .NET API
description: สำรวจ Aspose.GIS สำหรับ .NET - กุญแจสำคัญในการบูรณาการ GIS อย่างราบรื่น สร้างเลเยอร์เวกเตอร์ได้อย่างง่ายดายด้วยระบบอ้างอิงเชิงพื้นที่ที่ระบุ ดาวน์โหลดเดี๋ยวนี้!
type: docs
weight: 13
url: /th/net/layer-management/create-vector-layer-with-srs/
---
## การแนะนำ
Aspose.GIS สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถทำงานกับข้อมูลระบบสารสนเทศทางภูมิศาสตร์ (GIS) ได้อย่างราบรื่นในแอปพลิเคชัน .NET ในบทช่วยสอนนี้ เราจะเน้นที่การสร้างเลเยอร์เวกเตอร์ด้วยระบบอ้างอิงเชิงพื้นที่ (SRS) เมื่อสิ้นสุดคู่มือนี้ คุณจะสามารถรวมความสามารถ GIS เข้ากับโครงการ .NET ของคุณได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการพัฒนา C# และ .NET
-  ติดตั้ง Aspose.GIS สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/gis/net/).
- สภาพแวดล้อมการพัฒนาที่ตั้งค่าและพร้อม
## นำเข้าเนมสเปซ
ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าเนมสเปซที่จำเป็นที่จุดเริ่มต้นของไฟล์ C# ของคุณ:
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
## ขั้นตอนที่ 1: ตั้งค่าระบบอ้างอิงเชิงพื้นที่ที่คาดการณ์ไว้
เรามาสร้างระบบอ้างอิงเชิงพื้นที่ที่คาดการณ์ไว้ (SRS) โดยใช้การฉายภาพ World Mercator เป็นตัวอย่าง ทำตามขั้นตอนเหล่านี้:
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
## ขั้นตอนที่ 2: สร้างเลเยอร์เวกเตอร์และเพิ่มคุณสมบัติ
ตอนนี้ เรามาสร้างเชพไฟล์และเพิ่มฟีเจอร์ด้วย SRS ที่ระบุกันดีกว่า:
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
        layer.Add(feature); // สิ่งนี้จะทำให้เกิดข้อยกเว้นเนื่องจากเรขาคณิตมี SRS ที่แตกต่างกัน
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## ขั้นตอนที่ 3: ตรวจสอบระบบอ้างอิงเชิงพื้นที่
สุดท้ายนี้ เรามาเปิดเลเยอร์และตรวจสอบระบบอ้างอิงเชิงพื้นที่กันดีกว่า:
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / เวิลด์เมอร์เคเตอร์"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // ควรกลับมาจริง
}
```
เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถสร้างเลเยอร์เวกเตอร์พร้อมระบบอ้างอิงเชิงพื้นที่ที่ระบุโดยใช้ Aspose.GIS สำหรับ .NET ได้สำเร็จ
## บทสรุป
การรวมฟังก์ชัน GIS เข้ากับแอปพลิเคชัน .NET ของคุณง่ายกว่าที่เคย ด้วย Aspose.GIS ด้วยความสามารถในการสร้างเลเยอร์เวกเตอร์และจัดการระบบอ้างอิงเชิงพื้นที่ได้อย่างง่ายดาย คุณสามารถปรับปรุงโครงการของคุณด้วยความสามารถเชิงพื้นที่อันทรงพลัง
## คำถามที่พบบ่อย
### Aspose.GIS เข้ากันได้กับไฟล์ GIS ทุกรูปแบบหรือไม่
 Aspose.GIS รองรับรูปแบบ GIS หลากหลาย รวมถึง Shapefile, GeoJSON, KML และอื่นๆ ตรวจสอบ[เอกสารประกอบ](https://reference.aspose.com/gis/net/) สำหรับรายการทั้งหมด
### ฉันสามารถใช้ Aspose.GIS ในเว็บแอปพลิเคชันได้หรือไม่
อย่างแน่นอน! Aspose.GIS สำหรับ .NET มีความหลากหลายและสามารถใช้ได้บนเว็บแอปพลิเคชัน แอปพลิเคชันเดสก์ท็อป และแม้แต่แอปมือถือ
### ฉันจะรับการสนับสนุนสำหรับ Aspose.GIS ได้ที่ไหน
 คุณสามารถค้นหาชุมชนที่เป็นประโยชน์ได้ที่[ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33) สำหรับข้อสงสัยหรือปัญหาใด ๆ ที่คุณอาจพบ
### มีการทดลองใช้ฟรีหรือไม่?
 ใช่ คุณสามารถสำรวจคุณสมบัติของ Aspose.GIS ได้โดยการทดลองใช้ฟรี[ที่นี่](https://releases.aspose.com/).
### ฉันจะซื้อใบอนุญาตสำหรับ Aspose.GIS ได้อย่างไร
 หากต้องการซื้อใบอนุญาต โปรดไปที่[หน้าซื้อ](https://purchase.aspose.com/buy).