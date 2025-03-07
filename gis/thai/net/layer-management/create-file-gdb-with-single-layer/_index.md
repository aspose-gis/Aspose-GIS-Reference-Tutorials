---
title: สร้างไฟล์ GDB ด้วย Single Layer
linktitle: สร้างไฟล์ GDB ด้วย Single Layer
second_title: Aspose.GIS .NET API
description: ปลดล็อกศักยภาพของการจัดการข้อมูลเชิงพื้นที่ใน .NET ด้วย Aspose.GIS เรียนรู้วิธีสร้างฐานข้อมูลทางภูมิศาสตร์ของไฟล์และเลเยอร์ทีละขั้นตอน ดาวน์โหลดเดี๋ยวนี้!
weight: 11
url: /th/net/layer-management/create-file-gdb-with-single-layer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างไฟล์ GDB ด้วย Single Layer

## การแนะนำ
คุณพร้อมที่จะยกระดับแอปพลิเคชันเชิงพื้นที่ของคุณด้วยฐานข้อมูลทางภูมิศาสตร์และเลเยอร์ไฟล์ที่แข็งแกร่งแล้วหรือยัง? ไม่ต้องมองหาที่ไหนไกลนอกจาก Aspose.GIS สำหรับ .NET ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการสร้าง File Geodatabase (GDB) ด้วยเลเยอร์เดียวโดยใช้ Aspose.GIS สำหรับ .NET ควบคุมพลังของการจัดการข้อมูลเชิงพื้นที่และการแสดงภาพในแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Aspose.GIS สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.GIS แล้ว คุณสามารถดาวน์โหลดได้จาก[หน้าดาวน์โหลด Aspose.GIS สำหรับ .NET](https://releases.aspose.com/gis/net/).
2. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ที่ใช้งานได้บนเครื่องของคุณ
3. ไดเร็กทอรีเอกสาร: เลือกหรือสร้างไดเร็กทอรีบนระบบของคุณที่คุณจะจัดเก็บไฟล์ข้อมูลเชิงพื้นที่
## นำเข้าเนมสเปซ
ในการเริ่มต้น คุณต้องนำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ .NET ของคุณ เนมสเปซเหล่านี้จะให้การเข้าถึงฟังก์ชัน Aspose.GIS เพิ่มบรรทัดต่อไปนี้ที่จุดเริ่มต้นของไฟล์โค้ดของคุณ:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ
```csharp
string dataDir = "Your Document Directory";
```
แทนที่ "Your Document Directory" ด้วยเส้นทางไปยังไดเร็กทอรีที่คุณต้องการจัดเก็บไฟล์ข้อมูลเชิงพื้นที่
## ขั้นตอนที่ 2: สร้างฐานข้อมูลภูมิศาสตร์ไฟล์ด้วยเลเยอร์เดียว
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
ข้อมูลโค้ดนี้สร้างฐานข้อมูลทางภูมิศาสตร์ของไฟล์ด้วยเลเยอร์เดียวและเพิ่มคุณลักษณะบรรทัดลงไป
## ขั้นตอนที่ 3: เปิดฐานข้อมูลภูมิศาสตร์ของไฟล์และดึงข้อมูลเลเยอร์
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // เอาท์พุต: จำนวนคุณสมบัติ: 1
}
```
ในขั้นตอนนี้ เราจะเปิด File Geodatabase ที่สร้างขึ้น ดึงเลเยอร์ชื่อ "เลเยอร์" และพิมพ์จำนวนคุณลักษณะในเลเยอร์
## บทสรุป
ยินดีด้วย! คุณสร้าง File Geodatabase ด้วยเลเยอร์เดียวได้สำเร็จโดยใช้ Aspose.GIS สำหรับ .NET สำรวจความสามารถมากมายของการจัดการข้อมูลเชิงพื้นที่ในแอปพลิเคชันของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.GIS สำหรับ .NET ในโปรเจ็กต์ .NET ที่มีอยู่ได้หรือไม่
ใช่ Aspose.GIS สำหรับ .NET สามารถรวมเข้ากับโปรเจ็กต์ .NET ที่มีอยู่ของคุณได้อย่างราบรื่น
### มีรุ่นทดลองใช้สำหรับ Aspose.GIS สำหรับ .NET หรือไม่
 ใช่ คุณสามารถสำรวจคุณลักษณะต่างๆ ของ Aspose.GIS สำหรับ .NET ได้โดยการดาวน์โหลด[รุ่นทดลองใช้ฟรี](https://releases.aspose.com/).
### ฉันจะหาเอกสารโดยละเอียดสำหรับ Aspose.GIS สำหรับ .NET ได้ที่ไหน
 อ้างถึง[เอกสารประกอบ](https://reference.aspose.com/gis/net/) สำหรับข้อมูลที่ครอบคลุมเกี่ยวกับ Aspose.GIS สำหรับ .NET
### ฉันจะรับการสนับสนุน Aspose.GIS สำหรับ .NET ได้อย่างไร
 เยี่ยมชม[ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33) สำหรับการสนับสนุนและช่วยเหลือชุมชน
### มีใบอนุญาตชั่วคราวสำหรับ Aspose.GIS สำหรับ .NET หรือไม่
 ใช่ คุณสามารถได้รับ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) สำหรับ Aspose.GIS สำหรับ .NET
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
