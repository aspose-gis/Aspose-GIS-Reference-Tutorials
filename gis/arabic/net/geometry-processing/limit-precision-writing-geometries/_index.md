---
date: 2025-12-20
description: تعلم كيفية تحديد الدقة عند كتابة الأشكال الهندسية باستخدام Aspose.GIS
  لـ .NET. يساعدك هذا الدليل خطوة بخطوة على إدارة البيانات المكانية مع التحكم الدقيق
  في الإحداثيات.
linktitle: Limit Precision Writing Geometries
second_title: Aspose.GIS .NET API
title: كيفية تحديد الدقة عند كتابة الأشكال الهندسية باستخدام Aspose.GIS
url: /ar/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تحديد الدقة عند كتابة الأشكال الهندسية باستخدام Aspose.GIS

إذا كنت تتساءل **كيف تحدد الدقة** عند كتابة الأشكال الهندسية في تطبيق GIS على .NET، فإن Aspose.GIS for .NET يوفر طريقة مباشرة وعالية الأداء للتحكم في تقريب الإحداثيات. في هذا الدرس سنستعرض العملية بالكامل—من إعداد البيئة إلى التحقق من أن الناتج يلتزم بقواعد الدقة التي تحددها.

## إجابات سريعة
- **ماذا يعني “تحديد الدقة”?** يقوم بتقريب قيم الإحداثيات إلى عدد محدد من الأرقام العشرية أثناء كتابة ملف مكاني.  
- **ما هو التنسيق المستخدم في المثال؟** GeoJSON، لكن نفس الخيارات تنطبق على الصيغ المدعومة الأخرى.  
- **هل أحتاج إلى ترخيص لتجربة ذلك؟** الإصدار التجريبي المجاني يكفي للتطوير والاختبار؛ يلزم ترخيص تجاري للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **هل يمكن التحكم في دقة إحداثيات Z بشكل منفصل؟** نعم—استخدم `ZPrecisionModel` لتعيين قيم دقيقة أو مقربة.

## كيفية تحديد الدقة عند كتابة الأشكال الهندسية
تحديد الدقة أمر أساسي عندما تحتاج إلى تمثيل إحداثيات متسق عبر أدوات GIS مختلفة، أو لتقليل حجم الملف، أو للامتثال لمعايير تبادل البيانات. أدناه سنعرّف خيارات الدقة، نكتب شكلًا هندسيًا، ثم نقرأه مرة أخرى لتأكيد التقريب.

## المتطلبات المسبقة

### 1. التحميل والتثبيت
احصل على أحدث حزمة Aspose.GIS for .NET من الموقع الرسمي: [download link](https://releases.aspose.com/gis/net/). اتبع دليل التثبيت لإضافة حزمة NuGet إلى مشروعك.

### 2. استيراد مساحة الأسماء
أضف مساحات الأسماء المطلوبة حتى تتمكن من الوصول إلى فئات GIS ومرافق المساعدة.

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

## دليل خطوة بخطوة

### الخطوة 1: تحديد خيارات الدقة
أنشئ كائن `GeoJsonOptions` وأخبر Aspose.GIS بعدد الأرقام العشرية التي تريدها لإحداثيات X/Y وZ.

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### الخطوة 2: تحديد مسار الإخراج
حدد المكان الذي سيتم حفظ ملف GeoJSON الناتج فيه.

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### الخطوة 3: إنشاء وتعبئة الشكل الهندسي
افتح طبقة `VectorLayer` جديدة باستخدام الخيارات المحددة أعلاه، أنشئ شكلًا هندسيًا من نوع `Point`، وأضفه إلى الطبقة.

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

### الخطوة 4: قراءة والتحقق من الدقة
افتح الملف الذي أنشأته للتو واطبع الإحداثيات. يجب أن ترى قيم X/Y مقربة إلى ثلاثة أرقام عشرية بينما تظل قيمة Z دقيقة.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

## المشكلات الشائعة والنصائح

- **أخطاء المسار:** تأكد من وجود الدليل في `path` أو استخدم `Path.Combine` مع `Environment.CurrentDirectory` لإنشاء مسار ملف آمن.  
- **عدم تطبيق الدقة:** تحقق من تمرير كائن `GeoJsonOptions` عند إنشاء الطبقة؛ وإلا سيتم استخدام الدقة الافتراضية (قيمة double كاملة).  
- **مجموعات البيانات الكبيرة:** للعمليات الضخمة، فكر في إعادة استخدام كائن `VectorLayer` واحد وإضافة الميزات دفعةً لتحسين الأداء.

## الأسئلة المتكررة

**س: هل Aspose.GIS لـ .NET متوافق مع صيغ GIS أخرى؟**  
ج: نعم، يدعم Shapefile، GeoJSON، KML، GML، والعديد غيرها، مما يتيح تحويلًا سلسًا بين الصيغ.

**س: هل يمكنني تجربة Aspose.GIS لـ .NET قبل الشراء؟**  
ج: بالطبع. يتوفر إصدار تجريبي مجاني من صفحة التحميل، يمنحك وصولًا كاملًا إلى جميع الميزات للتقييم.

**س: كيف أحصل على ترخيص مؤقت للاختبار؟**  
ج: يمكن إنشاء تراخيص تقييم مؤقتة عبر بوابة تراخيص Aspose؛ تكون صالحة لمدة 30 يومًا.

**س: أين يمكنني الحصول على المساعدة إذا واجهت مشاكل؟**  
ج: منتدى Aspose.GIS وعلامة Stack Overflow `aspose-gis` هما مكانان رائعان لطرح الأسئلة وإيجاد حلول المجتمع.

**س: هل تعمل المكتبة لكل من السكريبتات الصغيرة وتطبيقات المستوى المؤسسي؟**  
ج: نعم، تم تصميم Aspose.GIS للتعامل مع كل شيء من النماذج الأولية السريعة إلى تطبيقات الخوادم ذات الإنتاجية العالية.

## الخلاصة
باتباع الخطوات أعلاه، أصبحت الآن تعرف **كيفية تحديد الدقة** عند كتابة الأشكال الهندسية باستخدام Aspose.GIS for .NET. يساعد التحكم في تقريب الإحداثيات على الحفاظ على بياناتك المكانية نظيفة، قابلة للتبادل، وفعّالة في التخزين—وهي فوائد أساسية لأي مشروع يركز على GIS.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2025-12-20  
**تم الاختبار باستخدام:** Aspose.GIS 24.11 for .NET  
**المؤلف:** Aspose