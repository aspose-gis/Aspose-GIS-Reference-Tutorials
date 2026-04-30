---
date: 2026-01-15
description: เรียนรู้วิธีทำป้ายกำกับฟีเจอร์แผนที่โดยใช้ Aspose.GIS สำหรับ .NET พร้อมตัวเลือกสไตล์ป้ายกำกับที่กำหนดเองสำหรับการทำป้ายกำกับชุดข้อมูลขนาดใหญ่
linktitle: Label Features on Map
second_title: Aspose.GIS .NET API
title: ทำเครื่องหมายคุณลักษณะแผนที่ด้วย Aspose.GIS สำหรับ .NET
url: /th/net/map-rendering/label-features-on-map/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ป้ายกำกับฟีเจอร์แผนที่ด้วย Aspose.GIS สำหรับ .NET

## บทนำ
การใส่ป้ายกำกับให้กับฟีเจอร์แผนที่เป็นสิ่งสำคัญสำหรับการเปลี่ยนข้อมูลเชิงพื้นที่ดิบให้เป็นภาพที่ชัดเจนและเป็นมิตรต่อผู้ใช้ ในบทแนะนำนี้คุณจะได้ค้นพบ **วิธีการป้ายกำกับฟีเจอร์แผนที่** (คีย์เวิร์ดหลัก) ด้วย Aspose.GIS สำหรับ .NET, สำรวจสไตล์ป้ายกำกับแบบกำหนดเอง, และดูเทคนิคที่ทำงานได้แม้กับชุดข้อมูลขนาดใหญ่ เมื่อจบแล้วคุณจะสามารถเพิ่มข้อความข้อมูลโดยตรงบนแผนที่ของคุณ ทำให้แผนที่มีข้อมูลเชิงลึกมากขึ้นสำหรับนักวิเคราะห์และผู้ใช้ปลายทาง

## คำตอบสั้น
- **คลาสหลักสำหรับการเรนเดอร์คืออะไร?** `Map` (Aspose.Gis.Rendering)
- **คลาสใดที่ใช้เพิ่มข้อความง่าย?** `SimpleLabeling`
- **สามารถจัดรูปแบบป้ายกำกับ (halo, font, rotation) ได้หรือไม่?** ได้ – ผ่านคุณสมบัติเช่น `HaloSize`, `FontStyle`, และ `Placement`
- **จะจัดการกับชุดข้อมูลขนาดใหญ่ได้อย่างไร?** ใช้ `FeatureBasedConfiguration` เพื่อจัดลำดับความสำคัญของป้ายกำกับตามค่าคุณลักษณะ
- **ต้องการไลเซนส์หรือไม่?** เวอร์ชันทดลองใช้ได้สำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง

## ป้ายกำกับฟีเจอร์แผนที่คืออะไร?
`label map features` หมายถึงการแนบข้อความที่อ่านได้ (เช่น ชื่อเมือง, ตัวเลขประชากร, หรือรหัสกำหนดเอง) ไปยังวัตถุเรขาคณิต—จุด, เส้น, หรือโพลิไกน์—เพื่อให้แผนที่สื่อสารข้อมูลเชิงพื้นที่และข้อมูลคุณลักษณะพร้อมกันในครั้งเดียว

## ทำไมต้องใช้ Aspose.GIS สำหรับป้ายกำกับฟีเจอร์แผนที่?
- **ไม่มีการพึ่งพาไลบรารีภายนอก** – ไลบรารี .NET แท้ ๆ ไม่ต้องใช้ไบนารี GIS แบบเนทีฟ  
- **ตัวเลือกการจัดรูปแบบที่หลากหลาย** – halo, ฟอนต์กำหนดเอง, การหมุน, และจุดยึดทำให้คุณปรับแต่งลักษณะได้ละเอียด  
- **ประสิทธิภาพที่คำนึงถึง** – ระบบป้ายกำกับแบบฟีเจอร์‑เบสในตัวช่วยให้คุณจัดลำดับความสำคัญของป้ายที่สำคัญที่สุดเมื่อเรนเดอร์ชุดข้อมูลขนาดใหญ่  
- **รองรับหลายรูปแบบผลลัพธ์** – SVG, PNG, PDF ฯลฯ พร้อมผลลัพธ์การป้ายกำกับที่สม่ำเสมอ

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน ตรวจสอบให้แน่ใจว่าคุณมี:

