---
date: 2026-10-05
description: تعلم كيفية قراءة geojson من تدفق باستخدام Aspose.GIS for .NET. يوضح هذا
  الدليل خطوة بخطوة كيفية تحميل تدفق geojson، تحليله، واستخراج الخصائص في C#.
keywords:
- how to read geojson
- load geojson stream
- parse geojson c#
- open geojson layer
- extract geojson properties
lastmod: 2026-10-05
linktitle: قراءة GeoJSON من تدفق
og_description: تعلم كيفية قراءة geojson من تدفق باستخدام Aspose.GIS for .NET، بما
  في ذلك التحليل، فتح طبقة geojson، واستخراج الخصائص في C#.
og_image_alt: Tutorial guide showing how to read geojson from a stream with Aspose.GIS
  in C#
og_title: كيفية قراءة geojson من تدفق باستخدام Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  headline: How to read geojson from a stream with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  name: How to read geojson from a stream with Aspose.GIS for .NET
  steps:
  - name: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
    text: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
  - name: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
    text: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
  type: HowTo
- questions:
  - answer: Aspose.GIS for .NET – it handles 30+ GIS formats out of the box.
    question: What library should I use?
  - answer: Yes – call `VectorLayer.Open` with `AbstractPath.FromStream`.
    question: Can I read GeoJSON directly from a stream?
  - answer: A free trial works for testing; a full license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Which .NET versions are supported?
  - answer: Absolutely – use `GetValue<T>(columnName)` on a feature.
    question: Is extracting properties simple?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET GIS
- C# geospatial
title: كيفية قراءة geojson من تدفق باستخدام Aspose.GIS for .NET
url: /ar/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية قراءة geojson من تدفق باستخدام Aspose.GIS لـ .NET

## المقدمة
إذا كنت تتساءل **كيفية قراءة geojson** في تطبيق .NET، فقد وصلت إلى المكان المناسب. في هذا الدرس سنستعرض مثالًا كاملًا **C# GeoJSON** يوضح كيفية تحويل سلسلة GeoJSON، **تحميل تدفق geojson** إلى تدفق ذاكرة، فتح طبقة GeoJSON، واستخراج خصائص GeoJSON باستخدام Aspose.GIS. في النهاية ستحصل على نمط يمكن إعادة استخدامه في أي مشروع يحتاج إلى التعامل مع البيانات الجغرافية.

## إجابات سريعة
- **ما المكتبة التي يجب أن أستخدمها؟** Aspose.GIS لـ .NET – تدعم أكثر من 30 تنسيق GIS جاهزة.  
- **هل يمكنني قراءة GeoJSON مباشرةً من تدفق؟** نعم – استدعِ `VectorLayer.Open` مع `AbstractPath.FromStream`.  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تكفي للاختبار؛ الترخيص الكامل مطلوب للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6+.  
- **هل استخراج الخصائص بسيط؟** بالتأكيد – استخدم `GetValue<T>(columnName)` على العنصر.

يقوم `VectorLayer.Open` بفتح طبقة GIS من مصدر بيانات مثل ملف أو تدفق. `AbstractPath.FromStream` ينشئ كائن مسار مجرد يمثل التدفق المقدم لسائق GIS. `GetValue<T>(columnName)` يقرأ قيمة السمة المحددة من العنصر ويعيدها كنوع T.

## ما هو كيفية قراءة geojson؟
قراءة geojson هي عملية تحويل سلسلة أو تدفق بتنسيق GeoJSON إلى كائنات ميزات جغرافية في الذاكرة. هذا التنسيق يشفّر النقاط والخطوط والمضلعات باستخدام JSON، مما يجعل تبادل البيانات المكانية بين خدمات الويب، قواعد البيانات، وتطبيقات العميل سهلًا. بمجرد التحليل، يمكنك الاستعلام، التعديل، أو عرض العناصر باستخدام أي مكتبة .NET تدعم GIS، مثل Aspose.GIS.

## لماذا نستخدم Aspose.GIS لفتح طبقة geojson؟
يتيح لك Aspose.GIS فتح طبقة GeoJSON مباشرةً من تدفق، مما يلغي الحاجة إلى ملفات مؤقتة ويقلل من عبء الإدخال/الإخراج. تدعم المكتبة أكثر من 30 تنسيق GIS ويمكنها معالجة ملفات تصل إلى 2 GB دون تحميل المستند بالكامل إلى الذاكرة، وهو ما يناسب مجموعات البيانات الكبيرة. كما أنها تقوم بتطبيع أنظمة الإحداثيات تلقائيًا، بحيث يمكنك التركيز على منطق الأعمال بدلاً من التحليل منخفض المستوى.

