---
date: 2026-01-10
description: تعلم كيفية تحويل GeoJSON إلى File GDB باستخدام Aspose.GIS لـ .NET. يغطي
  هذا الدليل خطوة بخطوة تحويل البيانات الجغرافية وتحويل Aspose GIS.
linktitle: Convert GeoJSON Layer to File GDB
second_title: Aspose.GIS .NET API
title: كيفية تحويل GeoJSON إلى File GDB باستخدام Aspose.GIS لـ .NET
url: /ar/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تحويل GeoJSON إلى File GDB باستخدام Aspose.GIS لـ .NET

## Introduction
إذا كنت تتساءل **how to convert GeoJSON** إلى قاعدة بيانات جغرافية ملفية (File GDB) لتدفقات عمل GIS قوية، فأنت في المكان الصحيح. في هذا الدرس سنرشدك خلال العملية بالكامل باستخدام Aspose.GIS لـ .NET، موضحين لماذا هذه المكتبة خيار ممتاز لتحويل البيانات الجغرافية وكيف يمكنك إنشاء قاعدة بيانات ملفية بسرعة من طبقة GeoJSON.

## Quick Answers
- **ما الذي يغطيه الدرس؟** تحويل طبقة GeoJSON إلى File GDB باستخدام Aspose.GIS لـ .NET.  
- **ما هي الكلمة المفتاحية الأساسية المستهدفة؟** *how to convert geojson*.  
- **هل أحتاج إلى ترخيص؟** الإصدار التجريبي المجاني يكفي للاختبار؛ يلزم ترخيص تجاري للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **كم من الوقت تستغرق العملية؟** حوالي 10‑15 دقيقة للتحويل الأساسي.

## What is GeoJSON and File GDB?
GeoJSON هو تنسيق نصي خفيف الوزن لتشفير مجموعة متنوعة من هياكل البيانات الجغرافية. File Geodatabase (File GDB) هو تنسيق قائم على المجلدات عالي الأداء يستخدمه العديد من تطبيقات GIS المكتبية. التحويل بينهما يتيح لك الاستفادة من مزايا كلا التنسيقين في مشاريعك.

## Why use Aspose.GIS for geospatial data conversion?
توفر Aspose.GIS واجهة برمجة تطبيقات موحدة تُبسط تعقيدات معالجة الصيغ. مع الدعم المدمج لـ **geojson to file gdb**، يمكنك:

- قراءة GeoJSON في C# دون الحاجة إلى محللات طرف ثالث.  
- إنشاء قاعدة بيانات ملفية برمجياً.  
- الحفاظ على بيانات السمات ومعلومات المرجع المكاني تلقائياً.  

## Prerequisites
قبل البدء، تأكد من وجود:

- معرفة عملية ببرمجة .NET.  
- Aspose.GIS لـ .NET مثبت. إذا لم يكن كذلك، قم بتنزيله من [here](https://releases.aspose.com/gis/net/) واتبع تعليمات التثبيت.

## Import Namespaces
الخطوة الأولى هي استيراد المساحات الاسمية المطلوبة.

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

## Step 1: Set up the GeoJSON Layer
إنشاء ملف GeoJSON مؤقت يحتوي على السمات والميزات التي تريد تحويلها. يضيف هذا المثال نقطتين بسيطتين.

```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Add attributes
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    // Construct and add features
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```

## Step 2: Copy Test Dataset
للحفاظ على بيانات الاختبار الأصلية دون تعديل، قم بنسخ مجموعة بيانات File GDB الحالية. يضمن ذلك بيئة نظيفة للتحويل.

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## Step 3: Convert GeoJSON to File GDB
افتح طبقة GeoJSON، أنشئ طبقة جديدة داخل File GDB المنسوخ، انسخ السمات، وانقل كل ميزة. هذا هو جوهر عملية **aspose gis conversion**.

```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copy attributes
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Add features
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```

## Common Issues and Solutions
- **غياب المرجع المكاني:** تأكد من أن GeoJSON المصدر يتضمن تعريف CRS أو قم بتعيين `SpatialReferenceSystem.Wgs84` صراحةً عند إنشاء طبقة File GDB.  
- **عدم تطابق نوع السمة:** يجب أن تتطابق أنواع بيانات السمات في GeoJSON مع مخطط الهدف؛ وإلا ستطلق Aspose.GIS استثناءً.  
- **أخطاء الوصول إلى الملف:** تحقق من أن المجلد الوجهة لديه صلاحيات كتابة وأنه لا توجد عملية أخرى تقفل ملفات GDB.

## Frequently Asked Questions
### هل Aspose.GIS متوافق مع أحدث إصدارات .NET framework؟
نعم، Aspose.GIS متوافق مع أحدث إصدارات .NET framework.

### هل يمكنني تحويل صيغ جغرافية أخرى باستخدام Aspose.GIS؟
بالطبع! تدعم Aspose.GIS مجموعة واسعة من الصيغ الجغرافية لتعامل مرن مع البيانات.

### هل هناك نسخة تجريبية متاحة لـ Aspose.GIS؟
نعم، يمكنك استكشاف وظائف Aspose.GIS بتحميل النسخة التجريبية [here](https://releases.aspose.com/).

### كيف يمكنني الحصول على دعم لاستفسارات متعلقة بـ Aspose.GIS؟
توجه إلى منتدى Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) للحصول على الدعم المتخصص.

### هل يمكنني الحصول على ترخيص مؤقت لـ Aspose.GIS؟
نعم، يمكنك الحصول على ترخيص مؤقت [here](https://purchase.aspose.com/temporary-license/).

---

**آخر تحديث:** 2026-01-10  
**تم الاختبار مع:** Aspose.GIS 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}