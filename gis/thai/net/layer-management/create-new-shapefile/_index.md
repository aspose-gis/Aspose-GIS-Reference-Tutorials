---
title: สร้างเชปไฟล์ใหม่
linktitle: สร้างเชปไฟล์ใหม่
second_title: Aspose.GIS .NET API
description: เรียนรู้วิธีสร้างเชปไฟล์ใหม่โดยใช้ Aspose.GIS สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราและปลดล็อกพลังของการจัดการข้อมูลเชิงพื้นที่
type: docs
weight: 12
url: /th/net/layer-management/create-new-shapefile/
---
## การแนะนำ
หากคุณกำลังเจาะลึกการพัฒนาระบบสารสนเทศทางภูมิศาสตร์ (GIS) ด้วย .NET Aspose.GIS คือโซลูชันที่เหมาะกับคุณ ไลบรารีอันทรงพลังนี้ช่วยให้นักพัฒนาสามารถทำงานกับข้อมูลเชิงพื้นที่ได้อย่างราบรื่น และในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการสร้างเชปไฟล์ใหม่โดยใช้ Aspose.GIS สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Visual Studio บนเครื่องของคุณแล้ว
-  Aspose.GIS สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/gis/net/).
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชันการทำงานของ Aspose.GIS:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
เริ่มต้นด้วยการสร้างโครงการ C# ใหม่ใน Visual Studio และรวมไลบรารี Aspose.GIS
## ขั้นตอนที่ 2: กำหนดไดเร็กทอรีเอกสาร
```csharp
string dataDir = "Your Document Directory";
```
แทนที่ "Your Document Directory" ด้วยเส้นทางจริงที่คุณต้องการบันทึกรูปร่างไฟล์ใหม่
## ขั้นตอนที่ 3: สร้าง VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //เพิ่มคุณสมบัติก่อนที่จะเพิ่มคุณสมบัติ
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
ส่วนของโค้ดนี้จะตั้งค่าเลเยอร์เวกเตอร์และกำหนดคุณลักษณะสำหรับจุดสนใจของคุณ
## ขั้นตอนที่ 4: เพิ่มคุณสมบัติ
### กรณีที่ 1: ตั้งค่าเป็นรายบุคคล
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
### กรณีที่ 2: ตั้งค่าใหม่สำหรับแอตทริบิวต์ทั้งหมด
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## บทสรุป
 ยินดีด้วย! คุณสร้างเชปไฟล์ใหม่โดยใช้ Aspose.GIS สำหรับ .NET สำเร็จแล้ว บทช่วยสอนนี้ครอบคลุมพื้นฐานการตั้งค่าโปรเจ็กต์ การกำหนดแอตทริบิวต์ และการเพิ่มฟีเจอร์ ขณะที่คุณสำรวจเพิ่มเติม โปรดดูที่[เอกสารประกอบ](https://reference.aspose.com/gis/net/) สำหรับคุณสมบัติและฟังก์ชันขั้นสูง
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.GIS กับภาษาการเขียนโปรแกรมอื่นๆ ได้หรือไม่
Aspose.GIS รองรับ .NET เป็นหลัก แต่ก็มีเวอร์ชันสำหรับ Java ด้วยเช่นกัน
### ถาม: มีการทดลองใช้ฟรีหรือไม่?
 ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะรับการสนับสนุนสำหรับ Aspose.GIS ได้ที่ไหน
 เยี่ยมชม[ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33) สำหรับการสนับสนุนและการอภิปรายของชุมชน
### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวได้อย่างไร
 รับใบอนุญาตชั่วคราวของคุณ[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ถาม: ฉันจะซื้อ Aspose.GIS สำหรับ .NET ได้ที่ไหน
 คุณสามารถซื้อห้องสมุดได้[ที่นี่](https://purchase.aspose.com/buy).