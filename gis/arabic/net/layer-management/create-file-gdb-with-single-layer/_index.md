---
date: 2026-06-30
description: تعلم كيفية إنشاء طبقة متجهة في File Geodatabase باستخدام Aspose.GIS لـ
  .NET. إدارة البيانات الجغرافية باستخدام المرجع المكاني WGS84 وخيارات file gdb.
keywords:
- create vector layer
- add line feature
- manage geospatial data
- feature count example
- file gdb compression
linktitle: إنشاء File GDB بطبقة واحدة
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  headline: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  type: TechArticle
- description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  name: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  steps:
  - name: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
    text: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
  - name: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
    text: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
  type: HowTo
- questions:
  - answer: It means adding a new vector dataset (points, lines, or polygons) to a
      geodatabase file.
    question: What does “create vector layer” mean?
  - answer: Aspose.GIS for .NET provides full support for File GDB creation and editing.
    question: Which library should I use?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `SpatialReferenceSystem.Wgs84` for the common WGS84 datum.
    question: Can I set the spatial reference?
  - answer: Less than 30 lines to create the GDB, add a line feature, and read back
      the feature count.
    question: How many lines of code?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: إنشاء طبقة متجهة في File GDB – Aspose.GIS .NET Tutorial
url: /ar/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء طبقة متجهة في ملف GDB

## مقدمة
إذا كنت بحاجة إلى **إنشاء طبقة متجهة** داخل قاعدة بيانات جغرافية ملفية (GDB) وإدارة البيانات الجغرافية بكفاءة، فإن Aspose.GIS for .NET يوفّر لك نهجًا نظيفًا يعتمد على الكود أولاً. في هذا الدليل خطوة بخطوة سنوضح لك كيفية كتابة ميزة خطية، وتكوين خيارات ملف GDB، والعمل مع المرجع المكاني WGS84 — كل ذلك في بضع أسطر من C#. في النهاية ستكون قادرًا على عدّ الميزات في طبقة ودمج ملف GDB الناتج في أي سير عمل للخرائط أو التحليل باستخدام .NET.

## إجابات سريعة
- **ماذا يعني “إنشاء طبقة متجهة”?** يعني إضافة مجموعة بيانات متجهة جديدة (نقاط، خطوط، أو مضلعات) إلى ملف قاعدة بيانات جغرافية.  
- **أي مكتبة يجب أن أستخدم؟** Aspose.GIS for .NET يوفر دعمًا كاملاً لإنشاء وتحرير File GDB.  
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تعمل للاختبار؛ يلزم ترخيص تجاري للإنتاج.  
- **هل يمكنني تعيين المرجع المكاني؟** نعم – استخدم `SpatialReferenceSystem.Wgs84` للمرجع الشائع WGS84.  
- **كم عدد أسطر الكود؟** أقل من 30 سطرًا لإنشاء الـ GDB، إضافة ميزة خطية، وقراءة عدد الميزات مرة أخرى.

## ما هي عملية “إنشاء طبقة متجهة”؟
إنشاء طبقة متجهة يعرّف جدولًا جديدًا في قاعدة البيانات الجغرافية يخزن الكائنات الهندسية (نقاط، خطوط، مضلعات) وسماتها. كل صف يمثل ميزة، وعمود الهندسة يحتوي على شكلها. في Aspose.GIS تقوم بإنشائه عن طريق إنشاء كائن `FeatureClass` داخل `FileGdbDataSource` وتحديد نوع الهندسة.

## لماذا استخدام Aspose.GIS لإنشاء طبقة متجهة؟
Aspose.GIS يزيل الاعتماديات الخارجية ويدعم **أكثر من 50** صيغة GIS، مما يجعله حلاً شاملاً لمطوري .NET.  
يوفر ضغطًا مدمجًا لملفات GDB (حتى تقليل بنسبة 70 % للبيانات المتجهة النموذجية)، وفهرسة مكانية، ومعالجة كاملة لـ WGS84 مباشرةً. تعمل المكتبة على .NET Framework 4.6+، .NET Core 2.0+، و .NET 5/6، لذا يمكنك استهداف أي بيئة حديثة على Windows أو عبر المنصات دون الحاجة إلى مكتبات أصلية إضافية.

## المتطلبات المسبقة
قبل البدء، تأكد من وجود:

