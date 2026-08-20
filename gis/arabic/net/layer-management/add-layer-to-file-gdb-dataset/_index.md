---
date: 2026-06-30
description: تعلم كيفية إضافة طبقة إلى مجموعة بيانات File GDB باستخدام Aspose.GIS
  مع المرجع المكاني WGS84. اتبع هذا الدليل خطوة بخطوة لإضافة طبقة في .NET.
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: إضافة طبقة إلى مجموعة بيانات File GDB
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: كيفية إضافة طبقة إلى مجموعة بيانات File GDB مع المرجع المكاني WGS84 باستخدام
  Aspose.GIS
url: /ar/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة طبقة – المرجع المكاني wgs84 باستخدام Aspose.GIS

## مقدمة
هل أنت مستعد لتعزيز سير عمل GIS الخاص بك باستخدام Aspose.GIS لـ .NET؟ في هذا الدرس ستتعلم **كيفية إضافة طبقة** إلى مجموعة بيانات File GDB أثناء العمل مع نظام إحداثيات **المرجع المكاني WGS84**. سنستعرض كل خطوة، من إعداد مجلد البيانات الخاص بك إلى التحقق من صحة الطبقة التي تم إنشاؤها حديثًا، حتى تتمكن من البدء في معالجة البيانات الجغرافية بثقة وكفاءة.

## إجابات سريعة
- **ما هو نظام الإحداثيات الأساسي المستخدم؟** spatial reference wgs84 (WGS 84)  
- **أي مكتبة توفر الـ API؟** Aspose.GIS for .NET  
- **هل أحتاج إلى ترخيص للاختبار؟** Yes – a temporary Aspose license is available.  
- **هل يمكنني إضافة سمات إلى الطبقة الجديدة؟** Absolutely, you can define any number of feature attributes.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## ما هو المرجع المكاني wgs84؟
المرجع المكاني wgs84 (World Geodetic System 1984) هو نظام الإحداثيات الجغرافية الأكثر استخدامًا. يحدد خطوط العرض والطول بالدرجات ويعمل كنظام إحداثيات افتراضي للعديد من مجموعات بيانات GIS، بما في ذلك تلك التي سننشئها في هذا الدليل.

## لماذا تستخدم Aspose.GIS لإضافة طبقة؟
حمّل بيانات GIS الخاصة بك دون الحاجة إلى ملفات ثنائية من طرف ثالث واحتفظ بالتحكم الكامل في تعريف المخطط. Aspose.GIS يدعم **40+ spatial reference systems**، ويمكنه معالجة ملفات أكبر من **2 GB** دون تحميل مجموعة البيانات بالكامل في الذاكرة، ويعمل على Windows وLinux وmacOS. هذا يجعله حلاً موثوقًا ومتعدد المنصات لأتمتة GIS على مستوى المؤسسات.

