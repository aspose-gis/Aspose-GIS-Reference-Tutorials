---
date: 2026-09-05
description: تعلم كيفية إنشاء حلقة داخلية لمضلع مع ثقب باستخدام Aspose.GIS لـ .NET.
  يوضح هذا الدليل كيفية إضافة ثقب إلى مضلع والعمل مع البيانات.
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: إنشاء Polygon مع هندسة ثقب
og_description: تعلم كيفية إنشاء حلقة داخلية لمضلع مع ثقب باستخدام Aspose.GIS لـ .NET.
  يوضح هذا الدليل كيفية إضافة ثقب إلى مضلع والعمل مع البيانات.
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: إنشاء حلقة داخلية لمضلع مع ثقب باستخدام Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: إنشاء حلقة داخلية لمضلع مع ثقب باستخدام Aspose.GIS
url: /ar/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء حلقة داخلية لمضلع مع فتحة باستخدام Aspose.GIS

## مقدمة
في هذا الدرس ستتعلم كيفية **إنشاء حلقة داخلية لمضلع** تحتوي على فتحة باستخدام Aspose.GIS لـ .NET. سواءً كنت تبني تطبيقًا للخرائط، أو تقوم بالتحليل المكاني، أو تحضر البيانات لخدمات GIS، فإن إدراج فتحة داخل مضلع يُعد مهارة أساسية. سنستعرض سير العمل بالكامل — من إعداد بيئة التطوير إلى إنشاء كائن مضلع صالح يمكن حفظه بأي تنسيق جغرافي مدعوم.

## إجابات سريعة
- **ماذا يعني “create polygon with hole”؟** يعني بناء مضلع يحتوي على حلقة (أو أكثر) داخلية (فتحات) يتم استبعادها من المساحة.  
- **أي مكتبة تتعامل مع ذلك؟** توفر Aspose.GIS لـ .NET دعمًا كاملاً للحلقات الخارجية والداخلية.  
- **هل أحتاج إلى ترخيص؟** الإصدار التجريبي المجاني يكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.  
- **كم من الوقت يستغرق؟** عادةً أقل من 10 دقائق للتنفيذ والاختبار.

## كيفية إضافة فتحة إلى مضلع باستخدام Aspose.GIS
حمّل بيئة GIS الخاصة بك، عرّف حلقة خارجية، ثم أضف حلقة (أو أكثر) داخلية. تقوم Aspose.GIS بتوجيه الحلقات تلقائيًا والتحقق من صحة الهندسة، لذا يمكنك التركيز على الإحداثيات التي تمثل الفراغ المطلوب.

## ما هي الحلقة الداخلية للمضلع؟
**حلقة داخلية للمضلع** هي حد داخلي يطرح مساحة من الشكل الخارجي للمضلع.  
تقوم بإنشائها عن طريق تعريف تسلسل مغلق من النقاط التي تتعامل معها Aspose.GIS كفتحة، والتي تُستبعد عند حساب المساحة أو عرض الشكل.

## لماذا إنشاء حلقة داخلية للمضلع باستخدام Aspose.GIS؟
تقوم Aspose.GIS بالتحقق من صحة وتصحيح توجيه الحلقات في أقل من 5 مللي ثانية للمضلعات النموذجية التي تحتوي على 200 نقطة، مما يلغي الحاجة إلى كتابة كود تحقق مخصص. كما تدعم **أكثر من 30 تنسيق ملف جغرافي** (Shapefile، GeoJSON، GML، KML، إلخ) ويمكنها معالجة مضلعات تصل إلى 10,000 نقطة دون تحميل الملف بالكامل في الذاكرة، مما يمنحك السرعة والقابلية للتوسع.

## سيناريوهات واقعية للمضلعات ذات الفتحات
1. **قطعة أرض بها بحيرة داخلية** – تُنمذج البحيرة كفتحة بحيث لا تُحسب في مساحة القطعة.  
2. **مخططات مباني مع ساحات داخلية** – تُستبعد الساحة من مخطط المبنى.  
3. **مناطق محمية داخل منطقة حفظ أكبر** – يمكنك استبعاد الأقسام المقيدة دون إنشاء طبقات منفصلة.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من توفر المتطلبات التالية:
1. مكتبة Aspose.GIS لـ .NET: يمكنك تنزيلها من **صفحة تنزيل Aspose.GIS لـ .NET**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).  
2. بيئة التطوير: تأكد من إعداد بيئة تطوير مع Visual Studio أو أي بيئة تطوير .NET أخرى مثبتة.

## استيراد مساحات الأسماء
تحتوي مساحة الأسماء `Aspose.Gis` على جميع أنواع الهندسة التي ستحتاجها، بما في ذلك `Polygon` و `LinearRing` وطرق المساعدة للتحقق من الصحة.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

