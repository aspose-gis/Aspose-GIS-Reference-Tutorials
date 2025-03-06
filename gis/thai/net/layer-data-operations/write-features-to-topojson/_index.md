---
title: เขียนคุณสมบัติลงใน TopoJSON
linktitle: เขียนคุณสมบัติลงใน TopoJSON
second_title: Aspose.GIS .NET API
description: เชี่ยวชาญการเขียนฟีเจอร์ TopoJSON ด้วย Aspose.GIS สำหรับ .NET ปฏิบัติตามบทช่วยสอนทีละขั้นตอนของเรา ยกระดับแอปพลิเคชัน GIS ของคุณ
weight: 24
url: /th/net/layer-data-operations/write-features-to-topojson/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เขียนคุณสมบัติลงใน TopoJSON

## การแนะนำ
ในขอบเขตของการพัฒนาระบบสารสนเทศภูมิศาสตร์ (GIS) Aspose.GIS สำหรับ .NET มีความโดดเด่นในฐานะชุดเครื่องมืออันทรงพลัง โดยมีฟังก์ชันการทำงานมากมายเหลือเฟือสำหรับการจัดการข้อมูลเชิงพื้นที่ ท่ามกลางความสามารถต่างๆ มากมาย บทช่วยสอนนี้มุ่งเน้นไปที่งานเฉพาะ: การเขียนคุณสมบัติเป็นรูปแบบ TopoJSON โดยใช้ Aspose.GIS สำหรับ .NET หากคุณกระตือรือร้นที่จะปรับปรุงแอปพลิเคชัน GIS ของคุณด้วยการสนับสนุน TopoJSON ให้ปฏิบัติตามเพื่อค้นหาคำแนะนำทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.GIS สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.GIS แล้ว คุณสามารถค้นหาเอกสารและดาวน์โหลดห้องสมุด[ที่นี่](https://reference.aspose.com/gis/net/).
- สภาพแวดล้อม .NET: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา .NET แล้ว
-  ไดเร็กทอรีเอกสาร: เลือกไดเร็กทอรีสำหรับเอกสารของคุณ ซึ่งก็จะเรียกกันว่า`Your Document Directory` ในตัวอย่างโค้ด
## นำเข้าเนมสเปซ
ในแอปพลิเคชัน .NET ของคุณ ให้รวมเนมสเปซที่จำเป็นสำหรับการทำงานกับ Aspose.GIS และฟังก์ชันที่จำเป็นอื่นๆ
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
```
ตอนนี้ เรามาแบ่งตัวอย่างโค้ดออกเป็นหลายขั้นตอนเพื่อความเข้าใจที่ชัดเจน
## 1. ตั้งค่าไดเร็กทอรีเอกสาร
```csharp
string dataDir = "Your Document Directory";
```
 แทนที่`"Your Document Directory"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ
## 2. ระบุเส้นทางเอาต์พุต
```csharp
var outputPath = dataDir + "sample_out.topojson";
```
กำหนดเส้นทางสำหรับไฟล์เอาต์พุต TopoJSON
## 3. สร้าง VectorLayer ด้วยไดรเวอร์ TopoJSON
```csharp
using (VectorLayer layer = VectorLayer.Create(outputPath, Drivers.TopoJson))
```
เริ่มต้น VectorLayer โดยใช้ไดรเวอร์ TopoJSON
## 4. เพิ่มคุณสมบัติให้กับเลเยอร์
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("measurement", AttributeDataType.Double));
layer.Attributes.Add(new FeatureAttribute("id", AttributeDataType.Integer));
```
กำหนดคุณลักษณะสำหรับคุณลักษณะที่จะเพิ่มลงในเลเยอร์
## 5. เพิ่มคุณสมบัติให้กับเลเยอร์
```csharp
var feature0 = layer.ConstructFeature();
feature0.SetValue("name", "name_0");
feature0.SetValue("measurement", 1.03);
feature0.SetValue("id", 0);
feature0.Geometry = new Point(1.3, 2.3);
layer.Add(feature0);
var feature1 = layer.ConstructFeature();
feature1.SetValue("name", "name_1");
feature1.SetValue("measurement", 10.03);
feature1.SetValue("id", 1);
feature1.Geometry = new Point(241.32, 23.2);
layer.Add(feature1);
```
สร้างคุณลักษณะด้วยคุณลักษณะและรูปทรงที่ระบุ และเพิ่มลงในเลเยอร์
## บทสรุป
ยินดีด้วย! คุณเขียนฟีเจอร์ไปยัง TopoJSON โดยใช้ Aspose.GIS สำหรับ .NET สำเร็จแล้ว บทช่วยสอนนี้ให้ความเข้าใจพื้นฐานเกี่ยวกับกระบวนการ ทำให้คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชัน GIS ของคุณได้อย่างราบรื่น
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.GIS สำหรับ .NET กับไลบรารี GIS อื่นๆ ได้หรือไม่
ตอบ: Aspose.GIS สำหรับ .NET ได้รับการออกแบบมาให้ทำงานแยกจากกัน แต่สามารถใช้งานร่วมกับไลบรารีอื่นๆ เพื่อเพิ่มฟังก์ชันการทำงานได้
### ถาม: มีตัวเลือกสิทธิ์การใช้งานสำหรับ Aspose.GIS หรือไม่
 ตอบ: ได้ คุณสามารถสำรวจตัวเลือกสิทธิ์การใช้งานและทำการซื้อได้[ที่นี่](https://purchase.aspose.com/buy).
### ถาม: Aspose.GIS สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: แน่นอน! คุณสามารถเข้าถึงการทดลองใช้ฟรี[ที่นี่](https://releases.aspose.com/).
### ถาม: ฉันจะขอรับการสนับสนุนหรือเชื่อมต่อกับชุมชน Aspose.GIS ได้ที่ไหน
 ตอบ: มุ่งหน้าไปที่[ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33) สำหรับการสนับสนุนและการอภิปรายของชุมชน
### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS ได้อย่างไร
 ตอบ: คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
