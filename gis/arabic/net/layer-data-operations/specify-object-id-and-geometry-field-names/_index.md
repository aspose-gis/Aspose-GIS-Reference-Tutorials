---
title: حدد معرف الكائن وأسماء الحقول الهندسية
linktitle: حدد معرف الكائن وأسماء الحقول الهندسية
second_title: Aspose.GIS .NET API
description: اكتشف سحر نظم المعلومات الجغرافية باستخدام Aspose.GIS لـ .NET! إدارة البيانات الجغرافية المكانية دون عناء. قم بالتنزيل الآن وأطلق العنان لقوة الذكاء المكاني.
weight: 20
url: /ar/net/layer-data-operations/specify-object-id-and-geometry-field-names/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# حدد معرف الكائن وأسماء الحقول الهندسية

## مقدمة
الشروع في رحلة إلى عالم نظم المعلومات الجغرافية (GIS) باستخدام Aspose.GIS for .NET يفتح عالمًا من الإمكانيات للمطورين والمتحمسين على حدٍ سواء. تمكّنك هذه المكتبة القوية من التعامل مع البيانات الجغرافية المكانية دون عناء. في هذا البرنامج التعليمي، سنرشدك خلال عملية تحديد معرف الكائن وأسماء الحقول الهندسية، ووضع الأساس لمساعيك في نظم المعلومات الجغرافية.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
-  Aspose.GIS for .NET: قم بتنزيل المكتبة وتثبيتها من[هنا](https://releases.aspose.com/gis/net/).
- دليل المستندات: قم بإعداد دليل لمستنداتك لتخزين قواعد البيانات الجغرافية.
- بيئة .NET: تأكد من أن لديك بيئة .NET صالحة للعمل.
## استيراد مساحات الأسماء
لبدء الأمور، تحتاج إلى استيراد مساحات الأسماء الضرورية إلى مشروعك. توفر مساحات الأسماء هذه الفئات والأساليب الأساسية للتفاعل مع Aspose.GIS for .NET.
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```
## الخطوة 1: حدد معرف الكائن وأسماء الحقول الهندسية
في هذه الخطوة، ستتعلم كيفية إعداد معرف الكائن وأسماء الحقول الهندسية لبيانات GIS الخاصة بك. وهذا أمر بالغ الأهمية لإدارة البيانات بكفاءة.
## الخطوة 1.1: قم بتعيين دليل المستندات
ابدأ بتحديد المسار إلى دليل المستندات الخاص بك:
```csharp
string dataDir = "Your Document Directory";
```
## الخطوة 1.2: إنشاء قاعدة بيانات جغرافية وتحديد الخيارات
قم بإنشاء قاعدة بيانات جغرافية بمعرف الكائن وأسماء حقول الهندسة المحددة:
```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // حدد اسم حقل معرف الكائن
        GeometryFieldName = "POINT",       // حدد اسم حقل الهندسة
    };
```
## الخطوة 1.3: إنشاء طبقة وإضافتها
أنشئ طبقة داخل قاعدة البيانات الجغرافية وأضف معلمًا ذو شكل هندسي محدد:
```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  //حدد الشكل الهندسي (في هذه الحالة، نقطة)
    layer.Add(feature);
}
```
## الخطوة 1.4: فتح واسترجاع البيانات من الطبقة
افتح الطبقة واحصل على البيانات منها بناءً على معرف الكائن المحدد:
```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // الإخراج: 1
}
```
## خاتمة
تهانينا! لقد نجحت في التنقل خلال عملية تحديد معرف الكائن وأسماء الحقول الهندسية باستخدام Aspose.GIS for .NET. وهذا يضع أساسًا متينًا لمشاريع نظم المعلومات الجغرافية الخاصة بك، مما يتيح لك إدارة البيانات الجغرافية المكانية بسهولة.
## أسئلة مكررة
### س: هل يمكنني استخدام Aspose.GIS for .NET في تطبيقات الويب الخاصة بي؟
ج: نعم، Aspose.GIS for .NET مناسب لكل من تطبيقات سطح المكتب والويب، مما يوفر إمكانات جغرافية مكانية متعددة الاستخدامات.
### س: هل هناك نسخة تجريبية متاحة قبل الشراء؟
 ج: نعم، يمكنك استكشاف ميزات Aspose.GIS for .NET من خلال الإصدار التجريبي المجاني المتاح[هنا](https://releases.aspose.com/).
### س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.GIS لـ .NET؟
 ج: يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/) لأغراض التقييم.
### س: ما هي أنظمة الإسناد المكاني التي يدعمها Aspose.GIS for .NET؟
ج: يدعم Aspose.GIS for .NET العديد من أنظمة الإسناد المكاني، مما يوفر المرونة لمجموعات البيانات الجغرافية المختلفة.
### س: أين يمكنني طلب المساعدة أو مناقشة الاستفسارات المتعلقة بـ Aspose.GIS؟
 ج: قم بزيارة منتدى Aspose.GIS[هنا](https://forum.aspose.com/c/gis/33) للدعم والمناقشات.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
