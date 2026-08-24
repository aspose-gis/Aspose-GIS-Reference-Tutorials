---
date: 2026-08-24
description: เรียนรู้วิธีสร้างเรขาคณิตเส้นโค้งและเพิ่มโค้งโดยใช้ Aspose.GIS สำหรับ
  .NET เพื่อให้การประมวลผลข้อมูลเชิงพื้นที่แม่นยำ
keywords:
- create curved line
- how to add curves
- create compound curve
- circular arc geometry
lastmod: 2026-08-24
linktitle: วิธีเพิ่มโค้ง – Compound Curve Geometry
og_description: เรียนรู้วิธีสร้างเรขาคณิตเส้นโค้งโดยใช้ Aspose.GIS สำหรับ .NET บทเรียนนี้แสดงขั้นตอนทีละขั้นตอนในการเพิ่มโค้งและสร้าง
  compound curves ภายในไม่กี่นาที
og_image_alt: Screenshot of Aspose.GIS creating a compound curved line geometry in
  a .NET project
og_title: วิธีสร้างเรขาคณิตเส้นโค้งด้วย Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to create curved line geometry and add curves using Aspose.GIS
    for .NET, enabling precise geospatial data processing.
  headline: How to create curved line geometry with Aspose.GIS
  type: TechArticle
- description: Learn how to create curved line geometry and add curves using Aspose.GIS
    for .NET, enabling precise geospatial data processing.
  name: How to create curved line geometry with Aspose.GIS
  steps:
  - name: define the output path
    text: First, specify where the resulting Shapefile will be saved. Replace the
      placeholder with a valid folder on your machine.
  - name: create a vector layer
    text: '`VectorLayer` represents a spatial layer that holds features and their
      geometries within a GIS dataset. The `using` block ensures the file is closed
      properly after writing.'
  - name: construct the compound curve feature
    text: The `CompoundCurve` class is Aspose.GIS's top‑level object for a geometry
      that consists of multiple connected curve parts. Here we instantiate an empty
      compound curve that will later receive individual components.
  - name: define component curves
    text: 'We prepare five pieces—two straight `LineString`s, two `CircularString`
      arcs, and a final `LineString`. `LineString` represents a simple straight line
      defined by an ordered list of points. `CircularString` is Aspose.GIS’s representation
      of a circular arc defined by three points (start, middle, end) '
  - name: add component curves to the compound curve
    text: Each component is appended in order, preserving continuity and orientation.
      The `Add` method automatically validates that the end point of one segment matches
      the start point of the next.
  - name: assign geometry to the feature
    text: Now the assembled `CompoundCurve` becomes the geometry of the feature we
      will store in the layer.
  - name: add the feature to the layer
    text: Finally, we write the feature into the Shapefile. When the `using` block
      ends, the file is closed and ready for use in any GIS application.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard,
      covering versions from 4.6 up to .NET 7.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. It reads and writes Shapefile, GeoJSON, KML, GML, and more
      than 30 additional formats.
    question: Does Aspose.GIS support reading and writing different geospatial file
      formats?
  - answer: Yes, the library can be used in desktop, web, and cloud services without
      any platform‑specific dependencies.
    question: Is Aspose.GIS suitable for both desktop and web applications?
  - answer: Yes, you can calculate distances, execute geometric operations, and run
      spatial queries directly on the geometries.
    question: Can I perform spatial analysis with Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) to ask
      questions and share ideas with other developers.
    question: Where can I get community help for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- GIS geometry
- Aspose.GIS
- .NET geospatial
- compound curve
title: วิธีสร้างเรขาคณิตเส้นโค้งด้วย Aspose.GIS
url: /th/net/geometry-creation/create-compound-curve-geometry/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างเรขาคณิตเส้นโค้งด้วย Aspose.GIS

## บทนำ
ในคู่มือนี้คุณจะได้เรียนรู้ **วิธีสร้างเรขาคณิตเส้นโค้ง** ด้วย Aspose.GIS สำหรับ .NET ไม่ว่าคุณจะสร้างแผนที่แบบโต้ตอบ, ทำการวิเคราะห์เชิงพื้นที่, หรือสร้างชุดข้อมูล GIS การเรียนรู้การเพิ่มโค้งจะทำให้คุณสามารถจำลองลักษณะของโลกจริง—เช่น ถนนที่โค้งงอหรือแม่น้ำที่ไหลตามโค้ง—ด้วยความแม่นยำสูง คู่มือนี้จะพาคุณผ่านทุกขั้นตอน ตั้งแต่การตั้งค่าโครงการจนถึงการส่งออกเรขาคณิตคอมพาวด์คอร์ฟที่สามารถนำกลับมาใช้ใหม่ได้

