---
date: 2026-05-31
description: เรียนรู้วิธีสร้าง GeoJSON, กำหนดค่า GeoJSON options, และเพิ่ม feature
  ไปยัง layer ด้วย Aspose.GIS for .NET. ทำตามคู่มือ step‑by‑step นี้.
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: ตั้งค่า Linearization Tolerance
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  headline: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  name: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  steps:
  - name: Configure GeoJSON Options (how to set tolerance)
    text: '`GeoJsonOptions` specifies the serialization settings used when writing
      GeoJSON files. `GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including
      linearization tolerance, coordinate precision, and other output settings. We’ll
      create a `GeoJsonOptions` object and tell Aspose.GIS how close '
  - name: Define the Output Path (how to export GeoJSON)
    text: Specify the full file path where the resulting GeoJSON will be saved. Ensure
      the folder exists and the application has write permissions.
  - name: '**Create Vector Layer** with the configured options'
    text: The `VectorLayer` class represents a GIS container that can read and write
      spatial data. `Drivers.GeoJson` is the driver identifier for writing GeoJSON
      format files. Using `VectorLayer.Create` together with the `Drivers.GeoJson`
      driver and the previously configured `GeoJsonOptions` creates a new Geo
  - name: Construct a Geometry (e.g., a circular string)
    text: '`CircularString` is a curved line geometry that Aspose.GIS can linearize
      based on the tolerance you set. You can replace this with any valid WKT representation
      such as `POINT`, `LINESTRING`, or `POLYGON`.'
  - name: '**Add Feature to Layer** and save'
    text: '`Feature` is the object that couples a geometry with attribute data. After
      creating a `Feature` instance, assign the geometry, optionally add attribute
      values, and call `layer.Add(feature)` to persist it. When the `using` block
      ends, the layer is automatically written to the file defined in `path`. '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. A commercial license removes all evaluation restrictions and
      provides full technical support.
    question: Can I use Aspose.GIS in commercial projects?
  - answer: Yes, it supports over 30 formats—including Shapefile, KML, GML, and CSV—allowing
      seamless conversion between them.
    question: Does Aspose.GIS support other GIS formats besides GeoJSON?
  - answer: You can download a free 30‑day trial from the Aspose website; it includes
      all features.
    question: Is there a trial version available?
  - answer: Use the Aspose forums, the dedicated support portal, or the “Contact Support”
      link in the product dashboard.
    question: Where can I get support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: วิธีสร้าง GeoJSON ด้วย Tolerance ใน Aspose.GIS for .NET
url: /th/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้าง GeoJSON พร้อมค่าความคลาดเคลื่อน Aspose.GIS สำหรับ .NET

## บทนำ
หากคุณต้องการ **เรียนรู้วิธีสร้างไฟล์ GeoJSON** ควบคุมความแม่นยำของเส้นโค้ง และส่งออกผลลัพธ์เป็นเอกสารพร้อมใช้งาน Aspose.GIS สำหรับ .NET ทำให้กระบวนการง่ายดาย ในบทเรียนนี้คุณจะได้ค้นพบวิธีกำหนดค่า GeoJSON options, ตั้งค่าความคลาดเคลื่อนของการทำเส้นตรง (linearization tolerance) และ **add feature to layer** พร้อมกับรักษาโค้ดให้สะอาดและพร้อมใช้งานในสภาพแวดล้อมการผลิต

## คำตอบสั้น
- **What does “create vector layer” mean?** มันสร้างชุดข้อมูลเวกเตอร์ GIS ใหม่ (เช่น ไฟล์ GeoJSON) ที่สามารถเก็บรูปทรงเรขาคณิตและแอตทริบิวต์ได้  
- **How do I set linearization tolerance?** ตั้งค่าคุณสมบัติ `LinearizationTolerance` บนอินสแตนซ์ `GeoJsonOptions` ก่อนสร้างเลเยอร์  
- **Can I export a GeoJSON file directly?** ใช่—ใช้ `VectorLayer.Create` พร้อมกับไดรเวอร์ `Drivers.GeoJson` และตัวเลือกที่กำหนดค่าไว้  
- **Do I need a license?** ใบอนุญาต Aspose.GIS ที่ถูกต้องจะปลดล็อกคุณสมบัติทั้งหมด; คีย์ประเมินผลชั่วคราวสามารถใช้งานสำหรับการทดสอบได้  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “create vector layer” คืออะไร
การสร้างเวกเตอร์เลเยอร์หมายถึงการเริ่มต้นคอนเทนเนอร์ GIS ใหม่ (เช่น ไฟล์ GeoJSON) ที่สามารถเก็บจุด, เส้น, โพลิกอน, และข้อมูลแอตทริบิวต์ที่เกี่ยวข้องได้ เลเยอร์นี้จะเป็นเป้าหมายสำหรับรูปทรงเรขาคณิตใด ๆ ที่คุณสร้างและแอตทริบิวต์ใด ๆ ที่คุณแนบ

## ทำไมต้องกำหนดค่า GeoJSON options
การกำหนดค่า GeoJSON options—โดยเฉพาะ **linearization tolerance**—ทำให้แน่ใจว่ารูปทรงโค้ง (เช่น `CircularString`) จะถูกประมาณด้วยความแม่นยำที่ตรงตามข้อกำหนดความแม่นยำของแอปพลิเคชันของคุณ การกำหนดค่าที่เหมาะสมช่วยลดขนาดไฟล์ในขณะที่คงความเที่ยงตรงของภาพ ซึ่งสำคัญเมื่อ GeoJSON ถูกใช้โดยแผนที่เว็บหรือเครื่องมือวิเคราะห์เชิงพื้นที่

## ข้อกำหนดเบื้องต้น
1. **Visual Studio** (เวอร์ชันล่าสุดใดก็ได้).  
2. **Aspose.GIS license** (หรือคีย์ประเมินผลชั่วคราว).  
3. ไลบรารี **Aspose.GIS for .NET** ที่อ้างอิงในโปรเจกต์ของคุณ.  
4. ความคุ้นเคยพื้นฐานกับ **C#**.

## นำเข้า Namespaces
ก่อนอื่น ให้นำเข้า namespaces ที่จำเป็นเพื่อให้คอมไพเลอร์รู้ว่าจะหาคลาส GIS จากที่ไหน:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: กำหนดค่า GeoJSON Options (วิธีตั้งค่าความคลาดเคลื่อน)
`GeoJsonOptions` ระบุการตั้งค่าการทำซีเรียลไลซ์ที่ใช้เมื่อเขียนไฟล์ GeoJSON.  
`GeoJsonOptions` กำหนดวิธีที่ Aspose.GIS ทำการซีเรียลไลซ์ GeoJSON รวมถึง linearization tolerance, ความแม่นยำของพิกัด, และการตั้งค่าเอาต์พุตอื่น ๆ.  
เราจะสร้างอ็อบเจ็กต์ `GeoJsonOptions` และบอก Aspose.GIS ว่ารูปทรงเรขาคณิตที่ทำเส้นตรงต้องใกล้เคียงกับเส้นโค้งต้นฉบับเท่าใด

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### ขั้นตอนที่ 2: กำหนดเส้นทางเอาต์พุต (วิธีส่งออก GeoJSON)
ระบุเส้นทางไฟล์เต็มที่ไฟล์ GeoJSON ที่ได้จะถูกบันทึก ตรวจสอบให้แน่ใจว่าโฟลเดอร์มีอยู่และแอปพลิเคชันมีสิทธิ์เขียน

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### ขั้นตอนที่ 3: **Create Vector Layer** ด้วยตัวเลือกที่กำหนดค่าไว้
`VectorLayer` เป็นคลาสที่แสดงถึงคอนเทนเนอร์ GIS ที่สามารถอ่านและเขียนข้อมูลเชิงพื้นที่ได้.  
`Drivers.GeoJson` คือไดรเวอร์ที่ใช้สำหรับเขียนไฟล์รูปแบบ GeoJSON.  
การใช้ `VectorLayer.Create` ร่วมกับไดรเวอร์ `Drivers.GeoJson` และ `GeoJsonOptions` ที่กำหนดค่าไว้ก่อนหน้านี้ จะสร้างไฟล์ GeoJSON ใหม่พร้อมสำหรับการแทรกฟีเจอร์.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### ขั้นตอนที่ 4: สร้าง Geometry (เช่น circular string)
`CircularString` คือรูปทรงเส้นโค้งที่ Aspose.GIS สามารถทำเส้นตรงได้ตามค่าความคลาดเคลื่อนที่คุณตั้งค่า คุณสามารถแทนที่ด้วยการแทนค่า WKT ใด ๆ ที่ถูกต้อง เช่น `POINT`, `LINESTRING`, หรือ `POLYGON`.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### ขั้นตอนที่ 5: **Add Feature to Layer** และบันทึก
`Feature` คืออ็อบเจ็กต์ที่เชื่อมโยงรูปทรงเรขาคณิตกับข้อมูลแอตทริบิวต์ หลังจากสร้างอินสแตนซ์ `Feature` แล้ว ให้กำหนดรูปทรง, เพิ่มค่าแอตทริบิวต์ตามต้องการ, และเรียก `layer.Add(feature)` เพื่อบันทึก เมื่อบล็อก `using` สิ้นสุดลง เลเยอร์จะถูกเขียนลงไฟล์ที่กำหนดใน `path` โดยอัตโนมัติ.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

เมื่อบล็อก `using` สิ้นสุดลง เลเยอร์จะถูกเขียนลงไฟล์ที่กำหนดใน `path` โดยอัตโนมัติ ทำให้คุณได้ไฟล์ GeoJSON พร้อมใช้งาน

## ปัญหาที่พบบ่อยและเคล็ดลับ
- **Incorrect path** – ตรวจสอบว่าไดเรกทอรีมีอยู่และคุณมีสิทธิ์เขียน.  
- **Tolerance too low** – การตั้งค่า `LinearizationTolerance` เป็นค่าที่เล็กมากอาจทำให้ขนาดไฟล์เพิ่มขึ้นอย่างมาก; ค่าความคลาดเคลื่อนประมาณ 0.001 มักจะสมดุลระหว่างความแม่นยำและขนาดไฟล์.  
- **License errors** – หากคุณเห็นคำเตือนเกี่ยวกับใบอนุญาต, ตรวจสอบว่าไฟล์ใบอนุญาตถูกโหลดก่อนการเรียกใช้ Aspose.GIS ใด ๆ.  
- **Performance note** – Aspose.GIS รองรับการประมวลผลไฟล์ขนาดถึง 2 GB โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ, ขอบคุณสถาปัตยกรรมสตรีมมิ่งของมัน.

## คำถามที่พบบ่อย

**Q: Is Aspose.GIS for .NET compatible with other .NET frameworks?**  
A: ใช่, มันทำงานกับ .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6/7.

**Q: Can I use Aspose.GIS in commercial projects?**  
A: แน่นอน. ใบอนุญาตเชิงพาณิชย์จะลบข้อจำกัดการประเมินทั้งหมดและให้การสนับสนุนทางเทคนิคเต็มรูปแบบ.

**Q: Does Aspose.GIS support other GIS formats besides GeoJSON?**  
A: ใช่, มันรองรับมากกว่า 30 รูปแบบรวมถึง Shapefile, KML, GML, และ CSV—ทำให้การแปลงระหว่างรูปแบบต่าง ๆ เป็นไปอย่างราบรื่น.

**Q: Is there a trial version available?**  
A: คุณสามารถดาวน์โหลดรุ่นทดลองฟรี 30 วันจากเว็บไซต์ Aspose; มีคุณสมบัติทั้งหมด.

**Q: Where can I get support?**  
A: ใช้ฟอรั่มของ Aspose, พอร์ทัลสนับสนุนเฉพาะ, หรือลิงก์ “Contact Support” ในแดชบอร์ดผลิตภัณฑ์.

## สรุป
โดยทำตามขั้นตอนเหล่านี้ คุณจะรู้ **วิธีสร้าง GeoJSON**, กำหนดค่าความคลาดเคลื่อนของการทำเส้นตรง, และ **เพิ่มฟีเจอร์ลงในเลเยอร์** เพื่อการส่งออก GeoJSON อย่างราบรื่น สำรวจประเภทรูปทรงเรขาคณิตเพิ่มเติม, การจัดการแอตทริบิวต์, และสถานการณ์การประมวลผลแบบกลุ่มเพื่อใช้ประโยชน์จาก Aspose.GIS อย่างเต็มที่ในโครงการ GIS ของคุณบน .NET.

---

**Last Updated:** 2026-05-31  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## บทเรียนที่เกี่ยวข้อง

- [How to Convert GeoJSON – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [Create Vector Layer, Limit Precision with Aspose.GIS for .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}