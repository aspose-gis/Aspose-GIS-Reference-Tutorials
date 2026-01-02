---
date: 2026-01-02
description: เรียนรู้วิธีเพิ่มฟีเจอร์จุดพร้อมตั้งชื่อฟิลด์และอ่านรหัสวัตถุโดยใช้ Aspose.GIS
  สำหรับ .NET คู่มือขั้นตอนต่อขั้นสำหรับนักพัฒนา
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
title: เพิ่มฟีเจอร์จุดและระบุชื่อฟิลด์ Object ID และ Geometry
url: /th/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มฟีเจอร์จุดและระบุชื่อฟิลด์ Object ID และ Geometry

## บทนำ
การเริ่มต้นเดินทางสู่โลกของระบบสารสนเทศภูมิศาสตร์ (GIS) ด้วย Aspose.GIS for .NET เปิดโอกาสใหม่ ๆ ให้กับนักพัฒนาและผู้สนใจอย่างกว้างขวาง ในบทแนะนำนี้, **คุณจะได้เรียนรู้วิธีเพิ่มฟีเจอร์จุด** พร้อมกับ **การตั้งชื่อฟิลด์** และ **การอ่านค่า object id**, ให้คุณควบคุมข้อมูลเชิงพื้นที่ของคุณได้อย่างเต็มที่.

## คำตอบสั้น
- **วัตถุประสงค์หลักของคู่มือนี้คืออะไร?** เพื่อแสดงวิธีเพิ่มฟีเจอร์จุดและกำหนดค่า Object ID และชื่อฟิลด์ Geometry.  
- **ใช้ไลบรารีใด?** Aspose.GIS for .NET.  
- **ต้องการไลเซนส์หรือไม่?** มีรุ่นทดลองฟรี; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานจริง.  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **สามารถอ่าน Object ID หลังการแทรกได้หรือไม่?** ได้ – บทแนะนำแสดงวิธีการอ่าน object id จากเลเยอร์.

