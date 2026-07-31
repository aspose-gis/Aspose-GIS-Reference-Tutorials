---
date: 2026-04-24
description: เรียนรู้ **วิธีอ่าน geojson** จากสตรีมโดยใช้ Aspose.GIS สำหรับ .NET.
  คู่มือแบบขั้นตอนนี้จะแสดงให้คุณเห็น **วิธีโหลดสตรีม geojson**, แยกวิเคราะห์มัน,
  และดึงคุณสมบัติใน C#.
keywords:
- how to read geojson
- load geojson stream
- Aspose GIS GeoJSON
linktitle: อ่าน GeoJSON จากสตรีม
second_title: Aspose.GIS .NET API
title: วิธีอ่าน GeoJSON จากสตรีมด้วย Aspose.GIS สำหรับ .NET
url: /th/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีอ่าน GeoJSON จากสตรีมด้วย Aspose.GIS สำหรับ .NET

## บทนำ
หากคุณกำลังสงสัย **วิธีอ่าน geojson** ในแอปพลิเคชัน .NET, คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะพาคุณผ่านตัวอย่าง **C# GeoJSON** ครบชุดที่แสดงวิธีแปลงสตริง GeoJSON, **โหลด geojson สตรีม** ไปยัง memory stream, เปิดเลเยอร์ GeoJSON, และดึงคุณสมบัติ GeoJSON ด้วย Aspose.GIS. เมื่อเสร็จสิ้นคุณจะได้รูปแบบที่นำกลับมาใช้ได้ซึ่งสามารถใส่ลงในโปรเจกต์ใด ๆ ที่ต้องทำงานกับข้อมูลเชิงพื้นที่

## คำตอบสั้น ๆ
- **ควรใช้ไลบรารีอะไร?** Aspose.GIS สำหรับ .NET – รองรับรูปแบบ GIS หลายประเภทโดยไม่ต้องตั้งค่าเพิ่มเติม  
- **สามารถอ่าน GeoJSON โดยตรงจากสตรีมได้หรือไม่?** ได้ – ใช้ `VectorLayer.Open` พร้อม `AbstractPath.FromStream`  
- **ต้องมีลิขสิทธิ์สำหรับการพัฒนาหรือไม่?** รุ่นทดลองฟรีใช้ได้สำหรับการทดสอบ; ต้องมีลิขสิทธิ์เต็มสำหรับการใช้งานจริง  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+  
- **การดึงคุณสมบัติง่ายหรือไม่?** แน่นอน – เรียก `GetValue<T>(columnName)` บนฟีเจอร์

## “วิธีอ่าน geojson” คืออะไร?
การอ่าน GeoJSON หมายถึงการแยกวิเคราะห์รูปแบบ JSON‑based ที่อธิบายฟีเจอร์ทางภูมิศาสตร์ (จุด, เส้น, โพลิกอน) และแปลงฟีเจอร์เหล่านั้นเป็นอ็อบเจ็กต์ที่คุณสามารถสืบค้น, แก้ไข, หรือแสดงผลในแอปพลิเคชันของคุณได้

## ทำไมต้องใช้ Aspose.GIS เพื่อ **เปิดเลเยอร์ geojson**?
Aspose.GIS แยกรายละเอียดการแยกวิเคราะห์ระดับต่ำออกและให้ API ที่สอดคล้องสำหรับรูปแบบ GIS หลายประเภท มันทำให้คุณ **เปิดเลเยอร์ geojson** โดยตรงจากสตรีม, จัดการไฟล์ขนาดใหญ่อย่างมีประสิทธิภาพ, และเข้าถึงแอตทริบิวต์ของฟีเจอร์โดยไม่ต้องเขียนพาร์เซอร์ JSON เอง

## เมื่อใดที่คุณจะ **โหลด geojson สตรีม**?
- นำเข้าข้อมูลจากเว็บเซอร์วิสที่ส่งคืน GeoJSON ใน body ของการตอบกลับ  
- ประมวลผลไฟล์ GeoJSON ที่ผู้ใช้อัปโหลดโดยไม่ต้องบันทึกลงดิสก์ก่อน  
- ทำงานกับข้อมูลในหน่วยความจำที่สร้างขึ้นแบบไดนามิก (เช่น จากฐานข้อมูลหรือ API อื่น)

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงมือทำ, โปรดตรวจสอบว่าคุณมี:

