---
title: การเรียนรู้การติดฉลากคุณสมบัติอย่างเชี่ยวชาญด้วย Aspose.GIS สำหรับ .NET
linktitle: คุณลักษณะป้ายกำกับบนแผนที่
second_title: Aspose.GIS .NET API
description: สำรวจ Aspose.GIS สำหรับ .NET และเชี่ยวชาญศิลปะของการติดป้ายกำกับคุณลักษณะบนแผนที่ ปรับปรุงการแสดงภาพข้อมูลเชิงพื้นที่ของคุณได้อย่างง่ายดาย #จัดทำ #GIS
weight: 11
url: /th/net/map-rendering/label-features-on-map/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเรียนรู้การติดฉลากคุณสมบัติอย่างเชี่ยวชาญด้วย Aspose.GIS สำหรับ .NET

## การแนะนำ
ในโลกของการแสดงข้อมูลเชิงพื้นที่ คุณสมบัติการติดป้ายกำกับบนแผนที่มีบทบาทสำคัญในการถ่ายทอดข้อมูลอย่างมีประสิทธิภาพ Aspose.GIS สำหรับ .NET มอบชุดเครื่องมือที่มีประสิทธิภาพเพื่อให้บรรลุเป้าหมายนี้ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะสำรวจวิธีการต่างๆ ในการติดป้ายกำกับจุดบนแผนที่โดยใช้ Aspose.GIS ซึ่งจะช่วยเพิ่มประสิทธิภาพการแสดงภาพแผนที่ของคุณด้วยป้ายกำกับที่ให้ข้อมูล
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้เกี่ยวกับการทำงานของ C# และ .NET framework
-  ติดตั้ง Aspose.GIS สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/gis/net/).
- ไฟล์ GeoJSON ที่มีข้อมูลจุด หากไม่มี คุณสามารถใช้ไฟล์ตัวอย่างสำหรับการทดสอบได้
## นำเข้าเนมสเปซ
ในโค้ด C# ของคุณ ตรวจสอบให้แน่ใจว่าคุณนำเข้าเนมสเปซที่จำเป็นสำหรับการทำงานกับ Aspose.GIS:
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
ตอนนี้ เราจะแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอนในรูปแบบคำแนะนำทีละขั้นตอน
##  การติดฉลากจุด

### ขั้นตอนที่ 1: กำหนดเส้นทางไปยังไดเรกทอรีเอกสารของคุณ:
```csharp
string dataDir = "Your Document Directory";
```
### ขั้นตอนที่ 2: สร้างแผนที่ด้วยสัญลักษณ์เครื่องหมายง่ายๆ:
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. เพิ่มเลเยอร์เวกเตอร์และใช้การติดฉลาก
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. เรนเดอร์แผนที่เป็นไฟล์ SVG
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## สไตล์การติดฉลากคะแนน

ทำตามขั้นตอนที่ 1 และ 2 จากตัวอย่างก่อนหน้า

### ขั้นตอนที่ 1: ปรับแต่งสไตล์การติดฉลาก:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// ขั้นตอนที่เหลือยังคงเหมือนเดิม
```
## วางป้ายกำกับจุดแล้ว

ทำตามขั้นตอนที่ 1 และ 2 จากตัวอย่างแรก
### ขั้นตอนที่ 2: ปรับแต่งตำแหน่งป้ายกำกับ:
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
// ขั้นตอนที่เหลือยังคงเหมือนเดิม
```
## คุณสมบัติการติดฉลากคะแนนตาม

ทำตามขั้นตอนที่ 1 และ 2 จากตัวอย่างแรก

### ขั้นตอนที่ 1: ใช้การติดป้ายกำกับตามคุณลักษณะ:
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
        // ดึงข้อมูลประชากรจากคุณลักษณะ
        var population = feature.GetValue<int>("population");
        // ขนาดแบบอักษรได้รับการคำนวณและขึ้นอยู่กับจำนวนประชากร
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // ลำดับความสำคัญของฉลากยังขึ้นอยู่กับจำนวนประชากรด้วย
        // ยิ่งมีลำดับความสำคัญมากเท่าใด ป้ายกำกับก็จะมีโอกาสปรากฏบนภาพที่ส่งออกมากขึ้นเท่านั้น
        labeling.Priority = population;
    }
};
// ขั้นตอนที่เหลือยังคงเหมือนเดิม
```
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีปรับปรุงการแสดงภาพแผนที่ของคุณโดยการติดป้ายกำกับคุณลักษณะต่างๆ โดยใช้ Aspose.GIS สำหรับ .NET ทดลองใช้รูปแบบและตำแหน่งที่แตกต่างกันเพื่อสร้างแผนที่ที่น่าสนใจซึ่งปรับให้เหมาะกับข้อมูลของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถติดป้ายกำกับคุณสมบัติโดยใช้แบบอักษรที่กำหนดเองได้หรือไม่
ใช่ คุณสามารถปรับแต่งรูปแบบและขนาดแบบอักษรได้ในการกำหนดค่าการติดฉลาก
### Aspose.GIS เข้ากันได้กับรูปแบบข้อมูล GIS อื่นๆ หรือไม่
Aspose.GIS รองรับรูปแบบภูมิสารสนเทศที่หลากหลาย รวมถึง GeoJSON, Shapefile และอื่นๆ
### ฉันจะจัดการชุดข้อมูลขนาดใหญ่สำหรับการติดป้ายกำกับได้อย่างไร
Aspose.GIS ได้รับการปรับให้เหมาะสมเพื่อประสิทธิภาพ แต่ให้ลองใช้การกำหนดค่าตามฟีเจอร์เพื่อจัดลำดับความสำคัญของป้ายกำกับตามคุณลักษณะของข้อมูล
### มีตัวเลือกการจัดวางป้ายกำกับขั้นสูงหรือไม่
ใช่ คุณสามารถปรับแต่งการวางตำแหน่งฉลากได้โดยใช้ตัวเลือกต่างๆ เช่น การหมุน จุดยึด และออฟเซ็ต
### ฉันสามารถสร้างฉลากอัตโนมัติในกระบวนการเป็นชุดได้หรือไม่
แน่นอน คุณสามารถรวม Aspose.GIS เข้ากับเวิร์กโฟลว์อัตโนมัติสำหรับการสร้างฉลากเป็นชุดได้
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