## คำตอบสั้น
- **เป้าหมายหลักคืออะไร?** สร้างเรขาคณิตคอมพาวด์คอร์ฟที่รวมเส้นตรงและโค้งวงกลม.  
- **ไลบรารีที่ใช้คืออะไร?** Aspose.GIS for .NET.  
- **ข้อกำหนดเบื้องต้น?** Visual Studio, ติดตั้ง Aspose.GIS, และโครงการ C# ที่ใช้ .NET 6 หรือใหม่กว่า.  
- **ระยะเวลาการทำงานโดยประมาณ?** ประมาณ 10‑15 นาทีสำหรับตัวอย่างที่ทำงานได้.  
- **รูปแบบผลลัพธ์ที่รองรับ?** Shapefile (โค้ดเดียวกันยังสามารถเขียน GeoJSON, KML, และรูปแบบอื่น ๆ ได้).

## คอมพาวด์คอร์ฟคืออะไร?
คอมพาวด์คอร์ฟคือเรขาคณิตเดียวที่ประกอบด้วยส่วนโค้งหลายส่วนที่เชื่อมต่อกัน—`LineString` เส้นตรงและโค้งวงกลม—รวมกันเป็นรูปทรงที่ซับซ้อนยิ่งขึ้น เหมาะเมื่อเส้นตรงเดียวไม่สามารถแทนเส้นทางได้อย่างแม่นยำ เช่น ทางหลวงที่มีโค้งเรียบหรือแม่น้ำที่ตามโค้งธรรมชาติ

## ทำไมต้องใช้ Aspose.GIS สำหรับการเพิ่มโค้ง?
Aspose.GIS มี **API เรขาคณิตที่ครอบคลุม** ที่รองรับ line strings, circular strings, และ compound curves โดยตรง ทำให้ไม่ต้องพึ่งพาไลบรารี GIS ภายนอก ไลบรารีนี้ **ข้ามแพลตฟอร์ม** ทำงานกับ .NET Framework 4.6+, .NET Core 2.0+, และ .NET 5/6/7+ มัน **ประมวลผลชุดข้อมูลเวกเตอร์ขนาดถึง 500 หน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ** ให้การทำงานที่เร็วและใช้หน่วยความจำอย่างมีประสิทธิภาพ การส่งออกทำได้ง่าย: คุณสามารถเขียนโดยตรงไปยัง Shapefile, GeoJSON, KML, GML, และรูปแบบอื่น ๆ มากกว่า 30 รูปแบบ

## ทำไมเรื่องนี้สำคัญ
การเพิ่มโค้งทำให้คุณสามารถจำลองลักษณะของโลกจริงได้อย่างแม่นยำยิ่งขึ้น ซึ่งช่วยปรับปรุงคุณภาพภาพในการแสดงแผนที่และเพิ่มความแม่นยำในการวิเคราะห์เชิงพื้นที่ เช่น การค้นหาใกล้เคียงหรือการกำหนดเส้นทางเครือข่าย การเชี่ยวชาญ **วิธีสร้างเรขาคณิตเส้นโค้ง** จึงเพิ่มความละเอียดของโซลูชัน .NET ที่ขับเคลื่อนด้วย GIS ใด ๆ

## กรณีการใช้งานทั่วไป
- **เครือข่ายการขนส่ง:** จำลองทางหลวง, ทางรถไฟ หรือเส้นทางจักรยานที่มีโค้งเรียบ.  
- **อุทกวิทยา:** แสดงเส้นทางแม่น้ำที่ตามโค้งธรรมชาติ.  
- **การวางผังเมือง:** วาดขอบเขตที่ดินที่มีส่วนโค้ง.  
- **สัญลักษณ์กำหนดเอง:** สร้างรูปแบบประดับหรือสเก็ตช์สำหรับคำอธิบายแผนที่.

