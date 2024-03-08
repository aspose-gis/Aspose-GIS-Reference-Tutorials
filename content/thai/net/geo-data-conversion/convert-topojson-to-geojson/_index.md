---
title: แปลง TopoJSON เป็น GeoJSON
linktitle: แปลง TopoJSON เป็น GeoJSON
second_title: Aspose.GIS .NET API
description: เรียนรู้วิธีแปลง TopoJSON เป็น GeoJSON อย่างราบรื่นโดยใช้ Aspose.GIS สำหรับ .NET ปฏิบัติตามบทช่วยสอนทีละขั้นตอนของเราเพื่อการจัดการข้อมูลทางภูมิศาสตร์ที่มีประสิทธิภาพ
type: docs
weight: 16
url: /th/net/geo-data-conversion/convert-topojson-to-geojson/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการแปลงจาก TopoJSON เป็น GeoJSON โดยใช้ Aspose.GIS สำหรับ .NET Aspose.GIS เป็น API ที่ทรงพลังซึ่งออกแบบมาเพื่ออำนวยความสะดวกในการประมวลผลข้อมูลทางภูมิศาสตร์ภายในแอปพลิเคชัน .NET TopoJSON และ GeoJSON เป็นรูปแบบที่ใช้กันอย่างแพร่หลายในการแสดงข้อมูลทางภูมิศาสตร์ และความสามารถในการแปลงระหว่างรูปแบบเหล่านี้ถือเป็นสิ่งสำคัญสำหรับแอปพลิเคชัน GIS ต่างๆ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1.  Aspose.GIS สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ดาวน์โหลดและติดตั้งไลบรารี Aspose.GIS สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์ Aspose.GIS](https://releases.aspose.com/gis/net/).
2. สภาพแวดล้อมการพัฒนา: คุณต้องมีสภาพแวดล้อมการพัฒนาที่ใช้งานได้โดยติดตั้ง .NET
3. ไฟล์ TopoJSON ตัวอย่าง: เตรียมไฟล์ TopoJSON ตัวอย่างให้พร้อมสำหรับการแปลง หากคุณไม่มี คุณสามารถสร้างหรือรับได้จากแหล่งต่างๆ

## นำเข้าเนมสเปซ
ก่อนดำเนินการแปลงต่อ ให้นำเข้าเนมสเปซที่จำเป็นไปยังโปรเจ็กต์ของคุณ เนมสเปซเหล่านี้จะให้การเข้าถึงฟังก์ชันที่จำเป็นสำหรับการแปลง TopoJSON เป็น GeoJSON

   ```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

ตอนนี้คุณได้ตั้งค่าสภาพแวดล้อมของคุณและนำเข้าเนมสเปซที่จำเป็นแล้ว เรามาแจกแจงขั้นตอนการแปลง TopoJSON เป็น GeoJSON ให้เป็นคำแนะนำทีละขั้นตอนกัน
## ขั้นตอนที่ 1: ระบุเส้นทางอินพุตและเอาต์พุต

กำหนดเส้นทางสำหรับไฟล์ TopoJSON อินพุตและไฟล์ GeoJSON เอาต์พุต
```csharp
var sampleTopoJsonPath = "Your Document Directory" + "sample.topojson";
var outputFilePath = "Your Document Directory" + "convertedSample_out.geojson";
```
##  ขั้นตอนที่ 2: ทำการแปลงโดยใช้`VectorLayer.Convert` method to convert TopoJSON to GeoJSON.
```csharp
VectorLayer.Convert(sampleTopoJsonPath, Drivers.TopoJson, outputFilePath, Drivers.GeoJson);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีแปลง TopoJSON เป็น GeoJSON โดยใช้ Aspose.GIS สำหรับ .NET ด้วยการทำตามขั้นตอนที่ระบุไว้และใช้ไลบรารี Aspose.GIS คุณสามารถจัดการการแปลงข้อมูลทางภูมิศาสตร์ภายในแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น
## คำถามที่พบบ่อย
### Aspose.GIS สามารถจัดการชุดข้อมูลทางภูมิศาสตร์ขนาดใหญ่ได้หรือไม่
ใช่ Aspose.GIS สามารถประมวลผลชุดข้อมูลทางภูมิศาสตร์ขนาดใหญ่ได้อย่างมีประสิทธิภาพ เพื่อให้มั่นใจถึงประสิทธิภาพสูงสุด
### Aspose.GIS เข้ากันได้กับรูปแบบไฟล์ GIS ที่แตกต่างกันหรือไม่
แน่นอนว่า Aspose.GIS รองรับรูปแบบไฟล์ GIS ที่หลากหลาย รวมถึง TopoJSON, GeoJSON, Shapefile และอื่นๆ อีกมากมาย
### Aspose.GIS มีเอกสารและการสนับสนุนหรือไม่
 ใช่ เอกสารและการสนับสนุนที่ครอบคลุมมีให้ผ่านทาง[ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33).
### ฉันสามารถลองใช้ Aspose.GIS ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถทดลองใช้ฟรีได้จาก[เว็บไซต์กำหนด](https://releases.aspose.com/).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[กำหนดหน้าการซื้อ](https://purchase.aspose.com/temporary-license/).