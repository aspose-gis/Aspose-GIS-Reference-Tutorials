---
date: 2026-01-13
description: تعلم كيفية تحويل ملف shapefile إلى geojson باستخدام Aspose.GIS لـ .NET.
  يغطي الدليل أيضًا نسخ السمات بين الطبقات وتوليد ملف geojson باستخدام C#.
linktitle: Extract Features to GeoJSON
second_title: Aspose.GIS .NET API
title: كيفية تحويل ملف Shapefile إلى GeoJSON باستخدام Aspose.GIS لـ .NET
url: /ar/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل Shapefile إلى GeoJSON باستخدام Aspose.GIS لـ .NET

## المقدمة
في هذا الدرس الشامل خطوة بخطوة ستتعلم **كيفية تحويل shapefile إلى geojson** باستخدام مكتبة Aspose.GIS القوية لـ .NET. سواءً كنت تبني خدمة ويب للخرائط، أو تُعد بيانات لتطبيق GIS على الهاتف المحمول، أو تحتاج ببساطة إلى تبادل البيانات بين الصيغ، يوضح لك هذا الدليل ما يجب فعله، ولماذا كل خطوة مهمة، وكيفية تجنب الأخطاء الشائعة.

## إجابات سريعة
- **ما الذي يغطيه هذا الدرس؟** تحويل Shapefile إلى ملف GeoJSON، نسخ السمات بين الطبقات، وإنشاء الناتج باستخدام C#.
- **ما المكتبة المطلوبة؟** Aspose.GIS لـ .NET.
- **هل أحتاج إلى ترخيص؟** يلزم ترخيص مؤقت أو كامل للإنتاج؛ نسخة تجريبية مجانية تكفي للتقييم.
- **كم يستغرق التنفيذ؟** حوالي 10‑15 دقيقة للتحويل الأساسي.
- **هل يمكن تشغيله على .NET Core/.NET 6؟** نعم – الكود يعمل على جميع إصدارات .NET المدعومة.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