## ข้อกำหนดเบื้องต้น
- Visual Studio (รุ่นล่าสุดใดก็ได้).  
- Aspose.GIS for .NET ดาวน์โหลดจาก [หน้าดาวน์โหลด](https://releases.aspose.com/gis/net/).  
- โครงการ C# ที่ใช้ .NET 6 (หรือเวอร์ชันที่รองรับอื่น ๆ).

## นำเข้า namespace
คำสั่ง `using` จะนำประเภทของ Aspose.GIS ที่จำเป็นเข้าสู่ขอบเขต

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## คู่มือขั้นตอนสร้างเรขาคณิตคอมพาวด์คอร์ฟ

### ขั้นตอนที่ 1: กำหนดเส้นทางการบันทึกผลลัพธ์
แรกสุด ระบุที่ที่ไฟล์ Shapefile ที่สร้างขึ้นจะถูกบันทึก แทนที่ตัวแปรตำแหน่งที่เก็บด้วยโฟลเดอร์ที่ใช้งานได้บนเครื่องของคุณ.

```csharp
string path = "Your Document Directory" + "CreateCompoundCurve_out.shp";
```

### ขั้นตอนที่ 2: สร้าง vector layer
`VectorLayer` แทนชั้นข้อมูลเชิงพื้นที่ที่เก็บฟีเจอร์และเรขาคณิตของพวกมันในชุดข้อมูล GIS. บล็อก `using` ทำให้ไฟล์ถูกปิดอย่างถูกต้องหลังจากการเขียน.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block for creating the compound curve geometry will be inserted here.
}
```

### ขั้นตอนที่ 3: สร้างฟีเจอร์คอมพาวด์คอร์ฟ
คลาส `CompoundCurve` เป็นอ็อบเจ็กต์ระดับบนของ Aspose.GIS สำหรับเรขาคณิตที่ประกอบด้วยส่วนโค้งหลายส่วนที่เชื่อมต่อกัน ที่นี่เราสร้างอินสแตนซ์ของคอมพาวด์คอร์ฟว่างเปล่าที่จะรับส่วนประกอบต่อมา.

```csharp
var feature = layer.ConstructFeature();
var compoundCurve = new CompoundCurve();
```

### ขั้นตอนที่ 4: กำหนดส่วนโค้งประกอบ
เราจัดเตรียมส่วนประกอบห้าชิ้น—`LineString` เส้นตรงสองอัน, `CircularString` โค้งวงกลมสองอัน, และ `LineString` สุดท้ายหนึ่งอัน. `LineString` แทนเส้นตรงง่าย ๆ ที่กำหนดด้วยรายการจุดตามลำดับ. `CircularString` คือการแทนโค้งวงกลมของ Aspose.GIS ที่กำหนดด้วยจุดสามจุด (จุดเริ่ม, จุดกลาง, จุดสิ้นสุด) ที่อยู่บนวงกลมเดียวกัน.

```csharp
var bottom = (ILineString)Geometry.FromText("LineString (0 0, 3 0)");
var firstArc = (ICircularString)Geometry.FromText("CircularString (3 0, 4 1, 3 2)");
var middle = (ILineString)Geometry.FromText("LineString (3 2, 1 2)");
var secondArc = (ICircularString)Geometry.FromText("CircularString (1 2, 0 3, 1 4)");
var top = (ILineString)Geometry.FromText("LineString (1 4, 4 4)");
```

### ขั้นตอนที่ 5: เพิ่มส่วนโค้งประกอบลงในคอมพาวด์คอร์ฟ
แต่ละส่วนจะถูกต่อเติมตามลำดับ เพื่อรักษาการต่อเนื่องและทิศทาง วิธี `Add` จะตรวจสอบโดยอัตโนมัติว่าจุดสิ้นสุดของส่วนหนึ่งตรงกับจุดเริ่มของส่วนถัดไป.

```csharp
compoundCurve.AddCurve(bottom);
compoundCurve.AddCurve(firstArc);
compoundCurve.AddCurve(middle);
compoundCurve.AddCurve(secondArc);
compoundCurve.AddCurve(top);
```

### ขั้นตอนที่ 6: กำหนดเรขาคณิตให้กับฟีเจอร์
ตอนนี้ `CompoundCurve` ที่ประกอบเสร็จแล้วจะกลายเป็นเรขาคณิตของฟีเจอร์ที่เราจะเก็บในเลเยอร์.

```csharp
feature.Geometry = compoundCurve;
```

### ขั้นตอนที่ 7: เพิ่มฟีเจอร์ลงในเลเยอร์
สุดท้าย เราเขียนฟีเจอร์ลงใน Shapefile. เมื่อบล็อก `using` สิ้นสุด ไฟล์จะถูกปิดและพร้อมใช้งานในแอปพลิเคชัน GIS ใด ๆ.

```csharp
layer.Add(feature);
```

## ปัญหาทั่วไป & เคล็ดลับ
- **ลำดับพิกัด:** Aspose.GIS คาดว่าพิกัดอยู่ในลำดับ `X Y` (ลองจิจูด, ละติจูด). การสลับลำดับจะทำให้เรขาคณิตกลับด้าน.  
- **ไวยากรณ์ CircularString:** จุดกลางต้องอยู่บนโค้งที่ต้องการ มิฉะนั้นโค้งจะกลายเป็นเส้นตรง.  
- **การเขียนทับไฟล์:** `VectorLayer.Create` จะเขียนทับ Shapefile ที่มีอยู่โดยไม่มีคำเตือน—ใช้ชื่อไฟล์ที่ไม่ซ้ำกันระหว่างการพัฒนา.  
- **ประสิทธิภาพ:** สำหรับชุดข้อมูลขนาดใหญ่ ควรเพิ่มฟีเจอร์เป็นชุดแทนการแทรกทีละฟีเจอร์ภายในบล็อก `using`.  
- **เคล็ดลับ:** ใช้อินสแตนซ์ `CompoundCurve` เดียวกันเมื่อต้องสร้างฟีเจอร์ที่คล้ายกันหลายรายการ; เรียก `compoundCurve.Clear()` ก่อนเติมข้อมูลใหม่เพื่อ ลดการจัดสรรหน่วยความจำ.

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.GIS สำหรับ .NET กับเฟรมเวิร์ก .NET อื่น ๆ ได้หรือไม่?**  
A: ใช่, Aspose.GIS ทำงานกับ .NET Framework, .NET Core, และ .NET Standard, รองรับเวอร์ชันตั้งแต่ 4.6 ถึง .NET 7.

**Q: Aspose.GIS รองรับการอ่านและเขียนรูปแบบไฟล์เชิงพื้นที่ต่าง ๆ หรือไม่?**  
A: แน่นอน. มันสามารถอ่านและเขียน Shapefile, GeoJSON, KML, GML, และรูปแบบเพิ่มเติมกว่า 30 รูปแบบอื่น ๆ.

**Q: Aspose.GIS เหมาะสำหรับแอปพลิเคชันเดสก์ท็อปและเว็บหรือไม่?**  
A: ใช่, ไลบรารีนี้สามารถใช้ได้ในเดสก์ท็อป, เว็บ, และบริการคลาวด์โดยไม่มีการพึ่งพาแพลตฟอร์มเฉพาะ.

**Q: ฉันสามารถทำการวิเคราะห์เชิงพื้นที่ด้วย Aspose.GIS สำหรับ .NET ได้หรือไม่?**  
A: ได้, คุณสามารถคำนวณระยะทาง, ทำการดำเนินการเรขาคณิต, และรันการค้นหาเชิงพื้นที่โดยตรงบนเรขาคณิต.

**Q: ฉันจะหาแหล่งช่วยเหลือจากชุมชนสำหรับ Aspose.GIS ได้จากที่ไหน?**  
A: เยี่ยมชม [ฟอรั่ม Aspose.GIS](https://forum.aspose.com/c/gis/33) เพื่อถามคำถามและแบ่งปันแนวคิดกับนักพัฒนาคนอื่น ๆ.

---

**อัปเดตล่าสุด:** 2026-08-24  
**ทดสอบด้วย:** Aspose.GIS for .NET (latest stable release)  
**ผู้เขียน:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [สร้าง Vector Layer & Circular String ใน Aspose.GIS สำหรับ .NET](/gis/net/geometry-creation/create-circular-string-geometry/)
- [สร้าง vector layer และ curve polygon ด้วย Aspose.GIS](/gis/net/geometry-creation/create-curve-polygon-geometry/)
- [แปลง WKT เป็น Geometry: MultiCurve ด้วย Aspose.GIS .NET](/gis/net/geometry-creation/create-multicurve-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}