---
date: 2026-06-10
description: تعلم كيفية إنشاء هندسة الخط المتعدد في .NET وتحويل الهندسة إلى WKB باستخدام
  Aspose.GIS for .NET مع نسخة ExtendedPostGis.
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: تحديد نسخة WKB عند الترجمة
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  headline: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  name: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  steps:
  - name: Creating a Geometry Object
    text: The `Geometry` class is Aspose.GIS's base type that represents any spatial
      object in memory. Linestring represents a series of connected points forming
      a linear geometry. In this step we instantiate a `Linestring` with a collection
      of coordinate pairs that model a simple road segment.
  - name: Generating WKB Representation
    text: '`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to
      include SRID in the output binary. Here we call the `AsBinary` method, passing
      the EWKB variant, which returns a `byte[]` containing the full binary representation.'
  - name: Writing to File
    text: '`File.WriteAllBytes` writes the binary array to disk. The resulting file
      (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB`
      function.'
  type: HowTo
- questions:
  - answer: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which
      PostGIS reads directly via `ST_GeomFromEWKB`.
    question: Can I use the EWKB file with PostGIS?
  - answer: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry
      from its binary form.
    question: Is it possible to read a WKB file back into a geometry object?
  - answer: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons,
      and many more spatial types.
    question: Does the library support other geometry types like polygons?
  - answer: Set the `SRID` property on the geometry object before calling `AsBinary`,
      e.g., `linestring.SRID = 4326;`.
    question: How do I specify a different SRID when creating the geometry?
  - answer: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6
      without modification.
    question: Will this code work on .NET Core?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: إنشاء هندسة الخط المتعدد & نسخة WKB في Aspose.GIS for .NET
url: /ar/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء هندسة Linestring ومتغير WKB في Aspose.GIS لـ .NET

## المقدمة
إذا كنت بحاجة إلى **إنشاء هندسة linestring .NET** ثم تحويل تلك الهندسة إلى صيغة ثنائية، فإن Aspose.GIS لـ .NET يوفّر لك واجهة برمجة تطبيقات نظيفة وعالية الأداء تعمل عبر .NET Framework و .NET Core و .NET 5/6+. في هذا الدرس سنستعرض كل خطوة—من استيراد مساحات الأسماء إلى كتابة ملف EWKB—حتى تتمكن من الحفاظ على معلومات SRID ودمج بيانات GIS في PostgreSQL/PostGIS أو أي سير عمل يعتمد على الصيغ الثنائية دون عناء.

## إجابات سريعة
- **ماذا يعني WKB؟** Well‑Known Binary، تمثيل ثنائي مضغوط للكائنات الهندسية.  
- **أي متغير WKB يخزن SRID؟** المتغير `ExtendedPostGis` (EWKB) يدمج SRID مباشرة داخل الثنائي.  
- **هل أحتاج إلى رخصة؟** يلزم وجود رخصة مؤقتة أو كاملة لـ Aspose.GIS للتنفيذ في بيئات الإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، و .NET 5/6+.  
- **كم يستغرق التنفيذ؟** عادةً أقل من 10 دقائق لمثال أساسي.

## ما هي هندسة Linestring؟
هندسة linestring هي شكل بسيط يتكوّن من قائمة مرتبة من النقاط المتصلة بقطاعات خطية مستقيمة. تُعدّ التمثيل المفضّل للميزات الخطية مثل الطرق، الأنابيب، أو مسارات الأنهار في قواعد البيانات المكانية.

## لماذا تحديد متغير WKB؟
استخدام المتغير الصحيح لـ WKB يضمن أن البيانات الوصفية الحرجة—وخاصة معرف نظام الإحداثيات (SRID)—تنتقل مع الهندسة. المتغير `ExtendedPostGis` (EWKB) يخزن الـ SRID داخل الحمولة الثنائية، مما يتيح تبادل سلس مع PostGIS، Oracle Spatial، أو أي نظام يتوقع ملفات ثنائية تدعم SRID.

## المتطلبات المسبقة
قبل البدء، تأكد من توفر ما يلي:

### تثبيت Aspose.GIS لـ .NET
1. تحميل Aspose.GIS: زر [رابط التحميل](https://releases.aspose.com/gis/net/) للحصول على أحدث حزمة.  
2. إضافة حزمة NuGet إلى مشروعك (مثال: `Install-Package Aspose.GIS`).  

### الإلمام ببرمجة C#
- فهم أساسي لبنية جمل C# وهيكل المشروع.  
- القدرة على تشغيل مشروع وحدة تحكم .NET أو مكتبة فئات.

## استيراد مساحات الأسماء
مساحة الأسماء `Aspose.GIS` تمنحك الوصول إلى جميع الفئات المتعلقة بالهندسة.  

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

توفر هذه المساحات الوظائف الأساسية لـ GIS، بما في ذلك إنشاء الهندسة، التحويل، والتسلسل الثنائي.

## كيفية إنشاء هندسة linestring؟
لإنشاء linestring، أنشئ كائن `Linestring` مع قائمة مرتبة من أزواج الإحداثيات، عيّن الـ SRID إذا لزم الأمر، ثم سَلسِل الكائن إلى المتغير WKB المطلوب. العملية تتضمن ثلاث خطوات: بناء الهندسة، اختيار متغير `ExtendedPostGis` للاحتفاظ بالـ SRID، وكتابة المصفوفة الثنائية الناتجة إلى ملف.

### الخطوة 1: إنشاء كائن هندسي
الفئة `Geometry` هي النوع الأساسي في Aspose.GIS الذي يمثل أي كائن مكاني في الذاكرة.  
Linestring تمثل سلسلة من النقاط المتصلة لتكوين هندسة خطية.  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
في هذه الخطوة نقوم بإنشاء كائن `Linestring` يحتوي على مجموعة من أزواج الإحداثيات التي تمثل مقطع طريق بسيط.

### الخطوة 2: توليد تمثيل WKB
`WkbVariant.ExtendedPostGis` هو قيمة التعداد التي تُخبر Aspose.GIS بإدراج الـ SRID في الثنائي الناتج.  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
هنا نستدعي الطريقة `AsBinary` مع تمرير متغير EWKB، مما يُعيد مصفوفة `byte[]` تحتوي على التمثيل الثنائي الكامل.

### الخطوة 3: كتابة إلى ملف
`File.WriteAllBytes` يكتب المصفوفة الثنائية إلى القرص.  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
يمكن استيراد الملف الناتج (`EWkbFile.ewkb`) مباشرةً إلى جدول PostGIS باستخدام الدالة `ST_GeomFromEWKB`.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|----------|
| **ملف فارغ** | `Path.Combine` يشير إلى دليل غير موجود. | تأكد من وجود الدليل الهدف أو أنشئه باستخدام `Directory.CreateDirectory`. |
| **SRID غير صحيح** | استخدام المتغير الافتراضي `WkbVariant.Standard` يحذف الـ SRID. | استخدم دائمًا `WkbVariant.ExtendedPostGis` عندما تكون حفظ الـ SRID ضروريًا. |
| **استثناء الترخيص** | تشغيل بدون رخصة صالحة في بيئة الإنتاج. | طبّق رخصة مؤقتة أو كاملة قبل تنفيذ الكود في بيئة الإنتاج. |

## الأسئلة المتكررة
**س: هل يمكنني استخدام ملف EWKB مع PostGIS؟**  
ج: نعم، المتغير `ExtendedPostGis` ينتج EWKB يتضمن SRID، والذي يقرأه PostGIS مباشرة عبر الدالة `ST_GeomFromEWKB`.  

**س: هل من الممكن قراءة ملف WKB وإعادته إلى كائن هندسي؟**  
ج: بالتأكيد. استخدم `Geometry.FromBinary(byteArray)` لإعادة بناء الهندسة من تمثيلها الثنائي.  

**س: هل تدعم المكتبة أنواع هندسة أخرى مثل المضلعات؟**  
ج: نعم، Aspose.GIS يتعامل مع النقاط، linestrings، المضلعات، multipolygons، والعديد من الأنواع المكانية الأخرى.  

**س: كيف أحدد SRID مختلف عند إنشاء الهندسة؟**  
ج: عيّن الخاصية `SRID` على كائن الهندسة قبل استدعاء `AsBinary`، مثال: `linestring.SRID = 4326;`.  

**س: هل سيعمل هذا الكود على .NET Core؟**  
ج: نعم، نفس الواجهة تعمل عبر .NET Framework و .NET Core و .NET 5/6 دون تعديل.

---

**آخر تحديث:** 2026-06-10  
**تم الاختبار مع:** Aspose.GIS لـ .NET 23.9 (أحدث نسخة عند كتابة المقالة)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [تحويل الهندسة إلى تنسيق WKB باستخدام Aspose.GIS لـ .NET](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [تحديد متغير WKT عند التحويل باستخدام Aspose.GIS](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [إنشاء هندسة MultiLineString باستخدام Aspose.GIS لـ .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}