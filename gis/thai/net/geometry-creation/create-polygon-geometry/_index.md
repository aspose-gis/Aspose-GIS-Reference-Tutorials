---
date: 2026-05-31
description: เรียนรู้วิธีสร้างโพลิกอนโดยใช้ Aspose.GIS สำหรับ .NET. คู่มือขั้นตอนต่อขั้นตอนสำหรับนักพัฒนา
  .NET เพื่อสร้างเรขาคณิตโพลิกอนและส่งออกไฟล์ shapefile โพลิกอน.
keywords:
- how to create polygon
- export polygon shapefile
- add vertices polygon
- build polygon coordinates
linktitle: สร้างเรขาคณิตโพลิกอน
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create polygon using Aspose.GIS for .NET. Step‑by‑step
    guide for .NET developers to build polygon geometry and export polygon shapefile.
  headline: How to Create Polygon Geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create polygon using Aspose.GIS for .NET. Step‑by‑step
    guide for .NET developers to build polygon geometry and export polygon shapefile.
  name: How to Create Polygon Geometry with Aspose.GIS for .NET
  steps:
  - name: Create a Polygon Object
    text: The `Polygon` class is the top‑level container that represents a single
      polygon geometry. **The `Polygon` class represents a closed geometric shape
      consisting of an exterior ring and optional interior rings.**
  - name: Define Exterior Ring
    text: A `LinearRing` holds the sequence of points that form the outer boundary.
      **The `LinearRing` class stores an ordered list of coordinate pairs that must
      form a closed loop.**
  - name: Add Points to the Exterior Ring
    text: Now we **add vertices polygon** by feeding latitude‑longitude pairs (or
      any coordinate system you prefer) into the ring. The points must form a closed
      loop, so the first and last coordinates are identical. **`LinearRing.AddPoint(x,
      y)` adds a single vertex to the ring; repeat for each coordinate.**
  - name: Set Exterior Ring on the Polygon
    text: Finally, assign the prepared ring to the polygon’s `ExteriorRing` property.
      The polygon is now a complete, valid geometry object. **The `ExteriorRing` property
      links the constructed `LinearRing` to the `Polygon` instance, finalizing the
      shape.** Congratulations! You have just **created polygon geome
  type: HowTo
- questions:
  - answer: Yes – simply iterate through your coordinate collection and call `ring.AddPoint(x,
      y)` for each item.
    question: Can I create a polygon from an existing list of coordinates?
  - answer: Create another `LinearRing`, add points, and assign it to `polygon.InteriorRings.Add(yourRing);`.
    question: How do I add an interior ring (hole) to the polygon?
  - answer: Use `polygon.IsValid` property; it returns `true` if the geometry complies
      with OGC standards.
    question: Is there a way to validate the polygon after creation?
  - answer: Absolutely. Use `FeatureWriter` with `GeoJson` format to write the polygon
      to a file, or choose `Shapefile` to **export polygon shapefile**.
    question: Can I export the polygon directly to GeoJSON?
  - answer: The library currently focuses on 2‑D geometries; for 3‑D you’ll need to
      manage Z‑values manually or use another specialized library.
    question: Does Aspose.GIS support 3‑D polygons?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: วิธีสร้างเรขาคณิตโพลิกอนด้วย Aspose.GIS สำหรับ .NET
url: /th/net/geometry-creation/create-polygon-geometry/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีสร้างรูปหลายเหลี่ยม (Polygon) ด้วย Aspose.GIS สำหรับ .NET

## บทนำ

หากคุณกำลังมองหาคู่มือที่ชัดเจนและเป็นประโยชน์เกี่ยวกับ **วิธีสร้างรูปหลายเหลี่ยม** ในสภาพแวดล้อม .NET คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะเดินผ่านกระบวนการทั้งหมดโดยใช้ Aspose.GIS สำหรับ .NET – ตั้งแต่การตั้งค่าโครงการ การเพิ่มจุด และการสรุปรูปหลายเหลี่ยม เมื่อเสร็จคุณจะเข้าใจว่าทำไมไลบรารีนี้จึงเป็นตัวเลือกที่ดีสำหรับการทำงานกับโครงสร้างรูปหลายเหลี่ยมของข้อมูลเชิงพื้นที่ และคุณจะมี **ตัวอย่างรูปหลายเหลี่ยม** ที่สามารถนำกลับมาใช้ใหม่สำหรับแอปพลิเคชัน GIS ของคุณเอง คุณยังจะได้เห็นวิธี **ส่งออก shapefile ของรูปหลายเหลี่ยม** และรูปแบบทั่วไปอื่น ๆ

## คำตอบอย่างรวดเร็ว
`Polygon` คือคลาสที่แสดงถึงรูปหลายเหลี่ยมใน Aspose.GIS. `LinearRing.AddPoint` เพิ่มจุดยอดไปยัง linear ring.  

