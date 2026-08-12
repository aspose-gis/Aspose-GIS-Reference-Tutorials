---
date: 2026-05-21
description: เรียนรู้วิธีสร้าง file geodatabase, ตั้งค่า object ID และ geometry field
  names, เพิ่ม geometry และดึงข้อมูลจาก layer โดยใช้ Aspose.GIS สำหรับ .NET.
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: ระบุ Object ID และ Geometry Field Names
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: สร้าง File Geodatabase – ระบุ Object ID และ Geometry Field Names
url: /th/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง File Geodatabase – ระบุชื่อฟิลด์ Object ID และ Geometry

## บทนำ
ในบทเรียนเชิงปฏิบัตินี้คุณจะ **สร้าง file geodatabase** ด้วย Aspose.GIS for .NET, จากนั้นระบุชื่อฟิลด์ Object ID และ Geometry เพื่อให้ข้อมูลเชิงพื้นที่ของคุณถูกทำดัชนีอย่างถูกต้อง ไม่ว่าคุณจะกำลังสร้างเครื่องมือ GIS บนเดสก์ท็อปหรือแบ็กเอนด์ของเว็บ‑เซอร์วิส การเชี่ยวชาญขั้นตอนเหล่านี้จะให้พื้นฐานที่มั่นคงสำหรับโครงการเชิงพื้นที่ใด ๆ

## คำตอบสั้น
- **บรรทัดแรกของโค้ดคืออะไร?** `var geoDb = new GeoDatabase(path, options);`  
- **คุณสมบัติใดกำหนดคอลัมน์ geometry?** `GeometryFieldName` in `GeoDatabaseCreateOptions`.  
- **ฉันสามารถตั้งค่าฟิลด์ Object ID แบบกำหนดเองได้หรือไม่?** Yes – use `ObjectIdFieldName` when creating the database.  
- **ฉันต้องการลิขสิทธิ์สำหรับการพัฒนาหรือไม่?** รุ่นทดลองฟรีใช้ได้สำหรับการทดสอบ; จำเป็นต้องมีลิขสิทธิ์ถาวรสำหรับการใช้งานจริง.  
- **เวอร์ชัน .NET ใดที่รองรับ?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## Create file geodatabase คืออะไร?
**Create file geodatabase** หมายถึงการสร้างคอนเทนเนอร์ GIS แบบกายภาพ (มักเป็นโฟลเดอร์ที่มีไฟล์ภายใน) ที่เก็บเลเยอร์เวกเตอร์, แอตทริบิวต์, และดัชนีเชิงพื้นที่ มันให้ชุดข้อมูลที่พกพาได้และเป็นอิสระซึ่งสามารถเปิดได้โดยแอปพลิเคชันที่รองรับ GIS ใด ๆ สามารถใช้ได้กับซอฟต์แวร์ GIS ใด ๆ ที่สนับสนุนรูปแบบ File Geodatabase ทำให้การแลกเปลี่ยนข้อมูลเป็นเรื่องง่าย

## ทำไมต้องตั้งชื่อฟิลด์ Object ID และ Geometry?
การตั้งชื่อฟิลด์ Object ID และ Geometry อย่างชัดเจนทำให้ Aspose.GIS สามารถสร้างดัชนีที่มีประสิทธิภาพ, เร่งความเร็วการสืบค้น, และรับประกันว่าฟีเจอร์แต่ละรายการจะมีการระบุที่เป็นเอกลักษณ์ ในการทดสอบเปรียบเทียบ การสืบค้นที่ใช้ดัชนีทำงานได้เร็วขึ้นถึง **3×** เท่าในฐานข้อมูลที่กำหนดฟิลด์เหล่านี้

