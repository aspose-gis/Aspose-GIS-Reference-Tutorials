---
date: 2026-10-15
description: تعلم كيفية إنشاء geojson من الإحداثيات وكتابته إلى تدفق باستخدام Aspose.GIS
  for .NET. يوضح هذا البرنامج التعليمي خطوة بخطوة تحويل النقاط وتوليد كود GeoJSON
  بلغة C#.
keywords:
- create geojson from coordinates
- stream large geojson files
- write geojson to stream
- geojson tutorial c#
- compress geojson with gzip
lastmod: 2026-10-15
linktitle: كتابة GeoJSON إلى تدفق
og_description: تعلم كيفية إنشاء geojson من الإحداثيات وكتابته إلى تدفق باستخدام Aspose.GIS
  for .NET – دليل خطوة بخطوة للمجموعات الكبيرة من البيانات.
og_image_alt: Screenshot of Aspose.GIS code generating GeoJSON stream in C#
og_title: إنشاء geojson من الإحداثيات، وكتابته إلى تدفق في .NET
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create geojson from coordinates and write it to a stream
    using Aspose.GIS for .NET. This tutorial shows step‑by‑step conversion of points
    and generation of GeoJSON C# code.
  headline: Create geojson from coordinates, write to a stream in .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET geospatial
- C# stream processing
- GIS data conversion
title: إنشاء geojson من الإحداثيات، وكتابته إلى تدفق في .NET
url: /ar/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء geojson من الإحداثيات وكتابته إلى تدفق

## مقدمة
في هذا الدرس ستتعلم **كيفية إنشاء geojson من الإحداثيات** وكتابته مباشرةً إلى تدفق باستخدام Aspose.GIS لـ .NET. سنستعرض إعداد البيئة، إنشاء الطبقة، تعبئة الكائنات، وتدفق النتيجة، حتى تتمكن من تضمين حمولات جغرافية في واجهات برمجة التطبيقات، وظائف السحابة، أو الخدمات بدون ملفات مؤقتة.

## إجابات سريعة
- **ما الفئة التي تكتب GeoJSON إلى تدفق؟** `VectorLayer` together with the `GeoJsonDriver`.
- **هل أحتاج إلى ترخيص للتطوير؟** A free trial works for development; a commercial license is required for production.
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **هل يمكنني تحويل مجموعات النقاط إلى GeoJSON؟** Yes – create a `Feature` for each point and assign a `Point` geometry.
- **هل التدفق مناسب لمجموعات البيانات الكبيرة؟** Absolutely – `MemoryStream` lets you write gigabyte‑scale GeoJSON without loading the whole file into memory.

## ما هو GeoJSON؟
GeoJSON هو تنسيق مفتوح يعتمد على JSON لتشفير الميزات الجغرافية مثل النقاط والخطوط والمضلعات. يتكون من `FeatureCollection` يجمع كائنات `Feature` الفردية، كل منها يحمل بيانات الهندسة والسمات. نظرًا لخفته وملاءمته للويب، يعتبر GeoJSON المعيار الفعلي لتبادل البيانات المكانية بين المتصفحات، خوادم GIS، وتطبيقات الهواتف المحمولة.

## لماذا تستخدم Aspose.GIS لإنشاء geojson؟
Aspose.GIS يدعم **أكثر من 35+ تنسيق ملف مكاني** ويمكنه تدفق ملفات أكبر من **2 GB** مع الحفاظ على استهلاك الذاكرة أقل من **50 MB**. محرك التدفق عالي الأداء يكتب GeoJSON مباشرةً إلى أي `Stream` في .NET، مما يلغي الحاجة إلى ملفات مؤقتة وسيقلل من زمن استجابة I/O بنسبة تصل إلى **70 %** في سيناريوهات السحابة النموذجية.

