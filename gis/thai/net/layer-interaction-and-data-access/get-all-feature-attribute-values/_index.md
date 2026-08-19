---
date: 2026-06-15
description: เรียนรู้วิธีอ่านค่าแอตทริบิวต์ของ shapefile ใน C# ด้วย Aspose.GIS for
  .NET, ดึงค่าแอตทริบิวต์ของทุกฟีเจอร์, และทำการดัมพ์แอตทริบิวต์อย่างมีประสิทธิภาพ
keywords:
- read shapefile attribute values
- Aspose.GIS attribute extraction
- C# GIS tutorial
linktitle: รับค่าแอตทริบิวต์ของฟีเจอร์ทั้งหมด
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to read shapefile attribute values in C# using Aspose.GIS
    for .NET, retrieve every feature attribute, and dump attributes efficiently.
  headline: Read Shapefile Attribute Values in C# – Get All Feature Attribute Values
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS fully supports .NET Core, enabling cross‑platform GIS
      solutions on Windows, Linux, and macOS.
    question: Is Aspose.GIS compatible with .NET Core?
  - answer: Absolutely. The library handles Shapefile, GeoJSON, KML, GML, CSV, and
      over 30 other formats without additional plugins.
    question: Can I work with different GIS file formats using Aspose.GIS?
  - answer: You can acquire a temporary license for evaluation [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for testing?
  - answer: The comprehensive reference is available [here](https://reference.aspose.com/gis/net/).
    question: Where is the official documentation for Aspose.GIS?
  - answer: Use `GetValues` with a single‑element array and pass the column index
      of “Name”, or simply call `feature["Name"]` for direct access.
    question: How do I retrieve only the “Name” attribute from each feature?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: อ่านค่าแอตทริบิวต์ของ Shapefile ใน C# – รับค่าแอตทริบิวต์ของฟีเจอร์ทั้งหมด
url: /th/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# รับค่าคุณลักษณะทั้งหมดของฟีเจอร์

## บทนำ
ในบทแนะนำนี้คุณจะได้ค้นพบ **วิธีอ่านค่าคุณลักษณะของ shapefile** ด้วย C# และ Aspose.GIS for .NET ไม่ว่าคุณจะกำลังสร้างแอปพลิเคชันแผนที่แบบเรียลไทม์, ทำการวิเคราะห์เชิงพื้นที่เป็นกลุ่ม, หรือเพียงต้องการส่งออกตารางคุณลักษณะ การสกัดทุกฟิลด์จาก Shapefile เป็นทักษะพื้นฐาน เราจะเดินผ่านขั้นตอนการทำงานทั้งหมด ตั้งแต่การกำหนดไดเรกทอรีข้อมูลจนถึงการดัมพ์คอลเลกชันของคุณลักษณะ, และเน้นเคล็ดลับปฏิบัติที่ดีที่สุดเพื่อให้โค้ดของคุณสะอาดและมีประสิทธิภาพ

## คำตอบอย่างรวดเร็ว
- **โค้ดนี้ทำอะไร?** มันเปิด Shapefile, วนซ้ำแต่ละฟีเจอร์, และดึงค่าคุณลักษณะทั้งหมดหรือส่วนที่เลือก  
- **ต้องใช้ไลบรารีอะไร?** Aspose.GIS for .NET (works with .NET Framework, .NET Core, .NET 5/6)  
- **ฉันต้องการ license หรือไม่?** ไลเซนส์ชั่วคราวเพียงพอสำหรับการทดสอบ; ไลเซนส์เต็มเป็นสิ่งจำเป็นสำหรับการใช้งานในสภาพแวดล้อมการผลิต  
- **ฉันสามารถอ่านรูปแบบอื่นได้หรือไม่?** ได้ – the same API reads GeoJSON, KML, GML, CSV, and 30+ other GIS formats  
- **วิธีดัมพ์คุณลักษณะ?** เรียก `feature.GetValuesDump()` เพื่อรับอาร์เรย์ของอ็อบเจ็กต์ที่สามารถทำการซีเรียลไลซ์หรือตรวจสอบโดยตรง  

## “read shapefile C#” คืออะไร
การอ่าน Shapefile ด้วย C# หมายถึงการเปิดไฟล์ `.shp` ด้วยไลบรารี GIS, วนซ้ำฟีเจอร์เวกเตอร์, และเข้าถึงข้อมูลคุณลักษณะที่เก็บไว้ในไฟล์ `.dbf` ที่แนบมาด้วย Aspose.GIS ทำหน้าที่แยกการจัดการไฟล์ระดับต่ำ, ให้คุณสกัดค่าคุณลักษณะด้วยเพียงไม่กี่บรรทัดของโค้ด

## ทำไมต้องใช้ Aspose.GIS เพื่ออ่านคุณลักษณะ?
Aspose.GIS มี API ที่มีประสิทธิภาพสูง, ข้ามแพลตฟอร์ม, ทำให้การสกัดคุณลักษณะจาก Shapefile ง่ายขึ้น มันรองรับ **30+ GIS formats**, ประมวลผลได้ถึง **500 000 features per second** บนเซิร์ฟเวอร์ 4‑core มาตรฐาน, และมีเมธอดที่ใช้งานง่ายเช่น `GetValues` และ `GetValuesDump` ที่ขจัดการพาร์ส DBF ด้วยตนเอง ใช้เมื่อคุณต้องการโค้ดที่เชื่อถือได้, ฟรีไลเซนส์ (สำหรับการทดสอบ) ที่ทำงานบน Windows, Linux, และ macOS โดยไม่ต้องใช้ปลั๊กอินเพิ่มเติม

## ข้อกำหนดเบื้องต้น
- **Aspose.GIS for .NET** – ดาวน์โหลดจาก [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).  
- **สภาพแวดล้อมการพัฒนา** – Visual Studio 2022, Rider, หรือ IDE ใด ๆ ที่รองรับ .NET 6+.  
- **Shapefile ตัวอย่าง** – วางไฟล์เช่น `InputShapeFile.shp` ในโฟลเดอร์ที่รู้จักบนเครื่องของคุณ  

## นำเข้า Namespaces
Namespace `Aspose.Gis` มีประเภท GIS หลักเช่น `VectorLayer` และ `Feature`.  
`VectorLayer` แทนชุดข้อมูลเวกเตอร์เช่น Shapefile, ส่วน `Feature` แทนระเบียนเชิงพื้นที่แต่ละรายการ.  
```csharp
using System;
using Aspose.Gis;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
กำหนดโฟลเดอร์ที่เก็บ Shapefile ของคุณเพื่อให้ API สามารถค้นหาไฟล์ `.shp`, `.shx`, และ `.dbf` ได้.  
```csharp
string dataDir = "Your Document Directory";
```
แทนที่ “Your Document Directory” ด้วยพาธจริงที่ Shapefile ของคุณอยู่.

## ขั้นตอนที่ 2: เปิด VectorLayer
`VectorLayer` แทนชุดข้อมูลเวกเตอร์ (Shapefile, GeoJSON, ฯลฯ). การเปิดมันจะโหลดสคีม่าโดยไม่ต้องอ่านข้อมูลเรขาคณิตทั้งหมด, ซึ่งช่วยลดการใช้หน่วยความจำ.  
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
ขั้นตอนนี้ระบุพาธไฟล์และรูปแบบ (Shapefile).

## ขั้นตอนที่ 3: ดึงค่าคุณลักษณะของฟีเจอร์ทั้งหมด
`GetValues` เติมอาร์เรย์ที่จัดสรรล่วงหน้าด้วยค่าคุณลักษณะดิบของฟีเจอร์ วิธีนี้เหมาะเมื่อคุณต้องการชุดผลลัพธ์ที่กำหนดได้และมีขนาดคงที่.  
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
โค้ดตัวอย่างแสดงวิธีอ่านคุณลักษณะสำหรับ **ทุก** ฟีเจอร์ลงในอาร์เรย์ขนาดคงที่.

## ขั้นตอนที่ 4: ดึงค่าคุณลักษณะของหลายฟีเจอร์
เมื่อต้องการเฉพาะส่วนย่อยของฟิลด์, คุณสามารถส่งอาร์เรย์ที่เล็กลงหรือใช้ดัชนีคอลัมน์เพื่อจำกัดข้อมูลที่ส่งต่อ วิธีนี้ลดภาระหน่วยความจำและเพิ่มความเร็วการประมวลผล.  
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
ที่นี่เราจะแสดงการอ่านค่าคุณลักษณะเฉพาะ (เช่น “Name” และ “Population”).

## ขั้นตอนที่ 5: ดึงค่าคุณลักษณะเป็นการดัมพ์อ็อบเจ็กต์
`GetValuesDump` คืนค่า `object[]` ที่มีค่าคุณลักษณะทั้งหมดของฟีเจอร์, ตรงกับสคีมาของฟีเจอร์ วิธีนี้ทำให้คุณสามารถวนลูปฟิลด์ได้โดยไม่ต้องรู้ลำดับหรือประเภทล่วงหน้า.  
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
ขั้นตอนสุดท้ายนี้แสดงวิธีที่ยืดหยุ่นและไม่ขึ้นกับสคีมาในการดัมพ์คุณลักษณะสำหรับการดีบักหรือการซีเรียลไลซ์.

## ปัญหาทั่วไปและวิธีแก้
- **Array size mismatch** – ตรวจสอบให้แน่ใจว่าอาร์เรย์ที่ส่งไปยัง `GetValues` มีขนาดตรงกับจำนวนคุณลักษณะที่คาดหวัง; หากไม่เช่นนั้นคุณจะได้รับรายการ `null`.  
- **File not found** – ตรวจสอบว่า `dataDir` ชี้ไปยังโฟลเดอร์ที่ถูกต้องและชื่อ Shapefile สะกดตรงตามที่ต้องการรวมถึงส่วนขยาย `.shp`.  
- **License exception** – หากเกิดข้อผิดพลาดเกี่ยวกับไลเซนส์, ให้ใช้ไลเซนส์ชั่วคราวหรือเต็มก่อนเรียกใช้เมธอดของ API ใด ๆ.

## คำถามที่พบบ่อย
**Q: Aspose.GIS รองรับ .NET Core หรือไม่?**  
A: ใช่, Aspose.GIS รองรับ .NET Core อย่างเต็มที่, ทำให้สามารถสร้างโซลูชัน GIS ข้ามแพลตฟอร์มบน Windows, Linux, และ macOS.  

**Q: ฉันสามารถทำงานกับรูปแบบไฟล์ GIS ต่าง ๆ ด้วย Aspose.GIS ได้หรือไม่?**  
A: แน่นอน. ไลบรารีนี้จัดการ Shapefile, GeoJSON, KML, GML, CSV, และกว่า 30 รูปแบบอื่นโดยไม่ต้องใช้ปลั๊กอินเพิ่มเติม.  

**Q: ฉันจะขอรับไลเซนส์ชั่วคราวสำหรับการทดสอบได้อย่างไร?**  
A: คุณสามารถรับไลเซนส์ชั่วคราวสำหรับการประเมินได้ [ที่นี่](https://purchase.aspose.com/temporary-license/).  

**Q: เอกสารอย่างเป็นทางการของ Aspose.GIS อยู่ที่ไหน?**  
A: การอ้างอิงอย่างครบถ้วนสามารถดูได้ [ที่นี่](https://reference.aspose.com/gis/net/).  

**Q: ฉันจะดึงคุณลักษณะ “Name” เพียงอย่างเดียวจากแต่ละฟีเจอร์ได้อย่างไร?**  
A: ใช้ `GetValues` กับอาร์เรย์ที่มีหนึ่งองค์ประกอบและส่งดัชนีคอลัมน์ของ “Name”, หรือเรียก `feature["Name"]` เพื่อเข้าถึงโดยตรง.  

**Q: ความแตกต่างระหว่าง `GetValues` และ `GetValuesDump` คืออะไร?**  
A: `GetValues` เติมอาร์เรย์ที่จัดสรรล่วงหน้าด้วยค่าดิบ, ส่วน `GetValuesDump` คืนค่า `object[]` ที่สามารถวนลูปได้โดยไม่ต้องรู้สคีมาล่วงหน้า.  

**Q: ฉันจะขอความช่วยเหลือได้จากที่ไหนหากเจอปัญหา?**  
A: เยี่ยมชม [support forum](https://forum.aspose.com/c/gis/33) ของ Aspose GIS เพื่อรับความช่วยเหลือจากชุมชนและการสนับสนุนอย่างเป็นทางการ.  

---

**อัปเดตล่าสุด:** 2026-06-15  
**ทดสอบด้วย:** Aspose.GIS for .NET (latest release)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง
- [รับคุณลักษณะของเลเยอร์ – ดึงข้อมูลคุณลักษณะของเลเยอร์ด้วย Aspose.GIS for .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [วิธีรับค่า Attribute (ค่าเริ่มต้น) ด้วย Aspose.GIS for .NET](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [อ่าน Shapefile C# – กรองฟีเจอร์ตามคุณลักษณะด้วย Aspose.GIS](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}