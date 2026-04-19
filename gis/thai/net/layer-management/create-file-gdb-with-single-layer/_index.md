---
date: 2026-01-10
description: เรียนรู้วิธีสร้างเลเยอร์เวกเตอร์ใน File Geodatabase ด้วย Aspose.GIS สำหรับ
  .NET จัดการข้อมูลเชิงพื้นที่ด้วยระบบอ้างอิง WGS84 และตัวเลือกไฟล์ gdb.
linktitle: Create File GDB with Single Layer
second_title: Aspose.GIS .NET API
title: สร้างเลเยอร์เวกเตอร์ในไฟล์ GDB – บทแนะนำ Aspose.GIS .NET
url: /th/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้าง Vector Layer ใน File GDB

## คำแนะนำ
หากคุณต้องการ **create vector layer** ภายใน File Geodatabase (GDB) และจัดการข้อมูลเชิงพื้นที่อย่างมีประสิทธิภาพ Aspose.GIS for .NET จะมอบวิธีการที่สะอาดและเน้นโค้ดเป็นหลัก ในคู่มือขั้นตอนนี้ เราจะแสดงวิธีเขียนฟีเจอร์เส้น, กำหนดค่า file gdb options, และทำงานกับ spatial reference WGS84 — ทั้งหมดในไม่กี่บรรทัดของ C# เมื่อเสร็จสิ้นคุณจะสามารถนับจำนวนฟีเจอร์ในเลเยอร์และนำ GDB ที่ได้ไปผสานกับกระบวนการแมปหรือวิเคราะห์ใด ๆ บน .NET

## คำตอบอย่างรวดเร็ว
- **What does “create vector layer” mean?** หมายถึงการเพิ่มชุดข้อมูลเวกเตอร์ใหม่ (จุด, เส้น, หรือโพลิกอน) ไปยังไฟล์ geodatabase.  
- **Which library should I use?** Aspose.GIS for .NET ให้การสนับสนุนเต็มรูปแบบสำหรับการสร้างและแก้ไข File GDB.  
- **Do I need a license for development?** เวอร์ชันทดลองฟรีใช้งานได้สำหรับการทดสอบ; ต้องมีใบอนุญาตเชิงพาณิชย์สำหรับการใช้งานจริง.  
- **Can I set the spatial reference?** ได้ – ใช้ `SpatialReferenceSystem.Wgs84` สำหรับ datum WGS84 ที่ทั่วไป.  
- **How many lines of code?** น้อยกว่า 30 บรรทัดสำหรับการสร้าง GDB, เพิ่มฟีเจอร์เส้น, และอ่านจำนวนฟีเจอร์กลับมา.

## การดำเนินการ “create vector layer” คืออะไร?
การสร้าง vector layer หมายถึงการกำหนดตารางใหม่ภายใน geodatabase ที่เก็บวัตถุเชิงเรขาคณิต (จุด, เส้น, โพลิกอน) พร้อมกับแอตทริบิวต์ของมัน การดำเนินการนี้เป็นพื้นฐานสำหรับแอปพลิเคชัน GIS ใด ๆ ที่ต้อง **manage geospatial data**.

## ทำไมต้องใช้ Aspose.GIS เพื่อสร้าง vector layer?
- **Zero external dependencies** – API ทำงานได้ทันทีบน .NET Framework, .NET Core, และ .NET 5/6.  
- **Full support for File GDB** – คุณสามารถกำหนดค่า `FileGdbOptions` เพื่อควบคุมการบีบอัด, ดัชนีเชิงพื้นที่, และอื่น ๆ.  
- **Built‑in spatial reference handling** – เพียงแค่ส่ง `SpatialReferenceSystem.Wgs84` เพื่อทำงานในระบบพิกัดทั่วโลก.  
- **Straightforward API** – เขียนฟีเจอร์เส้น, เพิ่มลงในเลเยอร์, และดึงจำนวนฟีเจอร์ด้วยการเรียกเมธอดเพียงไม่กี่ครั้ง.

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำงาน โปรดตรวจสอบว่าคุณมี:

1. **Aspose.GIS for .NET** – ดาวน์โหลดจาก [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).  
2. **A .NET development environment** – Visual Studio, Rider, หรือ `dotnet` CLI.  
3. **A folder** ที่จะสร้าง File GDB (เราจะเรียกมันว่า *Your Document Directory*).

## นำเข้า Namespaces
เพิ่ม `using` statements ที่จำเป็นที่ส่วนบนของไฟล์ C# ของคุณ:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```

## ขั้นตอนที่ 1: ตั้งค่า Your Document Directory ของคุณ
```csharp
string dataDir = "Your Document Directory";
```
แทนที่ `"Your Document Directory"` ด้วยเส้นทางเต็มที่คุณต้องการให้ File GDB อยู่.

## ขั้นตอนที่ 2: สร้าง File Geodatabase พร้อมเลเยอร์เดียว
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
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
โค้ดสแนปช็อตนี้ **creates a vector layer** ด้วย `FileGdbOptions`, เขียนฟีเจอร์เส้นง่าย ๆ, และบันทึกลงใน File GDB ที่ใช้ **spatial reference WGS84**.

## ขั้นตอนที่ 3: เปิด File Geodatabase และดึงข้อมูลเลเยอร์
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```
ที่นี่เราจะ **count features layer** โดยเปิดชุดข้อมูลและพิมพ์จำนวนฟีเจอร์ – ในกรณีนี้คือ `1`.

## ปัญหาทั่วไปและวิธีแก้
| Issue | Reason | Fix |
|-------|--------|-----|
| **`File not found`** | ตัวแปร `path` ไม่ถูกต้อง | ตรวจสอบให้แน่ใจว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่มีอยู่และ `path` รวมกับชื่อไฟล์อย่างถูกต้อง เช่น `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | ใช้ประเภทเรขาคณิตที่ไม่รองรับใน File GDB | ใช้ `Point`, `LineString`, หรือ `Polygon` สำหรับเลเยอร์พื้นฐาน. |
| **`License not set`** | รันโดยไม่มีใบอนุญาตที่ถูกต้องในสภาพแวดล้อมการผลิต | ลงทะเบียนใบอนุญาตของคุณด้วย `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.GIS for .NET ในโปรเจกต์ .NET ที่มีอยู่ของฉันได้หรือไม่?
ได้, Aspose.GIS for .NET สามารถรวมเข้ากับโปรเจกต์ .NET ของคุณได้อย่างราบรื่น.

### มีเวอร์ชันทดลองสำหรับ Aspose.GIS for .NET หรือไม่?
มี, คุณสามารถสำรวจคุณสมบัติของ Aspose.GIS for .NET ได้โดยดาวน์โหลด [free trial version](https://releases.aspose.com/).

### ฉันจะหาเอกสารรายละเอียดสำหรับ Aspose.GIS for .NET ได้จากที่ไหน?
ดูที่ [documentation](https://reference.aspose.com/gis/net/) เพื่อรับข้อมูลครบถ้วนเกี่ยวกับ Aspose.GIS for .NET.

### ฉันจะรับการสนับสนุนสำหรับ Aspose.GIS for .NET ได้อย่างไร?
เยี่ยมชม [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อรับการสนับสนุนจากชุมชนและความช่วยเหลือ.

### มีใบอนุญาตชั่วคราวสำหรับ Aspose.GIS for .NET หรือไม่?
มี, คุณสามารถขอ [temporary license](https://purchase.aspose.com/temporary-license/) สำหรับ Aspose.GIS for .NET.

---

**อัปเดตล่าสุด:** 2026-01-10  
**ทดสอบกับ:** Aspose.GIS 24.11 for .NET  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}