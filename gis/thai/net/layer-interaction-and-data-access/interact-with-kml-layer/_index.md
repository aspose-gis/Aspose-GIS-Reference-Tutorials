---
date: 2026-01-07
description: เรียนรู้วิธีเขียนไฟล์ KML ด้วย Aspose.GIS สำหรับ .NET วิธีสร้าง KML เพิ่มแอตทริบิวต์แบบบูลีน
  และสร้างเส้นเชื่อมต่อในแอปพลิเคชันของคุณ
linktitle: Interact with KML Layer
second_title: Aspose.GIS .NET API
title: วิธีเขียนไฟล์ KML ด้วย Aspose.GIS สำหรับ .NET
url: /th/net/layer-interaction-and-data-access/interact-with-kml-layer/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีเขียนไฟล์ KML ด้วย Aspose.GIS สำหรับ .NET

## บทนำ
ในโลกที่ขับเคลื่อนด้วยข้อมูลในปัจจุบัน ความสามารถในการ **write KML file** ด้วยโปรแกรมมิ่งให้คุณสามารถแชร์ข้อมูลภูมิศาสตร์ข้ามแพลตฟอร์ม, แสดงเส้นทางบนแผนที่, และบูรณาการข้อมูลตำแหน่งลงในเว็บหรือแอปมือถือได้อย่างง่ายดาย Aspose.GIS for .NET ทำให้กระบวนการนี้เป็นเรื่องตรงไปตรงมา ช่วยให้คุณโฟกัสที่ตรรกะของแอปพลิเคชันแทนการจัดการรายละเอียดของรูปแบบไฟล์ ในบทแนะนำนี้เราจะพาคุณผ่านการสร้าง KML layer, การเพิ่มแอตทริบิวต์ (รวมถึงแอตทริบิวต์ boolean), และการสร้างเรขาคณิต line string — ทั้งหมดด้วยโค้ดที่ชัดเจนเป็นขั้นตอน

## คำตอบสั้น
- **What does “write KML file” mean?** การสร้างเอกสาร KML (Keyhole Markup Language) ที่อธิบายลักษณะทางภูมิศาสตร์ เช่น จุด, เส้น, และหลายเหลี่ยม  
- **Which library is best for .NET?** Aspose.GIS for .NET ให้ API ที่ใช้งานง่ายสำหรับการสร้างและแก้ไขไฟล์ KML  
- **Do I need a license for development?** รุ่นทดลองฟรีใช้สำหรับการประเมิน; จำเป็นต้องมีลิขสิทธิ์สำหรับการใช้งานจริง  
- **Can I add custom attributes?** ได้ – คุณสามารถเพิ่มแอตทริบิวต์ประเภท string, integer, boolean, และ double ให้กับแต่ละฟีเจอร์  
- **Is geometry creation supported?** แน่นอน – คุณสามารถสร้างจุด, line strings, polygons และอื่น ๆ  

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มการเดินทางนี้ โปรดตรวจสอบว่าคุณมีข้อกำหนดต่อไปนี้พร้อมใช้งาน:
- Aspose.GIS for .NET: ดาวน์โหลดและติดตั้งไลบรารีจาก [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/)  
- Development Environment: ตั้งค่าสภาพแวดล้อมการพัฒนาที่เหมาะสม เช่น Visual Studio เพื่อบูรณาการ Aspose.GIS อย่างราบรื่นในโครงการ .NET ของคุณ  

## นำเข้า Namespaces
ก่อนที่เราจะเริ่มโต้ตอบกับ KML layers, อย่าลืมรวม namespaces ที่จำเป็นในโปรเจกต์ของคุณ ขั้นตอนนี้ทำให้คุณเข้าถึงคลาสและเมธอดที่ต้องใช้สำหรับการจัดการข้อมูลเชิงพื้นที่ได้

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Drawing;
using System.Threading;
using Aspose.Gis.Formats.Kml;
using Aspose.Gis.Formats.Kml.Styles;
using Aspose.Gis.Geometries;
using Point = Aspose.Gis.Geometries.Point;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
กำหนดพาธไปยังไดเรกทอรีเอกสารของคุณที่ไฟล์ KML จะถูกจัดเก็บ

```csharp
string dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 2: สร้าง KML Layer
เริ่มต้น KML layer ด้วย Aspose.GIS โดยระบุพาธสำหรับไฟล์ KML

```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```

## ขั้นตอนที่ 3: กำหนดแอตทริบิวต์ (เพิ่มแอตทริบิวต์ boolean)
เพิ่มแอตทริบิวต์ลงใน KML layer เพื่อแสดงประเภทข้อมูลต่าง ๆ เช่น string, integer, **boolean**, และ double นี่คือจุดที่คุณ “add boolean attribute” ให้กับแต่ละฟีเจอร์

```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```

## ขั้นตอนที่ 4: สร้างและเติมข้อมูลฟีเจอร์ (สร้าง line string)
สร้างฟีเจอร์ที่แทนเอนทิตีเชิงพื้นที่และกำหนดค่าให้กับแอตทริบิวต์ที่กำหนดไว้ ที่นี่เราจะ **create line string** เรขาคณิตเพื่อแสดงเส้นทางง่าย ๆ

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```

