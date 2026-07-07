---
date: 2026-05-21
description: تعلم كيفية كتابة GeoJSON إلى تدفق باستخدام Aspose.GIS لـ .NET. يوضح هذا
  البرنامج التعليمي لـ geojson .net خطوة بخطوة تحويل النقاط وإنشاء كود GeoJSON بلغة
  C#.
keywords:
- how to write geojson
- convert points geojson
- geojson tutorial .net
- generate geojson c#
linktitle: اكتب GeoJSON إلى تدفق
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to write GeoJSON to stream using Aspose.GIS for .NET. This
    geojson tutorial .net shows step‑by‑step conversion of points and generation of
    GeoJSON C# code.
  headline: How to Write GeoJSON to Stream with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: كيفية كتابة GeoJSON إلى تدفق باستخدام Aspose.GIS لـ .NET
url: /ar/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كتابة GeoJSON إلى Stream

## مقدمة
في هذا الدرس ستتعلم **كيفية كتابة GeoJSON إلى تدفق** في تطبيق .NET باستخدام Aspose.GIS. سنستعرض كل خطوة، بدءًا من إعداد البيئة إلى إخراج مستند GeoJSON صالح، حتى تتمكن من دمج البيانات الجغرافية بسهولة في خدماتك.

## إجابات سريعة
- **ما هو الصنف الأساسي لإخراج GeoJSON؟** `VectorLayer` مع `GeoJsonDriver`.
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.
- **هل يمكنني تحويل مجموعات النقاط إلى GeoJSON؟** نعم – استخدم الصنف `Feature` وحدد هندسة النقطة.
- **هل يدعم البث للبيانات الكبيرة؟** بالتأكيد؛ `MemoryStream` يتيح لك الكتابة دون ملفات وسيطة.

## ما هو GeoJSON؟
GeoJSON هو تنسيق معيار مفتوح لتشفير مجموعة متنوعة من هياكل البيانات الجغرافية باستخدام JSON. يعرّف كائنات مثل FeatureCollection و Feature وأنواع الهندسة (Point، LineString، Polygon). هذا التمثيل الخفيف والصديق للويب يتيح تبادلًا سهلًا وتصورًا للبيانات المكانية عبر العديد من المنصات ولغات البرمجة.

## لماذا تستخدم Aspose.GIS لإنشاء GeoJSON؟
يدعم Aspose.GIS أكثر من 30 تنسيق ملف مكاني ويمكنه معالجة ملفات أكبر من 2 GB دون تحميل المستند بالكامل في الذاكرة. محرك البث عالي الأداء يكتب GeoJSON مباشرة إلى التدفقات، مما يقلل من عبء الإدخال/الإخراج. هذا يجعله مثاليًا لأعباء العمل الجغرافية على مستوى المؤسسات، وخدمات السحابة، والتطبيقات في الوقت الحقيقي.

