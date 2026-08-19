---
date: 2026-06-15
description: تعلم كيفية إنشاء Vector Layer وتعيين Layer Spatial Reference System باستخدام
  Aspose.GIS for .NET. إتقان تعريف spatial reference، إضافة point feature، واسترجاع
  EPSG code.
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: تعيين Layer Spatial Reference System
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: إنشاء Vector Layer وتعيين Layer Spatial Reference System
url: /ar/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء طبقة متجهة وتعيين نظام الإسناد المكاني للطبقة

## مقدمة
في المشهد الواسع لأنظمة المعلومات الجغرافية (GIS)، تبرز **Aspose.GIS for .NET** كمكتبة قوية وعالية الأداء تدعم **70+** من صيغ المتجهات والراستر ويمكنها معالجة ملفات أكبر من **10 GB** دون تحميل مجموعة البيانات بالكامل في الذاكرة. في هذا البرنامج التعليمي ستقوم **create vector layer**، وتحدد إسنادها المكاني، **add point feature**، وتسترجع رمز EPSG — كل ذلك بإرشادات واضحة خطوة بخطوة. سواءً كنت تبني خدمة رسم خرائط، أو خط أنابيب تحويل بيانات، أو محرك تحليلات مكانية، فإن إتقان هذه الأساسيات سيحافظ على دقة نظام إحداثيات ملف الشيبفيل الخاص بك ويجعل سير عمل GIS موثوقًا.

## إجابات سريعة
- **What does “create vector layer” mean?** إنه ينشئ طبقة GIS جديدة (مثل Shapefile) يمكنها تخزين الأشكال الهندسية مثل النقاط أو الخطوط أو المضلعات.  
- **Which EPSG code is used in the example?** رمز EPSG 26918 (NAD83 / UTM zone 18N).  
- **Can I add a point feature after creating the layer?** نعم—استخدم `ConstructFeature()` وعيّن هندسة `Point`.  
- **How do I retrieve the layer’s CRS?** اقرأ `layer.SpatialReferenceSystem.EpsgCode` أو `.Name`.  
- **Do I need a license for Aspose.GIS?** يتوفر إصدار تجريبي مجاني؛ يلزم الحصول على ترخيص للاستخدام في الإنتاج.

## ما هو create vector layer؟
عملية **create vector layer** تنشئ مجموعة بيانات متجهة جديدة (مثل Shapefile) يمكنها احتواء ميزات هندسية وبيانات صفات. في Aspose.GIS، يتم ذلك بإنشاء كائن `VectorLayer` مع برنامج تشغيل ونظام إسناد مكاني.

## لماذا يجب تعيين نظام إحداثيات الطبقة (CRS) بشكل صحيح؟
تعيين نظام الإسناد المكاني (CRS) الصحيح يضمن أن كل هندسة تقوم بتخزينها تتطابق مع مجموعات البيانات المكانية الأخرى. باستخدام Aspose.GIS يمكنك تعريف CRS باستخدام رمز EPSG قياسي، مما يضمن التوافق مع برامج GIS حول العالم. على سبيل المثال، EPSG 26918 يحدد NAD83 / UTM zone 18N، وهو إسقاط شائع للبيانات في شرق الولايات المتحدة.

