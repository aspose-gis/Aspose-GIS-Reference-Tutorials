---
date: 2025-12-23
description: تعلم كيفية تحويل الهندسة إلى WKT مع خيارات متنوعة، وضبط تنسيق الأرقام
  وتعديل الدقة العشرية باستخدام Aspose.GIS لـ .NET.
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: تحويل الهندسة إلى خيارات متغير WKT باستخدام Aspose.GIS
url: /ar/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل الهندسة إلى خيارات متغير WKT باستخدام Aspose.GIS

## المقدمة
في تطبيقات .NET الحديثة، **تحويل الهندسة إلى WKT** هو خطوة شائعة عندما تحتاج إلى تبادل البيانات المكانية مع أنظمة أخرى أو تخزينها بصيغة نصية. تجعل Aspose.GIS لـ .NET هذا التحويل سهلًا مع إعطائك التحكم الكامل في متغير WKT، تنسيق الأرقام، ودقة الكسور العشرية. في هذا الدرس ستتعلم كيفية تحويل الهندسة إلى WKT، اختيار المتغير المناسب، وضبط المخرجات بدقة لتلبية متطلبات مشروعك بالضبط.

## إجابات سريعة
- **ماذا يعني “تحويل الهندسة إلى WKT”؟** يحول الكائنات الهندسية (نقاط، خطوط، مضلعات) إلى تمثيل النص المعروف باسم Well‑Known Text.  
- **ما هي متغيرات WKT المدعومة؟** `Iso`، `SimpleFeatureAccessOutdated`، و `ExtendedPostGis`.  
- **كيف يمكنني التحكم في دقة الكسور العشرية؟** استخدم خيارات `NumericFormat` مثل `General`، `RoundTrip`، أو `Flat`.  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، يلزم ترخيص تجاري للاستخدام غير التجريبي.  
- **ما إصدارات .NET المتوافقة؟** .NET Framework 4.0+ و .NET 5/6/7.

## ما هو “تحويل الهندسة إلى WKT”؟
تحويل الهندسة إلى WKT ينتج سلسلة قابلة للقراءة تصف الكائنات المكانية. تُقبل هذه الصيغة على نطاق واسع من قبل أدوات GIS، قواعد البيانات، وخدمات الويب، مما يجعلها مثالية لتبادل البيانات.

## لماذا نستخدم Aspose.GIS لهذا التحويل؟
- **التحكم في الدقة** – اختر عدد المنازل العشرية التي تُصدر.  
- **مرونة المتغير** – طابق لهجة WKT المطلوبة بالضبط من نظامك المستقبلي.  
- **بدون تبعيات خارجية** – مكتبة .NET صافية، بدون ملفات ثنائية أصلية.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

1. **Aspose.GIS لـ .NET** – قم بتنزيله وتثبيته من [صفحة التنزيل](https://releases.aspose.com/gis/net/).  
2. **بيئة التطوير** – أي نسخة حديثة من Visual Studio أو VS Code مع .NET SDK.  
3. **معرفة أساسية بـ C#** – إلمام بالفئات، الكائنات، وإطار عمل .NET.

## استيراد المساحات الاسمية
أولاً، استدعِ المساحات الاسمية المطلوبة إلى النطاق:

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## الخطوة 1: إنشاء كائن Point
أنشئ كائن `Point` ستقوم لاحقًا **بتحويل الهندسة إلى WKT**. يتضمن النقطة خط العرض، خط الطول، وقيمة قياس اختيارية (M):

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## الخطوة 2: تعيين نظام الإحداثيات المرجعي (SRS)
حدد نظام إحداثيات مرجعي حتى يعرف إخراج WKT نظام الإحداثيات الذي يجب الإشارة إليه. هنا نستخدم النظام الشائع WGS84:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## الخطوة 3: تحديد متغير WKT
اختر المتغير المناسب لـ WKT عندما **تحول الهندسة إلى WKT**. كل متغير ينسق الإخراج بطريقة مختلفة قليلاً:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## الخطوة 4: التحكم في تنسيق الأرقام (تعيين تنسيق الأرقام وضبط دقة الكسور العشرية)
قم بضبط تمثيل الأرقام للإحداثيات. تسمح لك فئة `NumericFormat` **بتعيين تنسيق الأرقام** و**ضبط دقة الكسور العشرية** لتناسب احتياجاتك:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## المشكلات الشائعة والنصائح
- **قيمة M مفقودة** – إذا لم تكن بحاجة إلى قياس، احذف خاصية `M`؛ سيقوم المتغير ISO بحذفها تلقائيًا.  
- **دقة غير متوقعة** – تأكد من أنك تستخدم `NumericFormat` الصحيح؛ `General` يحافظ على الدقة الكاملة للنوع double، بينما `Flat` يقرب إلى عدد المنازل العشرية المحدد.  
- **عدم عرض SRID** – فقط متغير `ExtendedPostGis` يضيف البادئة `SRID=` إلى الإخراج. اختر هذا المتغير عندما يتوقع نظامك المستهدف وجود SRID.

## الخاتمة
باتباع هذه الخطوات، أصبحت الآن تعرف **كيفية تحويل الهندسة إلى WKT**، اختيار المتغير المناسب، والتحكم بدقة في تمثيل الأرقام. يمنحك ذلك المرونة لدمج Aspose.GIS مع أي سير عمل GIS، قاعدة بيانات، أو خدمة ويب تستقبل WKT.

## الأسئلة المتكررة
### هل Aspose.GIS متوافق مع جميع إصدارات .NET؟
نعم، تدعم Aspose.GIS .NET Framework 4.0 وما فوق.  

### هل يمكنني استخدام Aspose.GIS في المشاريع التجارية؟
نعم، يمكن استخدام Aspose.GIS في المشاريع الشخصية والتجارية على حد سواء.  

### هل توفر Aspose.GIS دعمًا لتنسيقات بيانات مكانية أخرى؟
نعم، تدعم Aspose.GIS مجموعة واسعة من تنسيقات البيانات المكانية، بما في ذلك ESRI Shapefile، GeoJSON، و KML.  

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.GIS؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.GIS من [هنا](https://releases.aspose.com/).  

### أين يمكنني الحصول على المساعدة أو الدعم لـ Aspose.GIS؟
يمكنك طرح استفساراتك أو طلب المساعدة من مجتمع Aspose.GIS عبر [المنتدى](https://forum.aspose.com/c/gis/33).

## أسئلة شائعة
**س: كيف يمكنني تصدير مجموعة Geometry إلى سلسلة WKT واحدة؟**  
ج: قم بالتكرار على كل كائن Geometry في المجموعة ودمج نتائج `AsText` الخاصة به، مع إمكانية الفصل بينها بفواصل أو أسطر جديدة.

**س: هل يمكنني تغيير SRID دون تعديل الإحداثيات؟**  
ج: نعم، قم بتعيين خاصية `SpatialReferenceSystem` إلى SRID المطلوب؛ تظل قيم الإحداثيات دون تغيير.

**س: ماذا يحدث إذا استخدمت متغير WKT غير مدعوم؟**  
ج: ستطرح Aspose.GIS استثناء `ArgumentException`. تأكد دائمًا من صحة المتغير مقارنةً بقيم تعداد `WktVariant`.

---

**آخر تحديث:** 2025-12-23  
**تم الاختبار مع:** Aspose.GIS 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}