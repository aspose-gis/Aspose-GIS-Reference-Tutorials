---
date: 2025-12-28
description: เรียนรู้วิธีอ่าน GeoJSON จากสตรีมโดยใช้ Aspose.GIS สำหรับ .NET คู่มือการอ่าน
  GeoJSON ด้วย C# นี้ให้ตัวอย่างขั้นตอนต่อขั้นตอนสำหรับการรวมข้อมูลเชิงพื้นที่
linktitle: Read GeoJSON from Stream
second_title: Aspose.GIS .NET API
title: วิธีอ่าน GeoJSON จากสตรีมด้วย Aspose.GIS สำหรับ .NET
url: /th/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีอ่าน GeoJSON จาก Stream ด้วย Aspose.GIS สำหรับ .NET

## Introduction
หากคุณกำลังสงสัย **how to read geojson** ในแอปพลิเคชัน .NET คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะพาคุณผ่าน **c# geojson example** ที่สมบูรณ์ซึ่งแสดงวิธีแปลงสตริง GeoJSON, เปิดเลเยอร์ GeoJSON จาก memory stream, และดึงคุณสมบัติ GeoJSON ด้วย Aspose.GIS. เมื่อเสร็จคุณจะได้รูปแบบที่สามารถนำกลับมาใช้ใหม่ได้ในโครงการใด ๆ ที่ต้องทำงานกับข้อมูลเชิงพื้นที่

## Quick Answers
- **ห้องสมุดที่ควรใช้คืออะไร?** Aspose.GIS for .NET  
- **ฉันสามารถอ่าน GeoJSON โดยตรงจาก stream ได้หรือไม่?** ได้ – ใช้ `VectorLayer.Open` พร้อม `AbstractPath.FromStream`.  
- **ฉันต้องมีไลเซนส์สำหรับการพัฒนาหรือไม่?** ทดลองฟรีใช้ได้สำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **การดึงคุณสมบัติง่ายหรือไม่?** ง่าย – เรียก `GetValue<T>(columnName)` บนฟีเจอร์.

## What is “how to read geojson”?
การอ่าน GeoJSON หมายถึงการแยกวิเคราะห์รูปแบบ JSON‑based ที่อธิบายลักษณะทางภูมิศาสตร์ (จุด, เส้น, พอลิกอน) และทำให้ฟีเจอร์เหล่านั้นพร้อมใช้งานเป็นอ็อบเจกต์ที่คุณสามารถสอบถาม, แก้ไข, หรือแสดงผลในแอปพลิเคชันของคุณได้

## Why use Aspose.GIS to **open geojson layer**?
Aspose.GIS แยกรายละเอียดการแยกวิเคราะห์ระดับต่ำออกและให้ API ที่สอดคล้องกันสำหรับหลายรูปแบบ GIS. มันทำให้คุณ **open geojson layer** ได้โดยตรงจาก stream, จัดการไฟล์ขนาดใหญ่อย่างมีประสิทธิภาพ, และเข้าถึงแอตทริบิวต์ของฟีเจอร์โดยไม่ต้องเขียนพาร์เซอร์ JSON เอง.

## Prerequisites
ก่อนที่เราจะเริ่ม, โปรดตรวจสอบว่าคุณมี:

1. **ความรู้พื้นฐานของ C#** – คุณควรคุ้นเคยกับไวยากรณ์ .NET และ IDE Visual Studio.  
2. **ติดตั้ง Aspose.GIS** – ดาวน์โหลดไลบรารีจาก [here](https://releases.aspose.com/gis/net/).  
3. **สภาพแวดล้อมการพัฒนา** – Visual Studio, Visual Studio Code, หรือ JetBrains Rider จะทำงานได้ดี.

## Import Namespaces
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Step 1: **Convert GeoJSON string** – a **c# geojson example**
ก่อนอื่นเราจะสร้างสตริง JSON ที่เป็นตัวแทนของ `FeatureCollection` อย่างง่าย. นี่คือส่วน **convert geojson string** ของกระบวนการทำงาน.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Step 2: **Open GeoJSON layer** from stream and **extract geojson properties**
ต่อไปเราจะใส่สตริงลงใน `MemoryStream`, เปิดเป็นเลเยอร์ GIS, และสาธิตวิธีอ่านค่าคุณลักษณะ (ขั้นตอน **extract geojson properties**).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Pro tip:** `VectorLayer.Open` จะตรวจจับรูปแบบ GeoJSON อัตโนมัติเมื่อคุณส่ง `Drivers.GeoJson`. คุณยังสามารถเปิดไฟล์โดยตรงโดยระบุพาธไฟล์แทนการใช้ stream ได้อีกด้วย.

## Common Issues & Solutions
| Issue | Solution |
|-------|----------|
| **Invalid JSON format** | ตรวจสอบว่าสตริง GeoJSON มีรูปแบบที่ถูกต้อง; ใช้ตัวตรวจสอบ JSON. |
| **Encoding problems** | ตรวจสอบว่า stream ใช้ UTF‑8 (`Encoding.UTF8.GetBytes`). |
| **Missing properties** | ตรวจสอบว่าชื่อคุณสมบัติมีการสะกดถูกต้อง (`"name"` ในตัวอย่าง). |
| **License exception** | ใช้ไลเซนส์ทดลองสำหรับการทดสอบ; ใช้ไลเซนส์ถาวรสำหรับการใช้งานจริง. |

## Frequently Asked Questions
### Aspose.GIS รองรับรูปแบบ GIS อื่น ๆ หรือไม่?
ใช่, Aspose.GIS รองรับ GeoJSON, Shapefile, KML, GML, และรูปแบบอื่น ๆ อีกหลายประเภท.

### ฉันสามารถลองใช้ Aspose.GIS ก่อนซื้อได้หรือไม่?
ได้, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีของ Aspose.GIS ได้จาก [here](https://releases.aspose.com/).

### จะหาเอกสารของ Aspose.GIS ได้จากที่ไหน?
คุณสามารถค้นหาเอกสารของ Aspose.GIS ได้ที่ [here](https://reference.aspose.com/gis/net/).

### จะรับการสนับสนุนสำหรับ Aspose.GIS อย่างไร?
คุณสามารถรับการสนับสนุนสำหรับ Aspose.GIS ได้ที่ฟอรัมของ Aspose [here](https://forum.aspose.com/c/gis/33).

### จำเป็นต้องมีไลเซนส์ชั่วคราวเพื่อใช้ Aspose.GIS หรือไม่?
คุณสามารถขอไลเซนส์ชั่วคราวสำหรับ Aspose.GIS ได้จาก [here](https://purchase.aspose.com/temporary-license/).

## Conclusion
ในคู่มือนี้เราได้อธิบาย **how to read geojson** จาก memory stream ด้วย Aspose.GIS สำหรับ .NET, แสดงขั้นตอน **c# read geojson** อย่างครบถ้วน, และสาธิตวิธี **extract geojson properties** จากเลเยอร์ที่เปิด. ด้วยขั้นตอนเหล่านี้คุณสามารถผสานการจัดการข้อมูลเชิงพื้นที่เข้ากับแอปพลิเคชัน .NET ใด ๆ ได้อย่างราบรื่น.

---

**Last Updated:** 2025-12-28  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}