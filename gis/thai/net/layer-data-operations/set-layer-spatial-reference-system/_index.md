---
date: 2025-12-31
description: เรียนรู้วิธีสร้างเลเยอร์เวกเตอร์และตั้งค่าระบบอ้างอิงเชิงพื้นที่ของเลเยอร์ด้วย
  Aspose.GIS สำหรับ .NET. เชี่ยวชาญการกำหนดอ้างอิงเชิงพื้นที่, การเพิ่มฟีเจอร์จุด,
  และการดึงรหัส EPSG.
linktitle: Set Layer Spatial Reference System
second_title: Aspose.GIS .NET API
title: สร้างเลเยอร์เวกเตอร์และตั้งค่าระบบอ้างอิงเชิงพื้นที่ของเลเยอร์
url: /th/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง Vector Layer และตั้งค่า Spatial Reference System ของ Layer

## บทนำ
ในภูมิทัศน์กว้างใหญ่ของระบบข้อมูลภูมิศาสตร์ (GIS) **Aspose.GIS for .NET** โดดเด่นในฐานะเครื่องมือที่แข็งแรงและหลากหลายสำหรับนักพัฒนา ในบทเรียนนี้คุณจะ **create vector layer**, กำหนด spatial reference, เพิ่มฟีเจอร์จุด, และดึงรหัส EPSG—ทั้งหมดด้วยคำแนะนำที่ชัดเจนและเป็นขั้นตอน ไม่ว่าคุณจะเป็นวิศวกร GIS ที่มีประสบการณ์หรือเพิ่งเริ่มต้น เทคนิคเหล่านี้จะช่วยให้คุณตั้งค่า coordinate system ของ shapefile อย่างถูกต้องและเพิ่มความน่าเชื่อถือให้กับกระบวนการทำงานกับข้อมูลเชิงพื้นที่ของคุณ.

## คำตอบสั้น
- **สร้าง vector layer หมายถึงอะไร?** มันสร้าง GIS layer ใหม่ (เช่น Shapefile) ที่สามารถเก็บเรขาคณิตเช่น จุด, เส้น, หรือโพลิกอน.  
- **รหัส EPSG ที่ใช้ในตัวอย่างคืออะไร?** EPSG 26918 (NAD83 / UTM zone 18N).  
- **ฉันสามารถเพิ่มฟีเจอร์จุดหลังจากสร้าง layer ได้หรือไม่?** ได้—ใช้ `ConstructFeature()` และกำหนดเรขาคณิต `Point`.  
- **ฉันจะดึง CRS ของ layer อย่างไร?** อ่าน `layer.SpatialReferenceSystem.EpsgCode` หรือ `.Name`.  
- **ฉันต้องมีไลเซนส์สำหรับ Aspose.GIS หรือไม่?** มีรุ่นทดลองฟรี; จำเป็นต้องมีไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มบทเรียน โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:
- ความรู้พื้นฐานในการเขียนโปรแกรม .NET.  
- มี Visual Studio ติดตั้งบนระบบของคุณ.  
- ไลบรารี Aspose.GIS for .NET ที่คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/gis/net/).  
- ความเข้าใจพื้นฐานเกี่ยวกับระบบอ้างอิงเชิงพื้นที่ใน GIS.

## นำเข้า Namespaces
ในโครงการ .NET ของคุณ ให้เริ่มต้นโดยการนำเข้า namespaces ที่จำเป็นเพื่อเข้าถึงฟังก์ชันที่ Aspose.GIS ให้มา ใช้โค้ดตัวอย่างต่อไปนี้:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## ขั้นตอนที่ 1: ระบุไดเรกทอรีเอกสาร
เริ่มต้นโดยระบุเส้นทางไปยังไดเรกทอรีเอกสารของคุณ ซึ่งจะเป็นตำแหน่งที่ไฟล์ข้อมูลเชิงพื้นที่ของคุณถูกจัดเก็บ

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: กำหนด Spatial Reference และตั้งค่า Coordinate System ของ Shapefile
กำหนดเส้นทางสำหรับ Shapefile และ **กำหนด spatial reference** ด้วยรหัส EPSG (26918 ในตัวอย่างนี้) ขั้นตอนนี้ **ตั้งค่า coordinate system ของ shapefile** สำหรับ layer

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## ขั้นตอนที่ 3: สร้าง Vector Layer
ตอนนี้ **create vector layer** ด้วยเส้นทาง Shapefile ที่ระบุ, ประเภทไดรเวอร์ (Shapefile) และระบบอ้างอิงเชิงพื้นที่ที่คุณเพิ่งกำหนด

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

## ขั้นตอนที่ 4: เพิ่มฟีเจอร์จุดลงใน Layer
สร้างฟีเจอร์ใหม่และ **add point feature** โดยตั้งค่าเรขาคณิตของมัน ( `Point` ที่มีพิกัด 60, 24) จากนั้นเพิ่มฟีเจอร์นี้ลงใน vector layer

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

