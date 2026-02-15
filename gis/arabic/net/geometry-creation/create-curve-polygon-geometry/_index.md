---
date: 2026-02-15
description: تعلم كيفية إنشاء طبقة متجهية وهندسة مضلع منحني باستخدام Aspose.GIS لـ
  .NET، بما في ذلك هندسة السلسلة الدائرية للحلقات الداخلية.
linktitle: Create Curve Polygon Geometry
second_title: Aspose.GIS .NET API
title: إنشاء طبقة متجهة ومضلع منحني باستخدام Aspose.GIS
url: /ar/net/geometry-creation/create-curve-polygon-geometry/
weight: 18
---

.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء طبقة متجهية ومضلع منحني باستخدام Aspose.GIS

## Introduction
في مجال تطوير نظم المعلومات الجغرافية (GIS)، **Aspose.GIS for .NET** تبرز كمكتبة قوية لإنشاء وتحرير ومعالجة البيانات المكانية. في هذا الدرس ستتعلم كيفية **إنشاء طبقة متجهية** و **إنشاء مضلع منحني** خطوة بخطوة، بحيث يمكنك دمج أشكال متقدمة مباشرةً في تطبيقات GIS الخاصة بك. بنهاية الدليل ستحصل على ملف Shapefile جاهز يحتوي على مضلع منحني مع الحلقات الخارجية والداخلية.

## Quick Answers
- **ما المكتبة المستخدمة؟** Aspose.GIS for .NET  
- **المهمة الأساسية؟** إنشاء شكل مضلع منحني، حفظه كملف Shapefile، و **إنشاء طبقة متجهية** للبيانات  
- **الوقت النموذجي للتنفيذ؟** 5–10 دقائق لشكل أساسي  
- **المتطلبات المسبقة؟** بيئة تطوير .NET وحزمة Aspose.GIS NuGet  
- **هل يمكنني عرض النتيجة؟** نعم – أي عارض GIS يدعم Shapefile (مثل QGIS، ArcGIS)

## What is a Curve Polygon?
المضلع المنحني هو مضلع يمكن أن تتكون حوافه من مقاطع منحنية (مثل الأقواس الدائرية) بدلاً من الخطوط المستقيمة فقط. يتيح ذلك نمذجة أكثر واقعية للميزات الطبيعية مثل البحيرات والجزر أو أي شكل يستفيد من حدود ناعمة.

## Why create curve polygon geometry with Aspose.GIS?
- **الدقة** – يتم تخزين الحواف المنحنية رياضياً، مما يحافظ على الشكل الدقيق.  
- **قابلية التشغيل المتبادل** – ملف Shapefile المُنتج يعمل مع جميع منصات GIS الرئيسية.  
- **الإنتاجية** – يتطلب القليل من الشيفرة لتعريف الأشكال المعقدة، مما يسرّع دورات التطوير.  
- **المرونة** – يمكنك **إنشاء طبقة متجهية** في الوقت الفعلي وإرفاق أي شكل تحتاجه.

## Prerequisites
قبل البدء، تأكد من وجود ما يلي:

