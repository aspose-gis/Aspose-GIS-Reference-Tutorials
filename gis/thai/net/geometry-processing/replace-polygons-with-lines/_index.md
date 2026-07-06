---
date: 2026-04-09
description: เรียนรู้วิธีแปลงรูปหลายเหลี่ยมเป็นเส้นและแปลงหลายรูปหลายเหลี่ยมเป็นเส้นโดยใช้
  Aspose.GIS สำหรับ .NET คู่มือสั้นสำหรับนักพัฒนา GIS
keywords:
- convert polygon to line
- how to replace polygons
- transform polygons to lines
linktitle: แทนที่รูปหลายเหลี่ยมด้วยเส้น
second_title: Aspose.GIS .NET API
title: แปลงรูปหลายเหลี่ยมเป็นเส้นด้วย Aspose.GIS สำหรับ .NET
url: /th/net/geometry-processing/replace-polygons-with-lines/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง Polygon เป็น Line ด้วย Aspose.GIS สำหรับ .NET

## บทนำ
หากคุณต้องการ **แปลง polygon เป็น line** ในโครงการ GIS บน .NET, Aspose.GIS ทำให้กระบวนการเป็นเรื่องง่าย ไม่ว่าคุณจะกำลังทำให้การแสดงแผนที่ง่ายขึ้น, เตรียมข้อมูลสำหรับอัลกอริทึมการกำหนดเส้นทาง, หรือเพียงต้องการการแสดงผล geometry ที่สะอาดกว่า, บทแนะนำนี้จะพาคุณผ่านขั้นตอนการแทนที่ polygon ด้วย geometry แบบ line โดยใช้ Aspose.GIS API.

## คำตอบอย่างรวดเร็ว
- **“แปลง polygon เป็น line” หมายความว่าอย่างไร?** มันแปลงรูปทรง polygon ปิดเป็นเส้นขอบเขต (line strings).  
- **ทำไมต้องใช้ Aspose.GIS สำหรับงานนี้?** มันให้เมธอดเดียว (`ReplacePolygonsByLines`) ที่จัดการการแปลงได้อย่างมีประสิทธิภาพโดยไม่ต้องทำการพาร์ส geometry ด้วยตนเอง.  
- **เวอร์ชัน .NET ที่รองรับคืออะไร?** .NET Framework 4.5+, .NET Core 3.1+, และ .NET 5/6+.  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** การทดลองใช้ฟรีสามารถใช้สำหรับการทดสอบ; ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **การดำเนินการใช้เวลานานเท่าไหร่?** ปกติใช้เวลาน้อยกว่า 10 นาทีสำหรับการแปลงพื้นฐาน.

## “แปลง polygon เป็น line” คืออะไร?
การแปลง polygon เป็น line หมายถึงการดึงเอา outer ring (เส้นรอบ) ของ polygon ออกมาและแทนที่ด้วย `LineString`. Geometry ที่ได้จะคงรูปร่างของเส้นขอบแต่จะสูญเสียข้อมูลพื้นที่ภายใน ซึ่งมีประโยชน์สำหรับงานเช่นการวิเคราะห์เครือข่ายหรือการเรนเดอร์ขอบ.

## ทำไมต้องแปลง polygon เป็น line ด้วย Aspose.GIS?
- **ทำให้การแสดงผลง่ายขึ้น:** เส้นมีน้ำหนักเบากว่าในการเรนเดอร์, โดยเฉพาะบนแผนที่เว็บ.  
- **เตรียมข้อมูลสำหรับการกำหนดเส้นทาง:** เครื่องกำหนดเส้นทางหลายตัวต้องการ geometry แบบ line.  
- **รักษา topology:** เส้นจะคงขอบเขตที่แม่นยำของ polygon ดั้งเดิม, ทำให้ความแม่นยำเชิงพื้นที่คงที่.  
- **โซลูชันแบบบรรทัดเดียว:** เมธอด `ReplacePolygonsByLines()` ทำงานทั้งหมดให้คุณ.

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่ม, ตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

