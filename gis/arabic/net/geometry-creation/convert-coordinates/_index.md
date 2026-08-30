---
date: 2026-08-18
description: تحويل decimal degrees إلى dms باستخدام Aspose.GIS for .NET. يوضح هذا
  الدليل خطوة بخطوة بلغة C# كيفية تحويل latitude/longitude، decimal degrees إلى dms
  والمزيد.
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: تحويل الإحداثيات
og_description: تحويل decimal degrees إلى dms أصبح سهلًا مع Aspose.GIS for .NET. تعلم
  كيفية تحويل قيم latitude‑longitude إلى صيغة DMS بالدقائق.
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: تحويل decimal degrees إلى dms باستخدام Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: كيفية تحويل decimal degrees إلى dms باستخدام Aspose.GIS for .NET
url: /ar/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تحويل الدرجات العشرية إلى DMS باستخدام Aspose.GIS

## مقدمة
في هذا الدرس ستتعلم **كيفية تحويل الدرجات العشرية إلى DMS** باستخدام مكتبة Aspose.GIS القوية لـ .NET. سواء كنت بحاجة إلى **c# convert lat long**، أو إنشاء سلاسل موقع قابلة للقراءة البشرية للتقارير، أو مجرد استكشاف صيغ إحداثيات مختلفة، فإن هذا الدليل يمر بك عبر كل خطوة مع شروحات واضحة ومقاطع C# جاهزة للتنفيذ.

## إجابات سريعة
- **ماذا يعني “تحويل الإحداثيات إلى DMS”؟** يحول القيم الرقمية لخط العرض/خط الطول إلى الصيغة التقليدية للدرجات‑الدقائق‑الثواني.  
- **أي مكتبة تتولى التحويل؟** Aspose.GIS لـ .NET توفر فئة `GeoConvert` مع دعم مدمج للصيغ.  
- **هل أحتاج إلى ترخيص لتجربتها؟** يتوفر إصدار تجريبي مجاني؛ يلزم الحصول على ترخيص تجاري للاستخدام الإنتاجي.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، و .NET 5/6+.  
- **هل يمكنني استخدام نفس الكود لصيغ أخرى؟** نعم—فقط غير قيمة تعداد `PointFormats` (مثل `DecimalDegrees`، `GeoRef`).  

## ما هو تحويل الإحداثيات إلى DMS؟
تحويل الإحداثيات إلى DMS يعيد كتابة قيم خط العرض والطول العشرية إلى صيغة مثل `25°30'00"N 45°30'00"E`. العملية تقسم كل درجة عشرية إلى درجات كاملة، دقائق (واحد على ستين من الدرجة)، وثوانٍ (واحد على ستين من الدقيقة)، ثم تُضيف مؤشر نصف الكرة المناسب (N, S, E, W). هذا الشكل القابل للقراءة البشرية ضروري للعديد من مجموعات البيانات القديمة وللتواصل الدقيق للمواقع دون الاعتماد على الصيغة العشرية.

## لماذا نستخدم Aspose.GIS لتحويل الإحداثيات؟
Aspose.GIS يدعم **أكثر من 50 صيغة إدخال وإخراج** ويمكنه معالجة ملفات GIS مئات الصفحات دون تحميل كامل مجموعة البيانات في الذاكرة. توفر الـ API دقة تحت المليمتر للحالات الخاصة مثل القيم السالبة ومؤشرات نصف الكرة، وتعمل بشكل ثابت على أنظمة Windows و Linux و macOS runtimes الخاصة بـ .NET.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من وجود ما يلي:

1. **معرفة أساسية بـ C#** – إلمام بالمتغيرات، واستدعاءات الدوال، وإخراج الكونسول.  
2. **تثبيت Aspose.GIS** – حمّل أحدث حزمة من [موقع Aspose.GIS](https://releases.aspose.com/gis/net/). يمكنك أيضًا استكشاف موقع إصدارات Aspose الرئيسي عبر [موقع إصدارات Aspose](https://releases.aspose.com/).  

## استيراد مساحات الأسماء
First, import the namespaces required for GIS operations:

Import Namespaces placeholder remains unchanged.

## دليل خطوة بخطوة

### ما هي فئة GeoConvert؟
فئة `GeoConvert` توفر طرقًا ثابتة لتحويل بين صيغ الإحداثيات مثل الدرجات العشرية، DMS، و GeoRef. تشمل التحميلات التي تقبل قيمًا رقمية خام أو كائنات `Point` وتعيد سلاسل منسقة أو كائنات `Point` جديدة. من خلال معالجة الحالات الخاصة مثل الإحداثيات السالبة والتقريب، تضمن الفئة أن يكون الناتج متوافقًا مع مواصفات GIS القياسية، مما يبسط التكامل مع أي تطبيق .NET للخرائط.

### الخطوة 1: بدء عملية التحويل
نطبع رسالة ودية لتعلم أن العرض التوضيحي قد بدأ.

```csharp
using System;
using Aspose.Gis;
```

### الخطوة 2: التحويل إلى درجات عشرية
على الرغم من أن الهدف النهائي هو DMS، نبدأ بعرض التمثيل العشري الأصلي. هذا أيضًا يوضح مسار **decimal degrees to dms** الذي ستتبعه لاحقًا.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### الخطوة 3: التحويل إلى دقائق عشرية للدرجة
هذه الصيغة (`DD°MM.m'`) خطوة وسيطة شائعة عندما تحتاج إلى **convert lat long degree minutes**.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### الخطوة 4: التحويل إلى درجات دقائق ثوانٍ (DMS)
هنا نصل إلى جوهر الدرس—**convert coordinates to dms**.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### الخطوة 5: التحويل إلى GeoRef
للتكامل الكامل، نعرض أيضًا صيغة `GeoRef` المفيدة في سير عمل الاستشعار عن بعد.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## المشكلات الشائعة والحلول
- **حروف نصف الكرة غير صحيحة** – تأكد من تمرير قيم موجبة للشمال/الشرق وسالبة للجنوب/الغرب؛ الـ API يضيف اللاحقة الصحيحة تلقائيًا.  
- **ناتج فارغ غير متوقع** – تحقق من أن تجميع `Aspose.Gis` مُشار إليه بشكل صحيح وأن المشروع يستهدف نسخة .NET مدعومة.  
- **الترخيص غير موجود** – ضع ملف الترخيص في جذر التطبيق أو عيّنه برمجيًا باستخدام `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.

## الأسئلة المتكررة

**س: هل Aspose.GIS متوافق مع لغات برمجة أخرى؟**  
ج: Aspose.GIS يستهدف أساسًا مطوري .NET، لكن هناك نسخة Java متاحة أيضًا.

**س: هل يمكنني تجربة Aspose.GIS قبل الشراء؟**  
ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.GIS عبر [الموقع الإلكتروني](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على دعم لـ Aspose.GIS؟**  
ج: يمكنك طلب المساعدة من منتدى مجتمع Aspose.GIS [هنا](https://forum.aspose.com/c/gis/33).

**س: هل تتوفر تراخيص مؤقتة لـ Aspose.GIS؟**  
ج: نعم، يمكن الحصول على تراخيص مؤقتة من [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني شراء Aspose.GIS؟**  
ج: يمكنك شراء Aspose.GIS من [صفحة الشراء](https://purchase.aspose.com/buy).

## الخلاصة
باتباع هذه الخطوات، أصبحت الآن تعرف **كيفية تحويل الدرجات العشرية إلى DMS** وصيغ GIS شائعة أخرى باستخدام Aspose.GIS لـ .NET. تتيح لك هذه القدرة دمج سلاسل المواقع القابلة للقراءة البشرية بسلاسة في تطبيقات الخرائط، التقارير، أو أي سير عمل للبيانات المكانية. لا تتردد في تجربة قيم عرض/طول مختلفة واستكشاف الصيغ الأخرى التي تقدمها فئة `GeoConvert`.

---

**آخر تحديث:** 2026-08-18  
**تم الاختبار مع:** Aspose.GIS 24.11 لـ .NET  
**المؤلف:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## دروس ذات صلة

- [How to Create Point Geometry and Get Geometry Type with Aspose.GIS for .NET](/gis/net/geometry-analysis/get-geometry-type/)
- [How to Convert GeoJSON – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [Create MultiPoint Geometry .NET with Aspose.GIS](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}