---
date: 2026-02-13
description: تعلم كيفية تحويل الإحداثيات إلى نظام الدرجات والدقائق والثواني (DMS)
  باستخدام Aspose.GIS لـ .NET. يوضح هذا الدليل خطوة بخطوة بلغة C# كيفية تحويل خطوط
  العرض والطول، والدرجات العشرية إلى DMS والمزيد.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: كيفية تحويل الإحداثيات إلى نظام الدرجات والدقائق والثواني باستخدام Aspose.GIS
  لـ .NET
url: /ar/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تحويل الإحداثيات إلى DMS باستخدام Aspose.GIS

## Introduction
في هذا الدرس، ستتعلم **كيفية تحويل الإحداثيات** إلى DMS (درجات، دقائق، ثوان) باستخدام مكتبة Aspose.GIS القوية لـ .NET. سواء كنت بحاجة إلى **c# convert lat long**، أو إنشاء سلاسل موقع قابلة للقراءة البشرية، أو مجرد استكشاف صيغ إحداثيات مختلفة، فإن هذا الدليل يمرّ بك عبر كل خطوة مع شروحات واضحة وكود C# جاهز للتنفيذ.

## Quick Answers
- **ماذا يعني “convert coordinates to DMS”?** يحول قيم العرض/الطول الرقمية إلى الصيغة التقليدية للدرجات‑الدقائق‑الثواني.  
- **أي مكتبة تتولى التحويل؟** توفر Aspose.GIS لـ .NET الفئة `GeoConvert` مع دعم مدمج للصيغ.  
- **هل أحتاج إلى ترخيص لتجربتها؟** تتوفر نسخة تجريبية مجانية؛ يلزم ترخيص تجاري للاستخدام في الإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، و .NET 5/6+.  
- **هل يمكنني استخدام نفس الكود لصيغ أخرى؟** نعم—فقط غيّر قيمة تعداد `PointFormats` (مثال: `DecimalDegrees`، `GeoRef`).  

## How to Convert Coordinates to DMS
قبل الغوص في الكود، دعنا نوضح لماذا لا يزال DMS ذو قيمة. يعتمد عليه رسامو الخرائط، والطيارون، والعديد من مزودي بيانات GIS لأنّه سهل القراءة للإنسان ويتماشى مع الخرائط التقليدية. تزيل Aspose.GIS الحاجة إلى الحسابات اليدوية، مما يتيح لك التركيز على منطق التطبيق.

## What is coordinate conversion to DMS?
تحويل الإحداثيات إلى DMS يعيد كتابة قيم العرض والطول العشرية إلى صيغة مثل `25°30'00"N 45°30'00"E`. تُستخدم هذه الصيغة على نطاق واسع في رسم الخرائط، والملاحة، وتبادل بيانات GIS.

## Why use Aspose.GIS for coordinate conversion?
- **واجهة برمجة تطبيقات شاملة** – لا تحتاج إلى مكتبات خارجية أو حسابات معقدة؛ تتولى Aspose.GIS التحليل والتنسيق داخليًا.  
- **دقة عالية** – معالجة دقيقة للحالات الحدية مثل القيم السالبة ومؤشرات النصف الكرة.  
- **متعددة المنصات** – تعمل بنفس الطريقة على بيئات .NET في Windows وLinux وmacOS.  
- **قابلة للتوسيع** – يمكن التبديل بسهولة بين صيغ DMS، الدرجات العشرية، الدرجات‑الدقائق العشرية، وصيغة GeoRef.  

## Prerequisites
قبل البدء، تأكد من وجود ما يلي:

1. **معرفة أساسية بـ C#** – الإلمام بالمتغيّرات، واستدعاءات الدوال، وإخراج الكونسول.  
2. **تثبيت Aspose.GIS** – حمّل أحدث حزمة من [موقع Aspose.GIS](https://releases.aspose.com/gis/net/).

## Import Namespaces
First, import the namespaces required for GIS operations:

```csharp
using System;
using Aspose.Gis;
```

## Step‑by‑step guide

### Step 1: Start the conversion process
نطبع رسالة ترحيبية لتعرف أن العرض التجريبي قد بدأ.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Step 2: Convert to Decimal Degrees  
على الرغم من أن الهدف النهائي هو DMS، نبدأ بعرض التمثيل العشري الأصلي. يوضح ذلك أيضًا مسار **decimal degrees to dms** الذي ستتبعه لاحقًا.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Step 3: Convert to Degree Decimal Minutes  
هذه الصيغة (`DD°MM.m'`) هي خطوة وسيطة شائعة عندما تحتاج إلى *convert lat long degree minutes*.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Step 4: Convert to Degree Minutes Seconds (DMS)  
هذا هو جوهر الدرس—**convert coordinates to DMS**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Step 5: Convert to GeoRef  
لإكمال الصورة، نعرض أيضًا صيغة `GeoRef`، المفيدة في سير عمل الاستشعار عن بُعد.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Common Issues and Solutions
- **حروف النصف الكرة غير صحيحة** – تأكد من تمرير قيم موجبة للشمال/الشرق وسالبة للجنوب/الغرب؛ تضيف الواجهة البرمجية اللاحقة الصحيحة تلقائيًا.  
- **إخراج فارغ غير متوقع** – تحقق من أن تجميع `Aspose.Gis` مُشار إليه بشكل صحيح وأن المشروع يستهدف نسخة .NET مدعومة.  
- **الترخيص غير موجود** – ضع ملف الترخيص في جذر التطبيق أو اضبطه برمجيًا باستخدام `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.  

## Frequently Asked Questions

**س: هل Aspose.GIS متوافق مع لغات برمجة أخرى؟**  
ج: تستهدف Aspose.GIS أساسًا مطوري .NET، لكن هناك نسخة Java متاحة أيضًا.

**س: هل يمكنني تجربة Aspose.GIS قبل الشراء؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.GIS عبر [الموقع](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على دعم لـ Aspose.GIS؟**  
ج: يمكنك طلب المساعدة من منتدى مجتمع Aspose.GIS [هنا](https://forum.aspose.com/c/gis/33).

**س: هل تتوفر تراخيص مؤقتة لـ Aspose.GIS؟**  
ج: نعم، يمكن الحصول على تراخيص مؤقتة من [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني شراء Aspose.GIS؟**  
ج: يمكنك شراء Aspose.GIS من [صفحة الشراء](https://purchase.aspose.com/buy).

## Conclusion
باتباع هذه الخطوات، أصبحت الآن تعرف كيف **convert coordinates to DMS** وغيرها من صيغ GIS الشائعة باستخدام Aspose.GIS لـ .NET. تتيح لك هذه القدرة دمج سلاسل المواقع القابلة للقراءة البشرية بسلاسة في تطبيقات الخرائط، التقارير، أو أي سير عمل للبيانات المكانية. لا تتردد في تجربة قيم عرض/طول مختلفة واستكشاف الصيغ الأخرى التي توفرها الفئة `GeoConvert`.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}