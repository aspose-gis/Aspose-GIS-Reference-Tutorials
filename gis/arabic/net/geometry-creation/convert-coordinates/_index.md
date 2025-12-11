---
date: 2025-12-11
description: تعلم كيفية تحويل الإحداثيات إلى نظام الدرجات والدقائق والثواني (DMS)
  باستخدام Aspose.GIS لـ .NET. يتضمن أمثلة بلغة C#، تحويل خطوط العرض والطول باستخدام
  C#، ودليل خطوة بخطوة.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: تحويل الإحداثيات إلى نظام الدرجات والدقائق والثواني باستخدام Aspose.GIS لـ
  .NET
url: /ar/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل الإحداثيات إلى DMS باستخدام Aspose.GIS

## المقدمة
في هذا الدرس، ستكتشف كيفية **تحويل الإحداثيات إلى DMS** (درجات، دقائق، ثوانٍ) باستخدام مكتبة Aspose.GIS القوية لـ .NET. سواء كنت بحاجة إلى c# تحويل خطوط العرض والطول لتطبيقات الخرائط، أو إنشاء سلاسل موقع قابلة للقراءة البشرية، أو ببساطة استكشاف صيغ إحداثيات مختلفة، فإن هذا الدليل يمرّ بك عبر كل خطوة مع شروحات واضحة وكود C# جاهز للتنفيذ.

## إجابات سريعة
- **ماذا يعني “تحويل الإحداثيات إلى DMS”؟** يحول القيم الرقمية لخط العرض/خط الطول إلى تدوين الدرجات‑الدقائق‑الثواني التقليدي.  
- **أي مكتبة تتولى عملية التحويل؟** توفر Aspose.GIS لـ .NET الفئة `GeoConvert` مع دعم مدمج للصيغ.  
- **هل أحتاج إلى ترخيص لتجربتها؟** يتوفر إصدار تجريبي مجاني؛ يلزم الحصول على ترخيص تجاري للاستخدام في الإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، و .NET 5/6+.  
- **هل يمكنني استخدام نفس الكود لصيغ أخرى؟** نعم—ما عليك سوى تغيير قيمة تعداد `PointFormats` (مثلًا `DecimalDegrees`، `GeoRef`).  

## ما هو تحويل الإحداثيات إلى DMS؟
يعيد تحويل الإحداثيات إلى DMS كتابة قيم خط العرض والطول العشرية إلى صيغة مثل `25°30'00"N 45°30'00"E`. يُستخدم هذا التمثيل على نطاق واسع في علم الخرائط، الملاحة، وتبادل بيانات GIS.

## لماذا نستخدم Aspose.GIS لتحويل الإحداثيات؟
- **All‑in‑one API** – لا حاجة لمكتبات خارجية أو حسابات رياضية معقدة؛ Aspose.GIS يتعامل مع التحليل والتنسيق داخليًا.  
- **High accuracy** – معالجة دقيقة للحالات الخاصة مثل القيم السالبة ومؤشرات النصف الكرة.  
- **Cross‑platform** – يعمل بنفس الطريقة على أنظمة Windows و Linux و macOS في بيئات .NET.  
- **Extensible** – يمكن بسهولة التبديل بين صيغ DMS، الدرجات العشرية، الدرجات‑الدقائق‑العشرية، وصيغة GeoRef.

## المتطلبات المسبقة
قبل البدء، تأكد من وجود ما يلي:

1. **Basic knowledge of C#** – الإلمام بالمتغيرات، استدعاءات الدوال، وإخراج الكونسول.  
2. **Aspose.GIS installed** – حمّل أحدث حزمة من [موقع Aspose.GIS](https://releases.aspose.com/gis/net/).  

## استيراد مساحات الأسماء
أولًا، استورد مساحات الأسماء المطلوبة لعمليات GIS:

```csharp
using System;
using Aspose.Gis;
```

## دليل خطوة بخطوة

### الخطوة 1: بدء عملية التحويل
نطبع رسالة ودية لتعرف أن العرض التجريبي قد بدأ.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### الخطوة 2: التحويل إلى درجات عشرية  
على الرغم من أن الهدف النهائي هو DMS، نبدأ بعرض التمثيل العشري الأصلي.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### الخطوة 3: التحويل إلى دقائق عشرية للدرجة  
هذه الصيغة (`DD°MM.m'`) خطوة وسيطة شائعة عندما تحتاج *convert lat long degree minutes*.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### الخطوة 4: التحويل إلى درجات دقائق ثوانٍ (DMS)  
هذا هو جوهر درسنا—**تحويل الإحداثيات إلى DMS**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### الخطوة 5: التحويل إلى GeoRef  
للتكامل الكامل، نعرض أيضًا صيغة `GeoRef` المفيدة في سير عمل الاستشعار عن بُعد.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## المشكلات الشائعة والحلول
- **Incorrect hemisphere letters** – تأكد من تمرير قيم موجبة للشمال/الشرق وسالبة للجنوب/الغرب؛ يضيف الـ API اللاحقة الصحيحة تلقائيًا.  
- **Unexpected blank output** – تحقق من أن تجميع `Aspose.Gis` مُشار إليه بشكل صحيح وأن المشروع يستهدف نسخة .NET مدعومة.  
- **License not found** – ضع ملف الترخيص في جذر التطبيق أو اضبطه برمجيًا باستخدام `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.

## الأسئلة المتكررة

**س: هل Aspose.GIS متوافق مع لغات برمجة أخرى؟**  
ج: تستهدف Aspose.GIS أساسًا مطوري .NET، لكن هناك نسخة Java متاحة أيضًا.

**س: هل يمكنني تجربة Aspose.GIS قبل الشراء؟**  
ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.GIS عبر [الموقع الإلكتروني](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على دعم لـ Aspose.GIS؟**  
ج: يمكنك طلب المساعدة من منتدى مجتمع Aspose.GIS [هنا](https://forum.aspose.com/c/gis/33).

**س: هل تتوفر تراخيص مؤقتة لـ Aspose.GIS؟**  
ج: نعم، يمكن الحصول على تراخيص مؤقتة من [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني شراء Aspose.GIS؟**  
ج: يمكنك شراء Aspose.GIS من [صفحة الشراء](https://purchase.aspose.com/buy).

## الخاتمة
باتباع هذه الخطوات، أصبحت الآن تعرف كيفية **تحويل الإحداثيات إلى DMS** وصيغ GIS الشائعة الأخرى باستخدام Aspose.GIS لـ .NET. تتيح لك هذه القدرة دمج سلاسل المواقع القابلة للقراءة البشرية بسلاسة في تطبيقات الخرائط، التقارير، أو أي سير عمل للبيانات المكانية. لا تتردد في تجربة قيم خطوط عرض/طول مختلفة واستكشاف الصيغ الأخرى التي تقدمها الفئة `GeoConvert`.

---

**آخر تحديث:** 2025-12-11  
**تم الاختبار مع:** Aspose.GIS 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}