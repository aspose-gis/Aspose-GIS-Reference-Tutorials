---
date: 2026-08-13
description: تعلم كيفية حساب طول الهندسة .NET باستخدام Aspose.GIS لمعالجة البيانات
  المكانية بكفاءة. يتضمن أمثلة على الحصول على طول الخط C# وحساب طول الخط C#.
keywords:
- calculate geometry length .net
- Aspose.GIS length calculation
- C# geometry length
lastmod: 2026-08-13
linktitle: احصل على طول الهندسة
og_description: احسب طول الهندسة .NET باستخدام Aspose.GIS. احصل على أمثلة لطول الخط
  C# ومحيط المضلع في دليل مختصر وعالي الأداء لمطوري .NET.
og_image_alt: Developer guide showing how to calculate geometry length in .NET with
  Aspose.GIS
og_title: احسب طول الهندسة .NET باستخدام Aspose.GIS – قياسات مكانية سريعة
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to calculate geometry length .NET using Aspose.GIS for efficient
    spatial data handling. Includes get line length C# and calculate line length C#
    examples.
  headline: How to Calculate Geometry Length .NET with Aspose.GIS
  type: TechArticle
- description: Learn how to calculate geometry length .NET using Aspose.GIS for efficient
    spatial data handling. Includes get line length C# and calculate line length C#
    examples.
  name: How to Calculate Geometry Length .NET with Aspose.GIS
  steps:
  - name: Create geometry objects
    text: To begin with, create the geometry objects representing the shapes for which
      you want to calculate the length. This can include lines, polygons, or any other
      geometrical shapes.
  - name: Calculate line length in C#
    text: Once you have created the line geometry, you can calculate its length using
      the `GetLength()` method. This demonstrates **calculate line length c#** in
      a single line of code.
  - name: Create polygon geometry
    text: Similarly, you can create polygon geometry objects using the `Polygon` and
      `LinearRing` classes.
  - name: Get length of a polygon
    text: For polygons, the `GetLength()` method returns the perimeter, which is effectively
      the **how to get length** of the shape.
  type: HowTo
