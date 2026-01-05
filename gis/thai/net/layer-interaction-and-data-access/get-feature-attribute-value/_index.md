---
description: เรียนรู้วิธีใช้การแคสท์ประเภทแบบไดนามิกกับ Aspose.GIS สำหรับ .NET เพื่อดึงค่าคุณลักษณะจากไฟล์
  shapefile รวมถึงตัวอย่างการแคสท์ประเภทอย่างชัดเจน
linktitle: Get Feature Attribute Value using Dynamic Type Casting
second_title: Aspose.GIS .NET API
title: รับค่าแอตทริบิวต์ของฟีเจอร์โดยใช้การแคสต์ประเภทแบบไดนามิก
url: /th/net/layer-interaction-and-data-access/get-feature-attribute-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# รับค่าแอตทริบิวต์ของฟีเจอร์โดยใช้การแคสท์แบบไดนามิก

## บทนำ
ยินดีต้อนรับสู่โลกของ Aspose.GIS for .NET, ไลบรารีที่ทรงพลังซึ่งช่วยให้นักพัฒนา .NET ทำงานกับข้อมูลระบบสารสนเทศภูมิศาสตร์ (GIS) ได้อย่างราบรื่น ในบทเรียนนี้คุณจะได้ค้นพบว่า **dynamic type casting** ทำให้กระบวนการดึงค่าแอตทริบิวต์ของฟีเจอร์จาก shapefile ง่ายขึ้นอย่างไร พร้อมกับอธิบายวิธี **explicit type casting** แบบคลาสสิก ไม่ว่าคุณจะกำลังอ่าน shapefile ในแอปพลิเคชัน .NET หรือจำเป็นต้อง **fetch attribute values** เพื่อการวิเคราะห์ เทคนิคเหล่านี้จะทำให้โค้ดของคุณสะอาดและยืดหยุ่นมากขึ้น

