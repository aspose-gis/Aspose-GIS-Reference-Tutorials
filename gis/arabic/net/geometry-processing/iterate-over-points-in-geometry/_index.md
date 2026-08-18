---
date: 2026-06-10
description: تعلم كيفية إضافة نقاط وإضافة إحداثيات إلى الشكل أثناء التكرار على الهندسة
  باستخدام Aspose.GIS for .NET، مجموعة أدوات GIS القوية لمطوري .NET.
keywords:
- how to add points
- add coordinates to shape
- Aspose.GIS geometry
linktitle: كيفية إضافة نقاط وتكرار الهندسة في .NET
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  headline: How to Add Points and Iterate Over Geometry in .NET
  type: TechArticle
- description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  name: How to Add Points and Iterate Over Geometry in .NET
  steps:
  - name: Create a `LineString` object
    text: '`LineString` is Aspose.GIS''s geometry type that represents an ordered
      collection of points forming a polyline.'
  - name: Add points to the `LineString`
    text: The `AddPoint` method inserts a new vertex (longitude, latitude) at the
      end of the line. Call it repeatedly to **add coordinates to shape** objects.
  - name: Iterate over the points
    text: '`LineString` implements `IEnumerable<IPoint>`, allowing you to loop through
      each point with a `foreach` statement. This makes extracting X (longitude) and
      Y (latitude) values trivial. The loop prints each point’s X (longitude) and
      Y (latitude) values to the console, allowing you to verify that the p'
  type: HowTo
- questions:
  - answer: '`LineString`'
    question: What is the primary class for point collections?
  - answer: Use `AddPoint(longitude, latitude)`
    question: How do you add a point?
  - answer: Yes, `LineString` implements `IEnumerable<IPoint>`
    question: Can you iterate with a foreach loop?
  - answer: .NET 6+ (or .NET Core 3.1/Framework 4.6+) and Aspose.GIS for .NET library
    question: Prerequisites?
  - answer: Building routes, visualizing tracks, or preprocessing data for spatial
      analysis
    question: Typical use case?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: كيفية إضافة نقاط وتكرار الهندسة في .NET
url: /ar/net/geometry-processing/iterate-over-points-in-geometry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إضافة نقاط والتكرار على الهندسة في .NET

## مقدمة

إذا كنت تعمل مع بيانات GIS في بيئة .NET، فإن أحد أول الأشياء التي تحتاج إلى معرفتها هو **كيفية إضافة نقاط** إلى هندسة ثم التعامل مع تلك النقاط. توفر Aspose.GIS for .NET واجهة برمجة تطبيقات نظيفة كائنية التوجه تجعل هذه العملية مباشرة. في هذا البرنامج التعليمي سنستعرض إنشاء `LineString`، وإضافة نقاط إليه، والتكرار على تلك النقاط حتى تتمكن من استخراج الإحداثيات أو إجراء تحليلات إضافية. سترى أيضًا كيفية **إضافة إحداثيات إلى كائنات الشكل** بكفاءة.

## إجابات سريعة
- **ما هي الفئة الأساسية لمجموعات النقاط؟** `LineString`
- **كيف تضيف نقطة؟** استخدم `AddPoint(longitude, latitude)`
- **هل يمكنك التكرار باستخدام حلقة foreach؟** نعم، `LineString` تنفذ `IEnumerable<IPoint>`
- **المتطلبات المسبقة؟** .NET 6+ (أو .NET Core 3.1/Framework 4.6+) ومكتبة Aspose.GIS for .NET
- **حالة الاستخدام النموذجية؟** بناء مسارات، تصور المسارات، أو معالجة البيانات مسبقًا للتحليل المكاني  
- **IPoint** تمثل هندسة نقطة واحدة بإحداثيات X (خط الطول) و Y (خط العرض).

## ما هو “إضافة نقاط” في GIS؟

إضافة النقاط تعني إدراج أزواج إحداثيات فردية (خط الطول، خط العرض) في حاوية هندسية مثل `LineString` أو `Polygon` أو `MultiPoint`. كل نقطة تصبح رأسًا يحدد الشكل أو المسار الذي تقوم بنمذجته، مما يتيح عمليات ومشاهدات مكانية. يمكن الوصول إلى هذه الرؤوس لاحقًا للتحليل، أو تصديرها إلى صيغ GIS مختلفة، أو استخدامها في حسابات مكانية مثل قياس المسافة أو اختبار التقاطع.

## لماذا إضافة نقاط باستخدام Aspose.GIS؟

تضيف النقاط باستخدام Aspose.GIS لأن المكتبة تضمن **معالجة هندسية آمنة من حيث النوع**، وتدعم **أكثر من 30 صيغة متجهة ورسترية**، ويمكنها معالجة **مجموعات بيانات مئات الصفحات** دون تحميل الملف بالكامل في الذاكرة. كما توفر الواجهة البرمجية تكرارًا مدمجًا، عمليات مكانية، وتحويل صيغ (Shapefile، GeoJSON، KML، إلخ) على جميع المنصات المدعومة.

