---
date: 2026-01-10
description: เรียนรู้วิธีแปลง GeoJSON เป็น File GDB ด้วย Aspose.GIS สำหรับ .NET คู่มือแบบขั้นตอนนี้ครอบคลุมการแปลงข้อมูลเชิงพื้นที่และการแปลง
  Aspose GIS.
linktitle: Convert GeoJSON Layer to File GDB
second_title: Aspose.GIS .NET API
title: วิธีแปลง GeoJSON เป็น File GDB ด้วย Aspose.GIS สำหรับ .NET
url: /th/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีแปลง GeoJSON เป็น File GDB ด้วย Aspose.GIS สำหรับ .NET

## บทนำ
หากคุณกำลังสงสัย **วิธีแปลง GeoJSON** ให้เป็น File Geodatabase (File GDB) สำหรับกระบวนการทำงาน GIS ที่แข็งแรง คุณมาถูกที่แล้ว ในบทเรียนนี้เราจะพาคุณผ่านขั้นตอนทั้งหมดด้วย Aspose.GIS สำหรับ .NET แสดงให้คุณเห็นว่าทำไมนี่เป็นไลบรารีที่เป็นตัวเลือกอันดับต้น ๆ สำหรับการแปลงข้อมูลเชิงพื้นที่และคุณจะสร้างไฟล์ geodatabase จากเลเยอร์ GeoJSON ได้อย่างรวดเร็ว

## คำตอบอย่างรวดเร็ว
- **บทเรียนนี้ครอบคลุมอะไร?** การแปลงเลเยอร์ GeoJSON เป็น File GDB ด้วย Aspose.GIS สำหรับ .NET.  
- **คำหลักหลักที่มุ่งหมายคือ?** *how to convert geojson*.  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **การดำเนินการใช้เวลานานเท่าไหร่?** ประมาณ 10‑15 นาทีสำหรับการแปลงพื้นฐาน.

## GeoJSON และ File GDB คืออะไร?
GeoJSON เป็นรูปแบบที่มีน้ำหนักเบาและเป็นข้อความสำหรับการเข้ารหัสโครงสร้างข้อมูลเชิงพื้นที่หลายประเภท File Geodatabase (File GDB) เป็นรูปแบบที่อิงโฟลเดอร์และมีประสิทธิภาพสูงที่ใช้โดยแอปพลิเคชัน GIS บนเดสก์ท็อปหลายตัว การแปลงระหว่างสองรูปแบบนี้ทำให้คุณสามารถใช้ประโยชน์จากจุดแข็งของทั้งสองรูปแบบในโครงการของคุณ

## ทำไมต้องใช้ Aspose.GIS สำหรับการแปลงข้อมูลเชิงพื้นที่?
Aspose.GIS มี API ที่เป็นเอกภาพซึ่งทำให้ซับซ้อนของการจัดการรูปแบบหายไป ด้วยการสนับสนุนในตัวสำหรับ **geojson to file gdb** คุณสามารถ:
- อ่าน GeoJSON ใน C# โดยไม่ต้องใช้ตัวแยกวิเคราะห์ของบุคคลที่สาม.  
- สร้างไฟล์ geodatabase อย่างโปรแกรม.  
- รักษาข้อมูลแอตทริบิวต์และข้อมูลอ้างอิงเชิงพื้นที่โดยอัตโนมัติ.  

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่ม โปรดตรวจสอบว่าคุณมี:
- ความรู้พื้นฐานในการเขียนโปรแกรม .NET.  
- ติดตั้ง Aspose.GIS สำหรับ .NET หากยังไม่ได้ติดตั้ง ดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/gis/net/) และทำตามคำแนะนำการติดตั้ง.

## นำเข้า Namespaces
ขั้นตอนแรกคือการนำ namespaces ที่จำเป็นเข้าสู่ขอบเขต

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

## ขั้นตอนที่ 1: ตั้งค่าเลเยอร์ GeoJSON
สร้างไฟล์ GeoJSON ชั่วคราวที่มีแอตทริบิวต์และฟีเจอร์ที่คุณต้องการแปลง ตัวอย่างนี้เพิ่มจุดสองจุดแบบง่าย

```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Add attributes
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    // Construct and add features
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```

## ขั้นตอนที่ 2: คัดลอกชุดข้อมูลทดสอบ
เพื่อให้ข้อมูลทดสอบต้นฉบับไม่ถูกแก้ไข ให้ทำสำเนาชุดข้อมูล File GDB ที่มีอยู่ สิ่งนี้ทำให้สภาพแวดล้อมสำหรับการแปลงสะอาด

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## ขั้นตอนที่ 3: แปลง GeoJSON เป็น File GDB
เปิดเลเยอร์ GeoJSON สร้างเลเยอร์ใหม่ภายใน File GDB ที่คัดลอกแล้ว คัดลอกแอตทริบิวต์และถ่ายโอนแต่ละฟีเจอร์ นี้คือแกนหลักของกระบวนการ **aspose gis conversion**

```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copy attributes
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Add features
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```

## ปัญหาที่พบบ่อยและวิธีแก้
- **ไม่มีการอ้างอิงเชิงพื้นที่:** ตรวจสอบให้แน่ใจว่า GeoJSON ต้นทางมีการกำหนด CRS หรือกำหนด `SpatialReferenceSystem.Wgs84` อย่างชัดเจนเมื่อสร้างเลเยอร์ File GDB.  
- **ประเภทแอตทริบิวต์ไม่ตรงกัน:** ชนิดข้อมูลแอตทริบิวต์ใน GeoJSON ต้องตรงกับสคีมาที่ต้องการ; หากไม่ตรง Aspose.GIS จะโยนข้อยกเว้น.  
- **ข้อผิดพลาดการเข้าถึงไฟล์:** ตรวจสอบว่าโฟลเดอร์ปลายทางมีสิทธิ์เขียนและไม่มีโปรเซสอื่นล็อกไฟล์ GDB.  

## คำถามที่พบบ่อย
### Aspose.GIS เข้ากันได้กับ .NET framework เวอร์ชันล่าสุดหรือไม่?
ใช่, Aspose.GIS เข้ากันได้กับเวอร์ชันล่าสุดของ .NET framework.  

### ฉันสามารถแปลงรูปแบบเชิงพื้นที่อื่น ๆ ด้วย Aspose.GIS ได้หรือไม่?
แน่นอน! Aspose.GIS รองรับรูปแบบเชิงพื้นที่หลากหลายสำหรับการจัดการข้อมูลที่หลากหลาย.  

### มีเวอร์ชันทดลองสำหรับ Aspose.GIS หรือไม่?
ใช่, คุณสามารถสำรวจฟังก์ชันของ Aspose.GIS ได้โดยดาวน์โหลดเวอร์ชันทดลองจาก [ที่นี่](https://releases.aspose.com/).  

### ฉันจะขอรับการสนับสนุนสำหรับคำถามที่เกี่ยวกับ Aspose.GIS อย่างไร?
ไปที่ [ฟอรั่ม](https://forum.aspose.com/c/gis/33) ของ Aspose.GIS เพื่อรับการสนับสนุนโดยเฉพาะ.  

### ฉันสามารถขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.GIS ได้หรือไม่?
ใช่, คุณสามารถรับไลเซนส์ชั่วคราวได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/).  

---

**อัปเดตล่าสุด:** 2026-01-10  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}