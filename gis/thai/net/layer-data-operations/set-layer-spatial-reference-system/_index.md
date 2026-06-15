---
date: 2026-06-15
description: เรียนรู้วิธีสร้าง vector layer และตั้งค่า layer spatial reference system
  ด้วย Aspose.GIS for .NET. เชี่ยวชาญการกำหนด spatial reference, การเพิ่ม point feature,
  และการดึง EPSG code.
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: ตั้งค่า Layer Spatial Reference System
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: สร้าง Vector Layer และตั้งค่า Layer Spatial Reference System
url: /th/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างเลเยอร์เวกเตอร์และตั้งค่าระบบอ้างอิงเชิงพื้นที่ของเลเยอร์

## บทนำ
ในภูมิทัศน์กว้างใหญ่ของระบบสารสนเทศภูมิศาสตร์ (GIS) **Aspose.GIS for .NET** โดดเด่นในฐานะไลบรารีที่แข็งแรงและมีประสิทธิภาพสูง รองรับรูปแบบเวกเตอร์และเรสเตอร์กว่า **70+** รูปแบบ และสามารถประมวลผลไฟล์ที่ใหญ่กว่า **10 GB** โดยไม่ต้องโหลดชุดข้อมูลทั้งหมดเข้าสู่หน่วยความจำ ในบทเรียนนี้คุณจะ **สร้างเลเยอร์เวกเตอร์**, กำหนดการอ้างอิงเชิงพื้นที่, **เพิ่มฟีเจอร์จุด**, และดึงรหัส EPSG — ทั้งหมดด้วยคำแนะนำที่ชัดเจนเป็นขั้นตอน ไม่ว่าคุณจะสร้างบริการแผนที่, สายงานแปลงข้อมูล, หรือเครื่องมือวิเคราะห์เชิงพื้นที่ การเชี่ยวชาญพื้นฐานเหล่านี้จะทำให้ระบบพิกัดของ shapefile ของคุณแม่นยำและกระบวนการทำงาน GIS ของคุณเชื่อถือได้

## คำตอบสั้น
- **“create vector layer” หมายถึงอะไร?** มันสร้าง GIS layer ใหม่ (เช่น Shapefile) ที่สามารถเก็บเรขาคณิตเช่น จุด, เส้น, หรือโพลิกอน  
- **รหัส EPSG ที่ใช้ในตัวอย่างคืออะไร?** EPSG 26918 (NAD83 / UTM zone 18N).  
- **ฉันสามารถเพิ่มฟีเจอร์จุดหลังจากสร้างเลเยอร์ได้หรือไม่?** ใช่—ใช้ `ConstructFeature()` และกำหนดเรขาคณิต `Point`.  
- **ฉันจะดึง CRS ของเลเยอร์ได้อย่างไร?** อ่าน `layer.SpatialReferenceSystem.EpsgCode` หรือ `.Name`.  
- **ฉันต้องการไลเซนส์สำหรับ Aspose.GIS หรือไม่?** สามารถทดลองใช้ได้ฟรี; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์.

## สร้างเลเยอร์เวกเตอร์คืออะไร?
การดำเนินการ **create vector layer** จะสร้างชุดข้อมูลเวกเตอร์ใหม่ (เช่น Shapefile) ที่สามารถเก็บฟีเจอร์เชิงเรขาคณิตและข้อมูลแอตทริบิวต์ได้ ใน Aspose.GIS การทำเช่นนี้ทำโดยการสร้างอ็อบเจ็กต์ `VectorLayer` พร้อมด้วยไดรเวอร์และระบบอ้างอิงเชิงพื้นที่

## ทำไมต้องตั้งค่าระบบพิกัดของเลเยอร์ (CRS) อย่างถูกต้อง?
การตั้งค่าระบบอ้างอิงพิกัด (CRS) ที่ถูกต้องทำให้แน่ใจว่าเรขาคณิตทุกชิ้นที่คุณเก็บสอดคล้องกับชุดข้อมูลเชิงพื้นที่อื่น ๆ ด้วย Aspose.GIS คุณสามารถกำหนด CRS ด้วยรหัส EPSG มาตรฐาน ซึ่งรับประกันความสามารถในการทำงานร่วมกับซอฟต์แวร์ GIS ทั่วโลก ตัวอย่างเช่น EPSG 26918 กำหนด NAD83 / UTM โซน 18N ซึ่งเป็นการฉายภาพที่ทั่วไปสำหรับข้อมูลในภาคตะวันออกของสหรัฐอเมริกา

