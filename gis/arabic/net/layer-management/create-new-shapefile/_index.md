---
title: إنشاء ملف شكل جديد
linktitle: إنشاء ملف شكل جديد
second_title: Aspose.GIS .NET API
description: تعرف على كيفية إنشاء ملف شكل جديد باستخدام Aspose.GIS for .NET. اتبع دليلنا خطوة بخطوة واطلق العنان لقوة معالجة البيانات المكانية.
type: docs
weight: 12
url: /ar/net/layer-management/create-new-shapefile/
---
## مقدمة
إذا كنت تتعمق في تطوير أنظمة المعلومات الجغرافية (GIS) باستخدام .NET، فإن Aspose.GIS هو الحل الأمثل لك. تعمل هذه المكتبة القوية على تمكين المطورين من العمل بسلاسة مع البيانات المكانية، وفي هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء ملف شكل جديد باستخدام Aspose.GIS for .NET.
## المتطلبات الأساسية
قبل أن ننتقل إلى البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- الفهم الأساسي للغة البرمجة C#.
- تم تثبيت Visual Studio على جهازك.
-  Aspose.GIS لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/gis/net/).
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية للاستفادة من وظائف Aspose.GIS:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## الخطوة 1: قم بإعداد مشروعك
ابدأ بإنشاء مشروع C# جديد في Visual Studio وقم بتضمين مكتبة Aspose.GIS.
## الخطوة 2: تحديد دليل المستندات
```csharp
string dataDir = "Your Document Directory";
```
استبدل "دليل المستندات الخاص بك" بالمسار الفعلي الذي تريد حفظ ملف الشكل الجديد فيه.
## الخطوة 3: إنشاء VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //أضف السمات قبل إضافة الميزات
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
يقوم مقطع التعليمات البرمجية هذا بإعداد الطبقة المتجهة وتحديد السمات الخاصة بالمعالم الخاصة بك.
## الخطوة 4: إضافة الميزات
### الحالة 1: تعيين القيم بشكل فردي
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
### الحالة 2: تعيين قيم جديدة لجميع السمات
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## خاتمة
 تهانينا! لقد نجحت في إنشاء ملف شكل جديد باستخدام Aspose.GIS for .NET. يغطي هذا البرنامج التعليمي أساسيات إعداد مشروعك وتحديد السمات وإضافة الميزات. أثناء استكشاف المزيد، راجع[توثيق](https://reference.aspose.com/gis/net/) للميزات والوظائف المتقدمة.
## أسئلة مكررة
### س: هل يمكنني استخدام Aspose.GIS مع لغات البرمجة الأخرى؟
يدعم Aspose.GIS بشكل أساسي .NET، ولكن هناك إصدارات متاحة لـ Java أيضًا.
### س: هل هناك نسخة تجريبية مجانية متاحة؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### س: أين يمكنني العثور على الدعم لـ Aspose.GIS؟
 قم بزيارة[منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33) لدعم المجتمع والمناقشات.
### س: كيف يمكنني الحصول على ترخيص مؤقت؟
 احصل على ترخيصك المؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### س: أين يمكنني شراء Aspose.GIS لـ .NET؟
 يمكنك شراء المكتبة[هنا](https://purchase.aspose.com/buy).