- **คลาสหลักสำหรับรูปหลายเหลี่ยมคืออะไร?** `Polygon` จาก `Aspose.Gis.Geometries`.  
- **เมธอดใดที่เพิ่มจุดยอด?** `LinearRing.AddPoint(x, y)` – มันเพิ่มจุดยอดของรูปหลายเหลี่ยมทีละจุด.  
- **ฉันต้องการใบอนุญาตสำหรับการพัฒนาหรือไม่?** รุ่นทดลองฟรีใช้ได้สำหรับการทดสอบ; จำเป็นต้องมีใบอนุญาตสำหรับการใช้งานจริง.  
- **เวอร์ชัน .NET ที่รองรับ?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6+.  
- **ฉันสามารถส่งออกรูปหลายเหลี่ยมเป็นไฟล์ได้หรือไม่?** ใช่ – ใช้ `FeatureWriter` เพื่อเขียน Shapefile, GeoJSON ฯลฯ และสามารถ **ส่งออก shapefile ของรูปหลายเหลี่ยม** ได้อย่างง่ายดาย.  

## รูปหลายเหลี่ยม (Polygon) คืออะไร?

รูปหลายเหลี่ยมคือรูปแบบที่ปิดที่ประกอบด้วยวงแหวนภายนอก (ขอบเขตภายนอก) และอาจมีวงแหวนภายในหนึ่งหรือหลายวง (รู). ใน GIS, รูปหลายเหลี่ยมจำลองพื้นที่ในโลกจริงเช่น ทะเลสาบ, แปลงที่ดิน, หรือขอบเขตการปกครอง. Aspose.GIS ให้โมเดลวัตถุที่สะอาดที่ทำให้คุณ **สร้างพิกัดรูปหลายเหลี่ยม** ด้วยเพียงไม่กี่บรรทัดของ C#.

## ทำไมต้องใช้ Aspose.GIS เพื่อสร้างรูปหลายเหลี่ยม?

Aspose.GIS ให้คุณสร้างรูปหลายเหลี่ยมได้อย่างรวดเร็วพร้อมประสิทธิภาพระดับองค์กร. มันรองรับ **รูปแบบการนำเข้าและส่งออกกว่า 50 รูปแบบ**, สามารถประมวลผลชุดข้อมูลหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ, และทำงานบน .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6+. นั่นหมายความว่าคุณสามารถ **ส่งออก shapefile ของรูปหลายเหลี่ยม**, GeoJSON, KML, และรูปแบบอื่น ๆ อีกหลายรูปแบบโดยตรงจากโค้ด, ทำให้ไม่ต้องใช้ตัวแปลงของบุคคลที่สาม.

## ข้อกำหนดเบื้องต้น

