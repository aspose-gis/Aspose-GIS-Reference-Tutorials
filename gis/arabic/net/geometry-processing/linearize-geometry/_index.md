---
date: 2026-09-10
description: تعرف على كيفية تحويل المنحنيات إلى خطوط (linearize geometry) باستخدام
  Aspose.GIS for .NET، مما يتيح geospatial processing و analysis فعالين في تطبيقات
  .NET الخاصة بك.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
lastmod: 2026-09-10
linktitle: تحويل Geometry إلى خطوط
og_description: تحويل المنحنيات إلى خطوط (linearize geometry) باستخدام Aspose.GIS
  for .NET. تعرف step‑by‑step على كيفية simplify geometries للحصول على rendering أسرع
  وتوافق (compatibility) أوسع.
og_image_alt: Guide showing how to linearize curved geometries to straight lines using
  Aspose.GIS in a .NET application
og_title: تحويل المنحنيات إلى خطوط باستخدام Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  headline: How to Convert Curves to Lines with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  name: How to Convert Curves to Lines with Aspose.GIS for .NET
  steps:
  - name: Define the output path
    text: '`Path.Combine` builds a platform‑independent file path, handling Windows
      backslashes and Unix forward slashes automatically. Replace `"Your Document
      Directory"` with the folder where you want the KML file saved.'
  - name: Create a layer for the output file
    text: A *layer* groups geographic features of the same type. Here we instantiate
      a new KML layer that will store the linearized geometry.
  - name: Construct a new feature
    text: A *feature* represents a single geographic object (point, line, polygon,
      etc.). We’ll attach our linear geometry to this feature.
  - name: Define the original complex geometry
    text: '`Geometry.FromWkt` parses a Well‑Known Text (WKT) string into a geometry
      object. The sample WKT includes a `LineString`, a `CompoundCurve`, and a `CircularString`
      to showcase curve handling.'
  - name: Convert curves to lines
    text: '`ToLinearGeometry()` tessellates every curve in the source geometry into
      straight‑line segments, returning a new linear geometry that retains any Z‑coordinates.'
  - name: Assign the linear geometry to the feature
    text: The feature’s `Geometry` property now holds the simplified, linear version
      of the original shape.
  - name: Add the feature to the layer
    text: Adding the feature to the KML layer queues it for writing; when the `using`
      block ends, the layer flushes the data to the output file.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Core, enabling cross‑platform applications.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Absolutely! The library supports KML, Shapefile, GeoJSON, and many more
      formats—over 30 in total.
    question: Can I work with different GIS file formats using Aspose.GIS for .NET?
  - answer: Yes, it provides a wide range of spatial functions, from buffering to
      spatial joins.
    question: Does Aspose.GIS offer spatial operations and analysis?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      and staff support.
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert curves to lines
- Aspose.GIS
- .NET GIS processing
title: كيفية تحويل المنحنيات إلى خطوط باستخدام Aspose.GIS for .NET
url: /ar/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل المنحنيات إلى خطوط (تحويل الهندسة إلى خطية) باستخدام Aspose.GIS لـ .NET

## مقدمة
إذا كنت بحاجة إلى **تحويل المنحنيات إلى خطوط** لأغراض التخطيط، التحليل المكاني، أو مهام تبادل البيانات، فإن Aspose.GIS لـ .NET يوفّر لك طريقة برمجية نظيفة للقيام بذلك. في هذا البرنامج التعليمي سنستعرض مثالًا واقعيًا كاملًا يوضح لك كيفية أخذ هندسة معقدة—تحتوي على منحنيات وأشكال مركبة—وتحويلها إلى تمثيل خطي بسيط يعمل مع أي نظام GIS.

