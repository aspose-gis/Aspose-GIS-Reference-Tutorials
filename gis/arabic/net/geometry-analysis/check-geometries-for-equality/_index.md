---
date: 2026-06-05
description: تعلم كيفية مقارنة الأشكال الهندسية في .NET باستخدام Aspose.GIS، واكتشاف
  الأشكال الهندسية المكررة، والتحقق من تساوي الأشكال الهندسية في تطبيقاتك.
keywords:
- how to compare geometries
- detect duplicate geometries
- Aspose.GIS geometry equality
linktitle: كيفية مقارنة الأشكال الهندسية للتساوي
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to compare geometries in .NET using Aspose.GIS, detect duplicate
    geometries, and check geometry equality in your applications.
  headline: How to Compare Geometries for Equality using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard
      projects.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. Download a trial from the [Aspose.GIS releases page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Detailed docs are on the [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).
    question: Where can I find the full API documentation?
  - answer: Post your question on the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How do I get help if I run into an issue?
  - answer: Yes, temporary licenses are available on the [purchase page](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: كيفية مقارنة الأشكال الهندسية للتساوي باستخدام Aspose.GIS لـ .NET
url: /ar/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية مقارنة الأشكال الهندسية للتساوي باستخدام Aspose.GIS لـ .NET

## مقدمة
في هذا البرنامج التعليمي ستتعلم **كيفية مقارنة الأشكال الهندسية** باستخدام Aspose.GIS لـ .NET، وهي مهمة حيوية عندما تحتاج إلى اكتشاف الأشكال المكررة، والتحقق من صحة البيانات المكانية، أو فرض قواعد طوبولوجية. سواءً كنت تبني خدمة رسم خرائط، أو تُجري تحليلًا مكانيًا دفعيًا، أو ببساطة تتحقق من أن شكلين يشغلان نفس الموقع، فإن هذا الدليل يشرح لك كيفية إنشاء وتعديل واختبار تساوي الأشكال الهندسية باستخدام شفرة C# نظيفة وجاهزة للإنتاج.

## إجابات سريعة
- **ماذا يعني “compare geometries”؟** يتحقق مما إذا كان كائنان هندسيان يشغلان نفس المساحة، بغض النظر عن طريقة بنائهما.  
- **ما الطريقة المستخدمة؟** `SpatiallyEquals` من Aspose.GIS API.  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تكفي للاختبار؛ يلزم ترخيص تجاري للإنتاج.  
- **الإصدارات المدعومة من .NET؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6+.  
- **الوقت النموذجي للتنفيذ؟** حوالي 5‑10 دقائق لفحص التساوي الأساسي.

## ما هو تساوي الأشكال الهندسية؟
تساوي الأشكال الهندسية، المعروف أيضًا بالتساوي المكاني، يعني أن شكلين يمثلان نفس مجموعة النقاط بالضبط على سطح الأرض. حتى إذا تم بناء أحد الأشكال كـ `MultiLineString` والآخر كـ `LineString` واحد، فإنهما يُعتبران متساويين عندما تتطابق كل إحداثية ضمن التسامح المحدد. يتيح هذا التعريف للمطورين اكتشاف الأشكال المكررة بثقة عبر مصادر بيانات متباينة.

## لماذا نستخدم Aspose.GIS لمقارنة الأشكال الهندسية؟
توفر Aspose.GIS محركًا هندسيًا عالي الأداء وغير متصل بالإنترنت يلغي الحاجة إلى الخدمات الخارجية. إنها **تدعم أكثر من 30 صيغةً متجهة ورستريّة** (بما في ذلك WKT، GeoJSON، Shapefile، KML، GML) ويمكنها معالجة ملفات تحتوي على **مئات الآلاف من الرؤوس** مع الحفاظ على استهلاك الذاكرة أقل من 50 ميغابايت. طريقة المكتبة `SpatiallyEquals` تدرك الدقة، وتُعطي نتائج حتمية حتى مع إحداثيات ذات نقطة عائمة.

### لماذا هذا مهم للمطورين
عندما تحتاج إلى **اكتشاف الأشكال الهندسية المكررة** في عمليات الدفعات، أو خطوط أنابيب التحقق الفوري، أو ترحيلات بيانات GIS، فإن مكتبة موثوقة تُزيل التخمين وتضمن نتائج متسقة عبر مزودي البيانات المختلفين.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من وجود ما يلي:

- **.NET Framework أو .NET Core مثبت** – أي إصدار مدعوم من قبل Aspose.GIS.  
- **مكتبة Aspose.GIS لـ .NET** – قم بتنزيلها من [صفحة تنزيل Aspose.GIS](https://releases.aspose.com/gis/net/).  
- **بيئة تطوير متكاملة** – Visual Studio أو Rider أو VS Code مع ملحقات C#.

## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، أضف عبارات `using` المطلوبة حتى يعرف المترجم أين يجد فئات GIS:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## الخطوة 1: تعريف الأشكال الهندسية
`MultiLineString` تمثل مجموعة من مكوّنات الخط، بينما `LineString` تُعرّف خطًا مستمرًا واحدًا. كلا الفئتين يرثان من النوع الأساسي `Geometry`.

أولاً، نقوم بإنشاء شكلين هندسيين سنقارنهما. في هذا المثال `geometry1` هو `MultiLineString` مكوّن من مقطعين خطيين، بينما `geometry2` هو `LineString` واحد يمتد بين نفس نقطتي البداية والنهاية.

```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```

## الخطوة 2: فحص الأشكال الهندسية للتساوي
`SpatiallyEquals` تقيم ما إذا كان شكلان هندسيان يشغلان نفس مجموعة النقاط، مع إمكانية قبول قيمة تسامح لعدم دقة الأعداد ذات الفاصلة العائمة.

الآن نستخدم طريقة `SpatiallyEquals` لمعرفة ما إذا كان الشكلان يُعتبران متساويين بواسطة محرك GIS.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

تطبع وحدة التحكم `True` لأنهما، على الرغم من الاختلاف في البناء، يغطيان نفس الخط من (0,0) إلى (2,2).

## الخطوة 3: تعديل أحد الأشكال الهندسية
لتوضيح كيف يؤثر التغيير على التساوي، نضيف نقطة إضافية إلى `geometry2`.

```csharp
geometry2.AddPoint(3, 3);
```

## الخطوة 4: إعادة فحص التساوي بعد التعديل
بعد التعديل، لم تعد الأشكال الهندسية متساوية، لذا تُعيد `SpatiallyEquals` القيمة `False`.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

يؤكد الإخراج `False` أن النقطة الإضافية كسرّت التساوي المكاني.

## كيفية اكتشاف الأشكال الهندسية المكررة؟
حمّل كل شكل هندسي، استدعِ `SpatiallyEquals` مع تسامح مناسب، وقم بتصفية تلك التي تُعيد `True`. هذا النمط يتوسع بشكل جيد مع LINQ، مما يتيح لك تحديد الأشكال المكررة في مجموعات كبيرة باستخدام بضع أسطر من الشفرة فقط. يمكنك أيضًا دمجه مع `GroupBy` لتجميع الأشكال المتطابقة وتقليل تكاليف التخزين.

## المشكلات الشائعة والنصائح
- **مشكلات الدقة** – إذا كنت تعمل بإحداثيات ذات دقة عالية جدًا، فكر في التقريب أو استخدام نسخة التسامح من `SpatiallyEquals`.  
- **اختلاف SRID** – تأكد من أن كلا الشكلين يشتركان في نفس معرف نظام الإحداثيات المكانية (SRID) قبل المقارنة.  
- **الأداء** – بالنسبة للمجموعات الكبيرة، يمكن أن تقلل المقارنات الدفعية باستخدام LINQ أو الحلقات المتوازية من الحمل بشكل كبير.

## الأسئلة المتكررة
**س: هل يمكنني استخدام Aspose.GIS لـ .NET مع أطر .NET الأخرى؟**  
ج: نعم، Aspose.GIS يعمل مع مشاريع .NET Framework و .NET Core و .NET Standard.

**س: هل تتوفر نسخة تجريبية مجانية؟**  
ج: بالتأكيد. قم بتنزيل نسخة تجريبية من [صفحة إصدارات Aspose.GIS](https://releases.aspose.com/).

**س: أين يمكنني العثور على وثائق API الكاملة؟**  
ج: الوثائق التفصيلية موجودة على [صفحة توثيق Aspose.GIS](https://reference.aspose.com/gis/net/).

**س: كيف أحصل على مساعدة إذا واجهت مشكلة؟**  
ج: انشر سؤالك في منتدى مجتمع Aspose.GIS [هنا](https://forum.aspose.com/c/gis/33).

**س: هل يمكنني شراء ترخيص مؤقت للتقييم؟**  
ج: نعم، التراخيص المؤقتة متاحة على [صفحة الشراء](https://purchase.aspose.com/temporary-license/).

## الخلاصة
أنت الآن تعرف **كيفية مقارنة الأشكال الهندسية** باستخدام Aspose.GIS لـ .NET، من إنشاء الكائنات إلى فحص التساوي المكاني ومعالجة التعديلات. هذه القدرة تشكل أساسًا لتحليلات مكانية أكثر تقدمًا مثل التحقق من الطوبولوجيا، واكتشاف التكرارات، وتصفية الأشكال بناءً على الهندسة.

---

**آخر تحديث:** 2026-06-05  
**تم الاختبار باستخدام:** Aspose.GIS لـ .NET 24.11  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [إنشاء شكل مضلع C# والتحقق من التقاطع باستخدام Aspose.GIS لـ .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [كيفية إجراء تحليل التداخل المكاني للأشكال باستخدام Aspose.GIS لـ .NET](/gis/net/geometry-analysis/check-geometries-overlap/)
- [فحص توجيه الشبكة: الأشكال المتلامسة باستخدام Aspose.GIS](/gis/net/geometry-analysis/check-geometries-touching/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}