### การติดตั้ง Aspose.GIS สำหรับ .NET
1. ดาวน์โหลด Aspose.GIS สำหรับ .NET: เยี่ยมชม [this link](https://releases.aspose.com/gis/net/) เพื่อดาวน์โหลดเวอร์ชันล่าสุด.  
2. ติดตั้ง Aspose.GIS สำหรับ .NET: ปฏิบัติตามคำแนะนำการติดตั้งในแพ็กเกจหรือดูที่ [documentation](https://reference.aspose.com/gis/net/) สำหรับขั้นตอนโดยละเอียด.

## นำเข้า Namespaces
ในโครงการ .NET ของคุณ, ให้นำเข้า namespaces ที่จำเป็นเพื่อให้คุณสามารถทำงานกับคลาสของ Aspose.GIS ได้.

```csharp
using System;
using Aspose.Gis.Geometries;
```

## คู่มือขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: กำหนด geometry แหล่งที่มา
สร้าง collection ของ geometry ที่รวม polygon หนึ่งหรือหลายรูปที่คุณต้องการแปลง. ในตัวอย่างนี้เรายังเพิ่ม point เพื่อแสดงว่าองค์ประกอบที่ไม่ใช่ polygon จะคงเดิม.

```csharp
var srcGeometry = Geometry.FromText(@"GeometryCollection (POLYGON((1 2, 1 4, 3 4, 3 2)), Point (5 1))");
```

### ขั้นตอนที่ 2: แปลง polygon เป็น line
เรียกเมธอด `ReplacePolygonsByLines()`. การเรียกครั้งเดียวนี้จะสแกน collection, แทนที่ทุก polygon ด้วยการแสดงผลเป็น line ที่สอดคล้อง, และปล่อย geometry ประเภทอื่นไว้โดยไม่เปลี่ยนแปลง.

```csharp
var dstGeometry = srcGeometry.ReplacePolygonsByLines();
```

### ขั้นตอนที่ 3: แสดง geometry ดั้งเดิมและที่แปลงแล้ว
พิมพ์ geometry ดั้งเดิมและที่แปลงแล้วทั้งสองชุดลงคอนโซลเพื่อให้คุณตรวจสอบการแปลง.

```csharp
Console.WriteLine($"source: {srcGeometry.AsText()}");
Console.WriteLine($"result: {dstGeometry.AsText()}");
```

## ปัญหาและวิธีแก้ไขทั่วไป
- **ไม่มีผลลัพธ์เป็น line:** ตรวจสอบว่า geometry แหล่งที่มามี polygon จริง; point หรือ multipoint จะถูกส่งผ่านโดยไม่เปลี่ยนแปลง.  
- **ปัญหาเรื่องลำดับพิกัด:** Aspose.GIS คาดว่าพิกัดอยู่ในลำดับ `X Y` (longitude latitude). การสลับค่าจะทำให้รูปทรงไม่คาดคิด.  
- **คอลเลกชันขนาดใหญ่:** สำหรับชุดข้อมูลขนาดใหญ่มาก, ควรพิจารณาประมวลผล geometry เป็นชุดย่อยเพื่อหลีกเลี่ยงการใช้หน่วยความจำสูง.

## คำถามที่พบบ่อย

**Q: Aspose.GIS สำหรับ .NET สามารถทำงานกับรูปแบบไฟล์ GIS ต่าง ๆ ได้หรือไม่?**  
A: ใช่, รองรับ Shapefile, GeoJSON, KML, และรูปแบบ GIS ที่พบบ่อยอื่น ๆ อีกหลายรูปแบบ.

**Q: มีการทดลองใช้ฟรีสำหรับ Aspose.GIS สำหรับ .NET หรือไม่?**  
A: ใช่, คุณสามารถเข้าถึงการทดลองใช้ฟรีของ Aspose.GIS สำหรับ .NET ได้ที่ [here](https://releases.aspose.com/).

**Q: Aspose.GIS สำหรับ .NET มีการสนับสนุนสำหรับนักพัฒนาหรือไม่?**  
A: ใช่, นักพัฒนาสามารถรับการสนับสนุนและความช่วยเหลือจากฟอรั่มชุมชน Aspose.GIS ได้ที่ [here](https://forum.aspose.com/c/gis/33).

**Q: ฉันสามารถซื้อไลเซนส์ชั่วคราวสำหรับ Aspose.GIS สำหรับ .NET ได้หรือไม่?**  
A: ใช่, คุณสามารถรับไลเซนส์ชั่วคราวได้จาก [here](https://purchase.aspose.com/temporary-license/).

**Q: Aspose.GIS สำหรับ .NET เหมาะกับทั้งผู้เริ่มต้นและนักพัฒนาที่มีประสบการณ์หรือไม่?**  
A: แน่นอน, มันมีเอกสารที่ครอบคลุม, ตัวอย่างโค้ด, และอ้างอิง API สำหรับทุกระดับความชำนาญ.

## สรุป
โดยทำตามขั้นตอนเหล่านี้, คุณได้เรียนรู้วิธี **แปลง polygon เป็น line** และ **แปลง polygon เป็น line** อย่างมีประสิทธิภาพโดยใช้ Aspose.GIS สำหรับ .NET. ความสามารถนี้เปิดประตูสู่การแสดงผลที่เบาขึ้น, การเตรียมการกำหนดเส้นทาง, และกระบวนการ GIS อื่น ๆ อีกมากมาย. อย่าลังเลที่จะสำรวจคุณลักษณะเพิ่มเติมของ Aspose.GIS เช่น spatial queries, reprojection, และการแปลงรูปแบบเพื่อขยายความสามารถของแอปพลิเคชันของคุณ.

---

**อัปเดตล่าสุด:** 2026-04-09  
**ทดสอบด้วย:** Aspose.GIS for .NET (รุ่นล่าสุด)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}