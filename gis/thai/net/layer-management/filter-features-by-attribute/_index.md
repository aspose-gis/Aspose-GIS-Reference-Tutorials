---
title: กรองคุณสมบัติตามคุณสมบัติ
linktitle: กรองคุณสมบัติตามคุณสมบัติ
second_title: Aspose.GIS .NET API
description: สำรวจพลังของ Aspose.GIS สำหรับ .NET ในการจัดการข้อมูลเชิงพื้นที่ กรองคุณสมบัติได้อย่างง่ายดาย ปรับปรุงแอปพลิเคชัน GIS และเพิ่มประสิทธิภาพการทำงาน
weight: 21
url: /th/net/layer-management/filter-features-by-attribute/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# กรองคุณสมบัติตามคุณสมบัติ

## การแนะนำ
ในโลกแบบไดนามิกของระบบสารสนเทศทางภูมิศาสตร์ (GIS) Aspose.GIS สำหรับ .NET มีความโดดเด่นในฐานะเครื่องมืออันทรงพลังที่ช่วยให้นักพัฒนาสามารถจัดการและวิเคราะห์ข้อมูลเชิงพื้นที่ได้อย่างราบรื่น ไม่ว่าคุณจะเป็นมืออาชีพ GIS ที่ช่ำชองหรือเป็นนักพัฒนาที่อยากรู้อยากเห็นและกระตือรือร้นที่จะสำรวจความเป็นไปได้ต่างๆ บทช่วยสอนนี้จะแนะนำคุณตลอดขั้นตอนสำคัญของการใช้ Aspose.GIS ในสภาพแวดล้อม .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเจาะลึกตัวอย่างเชิงปฏิบัติ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  การติดตั้ง Aspose.GIS: ดาวน์โหลดและติดตั้งไลบรารี Aspose.GIS จาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/gis/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET บนเครื่องของคุณ
- ข้อมูลเชิงพื้นที่: เตรียมอินพุตเชปไฟล์ (เช่น "InputShapeFile.shp") ที่มีข้อมูลเชิงพื้นที่ที่คุณต้องการใช้งาน
- ความรู้พื้นฐานของ C#: ทำความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม C#
## นำเข้าเนมสเปซ
ในโค้ด C# ของคุณ ตรวจสอบให้แน่ใจว่าคุณนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.GIS:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
ตรวจสอบให้แน่ใจว่าคุณมีเส้นทางไดเรกทอรีเอกสารที่ถูกต้องในรหัสของคุณ:
```csharp
string dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: เปิดเลเยอร์เวกเตอร์
ใช้ Aspose.GIS เพื่อเปิดเลเยอร์เวกเตอร์จากเชปไฟล์:
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
```
## ขั้นตอนที่ 3: ทำซ้ำผ่านฟีเจอร์ต่างๆ
วนซ้ำคุณลักษณะทั้งหมดด้วยค่าวันที่ในแอตทริบิวต์ "dob" หลังจากวันที่ 1 มกราคม 1982:
```csharp
foreach (Feature feature in layer.WhereGreater("dob", new DateTime(1982, 1, 1, 0, 0, 0)))
{
    Console.WriteLine(feature.GetValue<DateTime>("dob").ToShortDateString());
}
```
ข้อมูลโค้ดนี้สาธิตคุณลักษณะการกรองตามแอตทริบิวต์ที่ระบุ ("dob" ในกรณีนี้) และเงื่อนไขวันที่ที่กำหนด
## บทสรุป
Aspose.GIS สำหรับ .NET ช่วยให้การจัดการและการวิเคราะห์ข้อมูลเชิงพื้นที่ง่ายขึ้น ทำให้เป็นเครื่องมือที่ขาดไม่ได้สำหรับนักพัฒนาในแอปพลิเคชัน GIS ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะได้เรียนรู้วิธีกรองฟีเจอร์ตามแอตทริบิวต์ ซึ่งเป็นการวางรากฐานสำหรับการดำเนินการข้อมูลเชิงพื้นที่ขั้นสูงยิ่งขึ้น
## คำถามที่พบบ่อย
### Aspose.GIS เข้ากันได้กับไฟล์ GIS ทุกรูปแบบหรือไม่
 Aspose.GIS รองรับไฟล์ GIS หลากหลายรูปแบบ รวมถึง Shapefile, GeoJSON และ KML ตรวจสอบ[เอกสารประกอบ](https://reference.aspose.com/gis/net/) สำหรับรายการที่ครอบคลุม
### ฉันสามารถลองใช้ Aspose.GIS ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถสำรวจ Aspose.GIS รุ่นทดลองใช้ฟรีได้โดยไปที่[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.GIS ได้ที่ไหน
 หากมีข้อสงสัยหรือความช่วยเหลือ โปรดไปที่[ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS ได้อย่างไร
 ได้รับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).
### มีบทช่วยสอนทีละขั้นตอนสำหรับคุณสมบัติอื่นๆ ของ Aspose.GIS หรือไม่
 ใช่ คุณสามารถค้นหาบทช่วยสอนและเอกสารประกอบเพิ่มเติมได้ที่[ข้อมูลอ้างอิง Aspose.GIS](https://reference.aspose.com/gis/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