1. **Aspose.GIS for .NET** – حمّله من [صفحة تحميل Aspose.GIS for .NET](https://releases.aspose.com/gis/net/).  
2. **بيئة تطوير .NET** – Visual Studio، Rider، أو سطر أوامر `dotnet`.  
3. **مجلد** حيث سيتم إنشاء File GDB (سنسميه *Your Document Directory*).

## استيراد مساحات الأسماء
عبارات `using` تجلب الأنواع المطلوبة إلى النطاق.  

مساحة الاسم `Document` توفر كائنات GIS الأساسية، بينما `System.IO` تتعامل مع مسارات الملفات.

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

## الخطوة 1: إعداد دليل المستند الخاص بك
استبدل `"Your Document Directory"` بالمسار المطلق حيث تريد أن يعيش File GDB.  
إنشاء الدليل مسبقًا يجنبك خطأ “File not found” الذي يواجهه كثير من المستخدمين الجدد.

```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 2: إنشاء قاعدة بيانات جغرافية ملفية بطبقة واحدة
`FileGdbOptions` هي فئة تتيح لك تكوين الضغط، الفهرسة المكانية، وإعدادات أخرى لقاعدة البيانات الجغرافية الملفية.  
هذا المقتطف **ينشئ طبقة متجهة** باستخدام `FileGdbOptions`، يكتب ميزة خطية بسيطة، ويخزنها في File GDB يستخدم **المرجع المكاني WGS84**.

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

## الخطوة 3: فتح قاعدة البيانات الجغرافية الملفية واسترجاع معلومات الطبقة
`FileGdbDataSource` هو نقطة الدخول لإنشاء وفتح قواعد البيانات الجغرافية الملفية.  
`FeatureClass` يمثل طبقة متجهة داخل قاعدة البيانات ويوفر الوصول إلى ميزاتها.  
هنا **نعدّ الميزات في الطبقة** بفتح مجموعة البيانات وطباعة عدد الميزات – في هذه الحالة، `1`.

```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```

## كيف تتحقق من أن الطبقة تم إنشاؤها بشكل صحيح؟
افتح قاعدة البيانات باستخدام `FileGdbDataSource.Open` واستعلم عن `FeatureClass`. الخاصية `Count` تُعيد العدد الكلي للميزات، مما يؤكد أن الخط تم حفظه. تساعدك هذه الخطوة السريعة على اكتشاف المشكلات مبكرًا، خاصةً عند أتمتة عمليات الاستيراد الضخمة.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **`File not found`** | متغيّر `path` غير صحيح | تحقق من أن `dataDir` يشير إلى مجلد موجود وأن `path` يجمعه مع اسم ملف، مثال `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | استخدام نوع هندسة غير مسموح به في File GDB | التزم بـ `Point` أو `LineString` أو `Polygon` للطبقات الأساسية. |
| **`License not set`** | تشغيل بدون ترخيص صالح في بيئة الإنتاج | سجّل ترخيصك باستخدام `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.GIS for .NET في مشاريعي .NET الحالية؟
نعم، يمكن دمج Aspose.GIS for .NET بسلاسة في مشاريع .NET الحالية الخاصة بك.

### هل تتوفر نسخة تجريبية من Aspose.GIS for .NET؟
نعم، يمكنك استكشاف ميزات Aspose.GIS for .NET بتحميل [نسخة التجربة المجانية](https://releases.aspose.com/).

### أين يمكنني العثور على وثائق مفصلة لـ Aspose.GIS for .NET؟
راجع [الوثائق](https://reference.aspose.com/gis/net/) للحصول على معلومات شاملة حول Aspose.GIS for .NET.

### كيف يمكنني الحصول على الدعم لـ Aspose.GIS for .NET؟
قم بزيارة [منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33) للحصول على دعم المجتمع والمساعدة.

### هل تتوفر تراخيص مؤقتة لـ Aspose.GIS for .NET؟
نعم، يمكنك الحصول على [ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) لـ Aspose.GIS for .NET.

---

**آخر تحديث:** 2026-06-30  
**تم الاختبار مع:** Aspose.GIS 24.11 for .NET  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء مجموعة بيانات ملف قاعدة بيانات جغرافية .NET باستخدام Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [إنشاء طبقة متجهة وتعيين نظام الإحداثيات المكاني للطبقة](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [كيفية حذف طبقة من مجموعة بيانات ملف GDB باستخدام Aspose.GIS](/gis/net/layer-data-operations/remove-layers-from-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}