## المتطلبات المسبقة
- مكتبة Aspose.GIS لـ .NET: قم بتنزيل وتثبيت المكتبة من [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- دليل المستندات: أنشئ مجلدًا مخصصًا على جهازك لتخزين ملفات GIS.  
- ترخيص Aspose مؤقت (اختياري للتقييم) – راجع الأسئلة الشائعة أدناه للحصول على رابط التحميل.

## استيراد مساحات الأسماء
أضف عبارات `using` المطلوبة إلى مشروع C# الخاص بك حتى تتمكن من الوصول إلى فئات Aspose.GIS:

*لا يلزم كتلة شفرة هنا؛ ما عليك سوى إضافة الأسطر التالية في أعلى ملفك:*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## الخطوة 1: نسخ الدليل
**Definition anchor:** مجموعة بيانات File GDB هي قاعدة بيانات جغرافية ESRI تعتمد على المجلد وتخزن البيانات المكانية في مجموعة من الملفات.  
أولاً، قم بنسخ المجلد الذي يحتوي على مجموعة بيانات GDB الأصلية. الحفاظ على نسخة يحمي البيانات الأصلية أثناء التجربة.

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

## الخطوة 2: فتح مجموعة البيانات والتحقق من إمكانية الإنشاء
`Dataset` تمثل مجموعة من طبقات GIS المخزنة في File GDB. افتح مجموعة البيانات المنسوخة حديثًا وتأكد من أنها يمكنها إنشاء طبقات جديدة. يجب أن تُعيد الخاصية `CanCreateLayers` القيمة **True**. **`CanCreateLayers` هي خاصية منطقية تشير إلى ما إذا كانت مجموعة البيانات تدعم إنشاء طبقات جديدة.**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## الخطوة 3: إنشاء وتعبئة طبقة جديدة مع المرجع المكاني wgs84
الآن نقوم بإنشاء طبقة باسم **data** ونحدد مرجعها المكاني صراحة إلى **Wgs84**. نضيف أيضًا سمة بسيطة تسمى **Name** ونُدرج ميزة نقطة واحدة. **`CreateLayer` ينشئ طبقة جديدة في مجموعة البيانات بالاسم والمرجع المكاني المحددين.** **`SpatialReference` يمثل نظام الإحداثيات المستخدم بواسطة الطبقة.** **`Feature` هو كائن جغرافي فردي (نقطة أو خط أو مضلع) مخزن في طبقة.**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## الخطوة 4: فتح والتحقق من صحة الطبقة المضافة
أخيرًا، افتح الطبقة التي أنشأتها للتو وتحقق من محتوياتها. سيظهر في وحدة التحكم أن الطبقة تحتوي على ميزة واحدة وأن السمة **Name** تتطابق مع ما حددناه. **`Layer.Open` يفتح طبقة موجودة للقراءة أو التعديل.** هذا يؤكد أن الطبقة تمت إضافتها بشكل صحيح وأن المرجع المكاني هو WGS84.

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

## كيفية إضافة طبقة إلى مجموعة بيانات File GDB؟
حمّل مجموعة البيانات، استدعِ `CreateLayer` بالاسم والمرجع المكاني المطلوبين، عرّف مخطط السمات، ثم أدخل الميزات. يمكن تنفيذ كل ذلك من خلال عدد قليل من استدعاءات طرق Aspose.GIS، ويتولى الـ API التعامل مع قفل الملفات والتحقق من صحة المخطط تلقائيًا. تضمن العملية أن الطبقة الجديدة تتوافق مع المرجع المكاني لمجموعة البيانات، وأن تعريفات السمات مخزنة في مخطط الطبقة، وأن البيانات يمكن الوصول إليها بواسطة أي برنامج GIS يدعم File GDB.

## المشكلات الشائعة والنصائح
- **مسار غير صحيح:** تأكد من أن `dataDir` ينتهي بفاصل مسار (`/` أو `\`) بحيث تُكوّن السلاسل المتصلة مسارات ملفات صالحة.  
- **أخطاء الترخيص:** إذا رأيت تحذيرات الترخيص، قم بتطبيق ترخيص مؤقت من بوابة Aspose قبل تشغيل الشفرة.  
- **عدم تطابق CRS:** عند فتح الطبقة لاحقًا في أداة GIS أخرى، تأكد من أن الأداة تتعرف على WGS 84 (EPSG:4326) كنظام إحداثيات.  
- **مجموعات بيانات كبيرة:** للمجموعات التي تتجاوز 1 GB، فكر في استخدام `Dataset.OpenReadOnly` لتقليل استهلاك الذاكرة.

## الأسئلة المتكررة
### س: هل يمكنني استخدام Aspose.GIS لـ .NET مع مكتبات GIS أخرى؟
نعم، يعمل Aspose.GIS بشكل مستقل لكنه يمكن دمجه مع مكتبات مثل GDAL أو NetTopologySuite للمعالجة المتقدمة.

### س: هل يتوفر ترخيص مؤقت لأغراض الاختبار؟
نعم، يمكنك الحصول على ترخيص مؤقت من [here](https://purchase.aspose.com/temporary-license/) للاختبار والتقييم.

### س: ما أنظمة المرجع المكاني التي يدعمها Aspose.GIS لـ .NET؟
يدعم Aspose.GIS أكثر من **40 رمز EPSG**، بما في ذلك الأنظمة الشائعة مثل WGS84 (EPSG:4326)، Web Mercator (EPSG:3857)، وNAD83 (EPSG:4269). استكشف الوثائق الشاملة [here](https://reference.aspose.com/gis/net/).

### س: هل يمكنني المساهمة في مجتمع Aspose.GIS؟
بالطبع! انضم إلى المناقشات وشارك تجاربك على [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### س: أين يمكنني العثور على وثائق مفصلة لـ Aspose.GIS لـ .NET؟
استكشف الوثائق الشاملة [here](https://reference.aspose.com/gis/net/) للحصول على معلومات متعمقة حول جميع الفئات والطرق وأفضل الممارسات.

---

**آخر تحديث:** 2026-06-30  
**تم الاختبار مع:** Aspose.GIS for .NET (latest stable version)  
**المؤلف:** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## دروس ذات صلة

- [إنشاء مجموعة بيانات File Geodatabase .NET باستخدام Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [إنشاء طبقة متجهة في File GDB – درس Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [إنشاء مجموعة بيانات File GDB وتعيين حدود للطبقة](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}