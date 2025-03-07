---
title: แปลงเชปไฟล์เป็น GeoJSON
linktitle: แปลงเชปไฟล์เป็น GeoJSON
second_title: Aspose.GIS .NET API
description: เรียนรู้วิธีแปลง Shapefile เป็น GeoJSON ใน .NET ได้อย่างง่ายดายโดยใช้ Aspose.GIS ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการทำงานร่วมกันของข้อมูลที่ราบรื่น
weight: 15
url: /th/net/geo-data-conversion/convert-shapefile-to-geojson/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลงเชปไฟล์เป็น GeoJSON

## การแนะนำ
ในขอบเขตของระบบสารสนเทศทางภูมิศาสตร์ (GIS) การทำงานร่วมกันของข้อมูลเป็นสิ่งสำคัญสำหรับการบูรณาการและการวิเคราะห์ที่ราบรื่น งานทั่วไปอย่างหนึ่งคือการแปลง Shapefiles ซึ่งเป็นรูปแบบข้อมูลเวกเตอร์เชิงพื้นที่ที่ใช้กันอย่างแพร่หลายไปเป็น GeoJSON ซึ่งเป็นรูปแบบขนาดเล็กสำหรับการแลกเปลี่ยนข้อมูลเชิงพื้นที่ บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการแปลง Shapefile เป็น GeoJSON ได้อย่างง่ายดายโดยใช้ไลบรารี Aspose.GIS สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่กระบวนการแปลง ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### 1. การติดตั้ง Aspose.GIS สำหรับ .NET Library
 เยี่ยมชม[Aspose.GIS สำหรับเอกสาร .NET](https://reference.aspose.com/gis/net/) เพื่อรับคำแนะนำโดยละเอียดเกี่ยวกับวิธีการติดตั้งและตั้งค่าไลบรารีในสภาพแวดล้อม .NET ของคุณ
### 2. กำลังดาวน์โหลดไฟล์ Shapefile อินพุต
ดาวน์โหลด Shapefile อินพุตที่คุณต้องการแปลงเป็น GeoJSON คุณสามารถรับ Shapefiles จากแหล่งต่างๆ รวมถึงหน่วยงานภาครัฐ เปิดพอร์ทัลข้อมูล หรือสร้าง Shapefile ของคุณเองโดยใช้ซอฟต์แวร์ GIS เช่น QGIS หรือ ArcGIS
### 3. ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C#
ทำความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม C# เนื่องจากบทช่วยสอนนี้จะใช้ตัวอย่างโค้ด C# สำหรับกระบวนการแปลง

## นำเข้าเนมสเปซ
ก่อนดำเนินการแปลงต่อ ตรวจสอบให้แน่ใจว่าคุณนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ Aspose.GIS สำหรับ .NET:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

ตอนนี้ เรามาแบ่งกระบวนการแปลงออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: กำหนดเส้นทางอินพุตและเอาต์พุต
ขั้นแรก ให้ระบุเส้นทางสำหรับอินพุต Shapefile และเอาต์พุตไฟล์ GeoJSON:
```csharp
string dataDir = "Your Document Directory";
string shapefilePath = dataDir + "InputShapeFile.shp";
string jsonPath = dataDir + "output_out.json";
```
 ให้แน่ใจว่าจะเปลี่ยน`"Your Document Directory"` ด้วยเส้นทางไดเร็กทอรีจริงซึ่งเป็นที่ตั้งของไฟล์ของคุณ
## ขั้นตอนที่ 2: ทำการแปลง
 ใช้`VectorLayer.Convert` วิธีการดำเนินการกระบวนการแปลง:
```csharp
VectorLayer.Convert(shapefilePath, Drivers.Shapefile, jsonPath, Drivers.GeoJson);
```
บรรทัดโค้ดนี้แปลงอินพุต Shapefile (`shapefilePath` ) เป็นรูปแบบ GeoJSON และบันทึกเอาต์พุตตามที่ระบุ`jsonPath`.

## บทสรุป
การแปลงเชปไฟล์เป็นรูปแบบ GeoJSON เป็นงานพื้นฐานในการประมวลผลข้อมูล GIS ด้วยความช่วยเหลือของ Aspose.GIS สำหรับไลบรารี .NET กระบวนการนี้จะมีความคล่องตัวและมีประสิทธิภาพ เมื่อทำตามบทช่วยสอนนี้ คุณสามารถทำการแปลงภายในแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย ช่วยให้สามารถทำงานร่วมกันและวิเคราะห์ข้อมูลเชิงพื้นที่ได้อย่างราบรื่น
## คำถามที่พบบ่อย
### ฉันสามารถแปลง Shapefiles หลายไฟล์เป็น GeoJSON ได้ในคราวเดียวโดยใช้ Aspose.GIS สำหรับ .NET ได้หรือไม่
ได้ คุณสามารถวนซ้ำ Shapefiles หลายไฟล์แล้วแปลงเป็นรูปแบบ GeoJSON โดยใช้แนวทางที่คล้ายกันซึ่งแสดงในบทช่วยสอนนี้
### Aspose.GIS สำหรับ .NET เข้ากันได้กับ .NET Framework ทุกเวอร์ชันหรือไม่
Aspose.GIS สำหรับ .NET รองรับ .NET Framework 4.5 และเวอร์ชันที่สูงกว่า
### Aspose.GIS สำหรับ .NET ให้การสนับสนุนรูปแบบภูมิสารสนเทศอื่นๆ นอกเหนือจาก Shapefile และ GeoJSON หรือไม่
ใช่ Aspose.GIS สำหรับ .NET รองรับรูปแบบภูมิสารสนเทศที่หลากหลาย รวมถึง GeoTIFF, KML, GML และอื่นๆ
### ฉันสามารถปรับแต่งกระบวนการแปลง เช่น การระบุระบบพิกัดหรือการแมปแอตทริบิวต์ได้หรือไม่
ใช่ Aspose.GIS สำหรับ .NET มีตัวเลือกมากมายสำหรับการปรับแต่งกระบวนการแปลงตามความต้องการของคุณ
### มีรุ่นทดลองใช้สำหรับ Aspose.GIS สำหรับ .NET หรือไม่
 ใช่ คุณสามารถใช้ Aspose.GIS สำหรับ .NET เวอร์ชันทดลองใช้ฟรีได้จาก[เว็บไซต์](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
