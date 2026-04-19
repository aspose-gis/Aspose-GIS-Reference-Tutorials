---
date: 2026-01-10
description: เรียนรู้วิธีอ่านไฟล์ shapefile ด้วย C# และแปลงไฟล์ shapefile แบบโพลิกอนเป็น
  linestring ด้วย Aspose.GIS สำหรับ .NET เพิ่มศักยภาพการพัฒนา GIS ของคุณด้วยคำแนะนำที่ชัดเจนเป็นขั้นตอน
linktitle: Convert Polygon Shapefile to Linestring
second_title: Aspose.GIS .NET API
title: อ่าน Shapefile C# – แปลง Shapefile โพลิกอนเป็น Linestring
url: /th/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# อ่าน Shapefile C# – แปลง Polygon Shapefile เป็น Linestring

## บทนำ
หากคุณทำงานกับระบบสารสนเทศภูมิศาสตร์ (GIS) ใน .NET, **read shapefile c#** เป็นขั้นตอนแรกที่พบบ่อยก่อนที่คุณจะสามารถจัดการข้อมูลได้ Aspose.GIS ทำให้กระบวนการนี้ง่ายดาย โดยให้คุณแปลง Polygon Shapefile เป็น Linestring เพียงไม่กี่บรรทัดของโค้ด ความสามารถนี้มีประโยชน์อย่างยิ่งเมื่อคุณต้องการสกัดคุณลักษณะเชิงเส้นจากชุดข้อมูลรูปหลายเหลี่ยมสำหรับงานเช่น การวางแผนเส้นทาง, การวิเคราะห์เครือข่าย หรือการแสดงผลข้อมูล

## คำตอบสั้น
- **ไลบรารีใดช่วยให้คุณอ่าน shapefile c#?** Aspose.GIS for .NET  
- **คุณสามารถแปลง polygon เป็น line ได้หรือไม่?** ใช่ – ใช้ `LineString` กับวงแหวนภายนอกของ polygon.  
- **ฉันต้องการไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานในผลิตภัณฑ์.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **มีรุ่นทดลองหรือไม่?** แน่นอน – ดาวน์โหลดรุ่นทดลองฟรีจากเว็บไซต์ Aspose.

## อะไรคือ “read shapefile c#”?
การอ่าน shapefile ใน C# หมายถึงการโหลดไฟล์ `.shp` เข้าไปในหน่วยความจำเพื่อให้คุณสามารถสอบถาม, แก้ไข หรือแปลงเรขาคณิตของมันได้ Aspose.GIS มี API ที่เรียบง่ายซึ่งซ่อนรายละเอียดระดับต่ำและให้คุณมุ่งเน้นที่ตรรกะ GIS

## ทำไมต้องแปลง polygon เป็น line ด้วย Aspose.GIS?
- **รักษา topology** – การแปลงจะคงขอบเขตภายนอกที่แม่นยำของแต่ละ polygon.  
- **ประสิทธิภาพ** – ไลบรารีได้รับการปรับให้ทำงานกับชุดข้อมูลขนาดใหญ่ ทำให้การแปลงแบบ batch เร็ว.  
- **ความยืดหยุ่น** – คุณสามารถบันทึก linestrings ไปยัง shapefile อื่น, GeoJSON, หรือรูปแบบที่รองรับอื่น ๆ ได้ในภายหลัง.

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงลึกในบทเรียนนี้ โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมใช้งาน:

- **Aspose.GIS Library** – ดาวน์โหลดและติดตั้งไลบรารี Aspose.GIS จาก [website](https://releases.aspose.com/gis/net/).  
- **Shapefile Data** – มี Polygon Shapefile พร้อมสำหรับการแปลง หากไม่มี คุณสามารถค้นหาข้อมูลตัวอย่างหรือสร้างเองได้.  
- **สภาพแวดล้อมการพัฒนา** – ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ของคุณพร้อมเครื่องมือที่จำเป็น (Visual Studio, .NET SDK ฯลฯ).

## นำเข้า Namespaces
ในโค้ด C# ของคุณ คุณต้องนำเข้า namespaces ของ Aspose.GIS เพื่อเข้าถึงคลาสและเมธอดที่จำเป็น เพิ่ม namespaces ต่อไปนี้ที่ส่วนต้นของไฟล์โค้ดของคุณ:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## วิธีแปลง shapefile จาก polygon เป็น line?
ด้านล่างเป็นคู่มือขั้นตอนต่อขั้นตอนที่แสดง **วิธีแปลง shapefile** จาก polygon เป็น line ด้วย Aspose.GIS

### ขั้นตอนที่ 1: ตั้งค่า Document Directory
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
แทนที่ `"Your Document Directory"` ด้วยพาธจริงที่ไฟล์ shapefile ของคุณอยู่

### ขั้นตอนที่ 2: เปิด Source Shapefile
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
บรรทัดนี้ **เปิด Polygon Shapefile ต้นทาง** เพื่อให้คุณสามารถอ่านฟีเจอร์ของมันได้

### ขั้นตอนที่ 3: สร้าง Destination Linestring Shapefile
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
ที่นี่เร **สร้าง Linestring Shapefile ใหม่** ที่จะเก็บเรขาคณิตที่แปลงแล้ว

### ขั้นตอนที่ 4: วนลูปผ่าน Source Features
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
ลูปนี้เดินผ่านแต่ละฟีเจอร์ polygon ในไฟล์ต้นฉบับ

### ขั้นตอนที่ 5: แปลง Polygon เป็น Linestring และเขียนไปยัง Destination
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
ในบล็อกนี้เร **แปลง polygon เป็น line** (`LineString`) และเพิ่มฟีเจอร์ใหม่ไปยัง shapefile ปลายทาง

## ปัญหาและเคล็ดลับทั่วไป
- **ความไม่ตรงกันของระบบพิกัด** – ตรวจสอบให้แน่ใจว่าชั้นต้นทางและปลายทางใช้การอ้างอิงเชิงพื้นที่เดียวกัน; หากไม่เช่นนั้น เส้นอาจแสดงตำแหน่งผิด.  
- **ไฟล์ขนาดใหญ่** – เมื่อประมวลผล shapefile ขนาดใหญ่มาก ควรพิจารณา stream ฟีเจอร์แทนการโหลดทั้งหมดเข้าสู่หน่วยความจำพร้อมกัน.  
- **เรขาคณิตเป็น Null** – ป้องกันฟีเจอร์ที่มีเรขาคณิตว่างเปล่าเพื่อหลีกเลี่ยงข้อยกเว้นขณะรัน.

## คำถามที่พบบ่อย

**Q: Aspose.GIS รองรับทุกเวอร์ชันของ .NET หรือไม่?**  
A: ใช่, Aspose.GIS รองรับเวอร์ชัน .NET ต่าง ๆ ทำให้เข้ากันได้กับสภาพแวดล้อมการพัฒนาของคุณ.

**Q: ฉันสามารถใช้ Aspose.GIS ในโครงการเชิงพาณิชย์ได้หรือไม่?**  
A: ใช่, คุณสามารถทำได้. เพื่อใช้ Aspose.GIS ในโครงการเชิงพาณิชย์, พิจารณาซื้อไลเซนส์จาก [here](https://purchase.aspose.com/buy).

**Q: มีตัวอย่างหรือเอกสารใดให้ใช้หรือไม่?**  
A: มี, คุณสามารถค้นหาเอกสารและตัวอย่างที่ครอบคลุมได้บน [documentation page](https://reference.aspose.com/gis/net/).

**Q: มีรุ่นทดลองให้ใช้งานหรือไม่?**  
A: มี, คุณสามารถสำรวจ Aspose.GIS ด้วยรุ่นทดลองฟรีโดยเยี่ยมชม [this link](https://releases.aspose.com/).

**Q: ฉันจะขอความช่วยเหลือหรือสนับสนุนได้จากที่ไหน?**  
A: เยี่ยมชม [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) สำหรับคำถามหรือปัญหาใด ๆ ที่เกี่ยวกับการสนับสนุน.

---

**อัปเดตล่าสุด:** 2026-01-10  
**ทดสอบด้วย:** Aspose.GIS for .NET (latest release)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}