## المتطلبات المسبقة
قبل أن نبدأ في الدرس، تأكد من توفر المتطلبات التالية:
1. مكتبة Aspose.GIS لـ .NET: تأكد من تثبيت مكتبة Aspose.GIS لـ .NET. يمكنك تنزيلها [هنا](https://releases.aspose.com/gis/net/).
2. دليل المستندات: أنشئ دليل مستندات في مشروعك، وسجل مساره.

الآن، لنبدأ الدرس!

## كيف أكتب GeoJSON إلى تدفق؟
VectorLayer يمثل مجموعة بيانات متجهة يمكن حفظها بصيغ متعددة، بما في ذلك GeoJSON.  
GeoJsonDriver هو السائق الذي يستخدمه Aspose.GIS لقراءة وكتابة ملفات GeoJSON.  
`layer.Save` يكتب محتوى الطبقة إلى التدفق المقدم باستخدام خيارات الحفظ المحددة.

حمّل `VectorLayer` باستخدام `GeoJsonDriver`، أضف ميزات تحتوي على هندسة نقطة، ثم استدعِ `layer.Save(stream, new GeoJsonSaveOptions())`. هذا يكتب مستند GeoJSON كامل ومتوافق مع المعايير مباشرةً في `MemoryStream` المقدم في بضع أسطر من الشيفرة فقط. تقوم الطريقة بتسلسل مجموعة الميزات، مع معالجة بيانات السمات وتحويل الهندسة تلقائيًا، بحيث تحصل على حمولة JSON جاهزة للاستخدام دون الحاجة إلى تعديل السلاسل يدويًا.

## استيراد المساحات الاسمية
أولًا، تأكد من تضمين المساحات الاسمية اللازمة للوصول إلى وظائف Aspose.GIS في الشيفرة الخاصة بك:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## الخطوة 1: إعداد دليل المستندات
```csharp
string dataDir = "Your Document Directory";
```
استبدل "Your Document Directory" بالمسار الفعلي لدليل المستندات الخاص بك.

## الخطوة 2: إنشاء Memory Stream
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## الخطوة 3: إنشاء طبقة VectorLayer باستخدام GeoJSON Driver
The `VectorLayer` class represents a vector dataset that can be saved in various formats, including GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## الخطوة 4: تعريف سمات الميزة
Define the attribute schema for your features (e.g., ID, Name).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## الخطوة 5: إنشاء وإضافة الميزات
Create `Feature` objects, assign point geometry, set attribute values, and add them to the layer.  
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
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

تهانينا! لقد نجحت في كتابة GeoJSON إلى تدفق باستخدام Aspose.GIS لـ .NET.

## المشكلات الشائعة والحلول
- **تدفق الإخراج فارغ:** تأكد من إعادة تعيين موضع التدفق (`stream.Position = 0`) قبل القراءة.
- **ترتيب الإحداثيات غير صحيح:** GeoJSON يتوقع ترتيب خط الطول‑خط العرض؛ تحقق من قيم النقاط الخاصة بك.
- **مجموعات بيانات كبيرة:** استخدم `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` لبث الميزات تدريجيًا.

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.GIS لـ .NET في بيئات Windows و Linux؟
نعم، Aspose.GIS لـ .NET متوافق مع أنظمة Windows و Linux.

### هل هناك نسخة تجريبية مجانية متاحة؟
بالطبع! يمكنك استكشاف نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

### أين يمكنني العثور على الوثائق التفصيلية؟
اطلع على الوثائق [هنا](https://reference.aspose.com/gis/net/).

### كيف يمكنني الحصول على ترخيص مؤقت؟
التراخيص المؤقتة متاحة [هنا](https://purchase.aspose.com/temporary-license/).

### هل تحتاج إلى مساعدة أو لديك أسئلة إضافية؟
قم بزيارة منتدى الدعم الخاص بنا [هنا](https://forum.aspose.com/c/gis/33).

**س: هل يمكنني إنشاء GeoJSON من مجموعة نقاط خط العرض/خط الطول؟**  
**ج:** نعم – أنشئ `Feature` لكل نقطة، عيّن هندسة `Point`، وأضفه إلى `VectorLayer`.

**س: هل يدعم Aspose.GIS كتابة GeoJSON مضغوط (gzip)؟**  
**ج:** يمكنك تغليف `MemoryStream` داخل `GZipStream` قبل الحفظ لإنتاج حمولة مضغوطة.

**س: ما هو الحد الأقصى لحجم ملف GeoJSON الذي يمكن لـ Aspose.GIS التعامل معه؟**  
**ج:** يمكن للمكتبة بث ملفات تتجاوز 2 GB؛ يبقى استهلاك الذاكرة منخفضًا لأن البيانات تُكتب تدريجيًا.

---

**آخر تحديث:** 2026-05-21  
**تم الاختبار مع:** Aspose.GIS 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [كيفية قراءة GeoJSON من تدفق باستخدام Aspose.GIS لـ .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [كيفية تحويل GeoJSON إلى TopoJSON باستخدام Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [كيفية تحويل Shapefile إلى GeoJSON باستخدام Aspose.GIS لـ .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}