## ขั้นตอนที่ 5: เพิ่มฟีเจอร์อีกหนึ่งรายการ
ทำซ้ำกระบวนการเพื่อเพิ่มฟีเจอร์ที่สองพร้อมค่แอตทริบิวต์ที่แตกต่างและเรขาคณิตเป็น null

```csharp
Feature feature2 = layer.ConstructFeature();
feature2.SetValue("string_data", "string value2");
feature2.SetValue("int_data", 100);
feature2.SetValue("bool_data", false);
feature2.SetValue("float_data", 3.1415);
feature2.Geometry = Geometry.Null;
layer.Add(feature2);
```

## วิธีเขียนไฟล์ KML – รวมทุกขั้นตอนเข้าด้วยกัน
โดยทำตามขั้นตอนข้างต้น คุณจะได้ไฟล์ KML ที่ทำงานได้เต็มรูปแบบซึ่งมีแอตทริบิวต์ที่กำหนดเอง (รวมถึงแฟล็ก boolean) และเรขาคณิต line string คุณสามารถเปิด `Kml_File_out.kml` ที่สร้างขึ้นใน Google Earth, ArcGIS หรือโปรแกรมดู GIS ใด ๆ ที่รองรับ KML

## ปัญหาทั่วไปและการแก้ไขข้อผิดพลาด
- **File path errors** – ตรวจสอบให้แน่ใจว่า `dataDir` ลงท้ายด้วยตัวคั่นพาธ (`\` หรือ `/`) ที่เหมาะสมกับ OS ของคุณ  
- **Missing license** – รุ่นทดลองใช้ได้สำหรับการประเมิน, แต่ต้องมีลิขสิทธิ์เพื่อเขียนไฟล์ KML อย่างไม่มีข้อจำกัด  
- **Null geometry** – การตั้งค่า `Geometry.Null` เป็นการตั้งใจสำหรับฟีเจอร์ที่ไม่มีข้อมูลเชิงพื้นที่; หากคุณต้องการเรขาคณิตเสมอให้ละเว้นส่วนนี้  

## คำถามที่พบบ่อย

### Aspose.GIS รองรับรูปแบบ GIS อื่น ๆ หรือไม่?
ใช่, Aspose.GIS รองรับรูปแบบ GIS ต่าง ๆ รวมถึง shapefile, GeoJSON, และ KML  

### ฉันสามารถแสดงผลข้อมูลเชิงพื้นที่ที่สร้างด้วย Aspose.GIS ได้หรือไม่?
แน่นอน! Aspose.GIS สามารถผสานรวมกับไลบรารีแผนที่ต่าง ๆ ทำให้คุณสามารถแสดงผลข้อมูลเชิงพื้นที่ของคุณได้  

### มีเวอร์ชันทดลองสำหรับ Aspose.GIS หรือไม่?
มี, คุณสามารถสำรวจคุณสมบัติของ Aspose.GIS ได้โดยดาวน์โหลด [free trial version](https://releases.aspose.com/)  

### ฉันจะขอรับการสนับสนุนสำหรับ Aspose.GIS ได้อย่างไร?
เยี่ยมชม [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) เพื่อรับการสนับสนุนจากชุมชน หรือสำรวจตัวเลือกการสนับสนุนระดับพรีเมียม [here](https://purchase.aspose.com/buy)  

### มีใบอนุญาตชั่วคราวสำหรับ Aspose.GIS หรือไม่?
มี, คุณสามารถรับใบอนุญาตชั่วคราว [here](https://purchase.aspose.com/temporary-license/)  

## คำถามที่พบบ่อยเพิ่มเติม

**Q: How do I **how to create KML** files with custom styling?**  
A: ใช้ namespace `Aspose.Gis.Formats.Kml.Styles` เพื่อกำหนดไอคอน, สีเส้น, และสไตล์ป้ายกำกับก่อนเพิ่มฟีเจอร์  

**Q: Can I write large KML files efficiently?**  
A: เขียนฟีเจอร์เป็นชุดและทำการ flush layer เป็นระยะเพื่อรักษาการใช้หน่วยความจำให้ต่ำ  

**Q: Does Aspose.GIS support .NET Core and .NET 6+?**  
A: ใช่, ไลบรารีนี้เข้ากันได้อย่างเต็มที่กับ .NET Core, .NET 5, และ .NET 6  

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}