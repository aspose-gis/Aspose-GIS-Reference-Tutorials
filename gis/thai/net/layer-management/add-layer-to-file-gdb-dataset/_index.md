---
date: 2026-01-13
description: เรียนรู้วิธีเพิ่มเลเยอร์ลงในชุดข้อมูล File GDB ด้วย Aspose.GIS พร้อมการสนับสนุนระบบพิกัดเชิงพื้นที่
  WGS84 ทำตามคู่มือขั้นตอนต่อขั้นตอนนี้เพื่อเพิ่มเลเยอร์ลงใน GDB ด้วย .NET.
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: การอ้างอิงเชิงพื้นที่ WGS84 – เพิ่มเลเยอร์ไปยัง GDB ด้วย Aspose.GIS
url: /th/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ระบบพิกัดทางภูมิศาสตร์ wgs84 – เพิ่มตำแหน่งที่ตั้งลงใน GDB ด้วย Aspose.GIS

## บทนำ
คุณพร้อมที่จะประมวลผลข้อมูล GIS ของคุณด้วย Aspose.GIS สำหรับ .NET แล้วหรือยัง? ในบทเรียนนี้ คุณจะได้เรียนรู้ **วิธีการเพิ่มเลเยอร์ลงในชุดข้อมูลไฟล์ GDB** ในขณะที่ทำงานกับระบบพิกัดทางภูมิศาสตร์ **wgs84**

## คำตอบด่วน
- ** ระบบพิกัดทางภูมิศาสตร์ WGS84 (WGS84) คืออะไร?
- ** นี่คือ API อะไร?** Aspose.GIS สำหรับ .NET
- ** คุณต้องมีใบอนุญาตสำหรับการทดสอบหรือไม่?** ใช่ – מיע ליעישןשן עבור Aspose து׮�்க்கு
- ** คุณสามารถเพิ่มแอตทริบิวต์ให้กับเลเยอร์ใหม่ได้หรือไม่?** แน่นอน คุณสามารถกำหนดแอตทริบิวต์ได้ตามต้องการ
- ** .NET เวอร์ชันใดที่รองรับ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6

## ระบบพิกัดทางภูมิศาสตร์ WGS84 คืออะไร?
ระบบพิกัดทางภูมิศาสตร์ WGS84 (World Geodetic System 1984) เป็นระบบพิกัดทางภูมิศาสตร์ที่ใช้กันอย่างแพร่หลายที่สุด

## เหตุใดจึงต้องใช้ Aspose.GIS ในการเพิ่มเลเยอร์?

(ข้อความต้นฉบับไม่ชัดเจน) - **ไม่ต้องพึ่งพาไลบรารีภายนอก:** ใช้งานได้ทันทีกับโค้ด .NET
- **กำหนดประเภทเรขาคณิตเองได้:**
- **ใช้งานได้บนทุกแพลตฟอร์ม:** รองรับ Windows, Linux และ macOS
- **ใบอนุญาตชั่วคราว:** ใบอนุญาตชั่วคราวช่วยให้คุณประเมินผลลัพธ์ได้อย่างรวดเร็วก่อนตัดสินใจ

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มงาน โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

