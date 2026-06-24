---
date: 2026-05-31
description: تعلم كيفية تحديد حد الدقة عند كتابة الأشكال الهندسية باستخدام Aspose.GIS
  لـ .NET، مما يقلل حجم GeoJSON ويحافظ على التحكم في الإحداثيات.
keywords:
- how to limit precision
- reduce geojson size
- Aspose.GIS precision control
linktitle: تحديد حد الدقة عند كتابة الأشكال الهندسية
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  headline: How to Limit Precision Writing Geometries with Aspose.GIS
  type: TechArticle
- description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  name: How to Limit Precision Writing Geometries with Aspose.GIS
  steps:
  - name: Define Precision Options
    text: The `GeoJsonOptions` class lets you specify how many fractional digits to
      keep for X/Y and Z coordinates. `PrecisionModel` defines how coordinate values
      are rounded or kept exact during writing.
  - name: Set Output Path
    text: Specify where the resulting GeoJSON file will be saved. `VectorLayer` is
      Aspose.GIS's container for a collection of features that share the same schema;
      it writes to the path you provide using the options set earlier.
  - name: Create and Populate Geometry
    text: Open a new `VectorLayer` with the options defined above, construct a `Point`
      geometry, and add it to the layer. `Point` represents a single coordinate (X,
      Y, optional Z) in a spatial reference system. It is the simplest geometry type
      and is used here to demonstrate precision rounding.
  - name: Read and Verify Precision
    text: Open the file you just created and print the coordinates. You should see
      the X/Y values rounded to three decimal places while the Z value remains exact.
      When you read the file back, Aspose.GIS parses the rounded values directly,
      so the in‑memory `Point` reflects the precision you defined during writ
  type: HowTo
- questions:
  - answer: Yes, it supports **50+** formats—including Shapefile, GeoJSON, KML, GML,
      and CSV—allowing seamless conversion between them.
    question: Is Aspose.GIS for .NET compatible with other GIS formats?
  - answer: Absolutely. A free trial is available from the download page, giving you
      full access to all features for evaluation.
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: Temporary evaluation licenses can be generated via the Aspose license
      portal; they are valid for 30 days.
    question: How do I obtain a temporary license for testing?
  - answer: The Aspose.GIS forum and Stack Overflow tag `aspose-gis` are great places
      to ask questions and find community solutions.
    question: Where can I get help if I run into issues?
  - answer: Yes, Aspose.GIS is designed to handle everything from quick prototypes
      to high‑throughput server workloads, processing multi‑gigabyte datasets with
      low memory overhead.
    question: Does the library work for both small scripts and enterprise‑scale applications?
  type: FAQPage
second_title: Aspise.GIS .NET API
title: كيفية تحديد حد الدقة عند كتابة الأشكال الهندسية باستخدام Aspose.GIS
url: /ar/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تحديد دقة كتابة الأشكال الهندسية باستخدام Aspose.GIS

إذا كنت تتساءل **عن كيفية تحديد الدقة** عند كتابة الأشكال الهندسية في تطبيق GIS باستخدام .NET، فإن Aspose.GIS لـ .NET يوفر طريقة بسيطة وعالية الأداء للتحكم في تقريب الإحداثيات. في هذا البرنامج التعليمي سنستعرض العملية بالكامل — من إعداد البيئة إلى التحقق من أن الناتج يلتزم بقواعد الدقة التي تحددها.

## إجابات سريعة
- **ماذا يعني “تحديد الدقة”?** يقوم بتقريب قيم الإحداثيات إلى عدد محدد من الأرقام العشرية أثناء كتابة ملف مكاني.  
- **ما هو التنسيق المستخدم في المثال؟** GeoJSON، لكن نفس الخيارات تنطبق على الصيغ المدعومة الأخرى.  
- **هل أحتاج إلى ترخيص لتجربة هذا؟** النسخة التجريبية المجانية تعمل للتطوير والاختبار؛ الترخيص التجاري مطلوب للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.  
- **هل يمكنني التحكم في دقة إحداثيات Z بشكل منفصل؟** نعم — استخدم `ZPrecisionModel` لتحديد القيم الدقيقة أو المقربة.

## كيفية تحديد الدقة عند كتابة الأشكال الهندسية

حمّل كاتب GeoJSON الخاص بك باستخدام كائن `GeoJsonOptions` الذي يحدد الدقة المطلوبة لإحداثيات X/Y و Z، ثم اكتب الشكل الهندسي واقرأه مرة أخرى — هذه العملية بالكامل تتناسب مع أقل من عشر أسطر من الشيفرة وتضمن تقريب جميع الإحداثيات بالضبط كما حددتها.

تحديد الدقة أمر أساسي عندما تحتاج إلى تمثيل إحداثيات متسق عبر أدوات GIS المختلفة، أو تقليل حجم الملف، أو الالتزام بمعايير تبادل البيانات. أدناه سنعرّف خيارات الدقة، نكتب شكلاً هندسياً، ثم نقرأه مرة أخرى لتأكيد عملية التقريب.

## ما هو تحديد الدقة؟

تحديد الدقة هو عملية تقريب الجزء العشري من قيم الإحداثيات إلى عدد ثابت من الأرقام قبل حفظ الشكل الهندسي في ملف. يضمن ذلك أن كل من يستخدم الملف يرى نفس القيم الرقمية، مما يساعد على تجنب الاختلافات الطفيفة التي قد تتسبب في أخطاء الطوبولوجيا.

## لماذا تستخدم Aspose.GIS للتحكم في الدقة؟