1. **ความรู้พื้นฐานของ C#** – ควรคุ้นเคยกับไวยากรณ์ .NET และ IDE Visual Studio  
2. **Aspose.GIS ติดตั้งแล้ว** – ดาวน์โหลดไลบรารีจาก [here](https://releases.aspose.com/gis/net/)  
3. **สภาพแวดล้อมการพัฒนา** – Visual Studio, Visual Studio Code, หรือ JetBrains Rider จะทำงานได้ดี  

## นำเข้า Namespaces
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## ขั้นตอนที่ 1: **แปลงสตริง GeoJSON** – **ตัวอย่าง C# GeoJSON**
ก่อนอื่นเราจะสร้างสตริง JSON ที่แสดง `FeatureCollection` อย่างง่าย นี่คือส่วน **แปลงสตริง geojson** ของกระบวนการ

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## ขั้นตอนที่ 2: **โหลดสตรีม GeoJSON** และ **ดึงคุณสมบัติ geojson**
ต่อไปเราจะใส่สตริงลงใน `MemoryStream`, เปิดเป็นเลเยอร์ GIS, และสาธิตวิธีอ่านค่าคุณลักษณะ (ขั้นตอน **ดึงคุณสมบัติ geojson**)

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **เคล็ดลับ:** `VectorLayer.Open` จะตรวจจับรูปแบบ GeoJSON อัตโนมัติเมื่อคุณส่ง `Drivers.GeoJson`. คุณยังสามารถเปิดไฟล์โดยตรงโดยระบุพาธไฟล์แทนสตรีมได้อีกด้วย

## ปัญหาและวิธีแก้ทั่วไป
| ปัญหา | วิธีแก้ |
|-------|----------|
| **รูปแบบ JSON ไม่ถูกต้อง** | ตรวจสอบว่าสตริง GeoJSON ถูกต้องตามรูปแบบ; ใช้ตัวตรวจสอบ JSON |
| **ปัญหาเรื่องการเข้ารหัส** | ตรวจสอบให้สตรีมใช้ UTF‑8 (`Encoding.UTF8.GetBytes`) |
| **ไม่มีคุณสมบัติ** | ตรวจสอบว่าชื่อคุณสมบัตถูกต้อง (`"name"` ในตัวอย่าง) |
| **ข้อยกเว้นใบอนุญาต** | ใช้ใบอนุญาตทดลองสำหรับการทดสอบ; ใช้ใบอนุญาตถาวรสำหรับการผลิต |

## คำถามที่พบบ่อย
### Aspose.GIS รองรับรูปแบบ GIS อื่น ๆ หรือไม่?
ใช่, Aspose.GIS รองรับ GeoJSON, Shapefile, KML, GML และรูปแบบอื่น ๆ อีกมากมาย

### ฉันสามารถลองใช้ Aspose.GIS ก่อนซื้อได้หรือไม่?
ใช่, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีของ Aspose.GIS ได้จาก [here](https://releases.aspose.com/)

### ฉันสามารถหาเอกสารสำหรับ Aspose.GIS ได้ที่ไหน?
คุณสามารถหาเอกสารสำหรับ Aspose.GIS ได้ที่ [here](https://reference.aspose.com/gis/net/)

### ฉันจะขอรับการสนับสนุนสำหรับ Aspose.GIS ได้อย่างไร?
คุณสามารถรับการสนับสนุนสำหรับ Aspose.GIS ได้ที่ฟอรั่ม Aspose [here](https://forum.aspose.com/c/gis/33)

### ฉันต้องการใบอนุญาตชั่วคราวเพื่อใช้ Aspose.GIS หรือไม่?
คุณสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS ได้จาก [here](https://purchase.aspose.com/temporary-license/)

## สรุป
ในคู่มือนี้เราได้ครอบคลุม **วิธีอ่าน geojson** จาก memory stream ด้วย Aspose.GIS สำหรับ .NET, แสดงกระบวนการ **C# read geojson**, และสาธิตวิธี **ดึงคุณสมบัติ geojson** จากเลเยอร์ที่เปิดไว้ ด้วยขั้นตอนเหล่านี้คุณสามารถรวมการจัดการข้อมูลเชิงพื้นที่เข้าไปในแอปพลิเคชัน .NET ใด ๆ ได้อย่างราบรื่น

---

**อัปเดตล่าสุด:** 2026-04-24  
**ทดสอบด้วย:** Aspose.GIS 24.11 สำหรับ .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}