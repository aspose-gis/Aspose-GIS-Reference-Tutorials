---
title: สร้างเรขาคณิต MultiPoint ด้วย Aspose.GIS สำหรับ .NET
linktitle: สร้างเรขาคณิตหลายจุด
second_title: Aspose.GIS .NET API
description: Master Aspose.GIS for .NET - เรียนรู้การสร้างรูปทรงเรขาคณิตแบบหลายจุดได้อย่างง่ายดาย บทช่วยสอนที่ครอบคลุมสำหรับนักพัฒนา
type: docs
weight: 14
url: /th/net/geometry-creation/create-multipoint-geometry/
---
## การแนะนำ

ในโลกของระบบสารสนเทศภูมิศาสตร์ (GIS) Aspose.GIS สำหรับ .NET มีความโดดเด่นในฐานะเครื่องมืออันทรงพลังสำหรับนักพัฒนา คุณสมบัติที่แข็งแกร่งและความยืดหยุ่นทำให้เป็นตัวเลือกอันดับต้นๆ สำหรับการทำงานกับข้อมูลเชิงพื้นที่ในแอปพลิเคชัน .NET ในบทช่วยสอนนี้ เราจะเจาะลึกพื้นฐานของ Aspose.GIS สำหรับ .NET โดยเน้นไปที่การสร้างรูปทรงเรขาคณิตแบบหลายจุดโดยเฉพาะ ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น คู่มือนี้จะแนะนำคุณในแต่ละขั้นตอน ทำให้ง่ายต่อการเข้าใจและนำไปใช้

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอนนี้ มีข้อกำหนดเบื้องต้นบางประการที่คุณต้องมี:

1. ความเข้าใจพื้นฐานของ C#: เนื่องจากเราจะทำงานร่วมกับ Aspose.GIS สำหรับ .NET ใน C# การมีความรู้พื้นฐานเกี่ยวกับภาษาจะเป็นประโยชน์

2. ติดตั้ง Visual Studio แล้ว: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio ในระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์หากยังไม่ได้ดาวน์โหลด

3. ติดตั้ง Aspose.GIS สำหรับ .NET แล้ว: คุณจะต้องติดตั้ง Aspose.GIS สำหรับ .NET บนเครื่องของคุณ หากคุณยังไม่ได้ติดตั้ง คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/gis/net/).

4.  ใบอนุญาตที่ถูกต้องหรือการทดลองใช้ฟรี: ตรวจสอบให้แน่ใจว่าคุณมีใบอนุญาตที่ถูกต้องเพื่อใช้ Aspose.GIS สำหรับ .NET หรือคุณสามารถเลือกทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).

ตอนนี้เรามีข้อกำหนดเบื้องต้นครอบคลุมแล้ว เรามาเจาะลึกบทช่วยสอนกันดีกว่า

## นำเข้าเนมสเปซ

ประการแรก เราต้องนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน Aspose.GIS สำหรับ .NET


```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

 ในขั้นตอนนี้ เราจะรวมไฟล์`Aspose.Gis` เนมสเปซซึ่งมีฟังก์ชันหลักของ Aspose.GIS สำหรับ .NET และ`Aspose.Gis.Geometries` เนมสเปซซึ่งมีคลาสและวิธีการทำงานกับรูปทรงเรขาคณิต

แบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอน

ตอนนี้ เรามาแจกแจงตัวอย่างที่ให้ไว้เป็นหลายขั้นตอนเพื่อทำความเข้าใจให้ดีขึ้น

### ขั้นตอนที่ 1: สร้างวัตถุเรขาคณิตหลายจุด

```csharp
MultiPoint multipoint = new MultiPoint();
```

 ที่นี่ เรากำลังเริ่มต้นอินสแตนซ์ใหม่ของ`MultiPoint`คลาสซึ่งแสดงถึงการสะสมของจุดในระนาบสองมิติ

### ขั้นตอนที่ 2: เพิ่มคะแนนให้กับเรขาคณิตหลายจุด

```csharp
multipoint.Add(new Point(1, 2));
multipoint.Add(new Point(3, 4));
```

 ในขั้นตอนนี้ เราจะเพิ่มจุดสองจุดไปที่`MultiPoint` เรขาคณิต. แต่ละจุดจะแสดงด้วยอินสแตนซ์ของ`Point` คลาสโดยมีพิกัดที่ระบุเป็นอาร์กิวเมนต์ (x, y)

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีสร้างเรขาคณิตแบบหลายจุดโดยใช้ Aspose.GIS สำหรับ .NET เรียบร้อยแล้ว เมื่อทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณจะมีความรู้พื้นฐานในการรวมการจัดการข้อมูลเชิงพื้นที่เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น

## คำถามที่พบบ่อย

### ถาม: Aspose.GIS สำหรับ .NET เข้ากันได้กับ .NET Framework ทุกเวอร์ชันหรือไม่
ตอบ: ใช่ Aspose.GIS สำหรับ .NET เข้ากันได้กับ .NET Framework 4.0 และเวอร์ชันที่ใหม่กว่า

### ถาม: ฉันสามารถลองใช้ Aspose.GIS สำหรับ .NET ก่อนซื้อใบอนุญาตได้หรือไม่
 ตอบ: ได้ คุณสามารถทดลองใช้งานฟรีได้จาก Aspose[เว็บไซต์](https://purchase.aspose.com/temporary-license/).

### ถาม: Aspose.GIS สำหรับ .NET รองรับรูปแบบข้อมูลเชิงพื้นที่อื่นๆ นอกเหนือจากจุดหรือไม่
ตอบ: แน่นอน! Aspose.GIS สำหรับ .NET รองรับรูปแบบข้อมูลเชิงพื้นที่ที่หลากหลาย รวมถึงรูปหลายเหลี่ยม เส้น และอื่นๆ

### ถาม: ฉันจะค้นหาแหล่งข้อมูลเพิ่มเติมและการสนับสนุนสำหรับ Aspose.GIS สำหรับ .NET ได้ที่ไหน
 ตอบ: คุณสามารถเยี่ยมชมได้ที่[ฟอรัม Aspose.GIS](https://forum.aspose.com/c/gis/33) สำหรับการสนับสนุนและการเข้าถึงเอกสาร[ที่นี่](https://reference.aspose.com/gis/net/).

### ถาม: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับโครงการระยะสั้นได้หรือไม่
ตอบ: ได้ คุณสามารถได้รับใบอนุญาตชั่วคราวสำหรับความต้องการเฉพาะของโครงการของคุณได้