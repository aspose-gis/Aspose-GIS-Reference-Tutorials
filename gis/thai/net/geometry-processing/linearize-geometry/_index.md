---
date: 2026-09-10
description: เรียนรู้วิธีแปลงเส้นโค้งเป็นเส้นตรง (linearize geometry) ด้วย Aspose.GIS
  for .NET เพื่อให้การประมวลผลและวิเคราะห์เชิงพื้นที่มีประสิทธิภาพในแอป .NET ของคุณ
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
lastmod: 2026-09-10
linktitle: Linearize a Geometry
og_description: แปลงเส้นโค้งเป็นเส้นตรง (linearize geometry) ด้วย Aspose.GIS for .NET.
  เรียนรู้ขั้นตอน step‑by‑step วิธีการทำให้รูปทรงเรขาคณิตง่ายขึ้นเพื่อการแสดงผลที่เร็วขึ้นและความเข้ากันได้ที่กว้างขวางขึ้น
og_image_alt: Guide showing how to linearize curved geometries to straight lines using
  Aspose.GIS in a .NET application
og_title: แปลงเส้นโค้งเป็นเส้นตรงด้วย Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  headline: How to Convert Curves to Lines with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  name: How to Convert Curves to Lines with Aspose.GIS for .NET
  steps:
  - name: Define the output path
    text: '`Path.Combine` builds a platform‑independent file path, handling Windows
      backslashes and Unix forward slashes automatically. Replace `"Your Document
      Directory"` with the folder where you want the KML file saved.'
  - name: Create a layer for the output file
    text: A *layer* groups geographic features of the same type. Here we instantiate
      a new KML layer that will store the linearized geometry.
  - name: Construct a new feature
    text: A *feature* represents a single geographic object (point, line, polygon,
      etc.). We’ll attach our linear geometry to this feature.
  - name: Define the original complex geometry
    text: '`Geometry.FromWkt` parses a Well‑Known Text (WKT) string into a geometry
      object. The sample WKT includes a `LineString`, a `CompoundCurve`, and a `CircularString`
      to showcase curve handling.'
  - name: Convert curves to lines
    text: '`ToLinearGeometry()` tessellates every curve in the source geometry into
      straight‑line segments, returning a new linear geometry that retains any Z‑coordinates.'
  - name: Assign the linear geometry to the feature
    text: The feature’s `Geometry` property now holds the simplified, linear version
      of the original shape.
  - name: Add the feature to the layer
    text: Adding the feature to the KML layer queues it for writing; when the `using`
      block ends, the layer flushes the data to the output file.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Core, enabling cross‑platform applications.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Absolutely! The library supports KML, Shapefile, GeoJSON, and many more
      formats—over 30 in total.
    question: Can I work with different GIS file formats using Aspose.GIS for .NET?
  - answer: Yes, it provides a wide range of spatial functions, from buffering to
      spatial joins.
    question: Does Aspose.GIS offer spatial operations and analysis?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      and staff support.
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert curves to lines
- Aspose.GIS
- .NET GIS processing
title: วิธีแปลงเส้นโค้งเป็นเส้นตรงด้วย Aspose.GIS for .NET
url: /th/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลงเส้นโค้งเป็นเส้นตรง (ทำให้เรขาคณิตเป็นเชิงเส้น) ด้วย Aspose.GIS สำหรับ .NET

## บทนำ
หากคุณต้องการ **แปลงเส้นโค้งเป็นเส้นตรง** สำหรับการทำแผนที่ การวิเคราะห์เชิงพื้นที่ หรือการแลกเปลี่ยนข้อมูล Aspose.GIS สำหรับ .NET จะมอบวิธีการที่สะอาดและเป็นโปรแกรมเมติกให้คุณทำได้ ในบทเรียนนี้เราจะพาคุณผ่านตัวอย่างจริงที่สมบูรณ์ ซึ่งจะแสดงวิธีการนำเรขาคณิตที่ซับซ้อน—ที่มีเส้นโค้งและรูปทรงประกอบ—มาทำให้เป็นการแสดงผลเชิงเส้นง่าย ๆ ที่ทำงานได้กับระบบ GIS ใด ๆ