## المتطلبات المسبقة

- Visual Studio 2022 (أو أي بيئة تطوير C#)  
- حزمة NuGet الخاصة بـ Aspose.GIS for .NET مثبتة  
- فهم أساسي لصياغة C#

## استيراد مساحات الأسماء

ابدأ باستيراد مساحات الأسماء اللازمة لتمكين الوصول إلى وظائف Aspose.GIS في تطبيق .NET الخاص بك:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## كيفية إضافة نقاط إلى هندسة؟

تضيف النقاط عن طريق إنشاء مثال `LineString`، واستدعاء طريقة `AddPoint` لكل زوج إحداثيات، ثم التكرار على المجموعة عند الحاجة. يغطي هذا النمط المكوّن من ثلاث خطوات الإنشاء، التعبئة، والعبور بطريقة مختصرة وسهلة القراءة. **LineString هو نوع هندسة يمثل مجموعة مرتبة من النقاط تشكل خطًا متعدد النقاط.** يضمن هذا النهج بقاء الهندسة صالحة وجاهزة للعمليات المكانية الإضافية مثل حساب الطول أو التصدير.

### الخطوة 1: إنشاء كائن `LineString`  

`LineString` هو نوع الهندسة في Aspose.GIS الذي يمثل مجموعة مرتبة من النقاط تشكل خطًا متعدد النقاط.

```csharp
LineString line = new LineString();
```

### الخطوة 2: إضافة نقاط إلى `LineString`  

طريقة `AddPoint` تُدرج رأسًا جديدًا (خط الطول، خط العرض) في نهاية الخط. استدعها بشكل متكرر **لإضافة إحداثيات إلى كائنات الشكل**.

```csharp
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```

### الخطوة 3: التكرار على النقاط  

`LineString` ينفذ `IEnumerable<IPoint>`، مما يتيح لك التكرار عبر كل نقطة باستخدام جملة `foreach`. هذا يجعل استخراج قيم X (خط الطول) و Y (خط العرض) أمرًا بسيطًا.

```csharp
foreach (IPoint point in line)
{
    Console.WriteLine(point.X + "," + point.Y);
}
```

تطبع الحلقة قيم X (خط الطول) و Y (خط العرض) لكل نقطة إلى وحدة التحكم، مما يتيح لك التحقق من أن النقاط أضيفت بشكل صحيح.

## حالات الاستخدام الشائعة

- **تخطيط المسار** – بناء مسار من سجلات GPS ثم تحليل المسافات بين نقاط الطريق.  
- **تحقق من البيانات** – التكرار على النقاط للتأكد من أنها تقع ضمن الحدود المتوقعة (مثلاً داخل حدود دولة).  
- **التصوير** – تصدير `LineString` إلى GeoJSON أو Shapefile للاستخدام في أدوات الخرائط.

## الأسئلة المتكررة

**س1: هل يمكن لـ Aspose.GIS for .NET التعامل مع أشكال هندسية أخرى غير `LineString`؟**  
ج: نعم، يدعم Aspose.GIS `Point` و `Polygon` و `MultiLineString` و `MultiPolygon` والعديد من أنواع الهندسة الأخرى.

**س2: هل Aspose.GIS مناسب لكل من المشاريع التجارية والشخصية؟**  
ج: بالتأكيد. خيارات الترخيص تغطي الاستخدام التجاري والشخصي والتعليمى.

**س3: هل يقدم Aspose.GIS for .NET وثائق شاملة للمبتدئين؟**  
ج: نعم، يتضمن المنتج وثائق واسعة، مراجع API، وعشرات الأمثلة البرمجية لمساعدتك على البدء بسرعة.

**س4: هل يمكنني توسيع وظائف Aspose.GIS for .NET من خلال تطوير مخصص؟**  
ج: يمكنك إنشاء طرق امتداد أو تغليف فئات Aspose.GIS لتناسب سير العمل المحدد، مما يمنحك سيطرة كاملة على حلول الجغرافيا المكانية المخصصة.

**س5: هل الدعم الفني متاح لمستخدمي Aspose.GIS؟**  
ج: يتم توفير دعم فني مخصص عبر منتديات Aspose ونظام التذاكر، لضمان حصولك على مساعدة سريعة.

---

**آخر تحديث:** 2026-06-10  
**تم الاختبار مع:** Aspose.GIS for .NET 24.5 (latest at time of writing)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [كيفية عد النقاط في الهندسة باستخدام Aspose.GIS for .NET](/gis/net/geometry-creation/count-points-in-geometry/)
- [كيفية إضافة نقطة إلى LineString وتحويل الهندسة إلى صيغة قابلة للتحرير باستخدام Aspose.GIS](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [إنشاء هندسة MultiPoint باستخدام Aspose.GIS for .NET](/gis/net/geometry-creation/create-multipoint-geometry/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}