- ไลบรารี Aspose.GIS สำหรับ .NET: ดาวน์โหลดและติดตั้ง [ಮ್ತ್ತಿಕ್ಟಿ Aspose.GIS for .NET](https://reference.aspose.com/gis/net/)
- โฟลเดอร์เอกสาร: สร้างโฟลเดอร์เฉพาะบนเครื่องของคุณเพื่อจัดเก็บไฟล์ GIS

## นำเข้าเนมสเปซ
เพิ่มคำสั่ง `using` ที่จำเป็นในโปรเจกต์ C# ของคุณเพื่อให้เข้าถึงคลาสของ Aspose.GIS ได้:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ขั้นตอนที่ 1: คัดลอกไดเร็กทอรี
เริ่มต้นโดยทำสำเนาโฟลเดอร์ที่มีชุดข้อมูล GDB ดั้งเดิม การมีสำเนาช่วยปกป้องข้อมูลต้นฉบับขณะคุณทำการทดลอง

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## ขั้นตอนที่ 2: เปิดชุดข้อมูลและตรวจสอบความสามารถในการสร้าง
เปิดชุดข้อมูลที่คัดลอกใหม่และตรวจสอบว่ามันสามารถสร้างเลเยอร์ใหม่ได้หรือไม่ คุณควรเห็นค่า `CanCreateLayers` คืนค่า **True**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## ขั้นตอนที่ 3: สร้างและเติมข้อมูลลงในเลเยอร์ใหม่โดยใช้ระบบพิกัด wgs84
ต่อไปเราจะสร้างเลเยอร์ชื่อ **data** และกำหนดระบบพิกัดเป็น **Wgs84** อย่างชัดเจน พร้อมเพิ่มแอตทริบิวต์ง่าย ๆ ชื่อ **Name** และแทรกฟีเจอร์จุดหนึ่งจุด

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## ขั้นตอนที่ 4: เปิดและตรวจสอบความถูกต้องของเลเยอร์ที่เพิ่มเข้ามา
สุดท้ายเปิดเลเยอร์ที่คุณสร้างขึ้นและตรวจสอบเนื้อหา คอนโซลจะแสดงว่าเลเยอร์มีฟีเจอร์หนึ่งรายการและแอตทริบิวต์ **Name** ตรงกับค่าที่คุณตั้งไว้

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## ปัญหาทั่วไปและเคล็ดลับ
- **เส้นทางไม่ถูกต้อง:** ตรวจสอบให้แน่ใจว่า `dataDir` ลงท้ายด้วยเส้นทางที่ถูกต้อง (`/` หรือ `\`) เพื่อให้สตริงที่แนบมาเป็นเส้นทางไฟล์ที่ถูกต้อง
- **ข้อผิดพลาดเกี่ยวกับใบอนุญาต:** หากคุณเห็นคำเตือนเกี่ยวกับใบอนุญาต โปรดใช้ใบอนุญาตชั่วคราวจากพอร์ทัล Aspose ก่อนเรียกใช้โค้ด
- **CRS ไม่ตรงกัน:** เมื่อคุณเปิดไฟล์ในเครื่องมือ GIS อื่น ตรวจสอบว่าเครื่องมือดังกล่าวรู้จัก WGS84 (EPSG:4326) อย่างถูกต้อง

## คำถามที่พบบ่อย

### ถาม: ฉันสามารถใช้ Aspose.GIS สำหรับ .NET ร่วมกับไลบรารี GIS อื่นๆ ได้หรือไม่?

Aspose.GIS สำหรับ .NET ออกแบบมาให้ทำงานได้อย่างอิสระ แต่คุณสามารถรวมเข้ากับไลบรารีอื่นๆ เพื่อเพิ่มฟังก์ชันการทำงานได้

### ถาม: มีใบอนุญาตชั่วคราวสำหรับการทดสอบหรือไม่?

ใช่ คุณสามารถขอใบอนุญาตชั่วคราวได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อการทดสอบและประเมินผล

### ถาม: Aspose.GIS สำหรับ .NET รองรับระบบอ้างอิงเชิงพื้นที่ใดบ้าง?

Aspose.GIS for .NET รองรับระบบ แชร์

### ถาม: ฉันสามารถสนับสนุนชุมชน Aspose.GIS ได้หรือไม่

แน่นอน! เข้าร่วมการสนทนาและแบ่งปันประสบการณ์ของคุณได้ที่ [ ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33)

### ถาม: ฉันจะหาเอกสารรายละเอียดสำหรับ Aspose.GIS สำหรับ .NET ได้ที่ไหน?

ศึกษาเอกสารฉบับเต็มของ Aspose.GIS สำหรับ .NET

---

**อัปเดตล่าสุด:** 2026-01-13
**ทดสอบกับ:** Aspose.GIS สำหรับ .NET (เวอร์ชันเสถียรล่าสุด)
**ผู้เขียน:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
