---
title: الحصول على قيمة سمة الميزة (افتراضي)
linktitle: الحصول على قيمة سمة الميزة (افتراضي)
second_title: Aspose.GIS .NET API
description: أطلق العنان لقوة Aspose.GIS لـ .NET! يمكنك استرداد قيم سمات الميزات ومعالجتها بسهولة باستخدام هذا الدليل التفصيلي خطوة بخطوة. قم بتنزيل النسخة التجريبية الآن!
weight: 14
url: /ar/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# الحصول على قيمة سمة الميزة (افتراضي)

## مقدمة
مرحبًا بك في عالم Aspose.GIS لـ .NET! في هذا الدليل الشامل، سنتعمق في تعقيدات استرداد قيم سمات الميزة باستخدام الإمكانات القوية لـ Aspose.GIS. سواء كنت مطورًا متمرسًا أو بدأت للتو، سيوفر لك هذا البرنامج التعليمي إرشادات تفصيلية خطوة بخطوة، مما يضمن لك الاستفادة من الإمكانات الكاملة لهذه الأداة الرائعة.
## المتطلبات الأساسية
قبل الشروع في مغامرة البرمجة هذه، تأكد من توفر المتطلبات الأساسية التالية:
- معرفة عملية بـ C# و.NET Framework.
-  تم تثبيت Aspose.GIS لـ .NET. إذا لم يكن الأمر كذلك، قم بتنزيله من[هنا](https://releases.aspose.com/gis/net/).
- محرر التعليمات البرمجية، مثل Visual Studio، للمتابعة بسلاسة.
## استيراد مساحات الأسماء
في مشروع C# الخاص بك، تأكد من تضمين مساحات الأسماء الضرورية:
```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
الآن، دعونا نقسم كل مثال إلى سلسلة من الخطوات سهلة المتابعة.
## الحصول على قيمة سمة الميزة (افتراضي)
### الخطوة 1: إعداد البيئة
ابدأ بتحديد المسار إلى دليل المستندات الخاص بك:
```csharp
string dataDir = "Your Document Directory";
```
### الخطوة 2: إنشاء طبقة GeoJson
قم بإنشاء طبقة GeoJson وحدد سمة بقيم افتراضية:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### الخطوة 3: بناء الميزة
إنشاء ميزة باستخدام السمة المحددة:
```csharp
    Feature feature = layer.ConstructFeature();
```
### الخطوة 4: استرداد القيم
استرداد قيم السمات باستخدام سيناريوهات مختلفة:
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // القيمة == فارغة
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // القيمة == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // القيمة == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## ضبط القيم الافتراضية
### الخطوة 1: إنشاء طبقة GeoJson أخرى
كرر العملية مع طبقة GeoJson مختلفة وسمة مزدوجة:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### الخطوة 2: إنشاء ميزة (مرة أخرى)
```csharp
    Feature feature = layer.ConstructFeature();
```
### الخطوة 3: استرداد وتعيين القيم
استرداد وتعيين قيم السمات، مع عرض الإعدادات الافتراضية:
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // القيمة == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // القيمة == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // القيمة == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
تهانينا! لقد نجحت في استغلال قوة Aspose.GIS for .NET في استرداد قيم سمات الميزات ومعالجتها.
## خاتمة
في هذا البرنامج التعليمي، اكتشفنا الفروق الدقيقة في استرداد قيم سمات الميزة باستخدام Aspose.GIS for .NET. بفضل واجهة برمجة التطبيقات (API) البديهية وإمكانياتها القوية، يفتح Aspose.GIS عالمًا من الإمكانيات لتطوير نظم المعلومات الجغرافية في بيئات .NET.
## أسئلة مكررة
### هل Aspose.GIS متوافق مع .NET Core؟
نعم، Aspose.GIS متوافق تمامًا مع .NET Core، مما يوفر دعمًا عبر الأنظمة الأساسية.
### هل يمكنني استخدام Aspose.GIS للمشاريع التجارية؟
قطعاً! يأتي Aspose.GIS مزودًا برخصة تجارية تسمح لك باستخدامه في تطبيقاتك التجارية دون أي قيود.
### أين يمكنني العثور على دعم وموارد إضافية؟
 قم بزيارة[منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33) لدعم المجتمع واستكشاف[توثيق](https://reference.aspose.com/gis/net/) للحصول على معلومات متعمقة.
### هل هناك نسخة تجريبية مجانية متاحة؟
 نعم، يمكنك استكشاف Aspose.GIS من خلال النسخة التجريبية المجانية. تنزيله[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على ترخيص مؤقت لأغراض الاختبار؟
 للحصول على تراخيص مؤقتة، قم بزيارة[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
