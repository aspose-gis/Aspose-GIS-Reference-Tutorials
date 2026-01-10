---
date: 2026-01-10
description: เรียนรู้วิธีสร้างชุดข้อมูล .NET ของไฟล์ฐานข้อมูลภูมิศาสตร์โดยใช้ Aspose.GIS
  สำหรับ .NET คู่มือทีละขั้นตอนเพื่อการจัดการข้อมูล GIS อย่างง่ายดาย
linktitle: Create New File GDB Dataset
second_title: Aspose.GIS .NET API
title: สร้าง File Geodatabase .NET Dataset ด้วย Aspose.GIS
url: /th/net/layer-management/create-new-file-gdb-dataset/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างชุดข้อมูล File Geodatabase .NET ด้วย Aspose.GIS

## บทนำ
ในบทเรียนนี้คุณจะ **สร้างไฟล์ geodatabase .NET** ชุดข้อมูลตั้งแต่เริ่มต้นโดยใช้ Aspose.GIS สำหรับ .NET ไม่ว่าคุณจะกำลังสร้างเครื่องมือ GIS บนเดสก์ท็อป, เว็บ‑เซอร์วิสที่จัดเก็บข้อมูลเชิงพื้นที่, หรือเพียงต้องการวิธีที่เชื่อถือได้ในการสร้าง File Geodatabases ด้วยโปรแกรมมิ่ง คู่มือนี้จะพาคุณผ่านทุกขั้นตอนพร้อมคำอธิบายที่ชัดเจนและบริบทจากโลกจริง

## คำตอบสั้น
- **บทเรียนนี้ครอบคลุมอะไรบ้าง?** การสร้าง File Geodatabase ใหม่, การเพิ่มสองเลเยอร์, และการตรวจสอบชุดข้อมูลด้วย Aspose.GIS สำหรับ .NET  
- **ใช้เวลานานเท่าไหร่?** ประมาณ 10‑15 นาทีสำหรับนักพัฒนาที่คุ้นเคยกับ C#  
- **ข้อกำหนดเบื้องต้น?** สภาพแวดล้อมการพัฒนา .NET, ไลบรารี Aspose.GIS สำหรับ .NET, และโฟลเดอร์ที่สามารถเขียนได้  
- **ใช้ได้กับ .NET Core / .NET 6+ หรือไม่?** ใช่ – API รองรับรันไทม์ .NET สมัยใหม่ทั้งหมด  
- **ต้องมีลิขสิทธิ์หรือไม่?** จำเป็นต้องมีลิขสิทธิ์ Aspose.GIS ชั่วคราวหรือถาวรสำหรับการใช้งานในผลิตภัณฑ์

## File Geodatabase คืออะไร?
File Geodatabase (File GDB) คือที่เก็บข้อมูลแบบโฟลเดอร์ที่บรรจุคลาสฟีเจอร์ GIS, ชุดข้อมูลเรสเตอร์, และเมตาดาต้าที่เกี่ยวข้อง มันให้ประสิทธิภาพการอ่าน/เขียนที่เร็ว, รองรับชุดข้อมูลขนาดใหญ่, และเป็นที่นิยมในระบบนิเวศของ Esri ArcGIS ด้วย Aspose.GIS คุณสามารถสร้างและจัดการฐานข้อมูลเหล่านี้โดยตรงจากโค้ด .NET โดยไม่ต้องพึ่งซอฟต์แวร์ GIS ภายนอก

## ทำไมต้องสร้าง file geodatabase .NET ด้วย Aspose.GIS?
- **ไม่มีการพึ่งพาภายนอก** – ไลบรารีจัดการรายละเอียดรูปแบบไฟล์ทั้งหมด  
- **ข้ามแพลตฟอร์ม** – ทำงานบน Windows, Linux, และ macOS .NET runtimes  
- **สนับสนุนเรขาคณิตครบครัน** – จุด, เส้น, โพลิกอน, และอื่น ๆ  
- **ควบคุมเต็มรูปแบบ** – คุณกำหนดสคีมา, แอตทริบิวต์, และการอ้างอิงเชิงพื้นที่เอง

## ข้อกำหนดเบื้องต้น
ก่อนเริ่มทำตามขั้นตอนต่อไปนี้ให้แน่ใจว่าคุณมี:

- Aspose.GIS สำหรับ .NET ที่ติดตั้งแล้ว คุณสามารถดาวน์โหลดได้จาก [หน้าดาวน์โหลด Aspose.GIS สำหรับ .NET](https://releases.aspose.com/gis/net/)  
- สภาพแวดล้อมการพัฒนา เช่น Visual Studio 2022 (หรือ IDE ใด ๆ ที่รองรับ .NET)  
- โฟลเดอร์ที่สามารถเขียนได้บนเครื่องของคุณซึ่งจะใช้เป็นที่สร้าง GDB ใหม่ – แทนที่ `"Your Document Directory"` ในโค้ดด้วยเส้นทางนั้น  
- ความคุ้นเคยพื้นฐานกับ C# และโครงสร้างโปรเจกต์ .NET

## นำเข้า Namespaces
ก่อนอื่นให้นำเข้า namespaces ที่ให้คุณเข้าถึงคลาสของ Aspose.GIS:

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

## คู่มือขั้นตอน‑โดย‑ขั้นตอน

### ขั้นตอนที่ 1: สร้างชุดข้อมูล File GDB ใหม่
โค้ดส่วนนี่สร้าง File Geodatabase ว่างเปล่า ซึ่งเป็นหัวใจของ **create file geodatabase .net**:

```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Output: 0
    // Continue with subsequent steps...
}
```

**คำอธิบาย:** `Dataset.Create` จะเริ่มต้น GDB ที่เส้นทางที่ระบุโดยใช้ไดรเวอร์ `FileGdb` ณ จุดนี้ชุดข้อมูลยังไม่มีเลเยอร์ใด ๆ จึงจำนวนเลเยอร์เป็นศูนย์

### ขั้นตอนที่ 2: สร้างและเติมข้อมูลให้ `layer_1`
ต่อไปเราจะเพิ่มเลเยอร์แรกที่เก็บแอตทริบิวต์จำนวนเต็มและเรขาคณิตแบบจุด:

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

**คำอธิบาย:**  
- `CreateLayer` สร้างคลาสฟีเจอร์ใหม่ชื่อ **layer_1**  
- กำหนดแอตทริบิวต์จำนวนเต็มชื่อ **value**  
- ลูปจะเพิ่มฟีเจอร์สิบรายการ แต่ละรายการมีค่าเต็มที่ไม่ซ้ำและจุดที่พิกัด *(i, i)*

### ขั้นตอนที่ 3: สร้างและเติมข้อมูลให้ `layer_2`
ต่อไปเป็นการเพิ่มเลเยอร์ที่สองเพื่อแสดงการจัดการเรขาคณิตแบบเส้น:

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

**คำอธิบาย:** โค้ดนี้สร้าง **layer_2** และแทรกฟีเจอร์เดียวที่มีเรขาคณิต `LineString` เชื่อมต่อสองจุด

### ขั้นตอนที่ 4: ตรวจสอบจำนวนเลเยอร์ที่อัปเดต
สุดท้ายให้ยืนยันว่าเลเยอร์ทั้งสองถูกเพิ่มสำเร็จ:

```csharp
Console.WriteLine(dataset.LayersCount); // Output: 2
```

**คำอธิบาย:** ตอนนี้ชุดข้อมูลรายงานว่ามีสองเลเยอร์ แสดงว่ากระบวนการ **create file geodatabase .net** เสร็จสมบูรณ์ตามที่คาดหวัง

## ปัญหาที่พบบ่อยและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| **`UnauthorizedAccessException`** ขณะสร้างชุดข้อมูล | โฟลเดอร์เป็นแบบอ่าน‑อย่างเดียวหรือคุณไม่มีสิทธิ์ | เลือกไดเรกทอรีที่เขียนได้หรือรัน Visual Studio ด้วยสิทธิ์ผู้ดูแลระบบ |
| **`ArgumentException` สำหรับไดรเวอร์** | ชื่อไดรเวอร์พิมพ์ผิดหรือเวอร์ชันไลบรารีไม่รองรับ | ใช้ `Drivers.FileGdb` ตรงตามตัวอย่าง; ตรวจสอบว่าคุณใช้แพคเกจ Aspose.GIS เวอร์ชันล่าสุด |
| **ฟีเจอร์ไม่แสดงใน ArcGIS** | ขาดการอ้างอิงเชิงพื้นที่หรือเรขาคณิตไม่เข้ากัน | ตั้งค่าการอ้างอิงเชิงพื้นที่บนเลเยอร์หากจำเป็นและตรวจสอบว่าเรขาคณิตถูกต้อง |

## คำถามที่พบบ่อย
### ถ: สามารถใช้ Aspose.GIS สำหรับ .NET ร่วมกับไลบรารี GIS อื่นได้หรือไม่?
Aspose.GIS สำหรับ .NET เป็นชุดเครื่องมืออิสระ; อย่างไรก็ตามคุณสามารถผสานรวมกับไลบรารี .NET อื่นเพื่อเพิ่มฟังก์ชันได้

### ถ: มีฟอรั่มชุมชนสำหรับการสนับสนุน Aspose.GIS หรือไม่?
มี, คุณสามารถเข้าร่วมการสนทนาและขอความช่วยเหลือได้ที่ [Aspose.GIS Forum](https://forum.aspose.com/c/gis/33)

### ถ: จะขอรับลิขสิทธิ์ชั่วคราวสำหรับ Aspose.GIS อย่างไร?
เยี่ยมชมหน้า [Temporary License](https://purchase.aspose.com/temporary-license/) เพื่อดูข้อมูลการขอรับลิขสิทธิ์ชั่วคราว

### ถ: มีตัวอย่างและเอกสารเพิ่มเติมหรือไม่?
สำรวจ [Aspose.GIS documentation](https://reference.aspose.com/gis/net/) เพื่อดูตัวอย่างเพิ่มเติมและข้อมูลเชิงลึก

### ถ: จะซื้อ Aspose.GIS สำหรับ .NET ได้จากที่ไหน?
คุณสามารถสั่งซื้อได้ที่ [purchase page](https://purchase.aspose.com/buy)

## สรุป
คุณได้ **สร้างไฟล์ geodatabase .NET** ชุดข้อมูลสำเร็จ, เพิ่มเลเยอร์สองชั้นที่แตกต่างกัน, และตรวจสอบผลลัพธ์ด้วย Aspose.GIS พื้นฐานนี้ช่วยให้คุณสร้างแอปพลิเคชัน GIS ที่ซับซ้อนยิ่งขึ้น—เพิ่มเลเยอร์, กำหนดสคีมาที่ซับซ้อน, หรือผสานรวมกับเว็บเซอร์วิส สำรวจ API ของ Aspose.GIS ต่อไปเพื่อทำงานกับข้อมูลเรสเตอร์, คำถามเชิงพื้นที่, และการดำเนินการเรขาคณิตขั้นสูง

---

**อัปเดตล่าสุด:** 2026-01-10  
**ทดสอบกับ:** Aspose.GIS สำหรับ .NET 24.11 (หรือเวอร์ชันล่าสุด)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}