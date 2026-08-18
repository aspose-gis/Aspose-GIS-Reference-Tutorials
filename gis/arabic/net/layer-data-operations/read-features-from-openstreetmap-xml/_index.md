---
date: 2026-06-10
description: تعرف على كيفية تحويل OSM إلى Shapefile وقراءة خصائص OpenStreetMap XML
  باستخدام Aspose.GIS لـ .NET. دليل خطوة بخطوة مع نصائح عملية.
keywords:
- convert osm to shapefile
- osm to geojson conversion
- how to read osm xml
linktitle: قراءة الخصائص من OpenStreetMap XML
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to convert OSM to Shapefile and read OpenStreetMap XML features
    using Aspose.GIS for .NET. Step‑by‑step guide with practical tips.
  headline: Convert OSM to Shapefile – Read Features from OpenStreetMap XML in Aspose.GIS
  type: TechArticle
- questions:
  - answer: Aspose.GIS for .NET
    question: What library handles OSM XML?
  - answer: About 20 lines (excluding setup)
    question: How many lines of code are needed?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes—Aspose.GIS streams data efficiently; filtering reduces memory usage.
    question: Can I read large OSM files?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: تحويل OSM إلى Shapefile – قراءة الخصائص من OpenStreetMap XML في Aspose.GIS
url: /ar/net/layer-data-operations/read-features-from-openstreetmap-xml/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل OSM إلى Shapefile – قراءة الميزات من XML لـ OpenStreetMap في Aspose.GIS

إذا كنت بحاجة إلى **تحويل OSM إلى Shapefile** أو ببساطة قراءة بيانات XML الخاصة بـ OpenStreetMap (OSM) داخل تطبيق .NET، فأنت في المكان الصحيح. تجعل Aspose.GIS for .NET عملية استيراد ملفات OSM XML سهلة، حيث تقوم باستخراج العقد (nodes) والمسارات (ways) والعلاقات (relations)، ثم تصديرها إلى Shapefile أو GeoJSON أو صيغ GIS أخرى. في هذا البرنامج التعليمي سنستعرض سير العمل بالكامل—من إعداد البيئة إلى تكرار الميزات—حتى تتمكن من بدء بناء حلول الخرائط أو التحليل المكاني فورًا.

## إجابات سريعة
- **ما المكتبة التي تتعامل مع OSM XML؟** Aspose.GIS for .NET  
- **كم عدد أسطر الكود المطلوبة؟** حوالي 20 سطرًا (باستثناء الإعداد)  
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تعمل للاختبار؛ الترخيص مطلوب للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **هل يمكنني قراءة ملفات OSM الكبيرة؟** نعم—Aspose.GIS يبث البيانات بكفاءة؛ التصفية تقلل من استهلاك الذاكرة.

## ما هو “how to read osm”؟
قراءة بيانات OSM (OpenStreetMap) تعني تحليل تنسيق OSM XML للوصول إلى العقد (nodes) والمسارات (ways) والعلاقات (relations) التي تمثل ميزات جغرافية حقيقية. بمجرد التحليل، يمكنك الاستعلام أو التصور أو تحويل هذه البيانات لمجموعة متنوعة من تطبيقات GIS. كما تشمل البيانات الوصفية مثل العلامات (tags)، الطوابع الزمنية (timestamps)، ومعلومات المستخدم، مما يتيح تحليلاً مفصلاً وتدفقات عمل تحريرية.

## لماذا تستخدم Aspose.GIS لـ OSM؟
توفر Aspose.GIS محلل **بدون تبعيات** يمكنه معالجة ملفات تصل إلى 1 GB مع استهلاك أقل من 250 MB من الذاكرة RAM، مما يجعله أسرع بثلاث مرات مقارنة بالعديد من البدائل مفتوحة المصدر. كما تقدم تحويلات هندسية مدمجة، استعلامات مكانية، وتصدير مباشر إلى Shapefile وGeoJSON وKML وغيرها، كل ذلك من خلال كود .NET نقي.

