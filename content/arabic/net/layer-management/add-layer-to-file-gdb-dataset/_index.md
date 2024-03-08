---
title: إتقان نظم المعلومات الجغرافية - أضف طبقات إلى GDB باستخدام Aspose.GIS لـ .NET
linktitle: أضف طبقة إلى مجموعة بيانات ملف GDB
second_title: Aspose.GIS .NET API
description: أطلق العنان لقوة نظم المعلومات الجغرافية باستخدام Aspose.GIS لـ .NET! تعرف على كيفية إضافة طبقات إلى مجموعات بيانات File GDB في هذا البرنامج التعليمي خطوة بخطوة. #بيانات جغرافية #Aspose #GIS
type: docs
weight: 16
url: /ar/net/layer-management/add-layer-to-file-gdb-dataset/
---
## مقدمة
هل أنت مستعد لتعزيز قدرات نظم المعلومات الجغرافية لديك باستخدام Aspose.GIS for .NET؟ في هذا الدليل المفصّل خطوة بخطوة، سنرشدك خلال عملية إضافة طبقة إلى مجموعة بيانات قاعدة البيانات الجغرافية للملفات (GDB). يوفر Aspose.GIS for .NET ميزات قوية لمعالجة المعلومات الجغرافية، ومن خلال هذا البرنامج التعليمي، ستتمكن من دمج طبقات إضافية في مجموعات البيانات الخاصة بك بسلاسة.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
-  Aspose.GIS for .NET Library: قم بتنزيل المكتبة وتثبيتها من ملف[Aspose.GIS لتوثيق .NET](https://reference.aspose.com/gis/net/).
- دليل المستندات: قم بإنشاء دليل مستندات مخصص على جهازك لتخزين وإدارة الملفات المتعلقة بـ GIS.
## استيراد مساحات الأسماء
في مشروع .NET الخاص بك، تأكد من استيراد مساحات الأسماء الضرورية للوصول إلى وظائف Aspose.GIS. استخدم مقتطف الكود التالي:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## الخطوة 1: نسخ الدليل
قبل المتابعة، قم بتكرار الدليل الذي يحتوي على مجموعة بيانات GDB الخاصة بك. تضمن هذه الخطوة بقاء مجموعة البيانات الأصلية سليمة. استخدم مقتطف الشفرة المقدم:
```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```
## الخطوة 2: افتح مجموعة البيانات وتحقق من إمكانية الإنشاء
 افتح مجموعة البيانات المكررة وتحقق مما إذا كان بإمكانها إنشاء طبقات. وهذا ما يؤكده حضور`True` في إخراج وحدة التحكم.
```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // حقيقي
```
## الخطوة 3: إنشاء وملء طبقة جديدة
قم بإنشاء طبقة جديدة داخل مجموعة البيانات، مع تحديد نظام الإسناد المكاني والسمات ونموذج المعالم. يوضح مقتطف الكود هذا العملية:
```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```
## الخطوة 4: افتح الطبقة المضافة والتحقق من صحتها
افتح الطبقة التي أنشأتها للتو وتحقق من محتواها. تحقق من العدد واسترجاع قيم السمات باستخدام الكود التالي:
```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "الاسم_1"
}
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إضافة طبقة إلى مجموعة بيانات File GDB باستخدام Aspose.GIS for .NET. باستخدام هذه المهارات المكتشفة حديثًا، يمكنك التعامل بكفاءة مع البيانات الجغرافية في مشاريع نظم المعلومات الجغرافية الخاصة بك.
## أسئلة مكررة
### س: هل يمكنني استخدام Aspose.GIS for .NET مع مكتبات GIS الأخرى؟
تم تصميم Aspose.GIS for .NET للعمل بشكل مستقل، ولكن يمكن دمجه مع مكتبات أخرى لتحسين الوظائف.
### س: هل الترخيص المؤقت متاح لأغراض الاختبار؟
 نعم يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/) للاختبار والتقييم.
### س: ما هي أنظمة الإسناد المكاني التي يدعمها Aspose.GIS for .NET؟
يدعم Aspose.GIS for .NET نطاقًا واسعًا من أنظمة الإسناد المكاني، مما يوفر المرونة في معالجة البيانات الجغرافية.
### س: هل يمكنني المساهمة في مجتمع Aspose.GIS؟
 قطعاً! انضم إلى المناقشات وشارك تجاربك في[منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33).
### س: أين يمكنني العثور على الوثائق التفصيلية لـ Aspose.GIS for .NET؟
 استكشاف الوثائق الشاملة[هنا](https://reference.aspose.com/gis/net/) للحصول على معلومات متعمقة حول Aspose.GIS for .NET.