## คำตอบอย่างรวดเร็ว
- **What is dynamic type casting?** วิธีการใน runtime เพื่อดึงค่าแอตทริบิวต์โดยไม่ต้องระบุประเภทเป้าหมายล่วงหน้า.  
- **Why use Aspose.GIS?** มันให้ API ที่เป็นเอกภาพสำหรับอ่านข้อมูล shapefile .NET และรองรับทั้งสองวิธีการแคสท์.  
- **Do I need a license?** มีรุ่นทดลองฟรี; จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 และรุ่นต่อไป.  
- **Can I fetch attribute values from large files?** ได้—ทำการวนซ้ำฟีเจอร์อย่างมีประสิทธิภาพตามตัวอย่าง

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มบทเรียน โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมแล้ว:
- ความเข้าใจพื้นฐานเกี่ยวกับการพัฒนา .NET.  
- มี Visual Studio ติดตั้งบนเครื่องของคุณ.  
- ไลบรารี Aspose.GIS for .NET, ซึ่งคุณสามารถดาวน์โหลดได้จาก [download link](https://releases.aspose.com/gis/net/).  
- คุ้นเคยกับแนวคิดและคำศัพท์ของ GIS.

## นำเข้า Namespaces
เพื่อเริ่มต้นโปรเจกต์ของคุณ ให้แน่ใจว่าคุณได้นำเข้า namespaces ที่จำเป็น ขั้นตอนนี้สำคัญสำหรับการเข้าถึงฟังก์ชันที่ Aspose.GIS for .NET ให้มา รวม namespaces ต่อไปนี้ในโค้ดของคุณ:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## วิธีใช้ Dynamic Type Casting เพื่อดึงค่าแอตทริบิวต์
ด้านล่างเป็นคำแนะนำแบบขั้นตอนที่พาคุณผ่านการตั้งค่าโปรเจกต์, การเปิด shapefile, และการดึงค่าแอตทริบิวต์โดยใช้ทั้ง **explicit type casting** และ **dynamic type casting**.

### ขั้นตอนที่ 1: ตั้งค่าโปรเจกต์ของคุณ
สร้างโปรเจกต์ .NET ใหม่ใน Visual Studio และอ้างอิงไลบรารี Aspose.GIS

### ขั้นตอนที่ 2: กำหนดไดเรกทอรีเอกสารของคุณ
ตั้งค่าเส้นทางไปยังไดเรกทอรีเอกสารของคุณ ซึ่งเป็นที่ตั้งของ shapefile (`InputShapeFile.shp`) ของคุณ
```csharp
string dataDir = "Your Document Directory";
```

### ขั้นตอนที่ 3: เปิด Vector Layer
เปิด vector layer ด้วย Aspose.GIS ตรวจสอบให้แน่ใจว่าได้ระบุ driver ที่ใช้ ในกรณีนี้คือ Shapefile driver
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the vector layer goes here
}
```

### ขั้นตอนที่ 4: ดึงค่าแอตทริบิวต์ของฟีเจอร์
ตอนนี้ให้วนลูปผ่านแต่ละฟีเจอร์ใน layer และดึงค่าแอตทริบิวต์ Aspose.GIS มีวิธีต่าง ๆ สำหรับการ **fetch attribute values**.

#### กรณีที่ 1: Explicit Type Casting
```csharp
for (int i = 0; i < layer.Count; i++)
{
    Feature feature = layer[i];
    Console.WriteLine("Entry {0} information\n ========================", i);
    string nameValue = feature.GetValue<string>("name"); // attribute name is case-sensitive
    int ageValue = feature.GetValue<int>("age");
    string dobValue = feature.GetValue<DateTime>("dob").ToString();
    Console.WriteLine("Attribute value for feature #{0} is: {1}, {2}", nameValue, ageValue, dobValue);
}
```

#### กรณีที่ 2: Dynamic Type Casting
```csharp
for (int i = 0; i < layer.Count; i++)
{
    Feature feature = layer[i];
    Console.WriteLine("Entry {0} information\n ========================", i);
    var objName = feature.GetValue("name"); // attribute name is case-sensitive
    var objAge = feature.GetValue("age");
    var objDob = feature.GetValue("dob");
    Console.WriteLine("Attribute object for feature #{0} is: {1}, {2}", objName, objAge, objDob);
}
```

> **Pro tip:** ใช้ dynamic type casting เมื่อคุณไม่แน่ใจในประเภทข้อมูลที่แน่นอนของแอตทริบิวต์หรือเมื่อคุณต้องการเขียนโค้ดทั่วไปที่ทำงานได้กับหลาย shapefile. เปลี่ยนไปใช้ explicit type casting เมื่อคุณต้องการความปลอดภัยของประเภทในระดับคอมไพล์.

## ปัญหาทั่วไปและวิธีแก้ไข
- **Attribute name mismatch:** ชื่อแอตทริบิวต์ของ GIS แยกแยะตัวพิมพ์ใหญ่‑เล็ก ตรวจสอบการสะกดให้ตรงกับสคีมาของ shapefile อย่างละเอียด.  
- **Null values:** `GetValue` คืนค่า `null` สำหรับแอตทริบิวต์ที่หายไป; ควรจัดการอย่างเหมาะสมเพื่อหลีกเลี่ยง `NullReferenceException`.  
- **Large datasets:** ใช้การวนซ้ำด้วย `foreach` หรือแบ่งหน้าเพื่อ ลดการใช้หน่วยความจำ.

## คำถามที่พบบ่อย
### Q: Is Aspose.GIS suitable for both beginners and experienced developers?
A: แน่นอน! Aspose.GIS รองรับนักพัฒนาทุกระดับความชำนาญ ให้ API ที่ใช้งานง่ายสำหรับการจัดการข้อมูล GIS.

### Q: Can I use Aspose.GIS in my commercial projects?
A: ใช่, Aspose.GIS เป็นผลิตภัณฑ์เชิงพาณิชย์ คุณสามารถดูรายละเอียดลิขสิทธิ์ได้ที่ [purchase page](https://purchase.aspose.com/buy).

### Q: Are temporary licenses available for testing purposes?
A: มี, คุณสามารถรับลิขสิทธิ์ชั่วคราวสำหรับการทดสอบได้จาก [here](https://purchase.aspose.com/temporary-license/).

### Q: Where can I find community support for Aspose.GIS?
A: เข้าร่วมการสนทนาที่ [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อขอความช่วยเหลือและเชื่อมต่อกับผู้ใช้คนอื่น ๆ.

### Q: Is there a free trial version of Aspose.GIS?
A: แน่นอน! คุณสามารถสำรวจคุณสมบัติของ Aspose.GIS ได้โดยดาวน์โหลดรุ่นทดลองฟรีจาก [here](https://releases.aspose.com/).

### Q: How do I get shapefile attribute values without knowing their types?
A: ใช้วิธี dynamic type casting (`feature.GetValue("attributeName")`) ซึ่งจะคืนค่าที่เป็น `object` ที่คุณสามารถแคสท์ได้ใน runtime.

### Q: Can I read shapefile .NET data in a .NET Core application?
A: ใช่, Aspose.GIS for .NET รองรับ .NET Core, .NET 5, และรุ่นต่อไปอย่างเต็มที่.

## สรุป
ขอแสดงความยินดี! คุณได้เรียนรู้วิธีใช้ Aspose.GIS for .NET เพื่อดึงค่าแอตทริบิวต์ของฟีเจอร์โดยใช้ทั้ง **explicit type casting** และ **dynamic type casting** แล้ว เทคนิคเหล่านี้ทำให้คุณสามารถ **get shapefile attribute** ได้อย่างมีประสิทธิภาพ ไม่ว่าจะเป็นการสร้างเครื่องมือ GIS บนเดสก์ท็อปหรือการรวมการวิเคราะห์เชิงพื้นที่เข้าในเว็บเซอร์วิส

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-01-05  
**ทดสอบด้วย:** Aspose.GIS for .NET (latest)  
**ผู้เขียน:** Aspose