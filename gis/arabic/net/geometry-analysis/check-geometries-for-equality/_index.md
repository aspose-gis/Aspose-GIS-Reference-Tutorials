---
date: 2025-12-03
description: تعلم كيفية مقارنة الأشكال الهندسية باستخدام Aspose.GIS لـ .NET وتحقق
  من تساوي الأشكال الهندسية في تطبيقات .NET الخاصة بك.
language: ar
linktitle: How to Compare Geometries for Equality
second_title: Aspose.GIS .NET API
title: كيفية مقارنة الأشكال الهندسية للتساوي باستخدام Aspose.GIS لـ .NET
url: /net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية مقارنة الأشكال الهندسية للتساوي باستخدام Aspose.GIS لـ .NET

## المقدمة
في هذا البرنامج التعليمي ستكتشف **كيفية مقارنة الأشكال الهندسية** باستخدام Aspose.GIS لـ .NET. سواءً كنت تبني خدمة رسم خرائط، أو تُجري تحليلاً مكانياً، أو تحتاج ببساطة إلى التحقق من أن شكلين يمثلان نفس الموقع، فإن معرفة كيفية مقارنة الأشكال الهندسية أمر أساسي. سنستعرض مثالاً كاملاً من البداية إلى النهاية يوضح لك كيفية إنشاء الأشكال، تعديلها، واختبار تساويها في بضع أسطر من كود C# فقط.

## إجابات سريعة
- **ماذا يعني “مقارنة الأشكال الهندسية”؟** يتحقق مما إذا كان كائنان هندسيان يشغلان نفس الفضاء، بغض النظر عن طريقة إنشائهما.  
- **ما الطريقة المستخدمة؟** `SpatiallyEquals` من واجهة برمجة تطبيقات Aspose.GIS.  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تكفي للاختبار؛ يلزم ترخيص تجاري للإنتاج.  
- **الإصدارات المدعومة من .NET؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6+.  
- **الوقت التقريبي للتنفيذ؟** حوالي 5‑10 دقائق لفحص تساوي أساسي.

## ما هو تساوي الأشكال الهندسية؟
تساوي الأشكال الهندسية (المعروف أيضاً بالتساوي المكاني) يعني أن شكلين يمثلان نفس مجموعة النقاط على سطح الأرض. يمكن بناء الشكلين بطرق مختلفة—مثل MultiLineString مقابل LineString واحد—ومع ذلك قد يكونان متساويين مكانيًا.

## لماذا نستخدم Aspose.GIS لمقارنة الأشكال الهندسية؟
يوفر Aspose.GIS محركًا هندسيًا قويًا وعالي الأداء يتيح لك:
- التعامل مع مجموعة واسعة من صيغ المتجهات (WKT، GeoJSON، Shapefile، إلخ).  
- توفير طرق مقارنة دقيقة مثل `SpatiallyEquals`.  
- العمل دون اتصال بالإنترنت، دون الحاجة إلى خدمات خارجية، مما يجعله مثاليًا للبيئات الآمنة أو المعزولة.

## المتطلبات السابقة
قبل البدء، تأكد من توفر ما يلي:

- **.NET Framework أو .NET Core مثبت** – أي إصدار يدعمه Aspose.GIS.  
- **مكتبة Aspose.GIS لـ .NET** – حمّلها من [صفحة تنزيل Aspose.GIS](https://releases.aspose.com/gis/net/).  
- **بيئة تطوير متكاملة** – Visual Studio، Rider، أو VS Code مع ملحقات C#.

## استيراد المساحات الاسمية
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
أولاً، نقوم بإنشاء شكلين هندسيين سنقارنهما. في هذا المثال `geometry1` هو `MultiLineString` يتكون من مقطعين، بينما `geometry2` هو `LineString` واحد يمتد بين نفس نقطتي البداية والنهاية.

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

## الخطوة 2: فحص التساوي بين الأشكال الهندسية
الآن نستخدم طريقة `SpatiallyEquals` لمعرفة ما إذا كان الشكلان يُعتبران متساويين من قبل محرك GIS.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

تطبع وحدة التحكم القيمة `True` لأن الشكلين، رغم اختلاف طريقة إنشائهما، يغطيان نفس الخط من (0,0) إلى (2,2).

## الخطوة 3: تعديل أحد الأشكال
لتوضيح كيف يؤثر التغيير على التساوي، نضيف نقطة إضافية إلى `geometry2`.

```csharp
geometry2.AddPoint(3, 3);
```

## الخطوة 4: إعادة فحص التساوي بعد التعديل
بعد التعديل، لم يعد الشكلان متساويين، لذا تُعيد `SpatiallyEquals` القيمة `False`.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

تؤكد النتيجة `False` أن النقطة الإضافية كسرت التساوي المكاني.

## المشكلات الشائعة والنصائح
- **مشكلات الدقة** – إذا كنت تتعامل مع إحداثيات ذات دقة عالية جدًا، ففكّر في التقريب أو استخدام نسخة `SpatiallyEquals` التي تقبل هامش tolerence.  
- **اختلاف SRID** – تأكد من أن كلا الشكلين يستخدمان نفس معرف نظام الإحداثيات (SRID) قبل المقارنة.  
- **الأداء** – بالنسبة لمجموعات كبيرة، يمكن أن يقلل استخدام مقارنات دفعة عبر LINQ من الحمل الزائد.

## الأسئلة المتكررة
**س: هل يمكنني استخدام Aspose.GIS لـ .NET مع أطر .NET أخرى؟**  
ج: نعم، يعمل Aspose.GIS مع مشاريع .NET Framework، .NET Core، و .NET Standard.

**س: هل هناك نسخة تجريبية مجانية؟**  
ج: بالتأكيد. حمّل نسخة تجريبية من [صفحة إصدارات Aspose.GIS](https://releases.aspose.com/).

**س: أين يمكنني العثور على الوثائق الكاملة للـ API؟**  
ج: الوثائق التفصيلية موجودة على [صفحة توثيق Aspose.GIS](https://reference.aspose.com/gis/net/).

**س: كيف أحصل على مساعدة إذا واجهت مشكلة؟**  
ج: انشر سؤالك في منتدى مجتمع Aspose.GIS [هنا](https://forum.aspose.com/c/gis/33).

**س: هل يمكنني شراء ترخيص مؤقت للتقييم؟**  
ج: نعم، الترخيصات المؤقتة متوفرة على [صفحة الشراء](https://purchase.aspose.com/temporary-license/).

## الخاتمة
أنت الآن تعرف **كيفية مقارنة الأشكال الهندسية** باستخدام Aspose.GIS لـ .NET، من إنشاء الكائنات إلى فحص التساوي المكاني ومعالجة التعديلات. تُعد هذه القدرة حجر أساس لتحليلات مكانية أكثر تقدماً مثل التحقق من الطوبولوجيا، اكتشاف التكرارات، وتصفية البيانات بناءً على الشكل الهندسي.

---

**آخر تحديث:** 2025-12-03  
**تم الاختبار مع:** Aspose.GIS لـ .NET 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}