## المتطلبات المسبقة
1. **Aspose.GIS for .NET** مثبت. قم بتنزيل حزمة **Aspose.GIS for .NET** من [here](https://releases.aspose.com/gis/net/).
2. مجلد قابل للكتابة في مشروعك حيث يمكنك وضع ملفات مؤقتة إذا لزم الأمر.
3. بيئة تشغيل .NET 5+ أو .NET Core 3.1+ مثبتة.

الآن، دعنا نغوص في التنفيذ.

## كيفية إنشاء geojson من الإحداثيات وكتابته إلى تدفق؟
`VectorLayer` يمثل مجموعة بيانات متجهية في الذاكرة يمكن حفظها بصيغ مختلفة.  
`GeoJsonDriver` هو السائق الذي يتيح قراءة وكتابة ملفات GeoJSON.  

حمّل `VectorLayer` باستخدام `GeoJsonDriver`، أضف كائنات `Feature` التي تحتوي على هندسة `Point`، واستدعِ `layer.Save(stream, new GeoJsonSaveOptions())`. هذه الدعوة الواحدة تسلسل مجموعة الميزات بالكامل إلى مستند GeoJSON متوافق مع المعايير يُخزن في `MemoryStream` المقدم. العملية تتعامل تلقائيًا مع تعيين السمات وتحويل الإحداثيات، لذا ستحصل على حمولة JSON جاهزة للاستخدام دون بناء سلاسل يدويًا.

### مرساة التعريف
**VectorLayer** هو كائن Aspose.GIS الأساسي الذي يمثل مجموعة بيانات متجهية قابلة للتعديل في الذاكرة.  
**GeoJsonDriver** هو السائق المسؤول عن قراءة وكتابة ملفات GeoJSON.

## استيراد مساحات الأسماء
First things first, make sure to include the necessary namespaces to access the Aspose.GIS functionalities in your code:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## الخطوة 1: إعداد دليل المستند
Create a folder path where Aspose.GIS can store auxiliary files if required.  
```csharp
string dataDir = "Your Document Directory";
```
استبدل "Your Document Directory" بالمسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 2: إنشاء تدفق ذاكرة
`MemoryStream` يوفر مخزنًا في الذاكرة يمكن إرساله مباشرةً عبر HTTP أو حفظه في تخزين سحابي.  
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## الخطوة 3: إنشاء طبقة متجهية باستخدام محرك GeoJSON
فئة `VectorLayer` تمثل مجموعة بيانات متجهية يمكن حفظها بصيغ مختلفة، بما في ذلك GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## الخطوة 4: تعريف سمات الميزة
عرّف مخطط السمات لميزاتك (مثلًا، ID، Name).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## الخطوة 5: إنشاء وإضافة الميزات
أنشئ كائنات `Feature`، عيّن هندسة النقطة، اضبط قيم السمات، وأضفها إلى الطبقة.  
```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## الخطوة 6: عرض مخرجات GeoJSON
بعد الحفظ، أعد ضبط موضع التدفق واقرأ سلسلة JSON للتحقق أو الإرسال.  
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

تهانينا! لقد نجحت في إنشاء geojson من الإحداثيات وكتابته إلى تدفق باستخدام Aspose.GIS لـ .NET.

## المشكلات الشائعة والحلول
- **تدفق الإخراج فارغ:** تأكد من إعادة ضبط موضع التدفق (`stream.Position = 0`) قبل القراءة.
- **ترتيب إحداثيات غير صحيح:** GeoJSON يتوقع ترتيب خط الطول‑خط العرض؛ تحقق من قيم النقاط الخاصة بك.
- **مجموعات بيانات كبيرة:** استخدم `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` لتدفق الميزات بشكل تدريجي والحفاظ على انخفاض استهلاك الذاكرة.

## الأسئلة المتكررة
**س: هل يمكنني استخدام Aspose.GIS لـ .NET في بيئات Windows و Linux؟**  
ج: نعم، Aspose.GIS لـ .NET يعمل على Windows و Linux و macOS مع دعم كامل لـ .NET Core.

**س: هل يتوفر نسخة تجريبية مجانية؟**  
ج: بالتأكيد! يمكنك استكشاف **صفحة تنزيل النسخة التجريبية** [here](https://releases.aspose.com/).

**س: أين يمكنني العثور على الوثائق التفصيلية؟**  
ج: اطلع على **وثائق Aspose.GIS .NET** [here](https://reference.aspose.com/gis/net/).

**س: كيف يمكنني الحصول على ترخيص مؤقت؟**  
ج: التراخيص المؤقتة متاحة على **صفحة الترخيص المؤقت** [here](https://purchase.aspose.com/temporary-license/).

**س: هل تحتاج إلى مساعدة أو لديك أسئلة إضافية؟**  
ج: زر **منتدى دعم GIS** [here](https://forum.aspose.com/c/gis/33).

**س: هل يمكنني إنشاء GeoJSON من مجموعة نقاط خط العرض/خط الطول؟**  
ج: نعم – أنشئ `Feature` لكل نقطة، عيّن هندسة `Point`، وأضفه إلى `VectorLayer`.

**س: هل يدعم Aspose.GIS كتابة GeoJSON مضغوط (gzip)؟**  
ج: يمكنك تغليف `MemoryStream` داخل `GZipStream` قبل الحفظ لإنتاج حمولة مضغوطة.

**س: ما هو الحد الأقصى لحجم ملف GeoJSON الذي يمكن لـ Aspose.GIS التعامل معه؟**  
ج: يمكن للمكتبة تدفق ملفات تتجاوز 2 GB؛ يبقى استهلاك الذاكرة منخفضًا لأن البيانات تُكتب تدريجيًا.

---

**آخر تحديث:** 2026-10-15  
**تم الاختبار مع:** Aspose.GIS 24.11 لـ .NET  
**المؤلف:** Aspose  

## الدروس ذات الصلة
- [كيفية قراءة GeoJSON من تدفق باستخدام Aspose.GIS لـ .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [كيفية تحويل GeoJSON إلى TopoJSON باستخدام Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [كيفية تحويل Shapefile إلى GeoJSON باستخدام Aspose.GIS لـ .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}