يدعم Aspose.GIS **أكثر من 50** تنسيقًا للإدخال والإخراج — بما في ذلك GeoJSON و Shapefile و KML و GML — ويمكنه معالجة ملفات تحتوي على **مئات الآلاف من المعالم** دون تحميل مجموعة البيانات بالكامل إلى الذاكرة. نماذج الدقة المدمجة تسمح لك بتقريب الإحداثيات في استدعاء واحد، مما يلغي الحاجة إلى سكريبتات المعالجة اللاحقة اليدوية.

## المتطلبات المسبقة

### 1. التحميل والتثبيت
احصل على أحدث حزمة Aspose.GIS لـ .NET من الموقع الرسمي: [download link](https://releases.aspose.com/gis/net/). اتبع دليل التثبيت لإضافة حزمة NuGet إلى مشروعك.

### 2. استيراد مساحة الأسماء
أضف مساحات الأسماء المطلوبة حتى تتمكن من الوصول إلى فئات GIS وأدوات المساعدة.

## دليل خطوة بخطوة

### الخطوة 1: تعريف خيارات الدقة
تتيح لك فئة `GeoJsonOptions` تحديد عدد الأرقام العشرية التي تريد الاحتفاظ بها لإحداثيات X/Y و Z.  
`PrecisionModel` يحدد كيفية تقريب قيم الإحداثيات أو الاحتفاظ بها دقيقة أثناء الكتابة.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### الخطوة 2: تحديد مسار الإخراج
حدد المكان الذي سيتم حفظ ملف GeoJSON الناتج فيه.  
`VectorLayer` هو حاوية Aspose.GIS لمجموعة من المعالم التي تشترك في نفس المخطط؛ يكتب إلى المسار الذي تحدده باستخدام الخيارات التي تم تعيينها مسبقًا.  

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### الخطوة 3: إنشاء وتعبئة الشكل الهندسي
افتح `VectorLayer` جديدًا باستخدام الخيارات المحددة أعلاه، أنشئ شكلًا هندسيًا من نوع `Point`، وأضفه إلى الطبقة.  
`Point` يمثل إحداثية واحدة (X, Y، Z اختياري) في نظام إحداثي مكاني. وهو أبسط نوع من الأشكال الهندسية ويُستخدم هنا لتوضيح تقريب الدقة.  

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### الخطوة 4: قراءة والتحقق من الدقة
افتح الملف الذي أنشأته للتو واطبع الإحداثيات. يجب أن ترى قيم X/Y مقربة إلى ثلاث منازل عشرية بينما يظل قيمة Z دقيقة.  
عند قراءة الملف مرة أخرى، يقوم Aspose.GIS بتحليل القيم المقربة مباشرة، لذا فإن كائن `Point` في الذاكرة يعكس الدقة التي حددتها أثناء الكتابة.  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

## المشكلات الشائعة والنصائح

- **أخطاء المسار:** تأكد من وجود الدليل في `path` أو استخدم `Path.Combine` مع `Environment.CurrentDirectory` لإنشاء مسار ملف آمن.  
- **عدم تطبيق الدقة:** تأكد من تمرير كائن `GeoJsonOptions` عند إنشاء الطبقة؛ وإلا سيتم استخدام الدقة الافتراضية (قيمة مزدوجة كاملة).  
- **مجموعات البيانات الكبيرة:** للعمليات الضخمة، فكر في إعادة استخدام نسخة واحدة من `VectorLayer` وإضافة المعالم دفعةً لتحسين الأداء.

## الأسئلة المتكررة

**س: هل Aspose.GIS لـ .NET متوافق مع صيغ GIS أخرى؟**  
ج: نعم، يدعم **أكثر من 50** صيغة — بما في ذلك Shapefile و GeoJSON و KML و GML و CSV — مما يتيح تحويلًا سلسًا بينها.

**س: هل يمكنني تجربة Aspose.GIS لـ .NET قبل الشراء؟**  
ج: بالتأكيد. نسخة تجريبية مجانية متاحة من صفحة التحميل، تمنحك وصولًا كاملاً إلى جميع الميزات للتقييم.

**س: كيف يمكنني الحصول على ترخيص مؤقت للاختبار؟**  
ج: يمكن إنشاء تراخيص تقييم مؤقتة عبر بوابة تراخيص Aspose؛ وهي صالحة لمدة 30 يومًا.

**س: أين يمكنني الحصول على المساعدة إذا واجهت مشاكل؟**  
ج: منتدى Aspose.GIS وعلامة Stack Overflow `aspose-gis` هي أماكن ممتازة لطرح الأسئلة والعثور على حلول من المجتمع.

**س: هل تعمل المكتبة لكل من السكريبتات الصغيرة وتطبيقات المستوى المؤسسي؟**  
ج: نعم، تم تصميم Aspose.GIS للتعامل مع كل شيء من النماذج الأولية السريعة إلى أحمال الخوادم عالية الإنتاجية، حيث يعالج مجموعات بيانات متعددة الجيجابايت بذاكرة منخفضة.

---

**آخر تحديث:** 2026-05-31  
**تم الاختبار مع:** Aspose.GIS 24.11 لـ .NET  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء طبقة متجهة، تحديد الدقة باستخدام Aspose.GIS لـ .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [كيفية تحويل GeoJSON – Aspose.GIS لـ .NET](/gis/net/geo-data-conversion/)
- [كيفية فحص الشكل الهندسي باستخدام Aspose.GIS لـ .NET](/gis/net/geometry-analysis/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

{{< /blocks/products/pf/main-wrap-class >}}