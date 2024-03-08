---
title: GeoJSON เป็นไฟล์การแปลง GDB ไม่ชัดเจน
linktitle: แปลงเลเยอร์ GeoJSON เป็นไฟล์ GDB
second_title: Aspose.GIS .NET API
description: ปลดล็อกความมหัศจรรย์เชิงพื้นที่ด้วย Aspose.GIS สำหรับ .NET! แปลงเลเยอร์ GeoJSON เป็น File Geodatabase ได้อย่างง่ายดาย ลองตอนนี้! #จัดทำ #GIS
type: docs
weight: 17
url: /th/net/layer-management/convert-geojson-layer-to-file-gdb/
---
## การแนะนำ
ในขอบเขตแบบไดนามิกของระบบสารสนเทศทางภูมิศาสตร์ (GIS) ความสามารถในการแปลงข้อมูลระหว่างรูปแบบต่างๆ ได้อย่างราบรื่นเป็นสิ่งสำคัญ Aspose.GIS สำหรับ .NET กลายเป็นพันธมิตรที่ทรงพลัง โดยนำเสนอชุดเครื่องมือที่ครอบคลุมสำหรับการจัดการข้อมูลเชิงพื้นที่ได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการแปลงเลเยอร์ GeoJSON เป็น File Geodatabase (File GDB) โดยใช้ Aspose.GIS สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มต้นการเดินทางเชิงพื้นที่นี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้การทำงานของการเขียนโปรแกรม .NET
-  ติดตั้ง Aspose.GIS สำหรับ .NET แล้ว ถ้าไม่เช่นนั้นให้ดาวน์โหลดจาก[ที่นี่](https://releases.aspose.com/gis/net/) และปฏิบัติตามคำแนะนำในการติดตั้ง
## นำเข้าเนมสเปซ
หากต้องการเริ่มต้นกระบวนการแปลง ให้เริ่มด้วยการนำเข้าเนมสเปซที่จำเป็น:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
ตอนนี้ เรามาแบ่งกระบวนการออกเป็นคำแนะนำทีละขั้นตอน:
## ขั้นตอนที่ 1: ตั้งค่าเลเยอร์ GeoJSON
เริ่มต้นด้วยการสร้างเลเยอร์ GeoJSON พร้อมแอตทริบิวต์และฟีเจอร์ที่เกี่ยวข้อง นี่เป็นตัวอย่างเพื่อแนะนำคุณ:
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // เพิ่มคุณสมบัติ
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //สร้างและเพิ่มคุณสมบัติ
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```
## ขั้นตอนที่ 2: คัดลอกชุดข้อมูลทดสอบ
เพื่อรักษาความสมบูรณ์ของข้อมูลทดสอบ ให้สร้างสำเนาของชุดข้อมูล ใช้ข้อมูลโค้ดต่อไปนี้:
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## ขั้นตอนที่ 3: แปลง GeoJSON เป็นไฟล์ GDB
ตอนนี้ก็ถึงเวลาที่จะทำการแปลง ใช้รหัสต่อไปนี้:
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // คัดลอกคุณลักษณะ
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // เพิ่มคุณสมบัติ
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจภูมิประเทศที่น่าสนใจของการแปลงเลเยอร์ GeoJSON เป็นฐานข้อมูลภูมิศาสตร์ไฟล์โดยใช้ Aspose.GIS สำหรับ .NET ด้วยความรู้นี้ ตอนนี้คุณก็พร้อมที่จะจัดการข้อมูลเชิงพื้นที่ในแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น
## คำถามที่พบบ่อย
### Aspose.GIS เข้ากันได้กับเฟรมเวิร์ก .NET ล่าสุดหรือไม่
ใช่ Aspose.GIS เข้ากันได้กับเวอร์ชันเฟรมเวิร์ก .NET ล่าสุด
### ฉันสามารถแปลงรูปแบบภูมิสารสนเทศอื่นๆ โดยใช้ Aspose.GIS ได้หรือไม่
อย่างแน่นอน! Aspose.GIS รองรับรูปแบบภูมิสารสนเทศที่หลากหลายสำหรับการจัดการข้อมูลที่หลากหลาย
### มี Aspose.GIS รุ่นทดลองใช้งานหรือไม่
 ใช่ คุณสามารถสำรวจฟังก์ชันการทำงานของ Aspose.GIS ได้โดยดาวน์โหลดเวอร์ชันทดลองใช้งาน[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับการสืบค้นที่เกี่ยวข้องกับ Aspose.GIS ได้อย่างไร
 ตรงไปที่ Aspose.GIS[ฟอรั่ม](https://forum.aspose.com/c/gis/33) สำหรับการสนับสนุนโดยเฉพาะ
### ฉันสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS ได้หรือไม่
 ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).