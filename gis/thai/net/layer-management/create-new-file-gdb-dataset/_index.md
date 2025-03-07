---
title: สร้างชุดข้อมูล GDB ของไฟล์ใหม่
linktitle: สร้างชุดข้อมูล GDB ของไฟล์ใหม่
second_title: Aspose.GIS .NET API
description: สำรวจ Aspose.GIS สำหรับ .NET เพื่อสร้างและจัดการชุดข้อมูล GIS ได้อย่างง่ายดาย ดาวน์โหลดเดี๋ยวนี้เพื่อการพัฒนาภูมิสารสนเทศที่ราบรื่น #จัดทำ #GIS
weight: 10
url: /th/net/layer-management/create-new-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างชุดข้อมูล GDB ของไฟล์ใหม่

## การแนะนำ
ในขอบเขตของการพัฒนาเชิงพื้นที่ Aspose.GIS สำหรับ .NET มีความโดดเด่นในฐานะชุดเครื่องมืออันทรงพลังสำหรับการจัดการและจัดการข้อมูลระบบสารสนเทศทางภูมิศาสตร์ (GIS) ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้นการเดินทางสู่ GIS บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการสร้างชุดข้อมูล File Geodatabase (GDB) ใหม่โดยใช้ Aspose.GIS สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.GIS สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.GIS สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[หน้าดาวน์โหลด Aspose.GIS สำหรับ .NET](https://releases.aspose.com/gis/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณด้วย IDE ที่เข้ากันได้ เช่น Visual Studio และมีความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม .NET
- ไดเรกทอรีเอกสาร: แทนที่ "ไดเรกทอรีเอกสารของคุณ" ในข้อมูลโค้ดด้วยเส้นทางที่เหมาะสมที่คุณต้องการจัดเก็บชุดข้อมูล GDB ของคุณ
- ความคุ้นเคยกับ C#: บทช่วยสอนนี้ถือว่าคุณคุ้นเคยกับภาษาการเขียนโปรแกรม C#
## นำเข้าเนมสเปซ
ในขั้นตอนเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชันการทำงานของ Aspose.GIS ในแอปพลิเคชัน .NET ของคุณ:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## ขั้นตอนที่ 1: สร้างชุดข้อมูล GDB ของไฟล์ใหม่
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // เอาท์พุต: 0
    // ดำเนินการตามขั้นตอนต่อไป...
}
```
 คำอธิบาย: ในขั้นตอนนี้ เราสร้างชุดข้อมูล GDB ใหม่โดยใช้`Dataset.Create` วิธี. เราระบุเส้นทางและไดรเวอร์ (FileGdb) เพื่อสร้าง File Geodatabase เอาต์พุตคอนโซลจะแสดงจำนวนเลเยอร์เริ่มต้น ซึ่งเป็นศูนย์ ณ จุดนี้
## ขั้นตอนที่ 2: สร้างและเติม Layer_1
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
คำอธิบาย: ขั้นตอนนี้เกี่ยวข้องกับการสร้างเลเยอร์ชื่อ "layer_1" ภายในชุดข้อมูล มันกำหนดแอตทริบิวต์ชื่อ "ค่า" ของประเภทจำนวนเต็มและเติมเลเยอร์ด้วยคุณสมบัติสิบประการ โดยแต่ละคุณสมบัติมีเรขาคณิตแบบจุด
## ขั้นตอนที่ 3: สร้างและเติม Layer_2
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
คำอธิบาย: ที่นี่ เราสร้างเลเยอร์ที่สองชื่อ "layer_2" และเพิ่มคุณลักษณะเดียวด้วยเรขาคณิตของสตริงเส้น
## ขั้นตอนที่ 4: ตรวจสอบจำนวนเลเยอร์ที่อัปเดต
```csharp
Console.WriteLine(dataset.LayersCount); // เอาท์พุต: 2
```
คำอธิบาย: สุดท้ายนี้ เราจะตรวจสอบจำนวนเลเยอร์ที่อัปเดตหลังจากเพิ่มสองชั้นแล้ว ในกรณีนี้เอาต์พุตควรเป็น 2
## บทสรุป
ยินดีด้วย! คุณสร้างชุดข้อมูล File GDB ใหม่สำเร็จแล้วและเติมข้อมูลด้วยเลเยอร์โดยใช้ Aspose.GIS สำหรับ .NET บทช่วยสอนนี้ให้ความเข้าใจพื้นฐานเกี่ยวกับการทำงานกับข้อมูลเชิงพื้นที่ในสภาพแวดล้อม .NET
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถใช้ Aspose.GIS สำหรับ .NET กับไลบรารี GIS อื่นๆ ได้หรือไม่
Aspose.GIS สำหรับ .NET เป็นชุดเครื่องมือแบบสแตนด์อโลน อย่างไรก็ตาม คุณสามารถรวมเข้ากับไลบรารี .NET อื่นๆ เพื่อปรับปรุงฟังก์ชันการทำงานได้
### ถาม: มีฟอรัมชุมชนสำหรับการสนับสนุน Aspose.GIS หรือไม่
 ใช่ คุณสามารถค้นหาการสนับสนุนและการสนทนาได้ที่[ฟอรั่ม Aspose.GIS](https://forum.aspose.com/c/gis/33).
### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.GIS ได้อย่างไร
 เยี่ยมชม[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) หน้าข้อมูลเกี่ยวกับการขอรับใบอนุญาตชั่วคราว
### ถาม: มีตัวอย่างและเอกสารประกอบเพิ่มเติมหรือไม่
 สำรวจ[เอกสาร Aspose.GIS](https://reference.aspose.com/gis/net/) สำหรับตัวอย่างเพิ่มเติมและข้อมูลโดยละเอียด
### ถาม: ฉันจะซื้อ Aspose.GIS สำหรับ .NET ได้ที่ไหน
 คุณสามารถซื้อ Aspose.GIS สำหรับ .NET ได้ที่[หน้าซื้อ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
