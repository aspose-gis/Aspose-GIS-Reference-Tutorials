---
date: 2025-12-31
description: تعرّف على كيفية إنشاء طبقة متجهة وتعيين نظام الإحداثيات المكاني للطبقة
  باستخدام Aspose.GIS لـ .NET. إتقان تعريف المرجع المكاني، إضافة ميزة نقطة، واسترجاع
  رمز EPSG.
linktitle: Set Layer Spatial Reference System
second_title: Aspose.GIS .NET API
title: إنشاء طبقة متجهة وتعيين نظام الإحداثيات المكاني للطبقة
url: /ar/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء طبقة متجهة وتعيين نظام الإسناد المكاني للطبقة

## مقدمة
في المشهد الواسع لأنظمة المعلومات الجغرافية (GIS)، يبرز **Aspose.GIS for .NET** كأداة قوية ومتعددة الاستخدامات للمطورين. في هذا البرنامج التعليمي ستقوم **بإنشاء طبقة متجهة**، تعريف نظام الإسناد المكاني لها، إضافة ميزة نقطة، واسترجاع رمز EPSG—كل ذلك بإرشادات واضحة خطوة بخطوة. سواء كنت مهندس GIS متمرسًا أو مبتدئًا، ستساعدك هذه التقنيات على ضبط نظام إحداثيات ملف الشيبفيل بشكل صحيح وتعزيز موثوقية سير عمل البيانات المكانية لديك.

## إجابات سريعة
- **ماذا يعني “إنشاء طبقة متجهة”؟** إنه ينشئ طبقة GIS جديدة (مثل ملف Shapefile) يمكنها تخزين الأشكال الهندسية مثل النقاط، الخطوط، أو المضلع.  
- **ما هو رمز EPSG المستخدم في المثال؟** EPSG 26918 (NAD83 / UTM المنطقة 18N).  
- **هل يمكنني إضافة ميزة نقطة بعد إنشاء الطبقة؟** نعم—استخدم `ConstructFeature()` وعيّن هندسة `Point`.  
- **كيف أسترجع نظام إسناد الطبقة؟** اقرأ `layer.SpatialReferenceSystem.EpsgCode` أو `.Name`.  
- **هل أحتاج إلى ترخيص لـ Aspose.GIS؟** يتوفر إصدار تجريبي مجاني؛ الترخيص مطلوب للاستخدام الإنتاجي.