## ข้อกำหนดเบื้องต้น
- ประสบการณ์การพัฒนา .NET (C# หรือ VB.NET).  
- Visual Studio 2022 หรือใหม่กว่า.  
- Aspose.GIS for .NET library – ดาวน์โหลดได้ **[ที่นี่](https://releases.aspose.com/gis/net/)**.  
- ความคุ้นเคยพื้นฐานกับระบบอ้างอิงเชิงพื้นที่ (CRS/EPSG).

## นำเข้าเนมสเปซ
`เนมสเปซ` `Aspose.Gis` ให้คลาส GIS หลัก, ส่วน `Aspose.Gis.Geometries` ให้ประเภทเรขาคณิตเช่น `Point`.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## คุณสร้างเลเยอร์เวกเตอร์ใน Aspose.GIS for .NET อย่างไร?
`VectorLayer` แทนชุดข้อมูลเวกเตอร์เช่น Shapefile และให้เมธอดสำหรับสร้าง, อ่าน, และแก้ไขฟีเจอร์  
`SpatialReferenceSystem` กำหนดระบบอ้างอิงพิกัดโดยใช้รหัส EPSG.  

โหลดโฟลเดอร์เป้าหมาย, กำหนด `SpatialReferenceSystem` ด้วยรหัส EPSG, และเรียก `VectorLayer.Create` พร้อมไดรเวอร์ Shapefile การเรียกเดียวนี้จะสร้างไฟล์ `.shp` ใหม่, เขียนไฟล์ `.shx` และ `.dbf` ที่เกี่ยวข้อง, และฝังเมตาดาต้า CRS พร้อมสำหรับการแทรกฟีเจอร์อย่างมีประสิทธิภาพ.

### ขั้นตอนที่ 1: ระบุไดเรกทอรีเอกสาร
เริ่มต้นโดยระบุพาธไปยังไดเรกทอรีเอกสารของคุณ ซึ่งจะเป็นตำแหน่งที่ไฟล์ข้อมูลเชิงพื้นที่ของคุณถูกจัดเก็บ.

```csharp
string dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 2: กำหนดการอ้างอิงเชิงพื้นที่และตั้งค่าระบบพิกัดของ Shapefile
`SpatialReferenceSystem` แทน CRS ของเลเยอร์โดยระบุด้วยรหัส EPSG.  

กำหนดพาธสำหรับ Shapefile, และ **กำหนดการอ้างอิงเชิงพื้นที่** ด้วยรหัส EPSG (26918 ในตัวอย่างนี้). ขั้นตอนนี้ **ตั้งค่าระบบพิกัดของ shapefile** สำหรับเลเยอร์.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## คุณสามารถเพิ่มฟีเจอร์จุดไปยังเลเยอร์เวกเตอร์ได้อย่างไร?
`Point` เป็นประเภทเรขาคณิตที่แสดงคู่พิกัด X/Y เดียว.  

สร้างฟีเจอร์ใหม่, กำหนดเรขาคณิต `Point` ด้วยพิกัด X/Y ที่ต้องการ, และเพิ่มฟีเจอร์ไปยัง `VectorLayer` ที่เปิดอยู่ การดำเนินการนี้จะเขียนเรขาคณิตลงในไฟล์ `.shp` และบันทึกแอตทริบิวต์ลงในไฟล์ `.dbf` ในหนึ่งธุรกรรม.

### ขั้นตอนที่ 3: สร้างเลเยอร์เวกเตอร์
`ConstructFeature` สร้างอ็อบเจ็กต์ฟีเจอร์ใหม่ที่สามารถเก็บเรขาคณิตและข้อมูลแอตทริบิวต์ได้.  

ตอนนี้ **สร้างเลเยอร์เวกเตอร์** ด้วยพาธ Shapefile ที่ระบุ, ประเภทไดรเวอร์ (Shapefile), และระบบอ้างอิงเชิงพื้นที่ที่คุณเพิ่งกำหนด.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### ขั้นตอนที่ 4: เพิ่มฟีเจอร์จุดไปยังเลเยอร์
สร้างฟีเจอร์ใหม่และ **เพิ่มฟีเจอร์จุด** โดยกำหนดเรขาคณิตเป็น `Point` ที่มีพิกัด 60, 24. จากนั้นเพิ่มฟีเจอร์ไปยังเลเยอร์เวกเตอร์.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### ขั้นตอนที่ 5: ดึงข้อมูลระบบอ้างอิงเชิงพื้นที่ (ดึงรหัส EPSG)
เปิด Vector Layer และดึงข้อมูลเกี่ยวกับระบบอ้างอิงเชิงพื้นที่ เช่น รหัส EPSG และชื่อที่อ่านได้โดยมนุษย์. นี้แสดงวิธี **ดึงรหัส EPSG** และ **ตั้งค่า CRS ของเลเยอร์**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|---------|
| **ไม่สามารถเปิดเลเยอร์** | ไดรเวอร์ไม่ถูกต้องหรือพาธไฟล์เสียหาย | ตรวจสอบ `Drivers.Shapefile` และให้แน่ใจว่า `path` ชี้ไปยังไฟล์ `.shp` ที่มีอยู่. |
| **แสดง CRS ไม่ถูกต้อง** | ใช้รหัส EPSG ผิด | ตรวจสอบรหัส EPSG อีกครั้งกับแหล่งข้อมูลที่เชื่อถือได้ (เช่น EPSG.io). |
| **ฟีเจอร์ไม่ถูกบันทึก** | ไม่ได้เรียก `layer.Add(feature)` ภายในบล็อก `using` | ตรวจสอบให้แน่ใจว่าเมธอด `Add` ถูกเรียกใช้ก่อนที่เลเยอร์จะถูกทำลาย. |

## คำถามที่พบบ่อย
**Q: ฉันจะเปลี่ยน CRS ของ Shapefile ที่มีอยู่ได้อย่างไร?**  
A: เปิดเลเยอร์, สร้าง `SpatialReferenceSystem` ใหม่ด้วยรหัส EPSG ที่ต้องการ, กำหนดให้กับ `layer.SpatialReferenceSystem`, แล้วบันทึกเลเยอร์.

**Q: ฉันสามารถเพิ่มประเภทเรขาคณิตอื่น (เช่น โพลิกอน) ด้วยวิธีเดียวกันได้หรือไม่?**  
A: ใช่—แทนที่ `new Point(x, y)` ด้วย `new Polygon(...)` หรือ `new LineString(...)` ตามต้องการ.

**Q: สามารถทำงานกับชุดข้อมูลขนาดใหญ่ได้อย่างมีประสิทธิภาพหรือไม่?**  
A: ใช้ API สตรีมมิ่ง (`VectorLayer.Create` กับ `FeatureCollection`) และทำลายเลเยอร์โดยเร็วเพื่อปล่อยทรัพยากร.

**Q: Aspose.GIS รองรับการแปลงพิกัดหรือไม่?**  
A: ใช่—ใช้ `Geometry.Transform(targetSrs)` เพื่อทำการรีโปรเจคเรขาคณิตระหว่างระบบอ้างอิงเชิงพื้นที่ต่าง ๆ.

**Q: .NET เวอร์ชันใดที่รองรับ?**  
A: Aspose.GIS ทำงานกับ .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

---

**อัปเดตล่าสุด:** 2026-06-15  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทเรียนที่เกี่ยวข้อง

- [สร้างเลเยอร์เวกเตอร์และตั้งค่าความทนทานต่อการเชิงเส้นโดยใช้ Aspose.GIS for .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [สร้างเลเยอร์เวกเตอร์ใน File GDB – บทเรียน Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [spatial reference wgs84 – เพิ่มเลเยอร์ไปยัง GDB โดยใช้ Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}