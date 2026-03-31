---
date: 2025-12-31
description: สำรวจ Aspose.GIS สำหรับ .NET และเรียนรู้วิธีสร้างชุดข้อมูลไฟล์ GDB และตั้งค่าความคลาดเคลื่อนอย่างง่ายดายด้วยคำแนะนำทีละขั้นตอน
  ปรับปรุงแอปพลิเคชัน .NET ของคุณ
linktitle: Set Tolerances for File GDB Layer
second_title: Aspose.GIS .NET API
title: สร้างชุดข้อมูล File GDB และตั้งค่าความคลาดเคลื่อนสำหรับเลเยอร์
url: /th/net/layer-data-operations/set-tolerances-for-file-gdb-layer/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง File GDB Dataset และตั้งค่าความทนทานสำหรับเลเยอร์

## คำแนะนำ
หากคุณต้องการ **สร้าง file GDB dataset** และควบคุมความแม่นยำของมัน คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะเดินผ่านกระบวนการทั้งหมด—ตั้งแต่การตั้งค่าโครงการ .NET ของคุณ, การสร้าง File Geodatabase (GDB) dataset, แล้วจึงนำค่า XY, Z, และ M tolerance ไปใช้กับเลเยอร์ใหม่ เมื่อเสร็จสิ้นคุณจะได้ dataset ที่พร้อมใช้งานและทำงานได้อย่างราบรื่นกับเครื่องมือ ArcGIS และแอปพลิเคชัน GIS อื่น ๆ

## คำตอบอย่างรวดเร็ว
- **“สร้าง file GDB dataset” หมายถึงอะไร?** มันสร้างคอนเทนเนอร์ File Geodatabase ใหม่บนดิสก์ที่สามารถเก็บหลายเลเยอร์ GIS ได้  
- **ทำไมต้องตั้งค่าความทนทาน?** ความทนทานกำหนดความแม่นยำสำหรับการดำเนินการเรขาคณิต ป้องกันข้อผิดพลาดการปัดเศษในการวิเคราะห์เชิงพื้นที่  
- **คลาส Aspose.GIS ที่ใช้คืออะไร?** `Dataset.Create` ร่วมกับ `FileGdbOptions`  
- **ต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** ไลเซนส์ชั่วคราวเพียงพอสำหรับการทดสอบ; ไลเซนส์เต็มจำเป็นสำหรับการใช้งานจริง  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  

## File GDB Dataset คืออะไร?
File Geodatabase (GDB) เป็นที่เก็บข้อมูลแบบโฟลเดอร์ที่บรรจุเลเยอร์ GIS, ตาราง, และความสัมพันธ์ต่าง ๆ ด้วย Aspose.GIS คุณสามารถ **สร้าง file GDB dataset** อย่างโปรแกรมได้โดยไม่ต้องติดตั้ง ArcGIS ทำให้เหมาะกับการทำงานอัตโนมัติหรือแอปพลิเคชันที่กำหนดเอง

## ทำไมต้องตั้งค่าความทนทานสำหรับเลเยอร์?
การตั้งค่าความทนทานทำให้การคำนวณเรขาคณิต (เช่น การตัดกัน, การบัฟเฟอร์, หรือการสแนป) เคารพความแม่นยำที่คุณต้องการ ซึ่งสำคัญมากเมื่อทำงานกับข้อมูลความละเอียดสูงหรือเมื่อส่งออกไปยังแพลตฟอร์ม GIS อื่น ๆ ที่คาดหวังค่าความทนทานเฉพาะ

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะลงมือเขียนโค้ด โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้พร้อมแล้ว:

- **Aspose.GIS for .NET Library** – ดาวน์โหลดและติดตั้งไลบรารี Aspose.GIS จาก [download link](https://releases.aspose.com/gis/net/). หากคุณยังไม่ได้รับไลบรารี คุณสามารถสำรวจเพิ่มเติมได้ใน [documentation](https://reference.aspose.com/gis/net/).  
- **Development Environment** – Visual Studio, Rider หรือ IDE ใด ๆ ที่รองรับการพัฒนา .NET  
- **A valid license** – ใช้ไลเซนส์ชั่วคราวสำหรับการทดสอบหรือไลเซนส์เต็มสำหรับการใช้งานจริง (ดูลิงก์ในส่วน FAQ)

ตอนนี้คุณพร้อมแล้ว เรามาเริ่มนำเข้า namespaces ที่จำเป็นกันเถอะ

## นำเข้า Namespaces
ในแอปพลิเคชัน .NET ของคุณ ให้รวม namespaces ต่อไปนี้เพื่อใช้ฟังก์ชันของ Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

เมื่อมี namespaces พร้อมแล้ว เราสามารถเริ่มสร้าง dataset ได้

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอกสารของคุณ
แรกสุด ให้ชี้โค้ดไปยังโฟลเดอร์ที่คุณต้องการให้สร้าง File GDB:

```csharp
string dataDir = "Your Document Directory";
```

> **เคล็ดลับ:** ใช้ `Path.Combine` หากคุณต้องการสร้างเส้นทางแบบพึ่งพาแพลตฟอร์ม

### ขั้นตอนที่ 2: สร้าง File GDB Dataset
ต่อไปเราจะ **สร้าง file GDB dataset** บนดิสก์จริง เมธอด `Dataset.Create` รับพาธเต็มและประเภทไดรเวอร์ (`Drivers.FileGdb`)

```csharp
var path = dataDir + "TolerancesForFileGdbLayer_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

> บล็อก `using` ทำให้แน่ใจว่า dataset ถูกปิดและบันทึกลงดิสก์อย่างถูกต้องเมื่อทำงานเสร็จ

### ขั้นตอนที่ 3: ตั้งค่าความทนทานโดยใช้ `FileGdbOptions`
ก่อนสร้างเลเยอร์ ให้กำหนดค่าความทนทานที่ต้องการ `FileGdbOptions` ให้คุณระบุ XY, Z, และ M tolerance

```csharp
var options = new FileGdbOptions
{
    XYTolerance = 0.001,
    ZTolerance = 0.1,
    MTolerance = 0.1,
};
```

ค่าต่าง ๆ เหล่านี้เป็นค่ามาตรฐานสำหรับข้อมูลวิศวกรรมความแม่นยำสูง แต่คุณสามารถปรับให้เหมาะกับโครงการของคุณได้

### ขั้นตอนที่ 4: สร้างเลเยอร์ด้วยความทนทานที่ระบุ
สุดท้าย สร้างเลเยอร์ใหม่ภายใน dataset โดยส่งอ็อบเจ็กต์ options ที่กำหนดไว้ไปด้วย

```csharp
using (var layer = dataset.CreateLayer("layer_name", options))
{
    // The layer is created with the provided tolerances, ready for use in ArcGIS features/tools.
}
```

เมื่อบล็อก `using` สิ้นสุดลง เลเยอร์จะถูกบันทึกพร้อมค่าความทนทานที่คุณตั้งไว้

## ปัญหาทั่วไปและวิธีแก้ไข
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|---------|
| **Dataset path not found** | ตัวแปร `dataDir` ชี้ไปยังโฟลเดอร์ที่ไม่มีอยู่ | ตรวจสอบให้แน่ใจว่าโฟลเดอร์มีอยู่หรือสร้างด้วย `Directory.CreateDirectory(dataDir)` |
| **Invalid tolerance values** | ความทนทานต้องเป็นค่าที่ไม่เป็นลบ | ใช้ค่าบวก; หลีกเลี่ยงค่า 0 เว้นแต่คุณต้องการไม่มีความทนทาน |
| **License error** | ไลเซนส์ทดลองหรือชั่วคราวหมดอายุ | ใช้ไลเซนส์ชั่วคราวใหม่หรืออัปเกรดเป็นไลเซนส์เต็ม |

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้ Aspose.GIS for .NET ร่วมกับไลบรารี GIS อื่น ๆ ได้หรือไม่?**  
A: ได้, Aspose.GIS รองรับการทำงานร่วมกัน ทำให้คุณสามารถผสานรวมกับไลบรารีเช่น NetTopologySuite หรือ GDAL ได้

**Q: มีเวอร์ชันทดลองสำหรับ Aspose.GIS for .NET หรือไม่?**  
A: แน่นอน! คุณสามารถสำรวจคุณสมบัติต่าง ๆ ด้วย [free trial version](https://releases.aspose.com/)

**Q: จะขอรับการสนับสนุนสำหรับ Aspose.GIS for .NET ได้อย่างไร?**  
A: เยี่ยมชม [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อเชื่อมต่อกับชุมชนและขอความช่วยเหลือ

**Q: จำเป็นต้องมีไลเซนส์ชั่วคราวสำหรับการทดสอบหรือไม่?**  
A: ใช่, คุณสามารถรับ [temporary license](https://purchase.aspose.com/temporary-license/) สำหรับการทดสอบและประเมินผล

**Q: จะซื้อไลเซนส์ Aspose.GIS for .NET ได้จากที่ไหน?**  
A: คุณสามารถซื้อไลเซนส์ได้จาก [buy page](https://purchase.aspose.com/buy)

## สรุป
ในคู่มือนี้เราได้อธิบายวิธี **สร้าง file GDB dataset**, ตั้งค่าความทนทานของเรขาคณิต, และบันทึกเลเยอร์ที่พร้อมใช้งานด้วย Aspose.GIS for .NET ขั้นตอนเหล่านี้ให้คุณควบคุมความแม่นยำของข้อมูลเชิงพื้นที่ได้อย่างละเอียด ทำให้แอปพลิเคชัน GIS ของคุณมีความน่าเชื่อถือและทำงานร่วมกันได้ดีขึ้น

---  
**อัปเดตล่าสุด:** 2025-12-31  
**ทดสอบด้วย:** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}