---
title: แปลง GeoJSON เป็น TopoJSON ด้วยการจัดกลุ่ม
linktitle: แปลง GeoJSON เป็น TopoJSON ด้วยการจัดกลุ่ม
second_title: Aspose.GIS .NET API
description: เรียนรู้วิธีแปลง GeoJSON เป็น TopoJSON ด้วยการจัดกลุ่มโดยใช้ Aspose.GIS สำหรับ .NET ในบทช่วยสอนที่ครอบคลุมนี้
type: docs
weight: 13
url: /th/net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
---
## การแนะนำ

ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนเกี่ยวกับการใช้ Aspose.GIS สำหรับ .NET เพื่อแปลง GeoJSON เป็น TopoJSON ด้วยการจัดกลุ่ม Aspose.GIS เป็น .NET API อันทรงพลังที่ช่วยให้นักพัฒนาทำงานกับข้อมูลทางภูมิศาสตร์ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการแปลงไฟล์ GeoJSON เป็น TopoJSON ในขณะที่จัดกลุ่มคุณสมบัติตามคุณลักษณะที่ระบุ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1.  Aspose.GIS สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ดาวน์โหลดและติดตั้งไลบรารี Aspose.GIS สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/gis/net/).

2. สภาพแวดล้อมการพัฒนา: คุณควรมีสภาพแวดล้อมการพัฒนาการทำงานที่ตั้งค่าด้วย Visual Studio หรือ IDE อื่นที่เข้ากันได้

3. ไฟล์ GeoJSON ตัวอย่าง: เตรียมไฟล์ GeoJSON ตัวอย่างที่คุณต้องการแปลง คุณสามารถรับไฟล์ GeoJSON ตัวอย่างจากแหล่งต่างๆ หรือสร้างไฟล์ของคุณเองได้

## นำเข้าเนมสเปซ

ขั้นแรก ตรวจสอบให้แน่ใจว่าได้รวมเนมสเปซที่จำเป็นในโครงการของคุณ:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```


ตอนนี้เรามาแบ่งกระบวนการแปลงออกเป็นหลายขั้นตอน:

## ขั้นตอนที่ 1: กำหนดเส้นทางไฟล์

กำหนดเส้นทางสำหรับไฟล์ GeoJSON อินพุตและไฟล์เอาต์พุต TopoJSON ของคุณ:

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

 แทนที่`"Your Document Directory"` ด้วยไดเร็กทอรีจริงที่ไฟล์ของคุณอยู่

## ขั้นตอนที่ 2: กำหนดค่าตัวเลือกการแปลง

กำหนดค่าตัวเลือกการแปลงเพื่อระบุวิธีการจัดกลุ่ม ในตัวอย่างนี้ เราจะจัดกลุ่มคุณลักษณะตามคุณลักษณะเฉพาะ

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // ระบุแอตทริบิวต์ในเลเยอร์ GeoJSON ที่เราจะจัดกลุ่มเป็นวัตถุ
        ObjectNameAttribute = "group",
        // ระบุชื่อออบเจ็กต์เริ่มต้นสำหรับคุณลักษณะที่มีค่าแอตทริบิวต์ที่ไม่รู้จัก
        DefaultObjectName = "unnamed",
    }
};
```

 ปรับ`ObjectNameAttribute` และ`DefaultObjectName` คุณสมบัติตามข้อมูล GeoJSON ของคุณ

## ขั้นตอนที่ 3: ทำการแปลง

ดำเนินการกระบวนการแปลงโดยใช้ Aspose.GIS API:

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

บรรทัดโค้ดนี้จะแปลงไฟล์ GeoJSON เป็น TopoJSON ด้วยตัวเลือกการจัดกลุ่มที่ระบุ

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแปลง GeoJSON เป็น TopoJSON ด้วยการจัดกลุ่มโดยใช้ Aspose.GIS สำหรับ .NET ด้วยการทำตามขั้นตอนง่ายๆ เหล่านี้ คุณสามารถจัดการรูปแบบข้อมูลทางภูมิศาสตร์ในแอปพลิเคชัน .NET ของคุณได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถจัดกลุ่มคุณสมบัติตามคุณสมบัติหลายรายการได้หรือไม่
ตอบ: ได้ คุณสามารถปรับแต่งตัวเลือกการแปลงเพื่อจัดกลุ่มฟีเจอร์ตามแอตทริบิวต์หลายรายการได้

### คำถามที่ 2: Aspose.GIS เข้ากันได้กับ .NET Core หรือไม่
ตอบ: ใช่ Aspose.GIS รองรับ .NET Core พร้อมกับ .NET Framework แบบดั้งเดิม

### คำถามที่ 3: ฉันสามารถแปลงรูปแบบข้อมูลทางภูมิศาสตร์อื่นๆ โดยใช้ Aspose.GIS ได้หรือไม่
ตอบ: ใช่ Aspose.GIS ให้การสนับสนุนรูปแบบข้อมูลทางภูมิศาสตร์ที่หลากหลาย นอกเหนือจาก GeoJSON และ TopoJSON

### คำถามที่ 4: Aspose.GIS ให้ทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถทดลองใช้ Aspose.GIS ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).

### คำถามที่ 5: ฉันจะรับการสนับสนุนสำหรับ Aspose.GIS ได้ที่ไหน
 ตอบ: คุณสามารถรับการสนับสนุนจากฟอรัมชุมชน Aspose.GIS[ที่นี่](https://forum.aspose.com/c/gis/33).