1. **Aspose.GIS for .NET** مثبت. قم بتنزيله من صفحة [Aspose.GIS for .NET releases page](https://releases.aspose.com/gis/net/).  
2. معرفة عملية بلغة C# ونظام .NET.  
3. بيئة تطوير متكاملة مثل Visual Studio (أي نسخة حديثة) أو Visual Studio Code.

## Import Namespaces
في هذه الخطوة، سنستورد المساحات الاسمية (namespaces) اللازمة لاستخدام وظائف Aspose.GIS في الشيفرة.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step‑by‑Step Guide

### Step 1: Define the File Path
أولاً، حدد المكان الذي سيُحفظ فيه ملف Shapefile الخاص بالمضلع المنحني.

```csharp
string path = "Your Document Directory" + "CreateCurvePolygon_out.shp";
```

استبدل `"Your Document Directory"` بالمسار الفعلي للمجلد على جهازك.

### Step 2: Create a Vector Layer
إنشاء مثيل جديد لطبقة متجهية باستخدام برنامج تشغيل Shapefile. هذه هي خطوة **إنشاء طبقة متجهية** التي تُجهّز الحاوية لشكلنا.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Your code for creating the Curve Polygon Geometry will go here
}
```

عبارة `using` تضمن تحرير الموارد بشكل صحيح.

### Step 3: Construct a Feature
إنشاء كائن Feature سيحمل الشكل وأي بيانات سمة.

```csharp
var feature = layer.ConstructFeature();
```

### Step 4: Create Curve Polygon Geometry
الآن سننشئ كائن `CurvePolygon` فارغ.

```csharp
var curvePolygon = new CurvePolygon();
```

### Step 5: Define the Exterior Ring
أضف سلسلة دائرية تشكل الحد الخارجي للمضلع.

```csharp
var exterior = new CircularString();
exterior.AddPoint(-2, 0);
exterior.AddPoint(0, 2);
exterior.AddPoint(2, 0);
exterior.AddPoint(0, -2);
exterior.AddPoint(-2, 0);
curvePolygon.ExteriorRing = exterior;
```

الإحداثيات أعلاه تُنتج شكلاً شبيهاً بالقرص الحلقي.

### Step 6: Define an Interior Ring (Optional)
إذا كنت بحاجة إلى فتحة داخل المضلع، عرّفها كسلسلة دائرية أخرى. يوضح هذا كيفية إضافة **مضلع حلقة داخلية** باستخدام **هندسة السلسلة الدائرية**.

```csharp
var interior = new CircularString();
interior.AddPoint(-1, 0);
interior.AddPoint(0, 1);
interior.AddPoint(1, 0);
interior.AddPoint(0, -1);
interior.AddPoint(-1, 0);
curvePolygon.AddInteriorRing(interior);
```

### Step 7: Assign Geometry to the Feature
اربط المضلع المنحني بالـ Feature الذي أنشأته مسبقاً.

```csharp
feature.Geometry = curvePolygon;
```

### Step 8: Add the Feature to the Layer
أخيراً، أضف الـ Feature إلى الطبقة المتجهية لتصبح جزءاً من مجموعة البيانات.

```csharp
layer.Add(feature);
```

عند انتهاء كتلة `using`، يتم كتابة ملف Shapefile إلى القرص.

## Common Issues and Solutions
| المشكلة | سبب حدوثها | الحل |
|-------|----------------|-----|
| **File not created** | مسار غير صحيح أو عدم وجود أذونات كتابة | تحقق من وجود الدليل وأن التطبيق يمتلك صلاحية الكتابة. |
| **Curved edges appear as straight lines in some viewers** | العارض لا يدعم السلاسل الدائرية | استخدم تطبيق GIS يدعم مواصفات Shapefile بالكامل (مثل QGIS 3.28+). |
| **Exception `ArgumentException` on `AddPoint`** | النقاط خارج نطاق الإحداثيات الصالحة لنظام الإحداثيات المختار | تأكد من أن الإحداثيات ضمن نظام الإحداثيات المرجعي الذي تنوي استخدامه. |

## Frequently Asked Questions

**Q: هل Aspose.GIS for .NET متوافق مع مكتبات GIS أخرى؟**  
A: نعم، يدعم Aspose.GIS for .NET قابلية التشغيل المتبادل مع العديد من صيغ GIS الشائعة، مما يتيح لك تبادل البيانات مع مكتبات مثل GDAL/OGR أو Proj.NET.

**Q: هل يمكنني عرض الشكل الهندسي للمضلع المنحني المُنتج في برنامج GIS؟**  
A: بالتأكيد! يمكن فتح ملف Shapefile الناتج في QGIS أو ArcGIS أو أي أداة GIS تدعم صيغة Shapefile.

**Q: هل يوفر Aspose.GIS for .NET قدرات التحليل المكاني؟**  
A: نعم، يتضمن وظائف للاستعلام المكاني، وإنشاء مناطق عازلة، والتقاطع، وغيرها، مما يتيح تحليلاً متقدماً مباشرةً في .NET.

**Q: أين يمكنني طلب المساعدة أو مناقشة الأفكار مع مستخدمين آخرين؟**  
A: انضم إلى منتدى مجتمع Aspose.GIS [هنا](https://forum.aspose.com/c/gis/33) للتواصل مع مطورين آخرين.

**Q: هل يتوفر نسخة تجريبية مجانية قبل الشراء؟**  
A: بالطبع! يمكنك تنزيل نسخة تجريبية مجانية من [صفحة الإصدارات](https://releases.aspose.com/) وتقييم جميع الميزات.

## Conclusion
لقد تعلمت الآن كيفية **إنشاء طبقة متجهية** و **إنشاء مضلع منحني** باستخدام Aspose.GIS for .NET، وحفظه كملف Shapefile، واستكشاف المشكلات الشائعة والأسئلة المتكررة. لا تتردد في تجربة مجموعات إحداثيات مختلفة، إضافة بيانات سمة، أو دمج الطبقة في سير عمل GIS أكبر.

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.GIS for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}