## ขั้นตอนที่ 5: ดึงข้อมูล Spatial Reference System (ดึงรหัส EPSG)
เปิด Vector Layer และดึงข้อมูลเกี่ยวกับระบบอ้างอิงเชิงพื้นที่ เช่น รหัส EPSG และชื่อที่อ่านได้มนุษย์ ขั้นตอนนี้แสดงวิธี **retrieve EPSG code** และ **set layer CRS**

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

ทำตามขั้นตอนเหล่านี้ตามกรณีการใช้งานของคุณ และคุณจะก้าวหน้าอย่างมั่นใจในการ **create vector layer** และการจัดการ spatial references ด้วย Aspose.GIS for .NET.

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| **ไม่สามารถเปิด Layer** | ไดรเวอร์ไม่ถูกต้องหรือเส้นทางไฟล์เสียหาย | ตรวจสอบ `Drivers.Shapefile` และให้แน่ใจว่า `path` ชี้ไปยังไฟล์ `.shp` ที่มีอยู่. |
| **แสดง CRS ไม่ถูกต้อง** | ใช้รหัส EPSG ไม่ถูกต้อง | ตรวจสอบรหัส EPSG อีกครั้งกับแหล่งข้อมูลที่เชื่อถือได้ (เช่น EPSG.io). |
| **ฟีเจอร์ไม่ถูกบันทึก** | ไม่ได้เรียก `layer.Add(feature)` ภายในบล็อก `using` | ตรวจสอบให้แน่ใจว่าเมธอด `Add` ถูกเรียกใช้ก่อนที่ layer จะถูกทำลาย. |

## คำถามที่พบบ่อย
### Aspose.GIS เข้ากันได้กับไลบรารี GIS อื่นหรือไม่?
ใช่, Aspose.GIS สามารถทำงานร่วมกับไลบรารี GIS อื่นได้อย่างดีและสามารถใช้ร่วมกับพวกมันได้.

### ฉันสามารถใช้ Aspose.GIS สำหรับแอปพลิเคชันเดสก์ท็อปและเว็บได้หรือไม่?
แน่นอน! Aspose.GIS มีความยืดหยุ่นและสามารถนำไปใช้ได้ทั้งในแอปพลิเคชันเดสก์ท็อปและเว็บ.

### มีตัวเลือกการให้ลิขสิทธิ์สำหรับ Aspose.GIS หรือไม่?
ใช่, คุณสามารถสำรวจตัวเลือกการให้ลิขสิทธิ์และทำการซื้อได้ [ที่นี่](https://purchase.aspose.com/buy).

### มีรุ่นทดลองฟรีสำหรับ Aspose.GIS หรือไม่?
แน่นอน! คุณสามารถดาวน์โหลดรุ่นทดลองฟรีได้ [ที่นี่](https://releases.aspose.com/).

### ฉันสามารถขอรับการสนับสนุนสำหรับคำถามที่เกี่ยวกับ Aspose.GIS ได้จากที่ไหน?
สำหรับการสนับสนุนหรือคำถามใด ๆ โปรดเยี่ยมชม [ฟอรั่ม Aspose.GIS](https://forum.aspose.com/c/gis/33).

## คำถามเพิ่มเติมที่พบบ่อย
**ถาม: ฉันจะเปลี่ยน CRS ของ Shapefile ที่มีอยู่ได้อย่างไร?**  
ตอบ: เปิด layer, สร้าง `SpatialReferenceSystem` ใหม่ด้วยรหัส EPSG ที่ต้องการ, แล้วกำหนดให้กับ `layer.SpatialReferenceSystem` ก่อนบันทึก.

**ถาม: ฉันสามารถเพิ่มประเภทเรขาคณิตอื่น (เช่น โพลิกอน) ด้วยวิธีเดียวกันได้หรือไม่?**  
ตอบ: ได้—เปลี่ยน `new Point(x, y)` เป็น `new Polygon(...)` หรือ `new LineString(...)` ตามต้องการ.

**ถาม: สามารถทำงานกับชุดข้อมูลขนาดใหญ่ได้อย่างมีประสิทธิภาพหรือไม่?**  
ตอบ: ใช้ API สตรีมมิ่ง (`VectorLayer.Create` พร้อม `FeatureCollection`) และทำลาย layer ทันทีเมื่อเสร็จเพื่อคืนทรัพยากร.

**ถาม: Aspose.GIS รองรับการแปลงพิกัดหรือไม่?**  
ตอบ: ใช่—ใช้ `Geometry.Transform(targetSrs)` เพื่อทำการแปลงเรขาคณิตระหว่างระบบอ้างอิงเชิงพื้นที่ต่าง ๆ.

**ถาม: .NET เวอร์ชันใดที่รองรับ?**  
ตอบ: Aspose.GIS ทำงานกับ .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## สรุป
ในบทเรียนนี้เราได้สำรวจวิธี **create vector layer**, กำหนด spatial reference, **add point feature**, และ **retrieve EPSG code** ด้วย Aspose.GIS for .NET โดยการเชี่ยวชาญขั้นตอนเหล่านี้คุณจะสามารถตั้งค่า coordinate system ของ shapefile ได้อย่างถูกต้อง, จัดการ CRS ของ layer, และสร้างแอปพลิเคชัน GIS ที่เชื่อถือได้

---

**Last Updated:** 2025-12-31  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}