1. **ความรู้พื้นฐานการเขียนโปรแกรม C#** – ความคุ้นเคยพื้นฐานกับคลาสและเมธอด.  
2. **การติดตั้ง Aspose.GIS สำหรับ .NET** – คุณสามารถดาวน์โหลดได้จาก [here](https://releases.aspose.com/gis/net/).  
3. **การตั้งค่าสภาพแวดล้อมการพัฒนา** – Visual Studio, Rider, หรือ IDE ใด ๆ ที่รองรับ .NET.  

## นำเข้า Namespaces

เราต้องนำคลาส GIS เข้ามาในขอบเขต. คำสั่ง `using` ด้านล่างเป็นทั้งหมดที่คุณต้องการสำหรับตัวอย่างนี้.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## วิธีสร้างรูปหลายเหลี่ยมใน Aspose.GIS  

โหลดโครงการของคุณ, เพิ่ม Namespaces ที่จำเป็น, สร้างอ็อบเจ็กต์ `Polygon`, สร้างวงแหวนภายนอก, เพิ่มจุดยอดของรูปหลายเหลี่ยม, และสุดท้ายกำหนดวงแหวน – ทั้งหมดในไม่กี่ขั้นตอนที่ง่ายดาย วิธีนี้ทำงานบน .NET runtime ที่รองรับทั้งหมดและสร้างรูปหลายเหลี่ยมที่สอดคล้องกับมาตรฐาน OGC พร้อมส่งออก.

### ขั้นตอนที่ 1: สร้างอ็อบเจ็กต์ Polygon  

`Polygon` class คือคอนเทนเนอร์ระดับบนสุดที่แสดงถึงรูปหลายเหลี่ยมเดียว.  
**คลาส `Polygon` แสดงถึงรูปทรงเรขาคณิตที่ปิดที่ประกอบด้วยวงแหวนภายนอกและวงแหวนภายในที่เป็นตัวเลือก.**  

```csharp
Polygon polygon = new Polygon();
```

### ขั้นตอนที่ 2: กำหนดวงแหวนภายนอก  

`LinearRing` เก็บลำดับของจุดที่สร้างขอบเขตภายนอก.  
**คลาส `LinearRing` เก็บรายการคู่พิกัดที่เรียงลำดับซึ่งต้องสร้างเป็นวงปิด.**  

```csharp
LinearRing ring = new LinearRing();
```

### ขั้นตอนที่ 3: เพิ่มจุดลงในวงแหวนภายนอก  

ตอนนี้เราจะ **เพิ่มจุดยอดของรูปหลายเหลี่ยม** โดยใส่คู่ละติจูด‑ลองจิจูด (หรือระบบพิกัดใด ๆ ที่คุณต้องการ) ลงในวงแหวน. จุดต้องสร้างเป็นวงปิด, ดังนั้นพิกัดแรกและสุดท้ายต้องเหมือนกัน.  
**`LinearRing.AddPoint(x, y)` เพิ่มจุดยอดหนึ่งจุดลงในวง; ทำซ้ำสำหรับแต่ละพิกัด.**  

```csharp
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

### ขั้นตอนที่ 4: กำหนดวงแหวนภายนอกให้กับ Polygon  

สุดท้าย, กำหนดวงแหวนที่เตรียมไว้ให้กับคุณสมบัติ `ExteriorRing` ของ polygon. ตอนนี้ polygon เป็นอ็อบเจ็กต์เรขาคณิตที่สมบูรณ์และถูกต้อง.  
**คุณสมบัติ `ExteriorRing` เชื่อม `LinearRing` ที่สร้างขึ้นกับอินสแตนซ์ `Polygon`, ทำให้รูปทรงเสร็จสมบูรณ์.**  

```csharp
polygon.ExteriorRing = ring;
```

ยินดีด้วย! คุณเพิ่ง **สร้างรูปหลายเหลี่ยม** ด้วย Aspose.GIS สำหรับ .NET. จากนี้คุณสามารถแนบรูปหลายเหลี่ยมเข้ากับฟีเจอร์, เขียนลงไฟล์, หรือทำการวิเคราะห์เชิงพื้นที่ได้.

## ปัญหาทั่วไป & เคล็ดลับ  

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| **วงแหวนไม่ปิด** | จุดแรกและจุดสุดท้ายต่างกัน ทำให้รูปหลายเหลี่ยมไม่ถูกต้อง. | ทำซ้ำพิกัดแรกเป็นพิกัดสุดท้าย (ตามที่แสดงข้างต้น). |
| **ลำดับพิกัดผิด** | ไลบรารี GIS คาดหวัง X (ลองจิจูด) แล้วตามด้วย Y (ละติจูด). | ตรวจสอบว่าคุณส่ง `(longitude, latitude)` ให้กับ `AddPoint`. |
| **ไม่มีใบอนุญาต** | โหมดทดลองอาจจำกัดการทำงานบางอย่าง. | ใช้ใบอนุญาตทดลองฟรีสำหรับการทดสอบ; ใช้ใบอนุญาตแบบชำระเงินสำหรับการใช้งานจริง. |

## คำถามที่พบบ่อย  

**Q: ฉันสามารถสร้างรูปหลายเหลี่ยมจากรายการพิกัดที่มีอยู่ได้หรือไม่?**  
A: ใช่ – เพียงแค่วนรอบผ่านคอลเลกชันพิกัดของคุณและเรียก `ring.AddPoint(x, y)` สำหรับแต่ละรายการ.  

**Q: ฉันจะเพิ่มวงแหวนภายใน (รู) ให้กับรูปหลายเหลี่ยมได้อย่างไร?**  
A: สร้าง `LinearRing` อีกอัน, เพิ่มจุด, แล้วกำหนดให้กับ `polygon.InteriorRings.Add(yourRing);`.  

**Q: มีวิธีตรวจสอบความถูกต้องของรูปหลายเหลี่ยมหลังจากสร้างหรือไม่?**  
A: ใช้คุณสมบัติ `polygon.IsValid`; จะคืนค่า `true` หากรูปหลายเหลี่ยมสอดคล้องกับมาตรฐาน OGC.  

**Q: ฉันสามารถส่งออกรูปหลายเหลี่ยมโดยตรงเป็น GeoJSON ได้หรือไม่?**  
A: ได้เลย. ใช้ `FeatureWriter` กับรูปแบบ `GeoJson` เพื่อเขียนรูปหลายเหลี่ยมลงไฟล์, หรือเลือก `Shapefile` เพื่อ **ส่งออก shapefile ของรูปหลายเหลี่ยม**.  

**Q: Aspose.GIS รองรับรูปหลายเหลี่ยม 3‑D หรือไม่?**  
A: ไลบรารีนี้ในปัจจุบันมุ่งเน้นที่รูปหลายเหลี่ยม 2‑D; สำหรับ 3‑D คุณต้องจัดการค่า Z ด้วยตนเองหรือใช้ไลบรารีเฉพาะอื่น.  

---

**อัปเดตล่าสุด:** 2026-05-31  
**ทดสอบด้วย:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [สร้างรูปหลายเหลี่ยมพร้อมรูโดยใช้ Aspose.GIS](/gis/net/geometry-creation/create-polygon-with-hole-geometry/)
- [สร้างรูปหลายเหลี่ยม C# และตรวจสอบการตัดกันด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [วิธีสร้าง Buffer ด้วย Aspose.GIS สำหรับ .NET](/gis/net/geometry-analysis/create-geometry-buffer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}