## إجابات سريعة
- **ماذا يعني “تحويل المنحنيات إلى خطوط”؟** يحول الهندسات المنحنية إلى مقاطع خطوط مستقيمة.  
- **لماذا تختار Aspose.GIS؟** المكتبة تدعم أكثر من 30 تنسيق GIS وتتعامل مع تحويل الهندسة دون الحاجة إلى أدوات خارجية.  
- **ماذا أحتاج مسبقًا؟** .NET Framework أو .NET Core، Visual Studio (أو أي بيئة تطوير C#)، وحزمة Aspose.GIS عبر NuGet.  
- **كم من الوقت سيستغرق تشغيل العينة؟** أقل من خمس دقائق بمجرد تثبيت المكتبة.  
- **هل يمكنني التصدير إلى تنسيقات أخرى؟** بالتأكيد—استبدل برنامج تشغيل KML بـ Shapefile أو GeoJSON أو غيرها.  
يمكنك تنزيل مجموعة المنتجات الكاملة من [موقع Aspose](https://releases.aspose.com/).

## ماذا يعني تحويل المنحنيات إلى خطوط؟
تحويل المنحنيات إلى خطوط (المعروف أيضًا باسم **تحويل الهندسة إلى خطية**) يستبدل كل مقطع منحني بسلسلة من القطع المستقيمة القصيرة، مما ينتج *هندسة خطية*. هذا يجعل العرض أسرع حتى خمس مرات، يقلل استهلاك الذاكرة، ويضمن إمكانية استهلاك البيانات من قبل خدمات GIS القديمة التي تقبل فقط الميزات الخطية.

## لماذا تحويل المنحنيات إلى خطوط؟
الهندسات الخطية تُظهر وتستعلم أسرع حتى **5×** من نظيراتها المنحنية، و**أكثر من 30 منصة GIS** تقبل فقط الميزات الخطية. تبسيط الهندسة يقلل أيضًا من حجم الملف للمعاينات على الويب ويفتح المجال لخوارزميات—مثل تحليل الشبكات أو التجميع—التي تتطلب مدخلات خطوط مستقيمة.

## كيف يتم تحويل الهندسة إلى خطية؟
استخدم الطريقة `ToLinearGeometry()` التي توفرها Aspose.GIS. تقوم تلقائيًا بتقسيم كل منحنى في الهندسة إلى مقاطع خطوط مستقيمة مع الحفاظ على قيم Z، بحيث تحصل على تقريب خطي دون فقدان بيانات الارتفاع. يمكنك أيضًا تحديد تسامح للتحكم في الحد الأقصى للانحراف بين المنحنى الأصلي والمقاطع المولدة، مما يتيح لك موازنة الدقة مع حجم الملف. تعمل الطريقة مع الهندسات ثنائية وثلاثية الأبعاد على حد سواء.

## المتطلبات المسبقة
قبل الغوص في الشيفرة، تأكد من وجود ما يلي:

1. **Aspose.GIS لـ .NET** – حمّله من [موقع Aspose.GIS](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (أو .NET Core) مثبت على جهاز التطوير الخاص بك.  
3. **Visual Studio** (أو أي بيئة تطوير متوافقة مع C#) لكتابة وتنفيذ العينة.

## استيراد مساحات الأسماء
لبدء استخدام وظائف Aspose.GIS، استورد مساحات الأسماء المطلوبة.

### مساحات الأسماء الأساسية لـ Aspose.GIS
مساحة الاسم `Aspose.Gis` تحتوي على فئات الهندسة الأساسية، برامج التشغيل، والأدوات المساعدة اللازمة لجميع عمليات GIS.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### برنامج تشغيل التنسيق المستهدف
`Aspose.Gis.Drivers` يوفر مصانع ثابتة لكل تنسيق ملف مدعوم؛ `Drivers.Kml` ينشئ كاتب KML.  
```csharp
using Aspose.GIS.Kml;
```

## دليل خطوة بخطوة لتحويل المنحنيات إلى خطوط
فيما يلي شرح مفصل لكل سطر من الشيفرة، يوضح **كيفية تحويل المنحنيات إلى خطوط** ولماذا كل خطوة مهمة.

### الخطوة 1: تحديد مسار الإخراج
`Path.Combine` يبني مسار ملف مستقل عن النظام، مع معالجة الفواصل الخلفية في Windows والشرطية في Unix تلقائيًا.  
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
استبدل `"Your Document Directory"` بالمجلد الذي تريد حفظ ملف KML فيه.

### الخطوة 2: إنشاء طبقة للملف الناتج
*الطبقة* تجمع الميزات الجغرافية من نفس النوع. هنا نقوم بإنشاء طبقة KML جديدة ستخزن الهندسة الخطية.  
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```

### الخطوة 3: إنشاء ميزة جديدة
*الميزة* تمثل كائنًا جغرافيًا واحدًا (نقطة، خط، مضلع، إلخ). سنرفق الهندسة الخطية بهذه الميزة.  
```csharp
var feature = layer.ConstructFeature();
```

### الخطوة 4: تعريف الهندسة المركبة الأصلية
`Geometry.FromWkt` يحلل نص Well‑Known Text (WKT) إلى كائن هندسة. تتضمن عينة WKT `LineString`، `CompoundCurve`، و`CircularString` لتوضيح التعامل مع المنحنيات.  
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```

### الخطوة 5: تحويل المنحنيات إلى خطوط
`ToLinearGeometry()` تقسم كل منحنى في الهندسة المصدر إلى مقاطع خطوط مستقيمة، وتعيد هندسة خطية جديدة تحتفظ بأي إحداثيات Z.  
```csharp
var linear = geometry.ToLinearGeometry();
```

### الخطوة 6: إسناد الهندسة الخطية إلى الميزة
خاصية `Geometry` في الميزة الآن تحمل النسخة المبسطة الخطية من الشكل الأصلي.  
```csharp
feature.Geometry = linear;
```

### الخطوة 7: إضافة الميزة إلى الطبقة
إضافة الميزة إلى طبقة KML تضعها في قائمة الانتظار للكتابة؛ عند انتهاء كتلة `using`، تقوم الطبقة بتفريغ البيانات إلى ملف الإخراج.  
```csharp
layer.Add(feature);
```

## المشكلات الشائعة ونصائح احترافية
- **فواصل المسار:** استخدم `Path.Combine` لتجنب المشكلات بين Windows وLinux.  
- **الهندسات الكبيرة جدًا:** قد يولد تحويل الأشكال المعقدة آلاف الرؤوس؛ فكر في استدعاء `Simplify()` بعد التحويل لتقليل عدد النقاط.  
- **اختيار برنامج التشغيل:** إذا كنت تحتاج إلى تنسيق إخراج مختلف، استبدل `Drivers.Kml` بـ `Drivers.Shapefile` أو `Drivers.GeoJson`، وغير امتداد الملف وفقًا لذلك.  
- **الحفاظ على قيم Z:** `ToLinearGeometry()` يحتفظ بالإحداثيات ثلاثية الأبعاد (Z)، لذا لا تفقد بيانات الارتفاع.

## الأسئلة المتكررة (FAQ)

**س: هل Aspose.GIS لـ .NET متوافق مع .NET Core؟**  
ج: نعم، Aspose.GIS يعمل مع .NET Core، مما يتيح تطبيقات متعددة المنصات.

**س: هل يمكنني العمل مع تنسيقات ملفات GIS مختلفة باستخدام Aspose.GIS لـ .NET؟**  
ج: بالتأكيد! تدعم المكتبة KML، Shapefile، GeoJSON، والعديد من التنسيقات الأخرى—أكثر من 30 تنسيقًا إجمالاً.

**س: هل يقدم Aspose.GIS عمليات وتحليلات مكانية؟**  
ج: نعم، يوفر مجموعة واسعة من الدوال المكانية، من التوسيع إلى الانضمامات المكانية.

**س: هل هناك نسخة تجريبية مجانية؟**  
ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من [موقع Aspose.GIS](https://releases.aspose.com/gis/net/).

**س: أين يمكنني الحصول على المساعدة إذا واجهت مشاكل؟**  
ج: زر [منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33) للحصول على دعم المجتمع والموظفين.

### استفسارات شائعة إضافية

**س: هل يمكنني تحويل الهندسات التي تحتوي على إحداثيات 3D (Z)؟**  
ج: نعم، `ToLinearGeometry()` يعمل مع الهندسات ثنائية وثلاثية الأبعاد؛ قيم Z تُحفظ.

**س: كيف يؤثر التحويل إلى خطوط على حجم الملف؟**  
ج: تحويل المنحنيات إلى عدد كبير من القطع الخطية قد يزيد حجم الملف؛ استخدم `Simplify()` بعد التحويل إذا كان الحجم يمثل قلقًا.

**س: هل يمكنني التحكم في طول القطع عند تحويل المنحنيات إلى خطوط؟**  
ج: الطريقة الافتراضية تستخدم تسامحًا داخليًا. للتحكم المخصص يمكنك تقسيم المنحنيات يدويًا قبل استدعاء `ToLinearGeometry()`.

## الخلاصة
في هذا البرنامج التعليمي غطينا **كيفية تحويل المنحنيات إلى خطوط** (تحويل الهندسة إلى خطية) باستخدام Aspose.GIS لـ .NET، بدءًا من إعداد البيئة وحتى كتابة النتيجة الخطية إلى ملف KML. الآن يمكنك دمج هذا التدفق في تطبيقات الخرائط، خطوط معالجة البيانات، أو أي مشروع GIS يتطلب هندسات مبسطة.

---

**آخر تحديث:** 2026-09-10  
**تم الاختبار مع:** Aspose.GIS 24.11 لـ .NET  
**المؤلف:** Aspose

## دروس ذات صلة

- [How to Create GeoJSON with Tolerance Aspose.GIS for .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Convert Polygon to Line with Aspose.GIS for .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)
- [Learn How to Create LineString Geometry with Aspose.GIS for .NET](/gis/net/geometry-creation/create-linestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}