الآن، دعنا نتابع لإنشاء هندسة مضلع بفتحة باستخدام Aspose.GIS لـ .NET.

## الخطوة 1: إنشاء كائن مضلع
`Polygon` هو نوع الهندسة في Aspose.GIS الذي يمثل مضلعًا مستويًا مع حلقات داخلية اختيارية. نبدأ بإنشاء كائن `Polygon` فارغ سيحتوي لاحقًا على كل من الحلقات الخارجية والداخلية.

```csharp
Polygon polygon = new Polygon();
```

## الخطوة 2: تعريف الحلقة الخارجية
`LinearRing` هو الفئة المستخدمة لكل من الحدود الخارجية والداخلية. تحدد الحلقة الخارجية الحد الخارجي للمضلع. أضف النقاط بترتيب عقارب الساعة لتشكيل شكل مغلق.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## الخطوة 3: تعريف الحلقة الداخلية (الفتحة)
`LinearRing` يمثل أيضًا الحلقات الداخلية. الحلقة الداخلية هي **الفتحة** التي ستُستبعد من مساحة المضلع. عادةً ما تُضاف النقاط بترتيب عكس عقارب الساعة، لكن Aspose.GIS يتعامل مع التوجيه تلقائيًا.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## الخطوة 4: تعيين الحلقة الخارجية وإضافة الحلقة الداخلية إلى المضلع
طريقة `AddInteriorRing` تُرفق حلقة (أو أكثر) داخلية إلى `Polygon`. استدعها بعد تعيين خاصية `ExteriorRing`؛ يمكنك تكرار الاستدعاء لإضافة عدة فتحات.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## نصائح وأفضل الممارسات
- **الاتجاه مهم للقراءة** – بينما تقوم Aspose.GIS بتصحيح الاتجاه تلقائيًا، فإن الحفاظ على الحلقات الخارجية باتجاه عقارب الساعة والحلقات الداخلية عكس عقارب الساعة يجعل الهندسة أسهل للفحص في عارضات GIS.  
- **إغلاق كل حلقة** – كرّر دائمًا الإحداثية الأولى كنقطة أخيرة؛ هذا يضمن شكلًا مغلقًا صالحًا.  
- **التحقق بعد الإنشاء** – يمكنك استدعاء `polygon.IsValid` للتأكد من أن الهندسة تتوافق مع معايير OGC قبل الحفظ.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| عدم ظهور الفتحة في عارض GIS | اتجاه الحلقة الداخلية معكوس | تأكد من إضافة النقاط في الاتجاه المعاكس للحلقة الخارجية (عكس عقارب الساعة). |
| خطأ عدم صلاحية المضلع | الحلقات غير مغلقة (الأول ≠ الأخير) | كرّر النقطة الأولى كنقطة أخيرة في كل حلقة (كما هو موضح أعلاه). |
| هندسة فارغة غير متوقعة | نسيان تعيين `ExteriorRing` قبل إضافة الحلقات الداخلية | عيّن `polygon.ExteriorRing` أولاً، ثم استدعِ `AddInteriorRing`. |

## الأسئلة المتكررة
### 1. ما هو Aspose.GIS؟
Aspose.GIS هي مكتبة .NET تمكّن المطورين من العمل مع البيانات الجغرافية، مما يسمح لهم بإنشاء، قراءة، ومعالجة تنسيقات ملفات جغرافية متعددة.

### 2. هل يمكنني استخدام Aspose.GIS للمشاريع التجارية؟
نعم، يمكنك استخدام Aspose.GIS للمشاريع الشخصية والتجارية عن طريق شراء ترخيص. زر **صفحة شراء Aspose.GIS**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)) لمزيد من التفاصيل.

### 3. هل يتوفر نسخة تجريبية مجانية لـ Aspose.GIS؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.GIS من **صفحة تنزيل النسخة التجريبية المجانية لـ Aspose.GIS**([https://releases.aspose.com/](https://releases.aspose.com/)).

### 4. أين يمكنني العثور على الدعم لـ Aspose.GIS؟
يمكنك العثور على الدعم لـ Aspose.GIS في [منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33).

### 5. كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.GIS؟
يمكنك الحصول على ترخيص مؤقت لـ Aspose.GIS من **صفحة الترخيص المؤقت لـ Aspose.GIS**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)).

---

**آخر تحديث:** 2026-09-05  
**تم الاختبار مع:** Aspose.GIS 24.11 لـ .NET  
**المؤلف:** Aspose

## الدروس ذات الصلة

- [كيفية إنشاء هندسة مضلع باستخدام Aspose.GIS لـ .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [تعلم كيفية إنشاء هندسة مضلع متعدد باستخدام Aspose.GIS](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [تحويل المضلع إلى خط باستخدام Aspose.GIS لـ .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}