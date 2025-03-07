---
title: ضبط نظام الإسناد المكاني للطبقة
linktitle: ضبط نظام الإسناد المكاني للطبقة
second_title: Aspose.GIS .NET API
description: الإعداد الرئيسي لنظام الإسناد المكاني للطبقة باستخدام Aspose.GIS لـ .NET. ارفع مستوى مشاريع نظم المعلومات الجغرافية الخاصة بك من خلال هذا البرنامج التعليمي خطوة بخطوة.
weight: 19
url: /ar/net/layer-data-operations/set-layer-spatial-reference-system/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ضبط نظام الإسناد المكاني للطبقة

## مقدمة
في المشهد الواسع لأنظمة المعلومات الجغرافية (GIS)، تبرز Aspose.GIS for .NET كأداة قوية ومتعددة الاستخدامات للمطورين. سيرشدك هذا البرنامج التعليمي خلال عملية إعداد نظام الإسناد المكاني للطبقة باستخدام Aspose.GIS for .NET. سواء كنت مطورًا متمرسًا أو وافدًا جديدًا في مجال تطوير نظم المعلومات الجغرافية، سيساعدك هذا الدليل التفصيلي خطوة بخطوة على تسخير قوة Aspose.GIS لتعزيز قدرات معالجة البيانات المكانية لديك.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- معرفة عملية ببرمجة .NET.
- تم تثبيت Visual Studio على نظامك.
-  Aspose.GIS for .NET Library، والتي يمكنك تنزيلها[هنا](https://releases.aspose.com/gis/net/).
- الفهم الأساسي لأنظمة الإسناد المكاني في نظم المعلومات الجغرافية.
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، ابدأ باستيراد مساحات الأسماء الضرورية للوصول إلى الوظائف التي يوفرها Aspose.GIS. استخدم مقتطف الكود التالي:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```
## الخطوة 1: حدد دليل المستندات
ابدأ بتحديد المسار إلى دليل المستند الخاص بك. سيكون هذا هو الموقع الذي يتم فيه تخزين ملفات البيانات المكانية الخاصة بك.
```csharp
string dataDir = "Your Document Directory";
```
## الخطوة 2: إنشاء وتعيين نظام الإسناد المكاني
حدد المسار لملف الشكل، وقم بإنشاء نظام إسناد مكاني جديد باستخدام رمز EPSG (26918 في هذا المثال).
```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```
## الخطوة 3: إنشاء طبقة المتجهات
استخدم Aspose.GIS لإنشاء طبقة متجهة بمسار Shapefile المحدد ونوع برنامج التشغيل (Shapefile) ونظام الإسناد المكاني.
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // الكود الخاص بك لمزيد من العمليات على الطبقة موجود هنا
}
```
## الخطوة 4: إضافة ميزة إلى الطبقة
قم ببناء معلم جديد وضبط شكله الهندسي (في هذه الحالة، نقطة بإحداثيات 60، 24). أضف الميزة إلى طبقة المتجهات.
```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```
## الخطوة 5: استرجاع معلومات نظام الإسناد المكاني
افتح طبقة المتجهات واحصل على معلومات حول نظام الإسناد المكاني.
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```
كرر هذه الخطوات وفقًا لحالة الاستخدام المحددة الخاصة بك، وستكون في طريقك لإتقان فن إعداد نظام الإسناد المكاني للطبقة باستخدام Aspose.GIS لـ .NET.
## خاتمة
في هذا البرنامج التعليمي، استكشفنا الخطوات الأساسية لتعيين نظام الإسناد المكاني للطبقة باستخدام Aspose.GIS for .NET. بفضل واجهة برمجة التطبيقات (API) البديهية والميزات القوية، يعمل Aspose.GIS على تمكين المطورين من التعامل مع البيانات المكانية بسلاسة. قم بدمج هذه التقنيات في مشاريع نظم المعلومات الجغرافية الخاصة بك لرفع قدرات معالجة البيانات المكانية لديك.
## أسئلة مكررة
### هل Aspose.GIS متوافق مع مكتبات نظم المعلومات الجغرافية الأخرى؟
نعم، يتكامل Aspose.GIS بشكل جيد مع مكتبات نظم المعلومات الجغرافية الأخرى ويمكن استخدامه مع هذه المكتبات.
### هل يمكنني استخدام Aspose.GIS لكل من تطبيقات سطح المكتب والويب؟
قطعاً! Aspose.GIS متعدد الاستخدامات ويمكن استخدامه في كل من تطبيقات سطح المكتب والتطبيقات المستندة إلى الويب.
### هل هناك أي خيارات ترخيص متاحة لـ Aspose.GIS؟
 نعم، يمكنك استكشاف خيارات الترخيص وإجراء عملية شراء[هنا](https://purchase.aspose.com/buy).
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.GIS؟
 بالتأكيد! يمكنك تنزيل نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
### أين يمكنني طلب الدعم للاستفسارات المتعلقة بـ Aspose.GIS؟
 للحصول على أي دعم أو استفسارات، قم بزيارة[منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