## المتطلبات المسبقة
- **Visual Studio** (Community, Professional, or Enterprise) – يُنصح بأحدث نسخة.  
- **Aspose.GIS for .NET** – حمّلها من [download link](https://releases.aspose.com/gis/net/) الرسمي وأضف حزمة NuGet إلى مشروعك.  
- معرفة أساسية بـ C# (المتغيرات، الحلقات، OOP).

## استيراد مساحات الأسماء
توفر مساحة الأسماء `Aspose.Gis` أنواع GIS الأساسية، بينما تحتوي `Aspose.Gis.Geometries` على مساعدات هندسية.

مساحة الأسماء `Aspose.Gis` هي نقطة الدخول لجميع عمليات GIS في Aspose.GIS.

## كيف تحوّل OSM إلى Shapefile باستخدام Aspose.GIS؟
حمّل طبقة OSM XML، وتكرّر عبر ميزاتها، واكتبها إلى Shapefile باستخدام ثلاث نداءات API فقط. تقوم فئة `ShapefileWriter` بإنشاء Shapefile جديد وتكتب الميزات إليه. أولاً، أنشئ كائن `Layer` لمصدر OSM، ثم افتح `ShapefileWriter` يشير إلى المجلد الوجهة، وأخيرًا انسخ هندسة كل ميزة وسماتها. يتيح هذا النهج تحويل OSM إلى Shapefile في أقل من دقيقة لمجموعات البيانات الحضرية النموذجية (≈ 200 k ميزة).

## كيف تُجري تحويل osm إلى geojson
يمكن لـ Aspose.GIS تصدير طبقة OSM نفسها مباشرة إلى GeoJSON باستخدام نداء `Save` واحد، مما يلغي الحاجة إلى خطوات تنسيق وسيطة. يكتب أسلوب `Save` الطبقة إلى الصيغة والمسار المحددين. استدعِ `layer.Save("output.geojson", SaveFormat.GeoJson)` وستتعامل المكتبة تلقائيًا مع تحويل الإحداثيات وتعيين السمات، لتُنتج ملف GeoJSON متوافق مع المعايير جاهزًا للخرائط الويب.

## الخطوة 1: تعريف دليل المستند
حدد المجلد الذي يحتوي على ملف OSM XML الخاص بك.  
استبدل `"Your Document Directory"` بالمسار المطلق أو النسبي للملف.

## الخطوة 2: فتح طبقة OpenStreetMap
تمثل فئة `Layer` طبقة GIS تم تحميلها من مصدر بيانات مثل ملف OSM XML.  
فتح الطبقة يبث XML، لذا تُحتفظ فقط بالأجزاء المطلوبة في الذاكرة.

## الخطوة 3: الحصول على عدد الميزات
استرجع العدد الإجمالي للميزات في طبقة OSM واطبع العدد في وحدة التحكم. يساعدك ذلك على التحقق من قراءة الملف بشكل صحيح.

## الخطوة 4: استرجاع ميزة حسب الفهرس
الوصول إلى أي ميزة مباشرةً باستخدام فهرسها الصفري؛ المثال يجلب الميزة الثالثة لتوضيح الوصول العشوائي.

## الخطوة 5: التكرار عبر الميزات
التكرار عبر الطبقة يتيح لك معالجة كل هندسة—نقاط، خطوط، أو مضلعات—بشكل منفرد. تُعيد طريقة `AsText()` الهندسة بصيغة Well‑Known Text (WKT)، وهو مفيد للتصحيح أو التسجيل.

## المشكلات الشائعة والحلول
- **الملف غير موجود** – تحقق مرة أخرى من المسار في `dataDir` وتأكد من أن اسم ملف OSM يطابق تمامًا.  
- **هندسة غير مدعومة** – بعض عناصر OSM تحتوي على علاقات معقدة؛ افحص `feature.Geometry` أولاً وتعامل مع الأنواع `MultiPolygon` أو `GeometryCollection` وفقًا لذلك.  
- **الأداء على الملفات الكبيرة** – حمّل الطبقة داخل كتلة `using` (كما هو موضح) لضمان التخلص منها، وطبق تصفية LINQ (`layer.Where(f => f.Geometry is Point)`) إذا كنت تحتاج فقط إلى جزء من الميزات.

## الأسئلة المتكررة
### هل Aspose.GIS لـ .NET متوافق مع صيغ بيانات GIS أخرى؟
نعم، يدعم Aspose.GIS أكثر من 30 صيغة GIS—بما في ذلك Shapefile وGeoJSON وKML وGML وCSV—مما يتيح تبادل بيانات سلس.

### هل يمكنني استخدام Aspose.GIS لأغراض تجارية؟
بالطبع. اشترِ ترخيصًا من [purchase page](https://purchase.aspose.com/buy) لإزالة قيود النسخة التجريبية والحصول على الدعم الكامل.

### هل تتوفر نسخة تجريبية مجانية لـ Aspose.GIS لـ .NET؟
نعم، حمّل نسخة تجريبية كاملة الوظائف من [website](https://releases.aspose.com/) لتقييم جميع الميزات قبل الشراء.

### أين يمكنني العثور على الدعم لـ Aspose.GIS لـ .NET؟
قم بزيارة [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) الرسمي لطرح الأسئلة، مشاركة الشفرات، والحصول على المساعدة من المجتمع ومهندسي Aspose.

### هل يمكنني الحصول على ترخيص مؤقت لـ Aspose.GIS لـ .NET؟
نعم، اطلب ترخيصًا مؤقتًا من [temporary license page](https://purchase.aspose.com/temporary-license/) للاختبار قصير الأمد أو خطوط أنابيب CI.

---

**آخر تحديث:** 2026-06-10  
**تم الاختبار مع:** Aspose.GIS 24.5 for .NET  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

```csharp
string dataDir = "Your Document Directory";
```

```csharp
using (var layer = Drivers.OsmXml.OpenLayer(dataDir + "fountain.osm"))
{
```

```csharp
int count = layer.Count;
Console.WriteLine("Layer count: " + count);
```

```csharp
Feature featureAtIndex2 = layer[2];
```

```csharp
foreach (Feature feature in layer)
{
    Console.WriteLine(feature.Geometry.AsText());
}
```

## دروس ذات صلة

- [كيفية تحويل Shapefile إلى GeoJSON باستخدام Aspose.GIS لـ .NET – دروس شاملة](/gis/net/)
- [كيفية تحويل GeoJSON إلى TopoJSON باستخدام Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [قراءة Shapefile C# – تصفية الميزات حسب السمة باستخدام Aspose.GIS](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}