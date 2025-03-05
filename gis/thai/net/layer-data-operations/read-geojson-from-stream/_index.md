---
title: อ่าน GeoJSON จากสตรีมด้วย Aspose.GIS สำหรับ .NET
linktitle: อ่าน GeoJSON จากสตรีม
second_title: Aspose.GIS .NET API
description: เรียนรู้วิธีอ่าน GeoJSON จากสตรีมโดยใช้ Aspose.GIS สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อบูรณาการภูมิสารสนเทศเข้ากับแอปพลิเคชันของคุณได้อย่างราบรื่น
type: docs
weight: 14
url: /th/net/layer-data-operations/read-geojson-from-stream/
---
## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนเกี่ยวกับการใช้ Aspose.GIS สำหรับ .NET เพื่ออ่าน GeoJSON จากสตรีม Aspose.GIS เป็น API ที่ทรงพลังที่ให้ความสามารถเชิงพื้นที่แก่แอปพลิเคชัน .NET ช่วยให้คุณทำงานกับรูปแบบ GIS ต่างๆ ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการอ่านข้อมูล GeoJSON จากสตรีมโดยใช้ Aspose.GIS โดยแจกแจงแต่ละขั้นตอนเพื่อความชัดเจนและง่ายต่อการทำความเข้าใจ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. ความรู้พื้นฐานของ C#: คุณควรคุ้นเคยกับภาษาการเขียนโปรแกรม C# และไวยากรณ์ของมัน
2.  การติดตั้ง Aspose.GIS: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.GIS สำหรับ .NET หากไม่ใช่คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/gis/net/).
3. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาที่คุณต้องการ เช่น Visual Studio หรือ JetBrains Rider

## นำเข้าเนมสเปซ
ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็นในโค้ด C# ของคุณ:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## ขั้นตอนที่ 1: กำหนดข้อมูล GeoJSON
ขั้นแรก เราต้องกำหนดข้อมูล GeoJSON เป็นสตริงในโค้ด C# ของเรา ตัวอย่างเช่น:
```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```
## ขั้นตอนที่ 2: อ่าน GeoJSON จากสตรีม
ต่อไป เราจะอ่านข้อมูล GeoJSON จากสตรีมโดยใช้ Aspose.GIS:
```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // เอาท์พุต: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // เอาท์พุต: แมรี่
}
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีอ่านข้อมูล GeoJSON จากสตรีมโดยใช้ Aspose.GIS สำหรับ .NET ด้วยการทำตามขั้นตอนที่อธิบายไว้ข้างต้น คุณสามารถรวมความสามารถเชิงพื้นที่เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### Aspose.GIS เข้ากันได้กับรูปแบบ GIS อื่นหรือไม่
ใช่ Aspose.GIS รองรับรูปแบบ GIS ที่หลากหลาย เช่น GeoJSON, Shapefile, KML และอื่นๆ
### ฉันสามารถลองใช้ Aspose.GIS ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถดาวน์โหลด Aspose.GIS รุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารสำหรับ Aspose.GIS ได้ที่ไหน
 คุณสามารถค้นหาเอกสารสำหรับ Aspose.GIS[ที่นี่](https://reference.aspose.com/gis/net/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.GIS ได้อย่างไร
 คุณสามารถรับการสนับสนุนสำหรับ Aspose.GIS ได้จากฟอรัม Aspose[ที่นี่](https://forum.aspose.com/c/gis/33).
### ฉันจำเป็นต้องมีใบอนุญาตชั่วคราวเพื่อใช้ Aspose.GIS หรือไม่
 คุณสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS ได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).