- ความรู้พื้นฐานเกี่ยวกับ C# และ .NET framework  
- ติดตั้ง Aspose.GIS สำหรับ .NET คุณสามารถดาวน์โหลดได้ **[ที่นี่](https://releases.aspose.com/gis/net/)**  
- ไฟล์ GeoJSON ที่มีข้อมูลจุด (หรือรูปแบบเวกเตอร์ที่รองรับอื่นใด)

## นำเข้า Namespaces
ในโค้ด C# ของคุณ ให้นำเข้า namespaces ที่จำเป็น:

```csharp
using System;
using System.Drawing;
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Labelings;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.GIS.Examples.CSharp;
using FontStyle = Aspose.Gis.Rendering.Labelings.FontStyle;
```

ต่อไปเราจะเดินผ่านหลายสถานการณ์การป้ายกำกับ โดยแต่ละขั้นตอนจะต่อยอดจากขั้นตอนก่อนหน้า

## ป้ายกำกับจุด – วิธีป้ายกำกับจุด
### ขั้นตอนที่ 1: ตั้งค่าเส้นทางไปยังไดเรกทอรีเอกสารของคุณ
```csharp
string dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 2: สร้างแผนที่พร้อมสัญลักษณ์มาร์คเกอร์แบบง่าย
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Add a vector layer and apply labeling
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Render the map to an SVG file
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```

ในตัวอย่างพื้นฐานนี้เราจะ **วิธีป้ายกำกับจุด** โดยใช้คุณลักษณะ `name` จากไฟล์ GeoJSON

## ป้ายกำกับจุดแบบสไตล์ – สไตล์ป้ายกำกับกำหนดเอง
ทำตามขั้นตอนที่ 1 และ 2 จากตัวอย่างก่อนหน้า แล้วปรับสไตล์การป้ายกำกับ:

```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Rest of the steps remain the same
```

Halo ที่เพิ่มเข้ามาและฟอนต์เอียงทำให้ป้ายกำกับมี **สไตล์ป้ายกำกับกำหนดเอง** ที่โดดเด่นบนพื้นหลังที่ซับซ้อน

## ป้ายกำกับจุดแบบวางตำแหน่ง – ตัวเลือกการวางตำแหน่งขั้นสูง
เริ่มต้นอีกครั้งด้วยขั้นตอนที่ 1 และ 2 จากตัวอย่างแรก แล้วปรับการวางตำแหน่ง:

```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        HorizontalOffset = 2,
        VerticalOffset = 2,
        Rotation = 10,
    }
};
// Rest of the steps remain the same
```

ที่นี่คุณสามารถควบคุมจุดยึด, การชิด, และการหมุนได้อย่างละเอียด ทำให้คุณมีการควบคุม **วิธีการป้ายกำกับจุด** ในพื้นที่แผนที่ที่แออัดได้อย่างแม่นยำ

## ป้ายกำกับจุดแบบฟีเจอร์‑เบส – การป้ายกำกับชุดข้อมูลขนาดใหญ่
เมื่อจัดการกับจุดจำนวนมาก คุณอาจต้องการจัดลำดับความสำคัญของป้ายตามคุณลักษณะเช่นประชากร ทำตามขั้นตอนที่ 1 และ 2 จากตัวอย่างแรก แล้วนำไปใช้กับการป้ายกำกับแบบฟีเจอร์‑เบส:

```csharp
var pointLabeling = new SimpleLabeling("name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        VerticalOffset = 4,
        HorizontalOffset = 4,
    },
    FeatureBasedConfiguration = (feature, labeling) =>
    {
        // Retrieve population from the feature.
        var population = feature.GetValue<int>("population");
        // Font size is computed and is based on the population.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // Priority of the label is also based on the population.
        // The greater the priority is, the more likely label will appear on the output image.
        labeling.Priority = population;
    }
};
// Rest of the steps remain the same
```

กลยุทธ์ **การป้ายกำกับชุดข้อมูลขนาดใหญ่** นี้ทำให้เมืองที่สำคัญที่สุด (ตามประชากร) แสดงก่อน ส่วนจุดที่สำคัญน้อยกว่าอาจถูกละเว้นเมื่อพื้นที่จำกัด

## สรุป
ขอแสดงความยินดี! ตอนนี้คุณรู้หลายวิธีในการ **ป้ายกำกับฟีเจอร์แผนที่** ด้วย Aspose.GIS สำหรับ .NET—from การป้ายกำกับจุดแบบง่ายจนถึงการจัดรูปแบบแบบฟีเจอร์‑เบสสำหรับชุดข้อมูลขนาดใหญ่ ทดลองใช้ halo, การหมุน, และกฎลำดับความสำคัญเพื่อสร้างแผนที่ที่สื่อสารข้อมูลตรงตามที่ผู้ชมของคุณต้องการเห็น

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถป้ายกำกับฟีเจอร์ด้วยฟอนต์กำหนดเองได้หรือไม่?**  
ตอบ: ได้. ตั้งค่า `FontFamily` และ `FontStyle` ในการกำหนดค่า `SimpleLabeling` เพื่อใช้ฟอนต์ที่ติดตั้งไว้ใดก็ได้

**ถาม: Aspose.GIS รองรับรูปแบบข้อมูล GIS อื่น ๆ หรือไม่?**  
ตอบ: แน่นอน. รองรับ GeoJSON, Shapefile, KML, GML, และรูปแบบอื่น ๆ อีกมากมาย

**ถาม: ฉันจะจัดการกับชุดข้อมูลขนาดใหญ่สำหรับการป้ายกำกับอย่างไร?**  
ตอบ: ใช้ `FeatureBasedConfiguration` เพื่อกำหนดลำดับความสำคัญและปรับขนาดฟอนต์แบบไดนามิกตามค่าคุณลักษณะ ตามที่แสดงในตัวอย่างฟีเจอร์‑เบส

**ถาม: มีตัวเลือกการวางตำแหน่งป้ายกำกับขั้นสูงหรือไม่?**  
ตอบ: มี. คุณสามารถปรับการวางตำแหน่งด้วย `PointLabelPlacement` ปรับจุดยึด, การชิด, และการหมุนได้ละเอียด

**ถาม: ฉันสามารถทำให้การสร้างป้ายกำกับเป็นอัตโนมัติในกระบวนการแบตช์ได้หรือไม่?**  
ตอบ: ได้แน่นอน. ห่อหุ้มโค้ดการเรนเดอร์แผนที่ในลูปหรือบริการพื้นหลังเพื่อประมวลผลหลายเลเยอร์หรือไฟล์โดยอัตโนมัติ

---

**อัปเดตล่าสุด:** 2026-01-15  
**ทดสอบกับ:** Aspose.GIS 24.11 สำหรับ .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}