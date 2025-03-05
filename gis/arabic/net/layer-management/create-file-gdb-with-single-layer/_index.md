---
title: قم بإنشاء ملف GDB بطبقة واحدة
linktitle: قم بإنشاء ملف GDB بطبقة واحدة
second_title: Aspose.GIS .NET API
description: أطلق العنان لإمكانات إدارة البيانات الجغرافية المكانية في .NET باستخدام Aspose.GIS. تعرف على كيفية إنشاء قواعد بيانات جغرافية ملفية وطبقات خطوة بخطوة. التحميل الان!
type: docs
weight: 11
url: /ar/net/layer-management/create-file-gdb-with-single-layer/
---
## مقدمة
هل أنت مستعد للارتقاء بتطبيقاتك الجغرافية المكانية باستخدام قواعد بيانات جغرافية وطبقات ملفات قوية؟ لا تنظر إلى أبعد من Aspose.GIS لـ .NET. في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء قاعدة بيانات جغرافية ملفية (GDB) بطبقة واحدة باستخدام Aspose.GIS for .NET. استفد من قوة إدارة البيانات المكانية وتصورها في تطبيقات .NET الخاصة بك دون عناء.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
1.  Aspose.GIS for .NET: تأكد من تثبيت مكتبة Aspose.GIS. يمكنك تنزيله من[صفحة تنزيل Aspose.GIS for .NET](https://releases.aspose.com/gis/net/).
2. بيئة التطوير: قم بإعداد بيئة تطوير .NET عاملة على جهازك.
3. دليل المستندات: اختر أو قم بإنشاء دليل على نظامك حيث ستقوم بتخزين ملفات البيانات الجغرافية المكانية الخاصة بك.
## استيراد مساحات الأسماء
للبدء، تحتاج إلى استيراد مساحات الأسماء الضرورية في مشروع .NET الخاص بك. ستوفر مساحات الأسماء هذه إمكانية الوصول إلى وظائف Aspose.GIS. أضف الأسطر التالية في بداية ملف التعليمات البرمجية الخاص بك:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## الخطوة 1: قم بإعداد دليل المستندات الخاص بك
```csharp
string dataDir = "Your Document Directory";
```
استبدل "دليل المستندات الخاص بك" بالمسار إلى الدليل الذي تريد تخزين ملفات البيانات الجغرافية المكانية فيه.
## الخطوة 2: إنشاء قاعدة بيانات جغرافية ملفية بطبقة واحدة
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
يقوم مقتطف التعليمات البرمجية هذا بإنشاء قاعدة بيانات جغرافية ملفية بطبقة واحدة ويضيف معلم خط إليها.
## الخطوة 3: افتح قاعدة البيانات الجغرافية للملفات واسترجع معلومات الطبقة
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // الإخراج: عدد الميزات: 1
}
```
في هذه الخطوة، نفتح قاعدة البيانات الجغرافية الملفية التي تم إنشاؤها، ونسترد الطبقة المسماة "الطبقة"، ونطبع عدد المعالم في الطبقة.
## خاتمة
تهانينا! لقد نجحت في إنشاء قاعدة بيانات جغرافية ملفية بطبقة واحدة باستخدام Aspose.GIS for .NET. اكتشف الإمكانات الهائلة لإدارة البيانات المكانية في تطبيقاتك بسهولة.
## أسئلة مكررة
### هل يمكنني استخدام Aspose.GIS for .NET في مشاريع .NET الحالية؟
نعم، يمكن دمج Aspose.GIS for .NET بسلاسة في مشاريع .NET الحالية لديك.
### هل هناك إصدار تجريبي متاح لـ Aspose.GIS for .NET؟
 نعم، يمكنك استكشاف ميزات Aspose.GIS for .NET عن طريق تنزيل ملف[نسخة تجريبية مجانية](https://releases.aspose.com/).
### أين يمكنني العثور على الوثائق التفصيلية لـ Aspose.GIS for .NET؟
 الرجوع إلى[توثيق](https://reference.aspose.com/gis/net/) للحصول على معلومات شاملة حول Aspose.GIS for .NET.
### كيف يمكنني الحصول على دعم Aspose.GIS لـ .NET؟
 قم بزيارة[منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33) لدعم المجتمع ومساعدته.
### هل التراخيص المؤقتة متاحة لـ Aspose.GIS لـ .NET؟
 نعم يمكنك الحصول على[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) لـ Aspose.GIS لـ .NET.