- questions:
  - answer: Aspose.GIS for .NET is compatible with .NET Framework 4.6.1 or later versions,
      as well as .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with all .NET frameworks?
  - answer: Yes, you can avail of a free trial of Aspose.GIS for .NET from [here](https://releases.aspose.com/).
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: You can find support and assistance from the Aspose.GIS community forum
      [here](https://forum.aspose.com/c/gis/33).
    question: Where can I find support for Aspose.GIS for .NET?
  - answer: You can acquire a temporary license from [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Yes, Aspose.GIS for .NET provides various formatting options to customize
      the output format as per your requirements.
    question: Can I customize the output format for geometry length calculations?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geometry length
- Aspose.GIS
- C# GIS
- spatial calculations
- line length
title: كيفية حساب طول الهندسة .NET باستخدام Aspose.GIS
url: /ar/net/geometry-analysis/get-geometry-length/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية حساب طول الهندسة .NET باستخدام Aspose.GIS

## مقدمة
إذا كنت تبحث عن طريقة واضحة وعملية لـ **calculate geometry length .NET**، فقد وصلت إلى المكان الصحيح. توفر Aspose.GIS لـ .NET مجموعة غنية من APIs الموجهة لنظم المعلومات الجغرافية التي تجعل الحسابات المكانية—مثل قياس طول الخط أو محيط المضلع—سهلة وسريعة. في هذا الدرس سنستعرض العملية بالكامل، بدءًا من إعداد البيئة وحتى كتابة كود C# الذي يُعيد قيم الطول الدقيقة.

## إجابات سريعة
- **What does “GetLength()” return?** بالنسبة للخطوط تُعيد طول الخط؛ بالنسبة للمضلعات تُعيد المحيط.  
- **Which namespace is required?** `Aspose.Gis.Geometries`.  
- **Can I use this with .NET 6?** نعم، يدعم Aspose.GIS .NET 5 و .NET 6 والإصدارات الأحدث.  
- **Do I need a license for development?** النسخة التجريبية المجانية تكفي للتقييم؛ يلزم الحصول على ترخيص للإنتاج.  
- **Is the calculation unit‑aware?** يتم إرجاع الطول بوحدات نظام الإحداثيات (مثلاً أمتار لنظام الإحداثيات المُسقطة).

## ما هو طول الهندسة؟
تحسب Geometry.GetLength() المسافة الخطية الإجمالية لكائن الهندسة بناءً على قيم إحداثياته. بالنسبة لـ LineString تقوم بجمع المسافات بين الرؤوس المتتالية، وتعيد طول الخط. عند تطبيقها على Polygon تضيف أطوال جميع الحواف، مما يوفر محيط الشكل.

## لماذا نستخدم Aspose.GIS لحساب الأطوال؟
توفر Aspose.GIS مكتبة .NET مُدارة بالكامل تقوم بالعمليات المكانية دون الحاجة إلى ثنائيات أصلية، مما يجعل النشر بسيطًا عبر Windows و Linux و macOS. تدعم أكثر من خمسين نظام إحداثيات مرجعية، وتُنتج نتائج ذات دقة مزدوجة حتى لسلاسل خطوط بطول مئات الكيلومترات، وتندمج بسلاسة مع مشاريع .NET 5/6/7، مما يضمن أداءً ثابتًا ودقةً عالية.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

### 1. مكتبة Aspose.GIS لـ .NET
أولاً، تحتاج إلى تثبيت مكتبة Aspose.GIS لـ .NET في بيئة التطوير الخاصة بك. إذا لم تقم بذلك بعد، يمكنك تحميلها من صفحة [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).

### 2. بيئة تطوير .NET
تأكد من إعداد بيئة تطوير .NET على جهازك. يشمل ذلك وجود Visual Studio أو أي بيئة تطوير متكاملة (IDE) متوافقة أخرى مثبتة.

### 3. فهم أساسي للغة C#
فهم أساسي للغة البرمجة C# ضروري لمتابعة هذا الدرس.

## استيراد مساحات الأسماء
للاستفادة من الوظائف التي توفرها Aspose.GIS لـ .NET، تحتاج إلى استيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك.

### استيراد مساحة الاسم Aspose.GIS
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## كيفية الحصول على طول الخط C#
يمثل `LineString` في Aspose.GIS سلسلة من نقطتين أو أكثر متصلة بقطاعات خطية مستقيمة، تُنمذج الميزات الخطية مثل الطرق والأنهار أو خطوط المرافق ضمن نظام إحداثيات مرجعي معين. بعد إنشاء `LineString` بالنقاط المطلوبة، تُعيد طريقة `GetLength()` المسافة الإجمالية المقاسة بوحدات CRS الخاصة بالهندسة، مما يتيح لك الحصول بسرعة على قياسات دقيقة للخط لأغراض التوجيه أو التحليل القائم على المسافة أو التقارير، ويمكن معالجتها أو تخزينها حسب الحاجة.

### الخطوة 1: إنشاء كائنات الهندسة
للبدء، أنشئ كائنات الهندسة التي تمثل الأشكال التي تريد حساب طولها. يمكن أن تشمل ذلك الخطوط، المضلعات، أو أي أشكال هندسية أخرى.

```csharp
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(2, 2);
line.AddPoint(2, 0);
```

### الخطوة 2: حساب طول الخط في C#
بعد إنشاء هندسة الخط، يمكنك حساب طولها باستخدام طريقة `GetLength()`. هذا يُظهر **calculate line length c#** في سطر واحد من الكود.

```csharp
Console.WriteLine("{0:F}", line.GetLength()); // Output: 4.83
```

## كيفية حساب طول الخط C# للمضلعات
يتكون `Polygon` في Aspose.GIS من `LinearRing` خارجي يحدد حدوده وحلقات داخلية اختيارية للثقوب، يُنمذج ميزات المساحة مثل القطع، البحيرات، أو المناطق الإدارية ضمن مرجع مكاني محدد. أنشئ `LinearRing` الخارجي بتزويد نقاط زوايا المضلع، ثم أنشئ `Polygon` باستخدام تلك الحلقة؛ عند استدعاء `GetLength()` على المضلع يتم حساب المحيط الكلي، وهو مفيد لمهام مثل تقدير طول السياج، تقارير الحدود، أو تحويل قيم المحيط إلى وحدات أخرى.

### الخطوة 3: إنشاء هندسة المضلع
وبالمثل، يمكنك إنشاء كائنات هندسة المضلع باستخدام الفئات `Polygon` و `LinearRing`.

```csharp
var rectangle = new Polygon(new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
}));
```

### الخطوة 4: الحصول على طول المضلع
بالنسبة للمضلعات، تُعيد طريقة `GetLength()` المحيط، وهو في الواقع **how to get length** للشكل.

```csharp
Console.WriteLine("{0:F}", rectangle.GetLength()); // Output: 4.00
```

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **طول صفر غير متوقع** | تحقق من أن نظام إحداثيات الهندسة يتطابق مع البيانات التي قدمتها؛ قد تتسبب النقاط المكررة في قطاعات بطول صفر. |
| **وحدات غير صحيحة** | تذكر أن `GetLength()` تُعيد القيم بوحدات نظام الإحداثيات. قم بالتحويل إلى أمتار/أقدام إذا لزم الأمر. |
| **الأداء مع مجموعات البيانات الكبيرة** | أعد استخدام كائنات الهندسة عندما يكون ذلك ممكنًا وتجنب إنشاء آلاف النقاط المؤقتة داخل الحلقات الضيقة. |

## الأسئلة المتكررة

**س:** هل Aspose.GIS لـ .NET متوافق مع جميع أطر .NET؟  
**ج:** Aspose.GIS لـ .NET متوافق مع .NET Framework 4.6.1 أو الإصدارات الأحدث، وكذلك .NET 5/6/7.

**س:** هل يمكنني تجربة Aspose.GIS لـ .NET قبل الشراء؟  
**ج:** نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.GIS لـ .NET من [here](https://releases.aspose.com/).

**س:** أين يمكنني العثور على الدعم لـ Aspose.GIS لـ .NET؟  
**ج:** يمكنك العثور على الدعم والمساعدة من منتدى مجتمع Aspose.GIS [here](https://forum.aspose.com/c/gis/33).

**س:** كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.GIS لـ .NET؟  
**ج:** يمكنك الحصول على ترخيص مؤقت من [here](https://purchase.aspose.com/temporary-license/).

**س:** هل يمكنني تخصيص تنسيق الإخراج لحسابات طول الهندسة؟  
**ج:** نعم، توفر Aspose.GIS لـ .NET خيارات تنسيق متعددة لتخصيص تنسيق الإخراج وفقًا لمتطلباتك.

## الخلاصة
في هذا الدرس غطينا **how to calculate geometry length .NET** لكل من هندسات الخط والمضلع باستخدام Aspose.GIS لـ .NET. باتباع الأمثلة خطوة بخطوة، يمكنك الآن دمج قياسات مكانية دقيقة في أي تطبيق .NET، سواء كان أداة GIS سطح مكتب، خدمة ويب، أو خط أنابيب معالجة بيانات خلفية.

---

**آخر تحديث:** 2026-08-13  
**تم الاختبار مع:** Aspose.GIS 24.11 for .NET  
**المؤلف:** Aspose

## دروس ذات صلة

- [تعلم كيفية إنشاء هندسة LineString باستخدام Aspose.GIS لـ .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [كيفية حساب المساحة باستخدام Aspose.GIS لـ .NET](/gis/net/geometry-analysis/get-geometry-area/)
- [كيفية إنشاء هندسة نقطة والحصول على نوع الهندسة باستخدام Aspose.GIS لـ .NET](/gis/net/geometry-analysis/get-geometry-type/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}