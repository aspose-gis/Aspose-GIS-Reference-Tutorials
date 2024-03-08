---
title: กำหนดตารางที่แม่นยำสำหรับเลเยอร์ GDB ของไฟล์ใน Aspose.GIS
linktitle: กำหนดตารางความแม่นยำสำหรับไฟล์ GDB Layer
second_title: Aspose.GIS .NET API
description: เรียนรู้วิธีกำหนดตารางที่แม่นยำสำหรับเลเยอร์ File GDB โดยใช้ Aspose.GIS สำหรับ .NET ปฏิบัติตามบทช่วยสอนทีละขั้นตอนของเรา
type: docs
weight: 21
url: /th/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีกำหนดตารางที่แม่นยำสำหรับเลเยอร์ File Geodatabase (GDB) โดยใช้ Aspose.GIS สำหรับ .NET Aspose.GIS เป็นไลบรารี .NET ที่ทรงพลังซึ่งมีฟังก์ชันเชิงพื้นที่ที่ครอบคลุมเพื่อทำงานกับไฟล์ GIS รูปแบบต่างๆ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งข้อกำหนดเบื้องต้นต่อไปนี้:
1. Visual Studio: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio บนระบบของคุณ
2.  Aspose.GIS สำหรับไลบรารี .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.GIS สำหรับ .NET จากไฟล์[เว็บไซต์](https://releases.aspose.com/gis/net/).
3. ความรู้พื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์ในการทำความเข้าใจตัวอย่างโค้ด
## นำเข้าเนมสเปซ
ขั้นแรก เรามานำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.GIS:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```
ตอนนี้ เรามาดูรายละเอียดแต่ละขั้นตอนในการกำหนดตารางที่แม่นยำสำหรับเลเยอร์ File GDB
## ขั้นตอนที่ 1: สร้างชุดข้อมูล
```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```
 ที่นี่ เราสร้างชุดข้อมูลใหม่ในรูปแบบ File Geodatabase โดยระบุเส้นทางและใช้`Dataset.Create` วิธี.
## ขั้นตอนที่ 2: กำหนดตัวเลือกกริดที่แม่นยำ
```csharp
var options = new FileGdbOptions
{
    CoordinatePrecisionGrid = new FileGdbCoordinatePrecisionGrid
    {
        XOrigin = -400,
        YOrigin = -400,
        XYScale = 1e10,
        MOrigin = 0,
        MScale = 1e4,
    },
    EnsureValidCoordinatesRange = true,
};
```
ในขั้นตอนนี้ เราจะกำหนดตัวเลือกตารางที่แม่นยำสำหรับเลเยอร์ File GDB เราระบุต้นกำเนิด X และ Y, สเกล XY, ต้นกำเนิด M, สเกล M และตรวจสอบให้แน่ใจว่ามีการบังคับใช้ช่วงพิกัดที่ถูกต้อง
## ขั้นตอนที่ 3: สร้างเลเยอร์
```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```
ที่นี่ เราสร้างเลเยอร์ใหม่ภายในชุดข้อมูลด้วยชื่อและตัวเลือกที่ระบุ เราใช้ระบบอ้างอิงเชิงพื้นที่ WGS84
## ขั้นตอนที่ 4: เพิ่มคุณสมบัติให้กับเลเยอร์
```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```
ในขั้นตอนนี้ เราจะสร้างคุณลักษณะที่มีรูปทรงเรขาคณิตแบบจุดและเพิ่มลงในเลเยอร์ โปรดทราบว่าการเพิ่มคุณลักษณะที่มีพิกัดนอกตารางความแม่นยำที่กำหนดไว้จะทำให้เกิดข้อยกเว้น
## ขั้นตอนที่ 5: จัดการกับข้อยกเว้น
```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // ค่า X -410 อยู่นอกช่วงที่ถูกต้อง
}
```
ที่นี่ เราจัดการกับข้อยกเว้นที่อาจเกิดขึ้นเมื่อมีการเพิ่มคุณลักษณะให้กับเลเยอร์ที่อยู่นอกช่วงพิกัดที่ถูกต้อง
## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีกำหนดตารางที่แม่นยำสำหรับเลเยอร์ File GDB โดยใช้ Aspose.GIS สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณสามารถทำงานกับข้อมูลเชิงพื้นที่ในแอปพลิเคชัน .NET ของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.GIS สำหรับ .NET กับไฟล์ GIS รูปแบบอื่นได้หรือไม่
ใช่ Aspose.GIS สำหรับ .NET รองรับไฟล์ GIS หลากหลายรูปแบบ รวมถึง Shapefile, GeoJSON, KML และอื่นๆ
### Aspose.GIS สำหรับ .NET เข้ากันได้กับ .NET Core หรือไม่
ใช่ Aspose.GIS สำหรับ .NET เข้ากันได้กับทั้ง .NET Framework และ .NET Core
### ฉันสามารถดำเนินการเชิงพื้นที่โดยใช้ Aspose.GIS สำหรับ .NET ได้หรือไม่
ใช่ คุณสามารถดำเนินการเชิงพื้นที่ เช่น การบัฟเฟอร์ การแยก และการคำนวณระยะทาง โดยใช้ Aspose.GIS สำหรับ .NET
### Aspose.GIS สำหรับ .NET ให้การสนับสนุนการแปลงพิกัดหรือไม่
ใช่ Aspose.GIS สำหรับ .NET ให้การสนับสนุนการแปลงพิกัดระหว่างระบบอ้างอิงเชิงพื้นที่ต่างๆ
### มีรุ่นทดลองใช้สำหรับ Aspose.GIS สำหรับ .NET หรือไม่
ใช่ คุณสามารถดาวน์โหลด Aspose.GIS สำหรับ .NET เวอร์ชันทดลองใช้ฟรีได้จาก[เว็บไซต์](https://releases.aspose.com/gis/net/).