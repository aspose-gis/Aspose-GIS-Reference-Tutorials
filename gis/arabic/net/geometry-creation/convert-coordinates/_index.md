---
title: تنسيق التحويل مع Aspose.GIS
linktitle: تحويل الإحداثيات
second_title: Aspose.GIS .NET API
description: تعرف على كيفية تحويل الإحداثيات باستخدام Aspose.GIS لـ .NET. يتم توفير دليل خطوة بخطوة والمتطلبات الأساسية والأسئلة الشائعة.
weight: 25
url: /ar/net/geometry-creation/convert-coordinates/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تنسيق التحويل مع Aspose.GIS

## مقدمة
في هذا البرنامج التعليمي، سوف نتعمق في عالم نظم المعلومات الجغرافية (GIS) باستخدام مكتبة Aspose.GIS القوية لـ .NET. Aspose.GIS عبارة عن مجموعة أدوات شاملة تمكن المطورين من العمل مع البيانات المكانية دون عناء. سواء كنت مطورًا متمرسًا أو بدأت للتو، سيرشدك هذا البرنامج التعليمي خلال عملية استخدام Aspose.GIS لتحويل الإحداثيات بشكل فعال.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1. المعرفة الأساسية بـ C#: يعد الإلمام بلغة برمجة C# أمرًا ضروريًا لفهم أمثلة التعليمات البرمجية المقدمة وتنفيذها.
  
2.  تثبيت Aspose.GIS: تأكد من تنزيل وتثبيت مكتبة Aspose.GIS لـ .NET. يمكنك تنزيله من[موقع Aspose.GIS](https://releases.aspose.com/gis/net/).

## استيراد مساحات الأسماء
قبل أن نبدأ، فلنستورد مساحات الأسماء الضرورية للوصول إلى وظائف Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

دعنا نقسم المثال المقدم إلى خطوات متعددة لفهم واضح:
## الخطوة 1: ابدأ عملية التحويل
```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```
يعرض هذا الخط ببساطة رسالة تشير إلى بدء عملية تحويل الإحداثيات.
## الخطوة 2: التحويل إلى الدرجات العشرية
```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```
 هنا، نقوم بتحويل الإحداثيات (25.5، 45.5) إلى تنسيق الدرجات العشرية باستخدام`AsPointText` الطريقة مع`PointFormats.DecimalDegrees` معامل. ثم تتم طباعة النتيجة على وحدة التحكم.
## الخطوة 3: تحويل إلى درجة عشرية دقيقة
```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```
تقوم هذه الخطوة بتحويل الإحداثيات إلى تنسيق الدرجة العشرية والدقائق وطباعة النتيجة.
## الخطوة 4: تحويل إلى درجة دقيقة ثانية
```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```
وبالمثل، نقوم بتحويل الإحداثيات إلى تنسيق الدرجة والدقائق والثواني ونعرض المخرجات.
## الخطوة 5: التحويل إلى GeoRef
```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```
وأخيرًا، نقوم بتحويل الإحداثيات إلى تنسيق GeoRef وطباعة النتيجة.

## خاتمة
في هذا البرنامج التعليمي، اكتشفنا عملية تحويل الإحداثيات باستخدام Aspose.GIS for .NET. باتباع الدليل الموضح خطوة بخطوة واستخدام مكتبة Aspose.GIS، يمكنك معالجة البيانات المكانية بكفاءة داخل تطبيقات .NET الخاصة بك.
## الأسئلة الشائعة
### هل Aspose.GIS متوافق مع لغات البرمجة الأخرى؟
يستهدف Aspose.GIS في المقام الأول مطوري .NET، ولكنه يوفر إمكانية التشغيل التفاعلي مع Java من خلال Aspose.GIS for Java.
### هل يمكنني تجربة Aspose.GIS قبل الشراء؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية من Aspose.GIS من[موقع إلكتروني](https://releases.aspose.com/).
### كيف يمكنني الحصول على الدعم لـ Aspose.GIS؟
 يمكنك طلب المساعدة من منتدى مجتمع Aspose.GIS[هنا](https://forum.aspose.com/c/gis/33).
### هل التراخيص المؤقتة متاحة لـ Aspose.GIS؟
 نعم يمكن الحصول على التراخيص المؤقتة من[صفحة الترخيص المؤقتة](https://purchase.aspose.com/temporary-license/).
### أين يمكنني شراء Aspose.GIS؟
 يمكنك شراء Aspose.GIS من[صفحة الشراء](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
