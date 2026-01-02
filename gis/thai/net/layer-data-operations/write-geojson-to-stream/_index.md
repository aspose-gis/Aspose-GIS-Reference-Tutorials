---
date: 2026-01-02
description: เรียนรู้วิธีเขียน GeoJSON ไปยังสตรีมใน C# ด้วย Aspose.GIS สำหรับ .NET
  แสดงตัวอย่าง GeoJSON C# และเพิ่มประสิทธิภาพให้แอปพลิเคชันเชิงพื้นที่ของคุณ
linktitle: Write GeoJSON to Stream
second_title: Aspose.GIS .NET API
title: วิธีเขียน GeoJSON ไปยังสตรีมด้วย Aspose.GIS สำหรับ .NET
url: /th/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเขียน GeoJSON ไปยัง Stream

## บทนำ
หากคุณต้องการ **วิธีเขียน geojson** โดยตรงลงในหน่วยความจำหรือไฟล์สตรีมในแอปพลิเคชัน .NET คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะพาคุณผ่านขั้นตอนทั้งหมดเพื่อเขียน GeoJSON ไปยังสตรีมโดยใช้ไลบรารี Aspose.GIS for .NET และเราจะสาธิตวิธี **display GeoJSON C#** ผลลัพธ์ในคอนโซล ด้วยขั้นตอนเหล่านี้ คุณจะได้รูปแบบที่นำกลับมาใช้ใหม่ได้ในทุกโครงการด้านภูมิสารสนเทศ

## คำตอบสั้น ๆ
- **“write GeoJSON to stream” หมายถึงอะไร?** หมายถึงการทำให้ชั้นเวกเตอร์เป็นรูปแบบ GeoJSON แล้วส่งไบต์ไปยังอ็อบเจ็กต์ `Stream` (เช่น `MemoryStream`)  
- **ไลบรารีใดจัดการเรื่องนี้?** Aspose.GIS for .NET มีไดรเวอร์ GeoJSON ในตัว  
- **ต้องมีลิขสิทธิ์สำหรับการพัฒนาหรือไม่?** สามารถใช้รุ่นทดลองฟรีสำหรับการพัฒนา; ต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง  
- **สามารถรันบน Linux ได้หรือไม่?** ได้ – Aspose.GIS รองรับหลายแพลตฟอร์มและทำงานบน Windows, Linux, และ macOS  
- **รองรับเวอร์ชัน .NET ใดบ้าง?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7

## “how to write geojson” ใน .NET คืออะไร?
Aspose.GIS ให้คุณสร้าง `VectorLayer` เพิ่มฟีเจอร์ แล้วทำการซีเรียลไลซ์ชั้นโดยใช้ไดรเวอร์ `Drivers.GeoJson` ไดรเวอร์นี้จะเขียนข้อความ GeoJSON ลงใน `Stream` ใดก็ได้ ทำให้คุณควบคุมได้เต็มที่ว่าจะเก็บข้อมูลที่ไหน (หน่วยความจำ, ไฟล์, เครือข่าย ฯลฯ)

## ทำไมต้องใช้ Aspose.GIS สำหรับงานนี้?
- **การซีเรียลไลซ์ไม่มีการพึ่งพา** – ไม่ต้องใช้ไลบรารี JSON ภายนอก  
- **สอดคล้องตามสเปค GeoJSON เต็มรูปแบบ** – รองรับ FeatureCollections, properties, และความแม่นยำของพิกัด  
- **ข้ามแพลตฟอร์ม** – ทำงานเหมือนกันบน Windows, Linux, และ macOS  
- **ประสิทธิภาพสูง** – เขียนโดยตรงลงสตรีมโดยไม่ต้องสร้างสตริงกลาง

## ข้อกำหนดเบื้องต้น
1. **Aspose.GIS for .NET** – ดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/gis/net/)  
2. **โฟลเดอร์เอกสาร** – กำหนดตำแหน่งที่คุณต้องการเก็บไฟล์ชั่วคราวหรือสตรีมผลลัพธ์  

ต่อไปมาดูโค้ดกัน

## นำเข้า Namespaces
ก่อนอื่นให้เพิ่ม Namespaces ที่ให้คุณเข้าถึงคลาสของ Aspose.GIS และยูทิลิตี้ I/O ของ .NET:

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## ขั้นตอนที่ 1: ตั้งค่า Document Directory
กำหนดโฟลเดอร์ที่จะใช้เก็บไฟล์ชั่วคราวใด ๆ ที่คุณอาจต้องการ

```csharp
string dataDir = "Your Document Directory";
```

เปลี่ยน `"Your Document Directory"` ให้เป็นพาธจริงบนเครื่องของคุณ

## ขั้นตอนที่ 2: สร้าง Memory Stream
`MemoryStream` ช่วยให้คุณเก็บ GeoJSON ในหน่วยความจำ ซึ่งเหมาะกับ API หรือกรณีที่ต้องส่งข้อมูลโดยตรงกลับไปยังไคลเอนต์

```csharp
using (var memoryStream = new MemoryStream())
{
    // Subsequent steps will be placed inside this block
}
```

## ขั้นตอนที่ 3: สร้าง Vector Layer ด้วย GeoJSON Driver
ภายในบล็อก memory‑stream ให้สร้าง `VectorLayer` ที่ใช้ไดรเวอร์ GeoJSON ซึ่งบอก Aspose.GIS ให้ทำการซีเรียลไลซ์ชั้นเป็น GeoJSON

```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Feature creation goes here
}
```