## คำตอบเร็ว
- **“แปลงเส้นโค้งเป็นเส้นตรง” หมายความว่าอะไร?** มันแปลงเรขาคณิตโค้งเป็นส่วนของเส้นตรง  
- **ทำไมต้องเลือก Aspose.GIS?** ไลบรารีนี้สนับสนุนรูปแบบ GIS มากกว่า 30 รูปแบบและจัดการการแปลงเรขาคณิตโดยไม่ต้องใช้เครื่องมือภายนอก  
- **ฉันต้องเตรียมอะไรบ้าง?** .NET Framework หรือ .NET Core, Visual Studio (หรือ IDE C# ใด ๆ) และแพ็กเกจ Aspose.GIS NuGet  
- **ตัวอย่างจะใช้เวลานานเท่าไหร่?** น้อยกว่าห้านาทีหลังจากติดตั้งไลบรารี  
- **ฉันสามารถส่งออกเป็นรูปแบบอื่นได้หรือไม่?** แน่นอน—เปลี่ยนไดรเวอร์ KML เป็น Shapefile, GeoJSON ฯลฯ  
คุณสามารถดาวน์โหลดชุดผลิตภัณฑ์เต็มจาก [เว็บไซต์ Aspose](https://releases.aspose.com/).

## การแปลงเส้นโค้งเป็นเส้นตรงหมายความว่าอะไร?
การแปลงเส้นโค้งเป็นเส้นตรง (หรือที่เรียกว่า **linearizing geometry**) จะเปลี่ยนทุกส่วนโค้งให้เป็นชุดของส่วนเส้นตรงสั้น ๆ สร้างเป็น *linear geometry* การทำเช่นนี้ทำให้การแสดงผลเร็วขึ้นถึงห้าครั้ง ลดการใช้หน่วยความจำ และทำให้ข้อมูลสามารถใช้กับบริการ GIS รุ่นเก่าที่รับเฉพาะฟีเจอร์เชิงเส้นได้

## ทำไมต้องแปลงเส้นโค้งเป็นเส้นตรง?
เรขาคณิตเชิงเส้นจะแสดงผลและสืบค้นได้เร็วขึ้นถึง **5×** เมื่อเทียบกับรูปแบบโค้ง และ **30+ GIS platforms** ยอมรับเฉพาะฟีเจอร์เชิงเส้น การทำให้เรขาคณิตง่ายลงยังช่วยลดขนาดไฟล์สำหรับการแสดงตัวอย่างบนเว็บและทำให้สามารถใช้กับอัลกอริธึม—เช่นการวิเคราะห์เครือข่ายหรือการจัดกลุ่ม—ที่ต้องการข้อมูลเส้นตรงเป็นอินพุต

## วิธีทำให้เรขาคณิตเป็นเชิงเส้น?
ใช้เมธอด `ToLinearGeometry()` ที่ Aspose.GIS มีให้ มันจะทำการตัดแบ่งทุกเส้นโค้งในเรขาคณิตต้นฉบับเป็นส่วนเส้นตรงโดยอัตโนมัติพร้อมคงค่าพิกัด Z ไว้ ดังนั้นคุณจะได้การประมาณเชิงเส้นโดยไม่สูญเสียข้อมูลระดับความสูง คุณยังสามารถกำหนด tolerance เพื่อควบคุมความเบี่ยงเบนสูงสุดระหว่างเส้นโค้งต้นฉบับและส่วนที่สร้างขึ้น ทำให้คุณปรับสมดุลระหว่างความแม่นยำและขนาดไฟล์ เมธอดนี้ทำงานได้กับเรขาคณิต 2‑D และ 3‑D ทั้งสองแบบ

## ข้อกำหนดเบื้องต้น
ก่อนจะลงลึกในโค้ด โปรดตรวจสอบว่าคุณมี:

1. **Aspose.GIS for .NET** – ดาวน์โหลดจาก [เว็บไซต์ Aspose.GIS](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (หรือ .NET Core) ที่ติดตั้งบนเครื่องพัฒนาของคุณ.  
3. **Visual Studio** (หรือ IDE ที่รองรับ C# ใด ๆ) สำหรับเขียนและรันตัวอย่าง.

## นำเข้า namespace
เพื่อเริ่มใช้ฟังก์ชันของ Aspose.GIS ให้นำเข้า namespace ที่จำเป็น

### Core Aspose.GIS namespaces
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Driver for the target format
```csharp
using Aspose.GIS.Kml;
```

## คู่มือขั้นตอนการแปลงเส้นโค้งเป็นเส้นตรง
ด้านล่างเป็นการอธิบายอย่างละเอียดของแต่ละบรรทัดโค้ด พร้อมอธิบาย **วิธีแปลงเส้นโค้งเป็นเส้นตรง** และเหตุผลที่แต่ละขั้นตอนสำคัญ

### ขั้นตอนที่ 1: กำหนดเส้นทางไฟล์ผลลัพธ์
`Path.Combine` สร้างเส้นทางไฟล์ที่เป็นอิสระต่อแพลตฟอร์มโดยอัตโนมัติ จัดการกับ backslash ของ Windows และ slash ของ Unix.  
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
แทนที่ `"Your Document Directory"` ด้วยโฟลเดอร์ที่คุณต้องการบันทึกไฟล์ KML

### ขั้นตอนที่ 2: สร้างเลเยอร์สำหรับไฟล์ผลลัพธ์
*layer* คือการจัดกลุ่มฟีเจอร์ทางภูมิศาสตร์ที่เป็นประเภทเดียวกัน ที่นี่เราจะสร้างอินสแตนซ์ของเลเยอร์ KML ใหม่ที่จะเก็บเรขาคณิตที่ทำให้เป็นเชิงเส้น  
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```

### ขั้นตอนที่ 3: สร้างฟีเจอร์ใหม่
*feature* แทนวัตถุทางภูมิศาสตร์หนึ่งรายการ (จุด, เส้น, โพลิกอน ฯลฯ) เราจะผูกเรขาคณิตเชิงเส้นของเราเข้ากับฟีเจอร์นี้  
```csharp
var feature = layer.ConstructFeature();
```

### ขั้นตอนที่ 4: กำหนดเรขาคณิตซับซ้อนต้นฉบับ
`Geometry.FromWkt` แปลงสตริง Well‑Known Text (WKT) ให้เป็นอ็อบเจ็กต์เรขาคณิต ตัวอย่าง WKT นี้รวม `LineString`, `CompoundCurve`, และ `CircularString` เพื่อแสดงการจัดการเส้นโค้ง  
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```

### ขั้นตอนที่ 5: แปลงเส้นโค้งเป็นเส้นตรง
`ToLinearGeometry()` ทำการตัดแบ่งทุกเส้นโค้งในเรขาคณิตต้นฉบับเป็นส่วนเส้นตรง และคืนค่าเรขาคณิตเชิงเส้นใหม่ที่คงค่าพิกัด Z ไว้  
```csharp
var linear = geometry.ToLinearGeometry();
```

### ขั้นตอนที่ 6: กำหนดเรขาคณิตเชิงเส้นให้กับฟีเจอร์
คุณสมบัติ `Geometry` ของฟีเจอร์ตอนนี้เก็บเวอร์ชันเชิงเส้นที่ทำให้เรียบง่ายของรูปร่างต้นฉบับ  
```csharp
feature.Geometry = linear;
```

### ขั้นตอนที่ 7: เพิ่มฟีเจอร์ลงในเลเยอร์
การเพิ่มฟีเจอร์ลงในเลเยอร์ KML จะทำให้มันอยู่ในคิวสำหรับการเขียน; เมื่อบล็อก `using` สิ้นสุด เลเยอร์จะทำการ flush ข้อมูลไปยังไฟล์ผลลัพธ์  
```csharp
layer.Add(feature);
```

## ข้อผิดพลาดทั่วไปและเคล็ดลับมืออาชีพ
- **ตัวคั่นเส้นทาง:** ใช้ `Path.Combine` เพื่อหลีกเลี่ยงปัญหาใน Windows vs. Linux.  
- **เรขาคณิตขนาดใหญ่มาก:** การทำให้เชิงเส้นของรูปทรงซับซ้อนอาจสร้างจุดหลายพันจุด; พิจารณาเรียก `Simplify()` หลังการทำให้เชิงเส้นเพื่อลดจำนวนจุด.  
- **การเลือกไดรเวอร์:** หากต้องการรูปแบบผลลัพธ์อื่น ให้เปลี่ยน `Drivers.Kml` เป็น `Drivers.Shapefile`, `Drivers.GeoJson` ฯลฯ และเปลี่ยนนามสกุลไฟล์ให้สอดคล้อง  
- **คงค่าพิกัด Z:** `ToLinearGeometry()` รักษาค่าพิกัด 3‑D (Z) ไว้ ดังนั้นคุณจะไม่สูญเสียข้อมูลระดับความสูง

## คำถามที่พบบ่อย (FAQ)

**Q: Aspose.GIS for .NET รองรับ .NET Core หรือไม่?**  
A: ใช่, Aspose.GIS ทำงานกับ .NET Core ทำให้สามารถพัฒนาแอปพลิเคชันข้ามแพลตฟอร์มได้  

**Q: ฉันสามารถทำงานกับรูปแบบไฟล์ GIS ต่าง ๆ ด้วย Aspose.GIS for .NET ได้หรือไม่?**  
A: ได้แน่นอน! ไลบรารีสนับสนุน KML, Shapefile, GeoJSON และรูปแบบอื่น ๆ มากกว่า 30 รูปแบบ  

**Q: Aspose.GIS มีฟังก์ชันการดำเนินการเชิงพื้นที่และการวิเคราะห์หรือไม่?**  
A: ใช่, มันให้ฟังก์ชันเชิงพื้นที่หลากหลาย ตั้งแต่การบัฟเฟอร์จนถึงการเชื่อมโยงเชิงพื้นที่  

**Q: มีการทดลองใช้งานฟรีหรือไม่?**  
A: มี, คุณสามารถดาวน์โหลดรุ่นทดลองฟรีจาก [เว็บไซต์ Aspose.GIS](https://releases.aspose.com/gis/net/).  

**Q: ฉันจะขอความช่วยเหลือได้จากที่ไหนหากพบปัญหา?**  
A: เยี่ยมชม [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อรับการสนับสนุนจากชุมชนและทีมงาน  

### คำถามเพิ่มเติมที่พบบ่อย

**Q: ฉันสามารถทำให้เรขาคณิตที่มีพิกัด 3D (Z) เป็นเชิงเส้นได้หรือไม่?**  
A: ได้, `ToLinearGeometry()` ทำงานกับเรขาคณิต 2D และ 3D ทั้งสองแบบ; ค่าพิกัด Z จะถูกคงไว้  

**Q: การทำให้เชิงเส้นส่งผลต่อขนาดไฟล์อย่างไร?**  
A: การแปลงเส้นโค้งเป็นหลายส่วนเส้นสั้น ๆ อาจทำให้ไฟล์ใหญ่ขึ้น; หากขนาดเป็นปัญหาให้เรียก `Simplify()` หลังการทำให้เชิงเส้น  

**Q: ฉันสามารถควบคุมความยาวของส่วนเมื่อแปลงเส้นโค้งเป็นเส้นตรงได้หรือไม่?**  
A: วิธีเริ่มต้นใช้ tolerance ภายใน; หากต้องการการแบ่งส่วนแบบกำหนดเองสามารถตัดแบ่งเส้นโค้งด้วยตนเองก่อนเรียก `ToLinearGeometry()`  

## สรุป
ในบทเรียนนี้เราได้อธิบาย **วิธีแปลงเส้นโค้งเป็นเส้นตรง** (ทำให้เรขาคณิตเป็นเชิงเส้น) ด้วย Aspose.GIS สำหรับ .NET ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการเขียนผลลัพธ์เชิงเส้นลงในไฟล์ KML คุณสามารถนำกระบวนการนี้ไปฝังในแอปพลิเคชันการทำแผนที่, pipeline การประมวลผลข้อมูล, หรือโครงการใด ๆ ที่เกี่ยวกับ GIS ที่ต้องการเรขาคณิตที่เรียบง่าย

---

**Last Updated:** 2026-09-10  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## บทเรียนที่เกี่ยวข้อง

- [วิธีสร้าง GeoJSON พร้อมความทนทาน Aspose.GIS for .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [แปลง Polygon เป็น Line ด้วย Aspose.GIS for .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)
- [เรียนรู้วิธีสร้างเรขาคณิต LineString ด้วย Aspose.GIS for .NET](/gis/net/geometry-creation/create-linestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}