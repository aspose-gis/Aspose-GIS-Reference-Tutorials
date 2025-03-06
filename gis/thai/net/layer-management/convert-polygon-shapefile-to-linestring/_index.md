---
title: แปลงไฟล์รูปหลายเหลี่ยมเป็น Linestring
linktitle: แปลงไฟล์รูปหลายเหลี่ยมเป็น Linestring
second_title: Aspose.GIS .NET API
description: สำรวจพลังของ Aspose.GIS สำหรับ .NET และแปลง Polygon Shapefiles เป็น Linestrings ได้อย่างง่ายดาย ส่งเสริมการพัฒนา GIS ของคุณวันนี้!
weight: 18
url: /th/net/layer-management/convert-polygon-shapefile-to-linestring/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลงไฟล์รูปหลายเหลี่ยมเป็น Linestring

## การแนะนำ
หากคุณกำลังทำงานกับระบบข้อมูลทางภูมิศาสตร์ (GIS) ใน .NET Aspose.GIS จะเป็นไลบรารีที่ทรงพลังที่สามารถทำให้งานของคุณง่ายขึ้น ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการแปลง Polygon Shapefile เป็น Linestring โดยใช้ Aspose.GIS สิ่งนี้มีประโยชน์อย่างยิ่งเมื่อคุณต้องการแยกคุณลักษณะเชิงเส้นออกจากข้อมูลเหลี่ยมสำหรับการใช้งานต่างๆ เช่น การวางแผนเส้นทางหรือการวิเคราะห์เครือข่าย
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
-  ไลบรารี Aspose.GIS: ดาวน์โหลดและติดตั้งไลบรารี Aspose.GIS จาก[เว็บไซต์](https://releases.aspose.com/gis/net/).
- ข้อมูลเชปไฟล์: เตรียมไฟล์เชปไฟล์รูปหลายเหลี่ยมให้พร้อมสำหรับการแปลง หากคุณไม่มี คุณสามารถค้นหาข้อมูลตัวอย่างหรือสร้างขึ้นเองได้
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ของคุณด้วยเครื่องมือที่จำเป็น
## นำเข้าเนมสเปซ
ในโค้ด C# ของคุณ คุณจะต้องนำเข้าเนมสเปซ Aspose.GIS เพื่อเข้าถึงคลาสและวิธีการที่จำเป็น เพิ่มเนมสเปซต่อไปนี้ที่จุดเริ่มต้นของไฟล์โค้ดของคุณ:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
```
แทนที่ "Your Document Directory" ด้วยเส้นทางไปยังไดเร็กทอรีที่ Shapefile ของคุณตั้งอยู่
## ขั้นตอนที่ 2: เปิด Shapefile ต้นฉบับ
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // รหัสที่เหลือจะไปที่นี่
}
```
ขั้นตอนนี้จะเปิดไฟล์ Polygon Shapefile ขึ้นมาเพื่ออ่าน
## ขั้นตอนที่ 3: สร้าง Shapefile Linestring ปลายทาง
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // รหัสที่เหลือจะไปที่นี่
}
```
ที่นี่ เราสร้าง Linestring Shapefile ใหม่สำหรับเขียนข้อมูลที่แปลงแล้ว
## ขั้นตอนที่ 4: วนซ้ำผ่านฟีเจอร์แหล่งที่มา
```csharp
foreach (Feature sourceFeature in source)
{
    // รหัสที่เหลือจะไปที่นี่
}
```
ลูปนี้จะวนซ้ำแต่ละฟีเจอร์ใน Polygon Shapefile ต้นทาง
## ขั้นตอนที่ 5: แปลงรูปหลายเหลี่ยมเป็น Linestring และเขียนไปยังปลายทาง
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
ในขั้นตอนนี้ คุณลักษณะของรูปหลายเหลี่ยมแต่ละรายการจะถูกแปลงเป็น Linestring และคุณลักษณะ Linestring ที่เป็นผลลัพธ์จะถูกเขียนไปยัง Shapefile ปลายทาง
## บทสรุป
ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถแปลง Polygon Shapefile เป็น Linestring ได้อย่างง่ายดายโดยใช้ Aspose.GIS สำหรับ .NET กระบวนการนี้เปิดโอกาสใหม่ๆ สำหรับการวิเคราะห์ข้อมูลและการแสดงภาพในแอปพลิเคชัน GIS

## คำถามที่พบบ่อย
### Aspose.GIS เข้ากันได้กับ .NET ทุกเวอร์ชันหรือไม่
ใช่ Aspose.GIS รองรับ .NET เวอร์ชันต่างๆ เพื่อให้มั่นใจว่าสามารถเข้ากันได้กับสภาพแวดล้อมการพัฒนาของคุณ
### ฉันสามารถใช้ Aspose.GIS สำหรับโครงการเชิงพาณิชย์ได้หรือไม่
 ใช่คุณสามารถ. หากต้องการใช้ Aspose.GIS ในโครงการเชิงพาณิชย์ โปรดพิจารณาซื้อใบอนุญาต[ที่นี่](https://purchase.aspose.com/buy).
### มีตัวอย่างหรือเอกสารประกอบอะไรบ้าง?
 ใช่ คุณสามารถค้นหาเอกสารและตัวอย่างที่ครอบคลุมได้ที่[หน้าเอกสาร](https://reference.aspose.com/gis/net/).
### มีรุ่นทดลองใช้งานหรือไม่?
 ใช่ คุณสามารถสำรวจ Aspose.GIS ด้วยการทดลองใช้ฟรีโดยไปที่[ลิงค์นี้](https://releases.aspose.com/).
### ฉันจะขอความช่วยเหลือหรือสนับสนุนได้ที่ไหน?
 เยี่ยมชม[ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33) สำหรับความช่วยเหลือหรือข้อสงสัยที่เกี่ยวข้องกับการสนับสนุน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