## ขั้นตอนที่ 4: กำหนด Attribute ของ Feature
เพิ่มการกำหนดคุณลักษณะที่จะปรากฏเป็น properties ในผลลัพธ์ GeoJSON สุดท้าย

```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## ขั้นตอนที่ 5: สร้างและเพิ่ม Features
สร้างจุดตัวอย่างสองจุด กำหนดค่า attribute แล้วเพิ่มลงในชั้น

```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);

// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## ขั้นตอนที่ 6: แสดงผล GeoJSON C# Output
หลังจากชั้นเต็มแล้ว ให้แปลงไบต์ของสตรีมเป็นสตริง UTF‑8 แล้วเขียนลงคอนโซล เพื่อสาธิตวิธี **display GeoJSON C#** ผลลัพธ์

```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

คุณควรเห็น FeatureCollection ของ GeoJSON ที่ถูกต้องแสดงบนเทอร์มินัล

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| ผลลัพธ์ว่าง | ตำแหน่งของสตรีมอยู่ที่ท้ายเมื่ออ่าน | เรียก `memoryStream.Position = 0;` ก่อนแปลงเป็นสตริง |
| รูปทรงไม่ถูกต้อง | พิกัดอยู่นอกช่วงที่รับได้ | ตรวจสอบให้ latitude อยู่ระหว่าง -90 ถึง 90, longitude ระหว่าง -180 ถึง 180 |
| ข้อผิดพลาดลิขสิทธิ์ | รันโดยไม่มีลิขสิทธิ์ที่ถูกต้องในสภาพการผลิต | ใช้ลิขสิทธิ์ชั่วคราวหรือเต็มโดย `License license = new License(); license.SetLicense("Aspose.GIS.lic");` |

## คำถามที่พบบ่อย
### สามารถใช้ Aspose.GIS for .NET ได้ทั้งบน Windows และ Linux หรือไม่?
ได้, Aspose.GIS for .NET รองรับทั้งสองระบบ

### มีรุ่นทดลองฟรีหรือไม่?
มีแน่นอน! คุณสามารถทดลองได้จาก [ที่นี่](https://releases.aspose.com/)

### จะหาเอกสารรายละเอียดได้จากที่ไหน?
ดูเอกสารได้ [ที่นี่](https://reference.aspose.com/gis/net/)

### จะขอรับลิขสิทธิ์ชั่วคราวได้อย่างไร?
ลิขสิทธิ์ชั่วคราวมีให้บริการ [ที่นี่](https://purchase.aspose.com/temporary-license/)

### ต้องการความช่วยเหลือหรือมีคำถามเพิ่มเติม?
เยี่ยมชมฟอรั่มสนับสนุนของเรา [ที่นี่](https://forum.aspose.com/c/gis/33)

## FAQ
**ถาม: สามารถเขียน GeoJSON ลงไฟล์โดยตรงแทนการใช้ memory stream ได้หรือไม่?**  
ตอบ: ได้ — แค่เปลี่ยน `MemoryStream` เป็น `FileStream` แล้วระบุพาธไฟล์ ไดรเวอร์เดียวกันจะทำงานได้

**ถาม: จะควบคุมการเยื้องหรือรูปแบบของ GeoJSON ที่สร้างออกมาอย่างไร?**  
ตอบ: Aspose.GIS จะเขียน JSON แบบกะทัดรัดโดยค่าเริ่มต้น หากต้องการ pretty‑print ให้ทำ post‑process สตริงด้วย `JsonSerializerOptions { WriteIndented = true }`

**ถาม: สามารถเพิ่มรูปทรงที่ซับซ้อนกว่า (เช่น polygon) ลงในชั้นได้หรือไม่?**  
ตอบ: แน่นอน สร้างอ็อบเจ็กต์ `Polygon` หรือ `LineString` กำหนดให้กับ `Feature.Geometry` แล้วเพิ่มฟีเจอร์ตามตัวอย่างข้างต้น

**ถาม: ชุดข้อมูลขนาดใหญ่จะใส่ลงใน `MemoryStream` ได้หรือไม่?**  
ตอบ: สำหรับคอลเลกชันขนาดใหญ่มาก ควรสตรีมโดยตรงไปยังไฟล์หรือใช้ `BufferedStream` เพื่อหลีกเลี่ยงการใช้หน่วยความจำสูง

**ถาม: ไดรเวอร์ GeoJSON รองรับการกำหนด CRS (Coordinate Reference System) หรือไม่?**  
ตอบ: รองรับ — ตั้งค่า `SpatialReferenceSystem` ของชั้นก่อนเพิ่มฟีเจอร์หากต้องการ CRS ที่ไม่ใช่ WGS84

## สรุป
คุณได้เรียนรู้รูปแบบที่พร้อมใช้งานในระดับ production สำหรับ **วิธีเขียน geojson** ไปยังสตรีมใด ๆ ใน .NET ด้วย Aspose.GIS ไม่ว่าจะเป็นการส่ง GeoJSON จาก Web API, บันทึกลงไฟล์, หรือแสดงผลในคอนโซล ขั้นตอนข้างต้นครอบคลุมเวิร์กโฟลว์ทั้งหมด ลองสำรวจไลบรารีต่อเพื่อทำงานกับฟอร์แมตอื่น ๆ เช่น Shapefile, KML, หรือ GML และต่อยอดแอปพลิเคชันภูมิสารสนเทศของคุณให้แข็งแกร่งยิ่งขึ้น

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-01-02  
**ทดสอบกับ:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

---