- Aspose.GIS لـ .NET: تأكد من تثبيت المكتبة. إذا لم تكن مثبتة، يمكنك تنزيلها من صفحة [Aspose.GIS for .NET](https://releases.aspose.com/gis/net/).
- بيانات Shapefile: احرص على وجود Shapefile جاهز كمدخل. إذا كنت تحتاج إلى بيانات نموذجية، يمكنك العثور عليها في [توثيق Aspose.GIS](https://reference.aspose.com/gis/net/).
- بيئة .NET: قم بإعداد بيئة .NET لتشغيل الكود المرفق.
- دليل المستندات: عرّف المسار إلى دليل المستندات في مقطع الكود.

الآن بعد أن أصبح كل شيء جاهزًا، لنبدأ بتحويل shapefile إلى geojson!

## ما هو “convert shapefile to geojson”؟
تحويل Shapefile إلى GeoJSON يعني قراءة المعالم المتجهة من صيغة ESRI Shapefile الكلاسيكية وكتابتها كوثيقة GeoJSON حديثة صديقة للويب. يُستخدم GeoJSON على نطاق واسع في مكتبات رسم الخرائط بجافاسكريبت (Leaflet, Mapbox GL) وواجهات برمجة التطبيقات، مما يجعل هذا التحويل مهمة متكررة في تطوير GIS.

## لماذا نستخدم Aspose.GIS لهذا التحويل؟
تُجرد Aspose.GIS التفاصيل منخفضة المستوى لصيغ الملفات، وتتيح لك نسخ جداول السمات بسهولة، وتوفر واجهة برمجة تطبيقات كائنية نظيفة تعمل عبر .NET Framework, .NET Core, و .NET 5/6. هذا يعني أنك تستطيع التركيز على منطق الأعمال بدلاً من تحليل الملفات الثنائية.

## استيراد المساحات الاسمية
أولاً، أضف المساحات الاسمية الضرورية في الكود الخاص بك:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

هذه المساحات الاسمية أساسية للعمل مع وظائف Aspose.GIS.

## كيفية تحويل Shapefile إلى GeoJSON
فيما يلي سير العمل الكامل مقسّم إلى خطوات واضحة. كل خطوة تتضمن شرحًا مختصرًا يليه مقطع الكود الذي تحتاج إلى نسخه إلى مشروعك.

### الخطوة 1: فتح Shapefile الإدخالي
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```
افتح Shapefile الإدخالي باستخدام طريقة `VectorLayer.Open`. سيعطيك ذلك مجموعة قابلة للتعداد من كائنات `Feature`.

### الخطوة 2: إنشاء GeoJSON الناتج
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```
أنشئ الملف الناتج باستخدام طريقة `VectorLayer.Create`، مع تحديد السائق `Drivers.GeoJson`.

### الخطوة 3: نسخ السمات بين الطبقات
```csharp
outputLayer.CopyAttributes(inputLayer);
```
هذه السطر الواحد ينسخ مخطط السمات (أسماء الحقول، الأنواع) من Shapefile المصدر إلى طبقة GeoJSON الجديدة — تمامًا ما تصفه العبارة الثانوية *copy attributes between layers*.

### الخطوة 4: معالجة المعالم
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```
تكرّر عبر كل معلم في Shapefile حتى تتمكن من تطبيق أي منطق مخصص قبل كتابته.

### الخطوة 5: تصفية المعالم حسب التاريخ
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
في هذا المثال نتخطى السجلات التي يكون حقل `dob` (تاريخ الميلاد) فيها مفقودًا أو أقدم من 1 يناير 1982. يمكنك تعديل الفلتر ليتناسب مع متطلبات بياناتك.

### الخطوة 6: إنشاء معلم جديد (C# Generate GeoJSON File)
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
هنا نبني `Feature` جديد لطبقة GeoJSON، ننسخ الهندسة وقيم السمات، ونضيفه إلى الناتج. هذا هو جوهر *c# generate geojson file*.

تهانينا! لقد نجحت في **تحويل shapefile إلى geojson** وتعلمت كيفية نسخ السمات بين الطبقات على طول الطريق.

## المشكلات الشائعة والحلول
| المشكلة | لماذا يحدث | الحل |
|---------|------------|------|
| ملف الإخراج فارغ | تم استدعاء `CopyAttributes` بعد إغلاق طبقة الإخراج | تأكد من بقاء كتلة `using` الخاصة بـ `outputLayer` مفتوحة حتى بعد إضافة جميع المعالم. |
| فلتر التاريخ يزيل جميع السجلات | اسم الحقل غير صحيح أو تنسيق التاريخ غير متوقع | تحقق من اسم السمة (`dob`) واستخدم `GetValue<string>` إذا كانت التواريخ مخزنة كسلاسل. |
| استثناء الترخيص | تشغيل بدون ترخيص Aspose.GIS صالح في الإنتاج | طبق ترخيصًا مؤقتًا أو كاملًا كما هو موضح في توثيق Aspose. |

## الأسئلة المتكررة
**س: أين يمكنني العثور على مزيد من التوثيق؟**  
ج: زر [توثيق Aspose.GIS](https://reference.aspose.com/gis/net/) للحصول على معلومات تفصيلية.

**س: كيف يمكنني الحصول على ترخيص مؤقت؟**  
ج: يمكنك الحصول على ترخيص مؤقت [من هنا](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني طلب الدعم؟**  
ج: انضم إلى [منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33) للحصول على دعم المجتمع والنقاشات.

**س: هل هناك نسخة تجريبية مجانية متاحة؟**  
ج: نعم، يمكنك العثور على النسخة التجريبية [من هنا](https://releases.aspose.com/).

**س: أين يمكنني شراء Aspose.GIS لـ .NET؟**  
ج: يمكنك شراء المنتج [من هنا](https://purchase.aspose.com/buy).

## الخاتمة
في هذا الدرس استعرضنا العملية الكاملة لـ **convert shapefile to geojson** باستخدام Aspose.GIS لـ .NET، وأظهرنا كيفية نسخ السمات بين الطبقات، وقدمنا طريقة نظيفة لـ *c# generate geojson file*. جرّب فلاتر مختلفة، مجموعات بيانات أكبر، أو تحويلات هندسية إضافية لتستفيد بالكامل من إمكانيات المكتبة.

---

**آخر تحديث:** 2026-01-13  
**تم الاختبار مع:** Aspose.GIS لـ .NET (أحدث إصدار ثابت)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}