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

## การแนะนำ
มีข้อสงสัย **how to read geojson** ในแอปพลิเคชัน .NET คุณมาถูกที่แล้วในบทแนะนำนี้เราจะพาคุณผ่าน **c# geojson example** ซึ่งแสดงวิธีการแปลงคำสั่ง GeoJSON, เปิดเว็บ GeoJSON จาก memory stream, และดึงคุณสมบัติ GeoJSON ด้วย Aspose.GIS. เมื่อเสร็จสิ้นแล้วคุณจะได้รูปแบบที่ต่อมากลับมาใช้ใหม่ได้เพื่อตรวจสอบข้อมูลใดๆ โดยคำนึงถึงข้อมูลเชิงพื้นที่

## คำตอบด่วน
- **ห้องสมุดที่นี่คืออะไร** Aspose.GIS สำหรับ .NET
- **ปกติอ่าน GeoJSON คุณสามารถสตรีมได้หรือไม่** ได้ – ใช้ `VectorLayer.Open` พร้อม `AbstractPath.FromStream`
- **ฉันต้องมีเซนส์สำหรับการพัฒนาหรือไม่?** ทดลองฟรีสามารถใช้ได้สำหรับการทดสอบ; อย่าลืมทานอาหารเซนส์จริง.
- ** รองรับ .NET รองรับอะไร?** .NET Framework4.5+, .NET Core3.1+, .NET5/6+
- **การดึงคุณสมบัติง่ายหรือไม่?** ง่าย – เรียก `GetValue<T>(columnName)` บนระบบปฏิบัติการ

## “วิธีการอ่าน geojson” คืออะไร?
หน้าที่ของ GeoJSON ในการตรวจสอบรูปแบบ JSON-based ที่อธิบายลักษณะเฉพาะ (จุด, การตรวจสอบ, การตรวจสอบ, การตรวจสอบ) ฟังก์ชั่นการใช้งานสามารถใช้ได้เป็นอ็อบเจกต์สำหรับสอบถาม, การประกาศ, หรือแอปพลิเคชันในแอปพลิเคชัน

## เหตุใดจึงต้องใช้ Aspose.GIS เพื่อ **เปิดเลเยอร์ geojson**
Aspose.GIS แยกรายละเอียดคำอธิบายสำหรับระดับต่ำออกข้อกำหนด API หลายรูปแบบ GIS มันทำให้คุณ **เปิดเลเยอร์ geojson** ได้ไม่ว่าจะสตรีม, จัดการไฟล์ขนาดใหญ่อย่างมีประสิทธิภาพ, และเข้าถึงความสามารถในการเขียนส่วนเซอร์ JSON เอง

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม, เป็นครั้งแรกที่คุณรู้จัก:

1. **ความรู้ในรูปแบบ C#** – ประกอบไปด้วย .NET และ IDE Visual Studio
2. ** ติดตั้ง Aspose.GIS** – ดาวน์โหลดไลบรารีจาก [ที่นี่](https://releases.aspose.com/gis/net/)
3. ** ในขณะที่การพัฒนา** – Visual Studio, Visual Studio Code หรือ JetBrains Rider จะเป็นอย่างไร

## นำเข้าเนมสเปซ
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## ขั้นตอนที่ 1: **แปลงสตริง GeoJSON** – **ตัวอย่าง GeoJSON ใน C#**
ก่อนอื่นเราจะสร้างสตริง JSON ที่เป็นตัวแทนของ `FeatureCollection` อย่างง่าย. นี่คือส่วน **convert geojson string** ของกระบวนการทำงาน.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## ขั้นตอนที่ 2: **เปิดเลเยอร์ GeoJSON** จากสตรีมและ **แยกคุณสมบัติ GeoJSON**
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

## ปัญหาและแนวทางแก้ไขทั่วไป
| ปัญหา | โซลูชั่น |
|-------|----------|
| **รูปแบบ JSON ไม่ถูกต้อง** | สำหรับคำสั่ง GeoJSON มีรูปแบบที่ถูกต้อง; ใช้ตัวตรวจสอบ JSON. |
| **ปัญหาการเข้ารหัส** | สตรีมใช้ UTF-8 (`Encoding.UTF8.GetBytes`) |
| **คุณสมบัติที่ขาดหายไป** | ฟังก์ชั่นชื่อคุณสมบัติในขณะที่สะกดถูกต้อง (`"ชื่อ"` ในตัวอย่าง) |
| **ข้อยกเว้นใบอนุญาต** | ใช้เซนส์ทดลองสำหรับการทดสอบ; ใช้ไลเซนส์ถาวรอย่างแท้จริง |

## คำถามที่พบบ่อย
### Aspose.GIS รองรับรูปแบบ GIS อื่นๆ อีกมากมาย?
เป็นไปได้, Aspose.GIS Geo กับ JSON, Shapefile, KML, GML, และรูปแบบอื่น ๆ อีกมากมายที่สามารถพบได้

### ในส่วนนี้ Aspose.GIS หลังจากนั้นซื้ออะไรบ้าง?
ได้ ดาวน์โหลดรุ่นทดลองฟรีของ Aspose.GIS จาก [ที่นี่](https://releases.aspose.com/)

### ที่นี่เอกสารของ Aspose.GIS จากที่ไหน?
รองรับเอกสารของ Aspose.GIS ได้ที่ [ที่นี่](https://reference.aspose.com/gis/net/)

### จะรับสำหรับ Aspose.GIS อย่างไร?
เรายินดีรับสำหรับ Aspose.GIS ได้ที่ไม่มีวันของ Aspose [ที่นี่](https://forum.aspose.com/c/gis/33)

### ครั้งหนึ่งเคยมีเซนส์ชั่วคราว Aspose.GIS อย่างเป็นทางการ?
โปรดขอไลเซนส์ชั่วคราวสำหรับ Aspose.GIS ได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/)

## บทสรุป
คู่มือนี้เราได้อธิบาย **how to read geojson** จาก memory stream ด้วย Aspose.GIS สำหรับ .NET, แสดงขั้นตอน **c# read geojson** อย่างครบถ้วน, และสาธิตวิธี **extract geojson properties** จากที่นี่อีกครั้ง ด้วยขั้นตอนนี้คุณจะต้องคำนึงถึงการจัดการข้อมูลเชิงพื้นที่สำหรับแอปพลิเคชัน .NET ใดๆ ก็ตาม

---

**อัปเดตล่าสุด:** 28-12-2025
**ทดสอบกับ:** Aspose.GIS 24.11 สำหรับ .NET
**ผู้เขียน:** สมมติ  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}