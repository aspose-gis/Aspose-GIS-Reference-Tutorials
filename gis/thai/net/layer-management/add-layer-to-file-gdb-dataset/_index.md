---
title: GIS Mastery - เพิ่มเลเยอร์ให้กับ GDB ด้วย Aspose.GIS สำหรับ .NET
linktitle: เพิ่มเลเยอร์ลงในไฟล์ชุดข้อมูล GDB
second_title: Aspose.GIS .NET API
description: ปลดล็อกพลังของ GIS ด้วย Aspose.GIS สำหรับ .NET! เรียนรู้วิธีเพิ่มเลเยอร์ให้กับชุดข้อมูล File GDB ในบทช่วยสอนทีละขั้นตอนนี้ #ข้อมูลทางภูมิศาสตร์ #Aspose #GIS
type: docs
weight: 16
url: /th/net/layer-management/add-layer-to-file-gdb-dataset/
---
## การแนะนำ
คุณพร้อมที่จะปรับปรุงความสามารถ GIS ของคุณโดยใช้ Aspose.GIS สำหรับ .NET แล้วหรือยัง? ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเพิ่มเลเยอร์ให้กับชุดข้อมูล File Geodatabase (GDB) Aspose.GIS สำหรับ .NET นำเสนอฟีเจอร์ที่มีประสิทธิภาพในการจัดการข้อมูลทางภูมิศาสตร์ และด้วยบทช่วยสอนนี้ คุณจะสามารถรวมเลเยอร์เพิ่มเติมเข้ากับชุดข้อมูลของคุณได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.GIS สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก[Aspose.GIS สำหรับเอกสาร .NET](https://reference.aspose.com/gis/net/).
- ไดเร็กทอรีเอกสาร: สร้างไดเร็กทอรีเอกสารเฉพาะบนเครื่องของคุณเพื่อจัดเก็บและจัดการไฟล์ที่เกี่ยวข้องกับ GIS
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.GIS ใช้ข้อมูลโค้ดต่อไปนี้:
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
## ขั้นตอนที่ 1: คัดลอกไดเรกทอรี
ก่อนดำเนินการต่อ ให้ทำซ้ำไดเรกทอรีที่มีชุดข้อมูล GDB ของคุณ ขั้นตอนนี้ช่วยให้แน่ใจว่าชุดข้อมูลดั้งเดิมยังคงไม่เสียหาย ใช้ข้อมูลโค้ดที่ให้มา:
```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```
## ขั้นตอนที่ 2: เปิดชุดข้อมูลและตรวจสอบความสามารถในการสร้าง
 เปิดชุดข้อมูลที่ซ้ำกันและตรวจสอบว่าสามารถสร้างเลเยอร์ได้หรือไม่ นี่คือการยืนยันโดยการมีอยู่ของ`True` ในเอาต์พุตคอนโซล
```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // จริง
```
## ขั้นตอนที่ 3: สร้างและเติมเลเยอร์ใหม่
สร้างเลเยอร์ใหม่ภายในชุดข้อมูล โดยกำหนดระบบอ้างอิงเชิงพื้นที่ คุณลักษณะ และคุณลักษณะตัวอย่าง ข้อมูลโค้ดนี้สาธิตกระบวนการ:
```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```
## ขั้นตอนที่ 4: เปิดและตรวจสอบเลเยอร์ที่เพิ่ม
เปิดเลเยอร์ที่คุณเพิ่งสร้างขึ้นและตรวจสอบความถูกต้องของเนื้อหา ตรวจสอบการนับและดึงค่าแอตทริบิวต์โดยใช้รหัสต่อไปนี้:
```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "ชื่อ_1"
}
```
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีเพิ่มเลเยอร์ให้กับชุดข้อมูล File GDB โดยใช้ Aspose.GIS สำหรับ .NET เรียบร้อยแล้ว ด้วยทักษะที่เพิ่งค้นพบเหล่านี้ คุณสามารถจัดการข้อมูลทางภูมิศาสตร์ในโครงการ GIS ของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.GIS สำหรับ .NET กับไลบรารี GIS อื่นๆ ได้หรือไม่
Aspose.GIS สำหรับ .NET ได้รับการออกแบบมาให้ทำงานแยกจากกัน แต่สามารถรวมเข้ากับไลบรารีอื่นๆ เพื่อเพิ่มฟังก์ชันการทำงานได้
### ถาม: มีใบอนุญาตชั่วคราวสำหรับการทดสอบหรือไม่
 ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อการทดสอบและประเมินผล
### ถาม: Aspose.GIS สำหรับ .NET รองรับระบบอ้างอิงเชิงพื้นที่ใดบ้าง
Aspose.GIS สำหรับ .NET รองรับระบบอ้างอิงเชิงพื้นที่ที่หลากหลาย ซึ่งให้ความยืดหยุ่นในการจัดการข้อมูลทางภูมิศาสตร์
### ถาม: ฉันสามารถสนับสนุนชุมชน Aspose.GIS ได้หรือไม่
 อย่างแน่นอน! เข้าร่วมการสนทนาและแบ่งปันประสบการณ์ของคุณเกี่ยวกับ[ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33).
### ถาม: ฉันจะหาเอกสารโดยละเอียดสำหรับ Aspose.GIS สำหรับ .NET ได้ที่ไหน
 สำรวจเอกสารที่ครอบคลุม[ที่นี่](https://reference.aspose.com/gis/net/) สำหรับข้อมูลเชิงลึกเกี่ยวกับ Aspose.GIS สำหรับ .NET