## المتطلبات المسبقة
- خبرة في تطوير .NET (C# أو VB.NET).  
- Visual Studio 2022 أو أحدث.  
- مكتبة Aspose.GIS for .NET – قم بتنزيلها **[here](https://releases.aspose.com/gis/net/)**.  
- إلمام أساسي بأنظمة الإسناد المكاني (CRS/EPSG).

## استيراد مساحات الأسماء
مساحة الأسماء `Aspose.Gis` توفر الفئات الأساسية لـ GIS، بينما `Aspose.Gis.Geometries` توفر لك أنواع الهندسة مثل `Point`.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## كيف تنشئ طبقة متجهة في Aspose.GIS for .NET؟
تمثل `VectorLayer` مجموعة بيانات متجهة مثل Shapefile وتوفر طرقًا لإنشاء، قراءة، وتعديل الميزات.  
`SpatialReferenceSystem` يحدد نظام الإسناد المكاني باستخدام رمز EPSG.  

حمّل المجلد الهدف، عرّف `SpatialReferenceSystem` برمز EPSG، واستدعِ `VectorLayer.Create` مع برنامج تشغيل Shapefile. هذه العملية الواحدة تنشئ ملف `.shp` جديد، وتكتب الملفات المرافقة `.shx` و`.dbf`، وتدمج بيانات تعريف CRS، جاهزة لإدراج الميزات بكفاءة.

### الخطوة 1: تحديد دليل المستند
ابدأ بتحديد المسار إلى دليل المستندات الخاص بك. سيكون هذا هو الموقع الذي تُخزن فيه ملفات البيانات المكانية.

```csharp
string dataDir = "Your Document Directory";
```

### الخطوة 2: تعريف الإسناد المكاني وتعيين نظام إحداثيات Shapefile
`SpatialReferenceSystem` يمثل CRS للطبقة، ويُحدد بواسطة رمز EPSG.  

عرّف المسار إلى Shapefile، و**define spatial reference** باستخدام رمز EPSG (26918 في هذا المثال). هذه الخطوة **sets the shapefile coordinate system** للطبقة.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## كيف يمكنك إضافة ميزة نقطة إلى طبقة متجهة؟
`Point` هو نوع هندسة يمثل زوج إحداثيات X/Y واحد.  

أنشئ ميزة جديدة، عيّن هندسة `Point` بالإحداثيات X/Y المطلوبة، وأضف الميزة إلى `VectorLayer` المفتوحة. العملية تكتب الهندسة في ملف `.shp` وسجل الصفات في ملف `.dbf` في معاملة واحدة.

### الخطوة 3: إنشاء طبقة متجهة
`ConstructFeature` ينشئ كائن ميزة جديد يمكنه احتواء الهندسة وبيانات الصفات.  

الآن **create vector layer** باستخدام مسار Shapefile المحدد، نوع البرنامج المشغل (Shapefile)، ونظام الإسناد المكاني الذي عرّفته للتو.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### الخطوة 4: إضافة ميزة نقطة إلى الطبقة
أنشئ ميزة جديدة و**add point feature** عن طريق تعيين هندستها (ـ `Point` بالإحداثيات 60, 24). ثم أضف الميزة إلى الطبقة المتجهة.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### الخطوة 5: استرجاع معلومات نظام الإسناد المكاني (استرجاع رمز EPSG)
افتح طبقة المتجهات واسترجع معلومات حول نظام الإسناد المكاني، مثل رمز EPSG والاسم القابل للقراءة البشرية. هذا يوضح كيفية **retrieve EPSG code** و**set layer CRS**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|------|
| **Layer fails to open** | Wrong driver or corrupted file path | Verify `Drivers.Shapefile` and ensure `path` points to an existing `.shp` file. |
| **Incorrect CRS displayed** | Using the wrong EPSG code | Double‑check the EPSG code with an authoritative source (e.g., EPSG.io). |
| **Feature not saved** | Not calling `layer.Add(feature)` inside the `using` block | Ensure the `Add` method is executed before the layer is disposed. |

## الأسئلة المتكررة
**Q: How do I change the CRS of an existing Shapefile?**  
A: افتح الطبقة، أنشئ `SpatialReferenceSystem` جديدًا برمز EPSG المطلوب، عينه إلى `layer.SpatialReferenceSystem`، ثم احفظ الطبقة.

**Q: Can I add other geometry types (e.g., polygons) using the same approach?**  
A: نعم—استبدل `new Point(x, y)` بـ `new Polygon(...)` أو `new LineString(...)` حسب الحاجة.

**Q: Is it possible to work with large datasets efficiently?**  
A: استخدم واجهات برمجة التطبيقات المتدفقة (`VectorLayer.Create` مع `FeatureCollection`) وتخلص من الطبقات بسرعة لتحرير الموارد.

**Q: Does Aspose.GIS support coordinate transformation?**  
A: نعم—استخدم `Geometry.Transform(targetSrs)` لإعادة إسقاط الهندسات بين أنظمة إسناد مختلفة.

**Q: What .NET versions are supported?**  
A: يعمل Aspose.GIS مع .NET Framework 4.6+، .NET Core 3.1+، .NET 5/6/7.

**---**

**آخر تحديث:** 2026-06-15  
**تم الاختبار مع:** Aspose.GIS 24.11 for .NET  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [إنشاء طبقة متجهة وتعيين تسامح التخطية باستخدام Aspose.GIS for .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [إنشاء طبقة متجهة في File GDB – درس Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [الإسناد المكاني wgs84 – إضافة طبقة إلى GDB باستخدام Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}