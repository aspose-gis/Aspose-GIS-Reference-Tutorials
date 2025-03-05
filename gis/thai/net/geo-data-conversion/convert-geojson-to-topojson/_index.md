---
title: แปลง GeoJSON เป็น TopoJSON
linktitle: แปลง GeoJSON เป็น TopoJSON
second_title: Aspose.GIS .NET API
description: เรียนรู้วิธีแปลงไฟล์ GeoJSON เป็นรูปแบบ TopoJSON ได้อย่างราบรื่นโดยใช้ Aspose.GIS สำหรับไลบรารี .NET เพิ่มประสิทธิภาพการประมวลผลข้อมูล GIS ของคุณ
type: docs
weight: 11
url: /th/net/geo-data-conversion/convert-geojson-to-topojson/
---
## การแนะนำ
ในขอบเขตของระบบสารสนเทศทางภูมิศาสตร์ (GIS) รูปแบบการแลกเปลี่ยนข้อมูลมีบทบาทสำคัญในการอำนวยความสะดวกในการแลกเปลี่ยนข้อมูลและการทำงานร่วมกันระหว่างระบบต่างๆ สองรูปแบบยอดนิยมดังกล่าวคือ GeoJSON และ TopoJSON GeoJSON ซึ่งเป็นรูปแบบน้ำหนักเบาสำหรับการเข้ารหัสโครงสร้างข้อมูลทางภูมิศาสตร์ และ TopoJSON ซึ่งเป็นส่วนขยายของ GeoJSON นำเสนอการเข้ารหัสโทโพโลยีเพื่อการจัดเก็บและการส่งข้อมูลทางภูมิศาสตร์ที่มีประสิทธิภาพมากขึ้น ในบทช่วยสอนนี้ เราจะเจาะลึกเกี่ยวกับการแปลง GeoJSON เป็น TopoJSON โดยใช้ไลบรารี Aspose.GIS สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่กระบวนการแปลง ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
### การติดตั้ง Aspose.GIS สำหรับ .NET
1.  ดาวน์โหลดไลบรารี Aspose.GIS สำหรับ .NET: ไปที่[ลิงค์นี้](https://releases.aspose.com/gis/net/) เพื่อดาวน์โหลดไลบรารี Aspose.GIS สำหรับ .NET
2.  ติดตั้งไลบรารี: ทำตามคำแนะนำการติดตั้งที่ให้ไว้ในเอกสารประกอบ[ที่นี่](https://reference.aspose.com/gis/net/).

## การนำเข้าเนมสเปซที่จำเป็น
ตรวจสอบให้แน่ใจว่าคุณนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ .NET ของคุณ:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: โหลดไฟล์ GeoJSON
ขั้นแรก คุณต้องโหลดไฟล์ GeoJSON ที่คุณต้องการแปลงเป็น TopoJSON ตรวจสอบให้แน่ใจว่าคุณมีเส้นทางของไฟล์ที่มีประโยชน์
## ขั้นตอนที่ 2: กำหนดเส้นทางไฟล์เอาท์พุต
ระบุเส้นทางที่คุณต้องการบันทึกไฟล์ TopoJSON ที่แปลงแล้ว ตรวจสอบให้แน่ใจว่าคุณมีสิทธิ์ในการเขียนในไดเร็กทอรีนั้น
## ขั้นตอนที่ 3: ทำการแปลง
 ใช้`VectorLayer.Convert()` วิธีการแปลงไฟล์ GeoJSON ที่โหลดเป็นรูปแบบ TopoJSON ผ่านพารามิเตอร์ไดรเวอร์ที่เหมาะสม (`Drivers.GeoJson` สำหรับการป้อนข้อมูลและ`Drivers.TopoJson` สำหรับเอาต์พุต) พร้อมกับพาธของไฟล์
```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSample_out.topojson";
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson);
```

## บทสรุป
การแปลง GeoJSON เป็น TopoJSON ถือเป็นงานสำคัญในการประมวลผลข้อมูล GIS ช่วยให้สามารถจัดเก็บและส่งข้อมูลทางภูมิศาสตร์ได้อย่างมีประสิทธิภาพ ด้วยไลบรารี Aspose.GIS สำหรับ .NET กระบวนการนี้จะมีความคล่องตัวและสามารถเข้าถึงได้สำหรับนักพัฒนา .NET
## คำถามที่พบบ่อย
### Aspose.GIS สำหรับ .NET เข้ากันได้กับ .NET ทุกเวอร์ชันหรือไม่
ใช่ Aspose.GIS สำหรับ .NET เข้ากันได้กับ .NET Framework และ .NET Core ทุกเวอร์ชัน
### ฉันสามารถลองใช้ Aspose.GIS สำหรับ .NET ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถทดลองใช้ฟรีได้จาก[ลิงค์นี้](https://releases.aspose.com/).
### Aspose.GIS สำหรับ .NET รองรับรูปแบบ GIS อื่นนอกเหนือจาก GeoJSON และ TopoJSON หรือไม่
ใช่ Aspose.GIS สำหรับ .NET รองรับรูปแบบ GIS ที่หลากหลายสำหรับการอ่านและการเขียน
### ฉันจะรับการสนับสนุน Aspose.GIS สำหรับ .NET ได้อย่างไร
 คุณสามารถขอการสนับสนุนจากฟอรัมชุมชน Aspose.GIS[ที่นี่](https://forum.aspose.com/c/gis/33).
### ฉันสามารถใช้ Aspose.GIS สำหรับ .NET สำหรับโครงการเชิงพาณิชย์ได้หรือไม่
 ใช่ คุณสามารถซื้อใบอนุญาตได้จาก[ลิงค์นี้](https://purchase.aspose.com/buy).