## ข้อกำหนดเบื้องต้น
- Aspose.GIS for .NET: ดาวน์โหลดและติดตั้งไลบรารีจาก [here](https://releases.aspose.com/gis/net/).
- Document Directory: ตั้งค่าโฟลเดอร์สำหรับเอกสารของคุณเพื่อเก็บ geodatabases.
- .NET Environment: ตรวจสอบว่าคุณมีสภาพแวดล้อม .NET ที่ทำงานได้.

## นำเข้า Namespaces
เพื่อเริ่มต้น คุณต้องนำเข้า namespaces ที่จำเป็นเข้าไปในโปรเจกต์ของคุณ. Namespaces เหล่านี้ให้คลาสและเมธอดที่สำคัญสำหรับการทำงานกับ Aspose.GIS for .NET.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## ขั้นตอนที่ 1: เพิ่มฟีเจอร์จุดและระบุชื่อฟิลด์ Object ID และ Geometry
ในขั้นตอนนี้ คุณจะได้เรียนรู้วิธีตั้งค่า Object ID และชื่อฟิลด์ Geometry สำหรับข้อมูล GIS ของคุณ. สิ่งนี้สำคัญสำหรับการจัดการข้อมูลอย่างมีประสิทธิภาพและเพื่อให้สามารถ **อ่าน object id** ได้ในภายหลัง.

### ขั้นตอน 1.1: ตั้งค่า Document Directory
เริ่มต้นโดยกำหนดเส้นทางไปยังโฟลเดอร์เอกสารของคุณ:

```csharp
string dataDir = "Your Document Directory";
```

### ขั้นตอน 1.2: สร้าง GeoDatabase และกำหนด Options
สร้าง GeoDatabase พร้อมกับ **ตั้งชื่อฟิลด์** ที่ต้องการสำหรับ Object ID และ Geometry:

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

### ขั้นตอน 1.3: สร้างและเพิ่ม Layer
สร้าง layer ภายใน GeoDatabase และเพิ่มฟีเจอร์ที่เป็นรูปทรงจุด:

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

### ขั้นตอน 1.4: เปิดและดึงข้อมูลจาก Layer
เปิด layer และดึงฟีเจอร์ที่เพิ่งเพิ่มเข้ามา. นี้แสดงวิธี **อ่าน object id** จากชุดข้อมูล:

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## ทำไมต้องตั้งชื่อฟิลด์แบบกำหนดเอง?
การกำหนดชื่อฟิลด์ Object ID และ Geometry ตามต้องการให้ความยืดหยุ่นเมื่อผสานกับฐานข้อมูลที่มีอยู่หรือเมื่อปฏิบัติตามมาตรฐานการตั้งชื่อที่แอปพลิเคชันต่อไปต้องการ. นอกจากนี้ยังทำให้ข้อมูลมีความอธิบายตัวเองมากขึ้น, ช่วยลดความซับซ้อนในการบำรุงรักษาและการทำงานร่วมกัน.

## ข้อผิดพลาดทั่วไปและการแก้ไขปัญหา
- **Missing directory** – ตรวจสอบให้แน่ใจว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่มีอยู่; หากไม่เช่นนั้น `Dataset.Create` จะโยนข้อยกเว้น.
- **Field name conflicts** – หากฟิลด์ที่มีชื่อเดียวกันมีอยู่แล้วใน geodatabase การสร้างจะล้มเหลว. เลือกชื่อที่ไม่ซ้ำ.
- **Spatial reference mismatch** – ควรให้ระบบอ้างอิงเชิงพื้นที่ (เช่น WGS84) ตรงกับข้อมูลที่คุณต้องการเก็บ.

## สรุป
ยินดีด้วย! คุณได้เรียนรู้วิธี **เพิ่มฟีเจอร์จุด**, **ตั้งชื่อฟิลด์**, และ **อ่าน object id** ด้วย Aspose.GIS for .NET อย่างสำเร็จ. พื้นฐานนี้ทำให้คุณสามารถสร้างแอปพลิเคชัน GIS ที่แข็งแรงและจัดการข้อมูลเชิงพื้นที่ได้อย่างมั่นใจ.

## คำถามที่พบบ่อย
### Q: ฉันสามารถใช้ Aspose.GIS for .NET ในเว็บแอปพลิเคชันของฉันได้หรือไม่?
A: ใช่, Aspose.GIS for .NET เหมาะสำหรับทั้งแอปพลิเคชันเดสก์ท็อปและเว็บ, ให้ความสามารถด้านภูมิสารสนเทศที่หลากหลาย.

### Q: มีเวอร์ชันทดลองก่อนซื้อหรือไม่?
A: มี, คุณสามารถสำรวจฟีเจอร์ของ Aspose.GIS for .NET ด้วยรุ่นทดลองฟรีที่ให้ไว้ [here](https://releases.aspose.com/).

### Q: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับ Aspose.GIS for .NET ได้อย่างไร?
A: คุณสามารถรับไลเซนส์ชั่วคราวได้จาก [here](https://purchase.aspose.com/temporary-license/) เพื่อการประเมิน.

### Q: Aspose.GIS for .NET รองรับระบบอ้างอิงเชิงพื้นที่ใดบ้าง?
A: Aspose.GIS for .NET รองรับระบบอ้างอิงเชิงพื้นที่หลายประเภท, ให้ความยืดหยุ่นสำหรับชุดข้อมูลภูมิศาสตร์ที่แตกต่างกัน.

### Q: ฉันสามารถขอความช่วยเหลือหรือหารือเกี่ยวกับ Aspose.GIS ได้ที่ไหน?
A: เยี่ยมชมฟอรั่ม Aspose.GIS [here](https://forum.aspose.com/c/gis/33) เพื่อรับการสนับสนุนและการสนทนา.

## คำถามเพิ่มเติมที่พบบ่อย

**Q: ฉันสามารถเปลี่ยนฟิลด์ Object ID หลังจากสร้าง layer แล้วได้หรือไม่?**  
A: ไม่. ชื่อฟิลด์จะถูกกำหนดเมื่อสร้าง layer; คุณต้องสร้าง layer ใหม่ด้วยอ็อบเจ็กต์ `FileGdbOptions` ใหม่เพื่อเปลี่ยน.

**Q: ฉันจะดึงค่าแอตทริบิวต์อื่น ๆ นอกจาก Object ID ได้อย่างไร?**  
A: ใช้ `feature.GetValue<T>("FieldName")` โดยที่ `FieldName` คือชื่อของแอตทริบิวต์ที่คุณต้องการอ่าน.

**Q: สามารถเพิ่มหลายฟีเจอร์จุดในหนึ่งแบตช์ได้หรือไม่?**  
A: ได้. วนลูปข้อมูลของคุณ, สร้างฟีเจอร์สำหรับแต่ละจุด, ตั้งค่า geometry, และเรียก `layer.Add(feature)` ภายในบล็อก `using` เดียวกัน.

**Q: Aspose.GIS รองรับประเภท geometry อื่น ๆ หรือไม่?**  
A: แน่นอน. คุณสามารถทำงานกับ `LineString`, `Polygon`, `MultiPoint` และอื่น ๆ โดยการสร้างอ็อบเจ็กต์ geometry ที่เหมาะสม.

**Q: จะเกิดอะไรขึ้นหากฉันพยายามอ่าน Object ID ที่ไม่มีอยู่?**  
A: การเข้าถึงดัชนีที่อยู่นอกช่วง (เช่น `layer[10]` เมื่อมีเพียงฟีเจอร์เดียว) จะทำให้เกิด `IndexOutOfRangeException`. ควรตรวจสอบ `layer.Count` ก่อนเสมอ.

**อัปเดตล่าสุด:** 2026-01-02  
**ทดสอบด้วย:** Aspose.GIS for .NET 24.11  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}