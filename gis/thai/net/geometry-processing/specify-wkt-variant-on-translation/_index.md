---
title: ระบุตัวแปร WKT ในการแปลโดยใช้ Aspose.GIS
linktitle: ระบุตัวแปร WKT ในการแปล
second_title: Aspose.GIS .NET API
description: เรียนรู้วิธีระบุตัวแปร WKT ใน Aspose.GIS สำหรับ .NET เพื่อควบคุมรูปแบบการแสดงข้อมูลเชิงพื้นที่และความแม่นยำอย่างมีประสิทธิภาพ
type: docs
weight: 19
url: /th/net/geometry-processing/specify-wkt-variant-on-translation/
---
## การแนะนำ
Aspose.GIS สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถทำงานกับข้อมูลระบบสารสนเทศภูมิศาสตร์ (GIS) ในแอปพลิเคชัน .NET ของตนได้อย่างง่ายดาย หนึ่งในคุณสมบัติที่สำคัญของ Aspose.GIS คือความสามารถในการระบุตัวแปร Well-Known Text (WKT) ในระหว่างการแปล ทำให้ผู้ใช้สามารถควบคุมรูปแบบและความแม่นยำของการแสดงข้อมูลเชิงพื้นที่ได้ ในบทช่วยสอนนี้ เราจะสำรวจวิธีระบุตัวแปร WKT ทีละขั้นตอนโดยใช้ Aspose.GIS สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. Aspose.GIS สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.GIS สำหรับ .NET จาก[หน้าดาวน์โหลด](https://releases.aspose.com/gis/net/).
2. สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา .NET แล้ว
3. ความรู้พื้นฐาน: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# และกรอบงาน .NET

## นำเข้าเนมสเปซ
ก่อนที่จะใช้ฟังก์ชัน Aspose.GIS ในโค้ดของคุณ ให้นำเข้าเนมสเปซที่จำเป็น:
```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```
## ขั้นตอนที่ 1: สร้างวัตถุจุด
 ขั้นแรกให้สร้างก`Point` วัตถุที่มีค่าละติจูด ลองจิจูด และค่าการวัดเสริม (M):
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## ขั้นตอนที่ 2: ตั้งค่าระบบอ้างอิงเชิงพื้นที่ (SRS)
กำหนดระบบอ้างอิงเชิงพื้นที่ (SRS) ให้กับวัตถุจุด ในตัวอย่างนี้ เราใช้ระบบอ้างอิงเชิงพื้นที่ WGS84:
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## ขั้นตอนที่ 3: ระบุตัวแปร WKT
 ตอนนี้ ให้ระบุตัวแปร WKT สำหรับการแปล Aspose.GIS รองรับ WKT หลากหลายรูปแบบ รวมถึง`Iso`, `SimpleFeatureAccessOutdated` , และ`ExtendedPostGis`. เลือกรุ่นที่เหมาะสมตามความต้องการของคุณ:
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // จุดเอ็ม (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // จุด (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```
## ขั้นตอนที่ 4: ควบคุมรูปแบบตัวเลข
คุณสามารถควบคุมรูปแบบตัวเลขของพิกัดในการเป็นตัวแทน WKT Aspose.GIS มีตัวเลือกในการระบุความแม่นยำของทศนิยม:
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // จุดเอ็ม (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // จุดเอ็ม (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // จุดเอ็ม (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // จุดเอ็ม (23.573 25.342 40.3)
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีระบุรูปแบบ WKT ในการแปลโดยใช้ Aspose.GIS สำหรับ .NET ด้วยการทำตามขั้นตอนที่สรุปไว้ข้างต้น นักพัฒนาจะสามารถควบคุมรูปแบบและความแม่นยำของการแสดงข้อมูลเชิงพื้นที่ในแอปพลิเคชัน .NET ได้อย่างมีประสิทธิภาพ เพิ่มความยืดหยุ่นและการใช้งานระบบสารสนเทศทางภูมิศาสตร์
## คำถามที่พบบ่อย
### Aspose.GIS เข้ากันได้กับ .NET ทุกเวอร์ชันหรือไม่
ใช่ Aspose.GIS รองรับ .NET Framework 4.0 และสูงกว่า
### ฉันสามารถใช้ Aspose.GIS สำหรับโครงการเชิงพาณิชย์ได้หรือไม่
ใช่ Aspose.GIS สามารถใช้กับทั้งโครงการส่วนตัวและเชิงพาณิชย์
### Aspose.GIS ให้การสนับสนุนรูปแบบข้อมูลเชิงพื้นที่อื่นๆ หรือไม่
ใช่ Aspose.GIS รองรับรูปแบบข้อมูลเชิงพื้นที่ที่หลากหลาย รวมถึง ESRI Shapefile, GeoJSON และ KML
### Aspose.GIS มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถดาวน์โหลด Aspose.GIS เวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะขอความช่วยเหลือหรือสนับสนุน Aspose.GIS ได้ที่ไหน
 คุณสามารถโพสต์คำถามของคุณหรือขอความช่วยเหลือจากชุมชน Aspose.GIS ได้ที่[ฟอรั่ม](https://forum.aspose.com/c/gis/33).