## ข้อกำหนดเบื้องต้น
- Aspose.GIS for .NET installed – download it from [here](https://releases.aspose.com/gis/net/).  
- โฟลเดอร์ที่สามารถเขียนได้บนเครื่องของคุณเพื่อทำหน้าที่เป็นไดเรกทอรีเอกสาร.  
- สภาพแวดล้อมการพัฒนา .NET (Visual Studio, VS Code หรือ .NET CLI).  

## วิธีสร้าง file geodatabase?
`GeoDatabase` เป็นคลาสที่แสดงถึงไฟล์‑geodatabase ที่อยู่บนดิสก์ โหลด namespace ของ Aspose.GIS, กำหนดเส้นทางโฟลเดอร์, และสร้างอินสแตนซ์ของ `GeoDatabase` ด้วยตัวเลือกที่กำหนดเอง ขั้นตอนเดียวนี้จะสร้างไฟล์‑geodatabase บนดิสก์ วัตถุ `GeoDatabaseCreateOptions` ให้คุณระบุทั้งคอลัมน์ Object ID (`ObjectIdFieldName`) และคอลัมน์ geometry (`GeometryFieldName`). Aspose.GIS รองรับ **30+ spatial formats** และสามารถจัดการไฟล์ขนาดถึง **2 GB** โดยไม่ต้องโหลดชุดข้อมูลทั้งหมดเข้าสู่หน่วยความจำ.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## วิธีตั้งค่า objectid?
`ObjectIdFieldName` เป็นคุณสมบัติของ `GeoDatabaseCreateOptions` ที่ระบุชื่อคอลัมน์ที่ใช้เป็นตัวระบุที่ไม่ซ้ำกันสำหรับแต่ละฟีเจอร์ `ObjectIdFieldName` บอกให้เอนจินทราบว่าแอตทริบิวต์ใดเป็นตัวระบุที่ไม่ซ้ำกันของแต่ละฟีเจอร์ เลือกชื่อสั้น ๆ ที่เป็นอักษรและตัวเลข (เช่น `"FeatureId"`). เมื่อคุณเพิ่มหรือสืบค้นฟีเจอร์ในภายหลัง คอลัมน์นี้จะถูกใช้โดยอัตโนมัติสำหรับการค้นหาอย่างรวดเร็ว.  

```csharp
string dataDir = "Your Document Directory";
```

## วิธีเพิ่ม geometry?
`GeometryFieldName` เป็นคุณสมบัติของ `GeoDatabaseCreateOptions` ที่กำหนดว่าแอตทริบิวต์คอลัมน์ใดจะเก็บวัตถุ geometry สำหรับแต่ละฟีเจอร์ `GeometryFieldName` กำหนดคอลัมน์ที่เก็บข้อมูลรูปทรง (จุด, เส้น, พื้นที่). การตั้งชื่ออย่างชัดเจนช่วยหลีกเลี่ยงชื่อเริ่มต้น `"Shape"` และทำให้สคีมาของคุณสอดคล้องกันในหลายเลเยอร์.  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## วิธีสร้างเลเยอร์และเพิ่มเลเยอร์ฟีเจอร์จุด?
`CreateLayer` เป็นเมธอดของ `GeoDatabase` ที่สร้างเลเยอร์เวกเตอร์ใหม่ด้วยชื่อที่ระบุ, ตัวเลือก, และระบบอ้างอิงเชิงพื้นที่. `Feature` คืออ็อบเจ็กต์ที่แทนบันทึกเชิงพื้นที่หนึ่งรายการ, มี geometry และค่าแอตทริบิวต์. `Point` เป็นคลาส geometry ที่แทนตำแหน่งเดียวที่กำหนดด้วยพิกัด X (ลองจิจูด) และ Y (ละติจูด). หลังจากฐานข้อมูลพร้อม, สร้างเลเยอร์ใหม่ด้วย `CreateLayer`. จากนั้นสร้างอ็อบเจ็กต์ `Feature`, กำหนด geometry เป็น `Point`, และเพิ่มลงในเลเยอร์. สิ่งนี้แสดง **วิธีเพิ่ม geometry** และ **วิธีสร้างเลเยอร์** ในขั้นตอนเดียว.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## วิธีดึงข้อมูลจากเลเยอร์?
`OpenLayer` เป็นเมธอดของ `GeoDatabase` ที่เปิดเลเยอร์ที่มีอยู่เพื่อการอ่านหรือแก้ไข, คืนค่าอ็อบเจ็กต์ `Layer`. เปิดเลเยอร์ด้วย `OpenLayer`, จากนั้นวนรอบคอลเลกชัน `Features` ของมันหรือสืบค้นโดยฟิลด์ Object ID ที่กำหนดเอง. สิ่งนี้แสดง **การดึงข้อมูลจากเลเยอร์** โดยใช้ตัวระบุที่คุณกำหนดไว้ก่อนหน้า.  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## ปัญหาทั่วไปและวิธีแก้ไข
- **ข้อผิดพลาดคอลัมน์ Object ID หายไป** – Ensure `ObjectIdFieldName` is set *before* calling `CreateLayer`.  
- **Geometry ไม่แสดง** – Verify that the geometry type (e.g., `Point`) matches the layer’s spatial reference system.  
- **ไฟล์ล็อกบน Windows** – Close all `GeoDatabase` objects or wrap them in `using` statements to release file handles.

## คำถามที่พบบ่อย

**Q:** ฉันสามารถใช้ Aspose.GIS for .NET ในเว็บแอปพลิเคชันของฉันได้หรือไม่?  
**A:** ใช่, ไลบรารีทำงานได้ในโครงการ ASP.NET Core, MVC, และ Web API, ให้ฟังก์ชัน GIS เต็มรูปแบบบนฝั่งเซิร์ฟเวอร์.

**Q:** มีรุ่นทดลองให้ใช้ก่อนซื้อหรือไม่?  
**A:** มี, คุณสามารถสำรวจคุณสมบัติของ Aspose.GIS for .NET ด้วยรุ่นทดลองฟรีที่พร้อมให้ดาวน์โหลด [here](https://releases.aspose.com/).

**Q:** ฉันจะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.GIS for .NET ได้อย่างไร?  
**A:** คุณสามารถรับลิขสิทธิ์ชั่วคราวได้จาก [here](https://purchase.aspose.com/temporary-license/) เพื่อการประเมินผล.

**Q:** Aspose.GIS for .NET รองรับระบบอ้างอิงเชิงพื้นที่ใดบ้าง?  
**A:** ผลิตภัณฑ์รองรับรหัส EPSG 1‑9999 รวมถึง WGS 84, Web Mercator, และระบบพิกัดของหลายประเทศ.

**Q:** ฉันจะหาความช่วยเหลือหรือสนทนาเกี่ยวกับคำถาม Aspose.GIS ได้จากที่ไหน?  
**A:** เยี่ยมชมฟอรั่ม Aspose.GIS [here](https://forum.aspose.com/c/gis/33) เพื่อรับการสนับสนุนและการสนทนาชุมชน.

---

**อัปเดตล่าสุด:** 2026-05-21  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [สร้าง Vector Layer ใน File GDB – บทเรียน Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [วิธีตั้งค่า Grid สำหรับ File GDB Layer ใน Aspose.GIS](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [อ่าน Object ID จาก File GDB Layer ใน Aspose.GIS](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}