## متى قد تقوم بتحميل تدفق geojson؟
ستقوم بتحميل تدفق GeoJSON عندما تتلقى بيانات مكانية من API، أو تحتاج إلى معالجة ملفات يرفعها المستخدم دون حفظها على القرص، أو توليد GeoJSON في الوقت الفعلي من استعلام قاعدة بيانات. يتيح البث تجنب الكتابة غير الضرورية على القرص، تحسين الأداء في سيناريوهات عالية التدفق، والحفاظ على تطبيقك بلا حالة، وهو أمر ذو قيمة خاصة في الخدمات الصغيرة السحابية.

## المتطلبات المسبقة
1. **معرفة أساسية بـ C#** – يجب أن تكون مرتاحًا مع صsyntax .NET وبيئة Visual Studio IDE.  
2. **تثبيت Aspose.GIS** – حمّل المكتبة من [صفحة تنزيل Aspose.GIS .NET](https://releases.aspose.com/gis/net/).  
3. **بيئة تطوير** – Visual Studio أو Visual Studio Code أو JetBrains Rider ستعمل بشكل جيد.  

## استيراد مساحات الأسماء
توفر مساحة الأسماء `Aspose.GIS` الفئات الأساسية لـ GIS. توفر `System.IO` لك كائن `MemoryStream`، وتوفر `System.Text` أدوات ترميز UTF‑8. استيراد هذه المساحات يجعل الشيفرة اللاحقة مختصرة وسهلة القراءة.

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## الخطوة 1: تحويل سلسلة geojson – مثال C# GeoJSON
أولاً نقوم بإنشاء سلسلة JSON تمثل `FeatureCollection` بسيطة. هذا هو جزء **تحويل سلسلة geojson** في سير العمل.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## الخطوة 2: تحميل تدفق geojson واستخراج خصائص geojson
الآن نقوم بتمرير السلسلة إلى `MemoryStream`، نفتحها كطبقة GIS، ونظهر كيفية قراءة قيم السمات (خطوة **استخراج خصائص geojson**).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **نصيحة احترافية:** `VectorLayer.Open` يكتشف تلقائيًا تنسيق GeoJSON عندما تمرر `Drivers.GeoJson`. يمكنك أيضًا فتح الملفات مباشرةً بتوفير مسار الملف بدلاً من التدفق.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **تنسيق JSON غير صالح** | تحقق من أن سلسلة GeoJSON مُشكّلة بشكل صحيح؛ استخدم أداة تحقق من JSON. |
| **مشكلات الترميز** | تأكد من أن التدفق يستخدم UTF‑8 (`Encoding.UTF8.GetBytes`). |
| **خصائص مفقودة** | تحقق من أن اسم الخاصية مكتوب بشكل صحيح (`"name"` في المثال). |
| **استثناء الترخيص** | استخدم ترخيص تجريبي للاختبار؛ طبق ترخيص دائم للإنتاج. |

## الأسئلة المتكررة
### هل Aspose.GIS متوافق مع تنسيقات GIS أخرى؟
نعم، يدعم Aspose.GIS تنسيقات GeoJSON، Shapefile، KML، GML، وأكثر من 20 تنسيقًا إضافيًا، مما يتيح لك التبديل بين مصادر البيانات دون تعديل الشيفرة.

### هل يمكنني تجربة Aspose.GIS قبل الشراء؟
يمكنك تنزيل نسخة تجريبية مجانية من Aspose.GIS من [صفحة تنزيل التجربة المجانية لـ Aspose.GIS](https://releases.aspose.com/).

### أين يمكنني العثور على وثائق Aspose.GIS؟
يمكنك العثور على وثائق Aspose.GIS في [مرجع Aspose.GIS .NET API](https://reference.aspose.com/gis/net/).

### كيف يمكنني الحصول على الدعم لـ Aspose.GIS؟
يمكنك الحصول على الدعم لـ Aspose.GIS عبر منتدى Aspose GIS [منتدى Aspose GIS](https://forum.aspose.com/c/gis/33).

### هل أحتاج إلى ترخيص مؤقت لاستخدام Aspose.GIS؟
يمكنك الحصول على ترخيص مؤقت لـ Aspose.GIS من [صفحة طلب الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).

## الخلاصة
في هذا الدليل غطينا **كيفية قراءة geojson** من تدفق ذاكرة باستخدام Aspose.GIS لـ .NET، وعرضنا سير عمل **قراءة geojson بـ C#**، وأظهرنا كيفية **استخراج خصائص geojson** من الطبقة المفتوحة. باستخدام هذه الخطوات يمكنك دمج معالجة البيانات الجغرافية بسلاسة في أي تطبيق .NET.

---

**آخر تحديث:** 2026-10-05  
**تم الاختبار مع:** Aspose.GIS 24.11 لـ .NET  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية كتابة GeoJSON إلى تدفق باستخدام Aspose.GIS لـ .NET](/gis/net/layer-data-operations/write-geojson-to-stream/)
- [كيفية تحويل GeoJSON إلى GDB باستخدام Aspose.GIS لـ .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [تحويل Shapefile إلى GeoJSON باستخدام Aspose.GIS لـ .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}