## المتطلبات المسبقة
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات التالية:
- معرفة عملية ببرمجة .NET.  
- تثبيت Visual Studio على نظامك.  
- مكتبة Aspose.GIS for .NET، التي يمكنك تنزيلها [من هنا](https://releases.aspose.com/gis/net/).  
- فهم أساسي لأنظمة الإسناد المكاني في GIS.

## استيراد المساحات الاسمية
في مشروع .NET الخاص بك، ابدأ باستيراد المساحات الاسمية الضرورية للوصول إلى الوظائف التي توفرها Aspose.GIS. استخدم المقتطف التالي:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## الخطوة 1: تحديد مسار دليل المستندات
ابدأ بتحديد المسار إلى دليل المستندات الخاص بك. سيكون هذا هو الموقع الذي تُخزن فيه ملفات البيانات المكانية.

```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 2: تعريف نظام الإسناد المكاني وتعيين نظام إحداثيات ملف الشيبفيل
عرّف مسار ملف Shapefile، و**عرّف نظام الإسناد المكاني** باستخدام رمز EPSG (26918 في هذا المثال). هذه الخطوة **تضبط نظام إحداثيات ملف الشيبفيل** للطبقة.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## الخطوة 3: إنشاء طبقة متجهة
الآن **أنشئ طبقة متجهة** باستخدام مسار Shapefile المحدد، نوع السائق (Shapefile)، ونظام الإسناد المكاني الذي عرّفته للتو.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

## الخطوة 4: إضافة ميزة نقطة إلى الطبقة
أنشئ ميزة جديدة و**أضف ميزة نقطة** عن طريق تعيين هندستها (نقطة `Point` بالإحداثيات 60, 24). ثم أضف الميزة إلى الطبقة المتجهة.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

## الخطوة 5: استرجاع معلومات نظام الإسناد المكاني (استرجاع رمز EPSG)
افتح الطبقة المتجهة واسترجع معلومات حول نظام الإسناد المكاني، مثل رمز EPSG والاسم القابل للقراءة البشرية. هذا يوضح كيفية **استرجاع رمز EPSG** و**تعيين CRS للطبقة**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

كرر هذه الخطوات وفقًا لحالتك الخاصة، وستكون في طريقك لإتقان فن **إنشاء طبقة متجهة** وإدارة الإسنادات المكانية باستخدام Aspose.GIS for .NET.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **فشل فتح الطبقة** | سائق غير صحيح أو مسار ملف تالف | تحقق من `Drivers.Shapefile` وتأكد أن `path` يشير إلى ملف `.shp` موجود. |
| **عرض نظام إسناد غير صحيح** | استخدام رمز EPSG خاطئ | أعد التحقق من رمز EPSG من مصدر موثوق (مثل EPSG.io). |
| **الميزة لم تُحفظ** | عدم استدعاء `layer.Add(feature)` داخل كتلة `using` | تأكد من تنفيذ طريقة `Add` قبل التخلص من الطبقة. |

## الأسئلة المتكررة
### هل Aspose.GIS متوافق مع مكتبات GIS أخرى؟
نعم، يتكامل Aspose.GIS جيدًا مع مكتبات GIS أخرى ويمكن استخدامه جنبًا إلى جنب معها.

### هل يمكنني استخدام Aspose.GIS لتطبيقات سطح المكتب والويب؟
بالطبع! Aspose.GIS متعدد الاستخدامات ويمكن توظيفه في كل من تطبيقات سطح المكتب وتطبيقات الويب.

### هل هناك خيارات ترخيص متاحة لـ Aspose.GIS؟
نعم، يمكنك استكشاف خيارات الترخيص وإجراء عملية الشراء [من هنا](https://purchase.aspose.com/buy).

### هل يتوفر نسخة تجريبية مجانية لـ Aspose.GIS؟
بالتأكيد! يمكنك تنزيل نسخة تجريبية مجانية [من هنا](https://releases.aspose.com/).

### أين يمكنني طلب الدعم للاستفسارات المتعلقة بـ Aspose.GIS؟
لأي دعم أو استفسارات، زر [منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33).

## أسئلة متكررة إضافية
**س: كيف أغيّر CRS لملف Shapefile موجود؟**  
ج: افتح الطبقة، أنشئ `SpatialReferenceSystem` جديدًا بالرمز EPSG المطلوب، وعيّنها إلى `layer.SpatialReferenceSystem` قبل الحفظ.

**س: هل يمكنني إضافة أنواع هندسية أخرى (مثل المضلعات) باستخدام نفس النهج؟**  
ج: نعم—استبدل `new Point(x, y)` بـ `new Polygon(...)` أو `new LineString(...)` حسب الحاجة.

**س: هل يمكن العمل مع مجموعات بيانات كبيرة بكفاءة؟**  
ج: استخدم واجهات برمجة التطبيقات المتدفقة (`VectorLayer.Create` مع `FeatureCollection`) وتخلص من الطبقات بسرعة لتحرير الموارد.

**س: هل يدعم Aspose.GIS تحويل الإحداثيات؟**  
ج: نعم—استخدم `Geometry.Transform(targetSrs)` لإعادة إسقاط الهندسات بين أنظمة إسناد مختلفة.

**س: ما إصدارات .NET المدعومة؟**  
ج: يعمل Aspose.GIS مع .NET Framework 4.6+، .NET Core 3.1+، .NET 5/6/7.

## الخاتمة
في هذا البرنامج التعليمي استعرضنا كيفية **إنشاء طبقة متجهة**، تعريف نظام الإسناد المكاني لها، **إضافة ميزة نقطة**، و**استرجاع رمز EPSG** باستخدام Aspose.GIS for .NET. من خلال إتقان هذه الخطوات يمكنك ضبط نظام إحداثيات ملف الشيبفيل بثقة، إدارة CRS للطبقة، وبناء تطبيقات GIS موثوقة.

---

**آخر تحديث:** 2025-12-31  
**تم الاختبار مع:** Aspose.GIS 24.11 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}