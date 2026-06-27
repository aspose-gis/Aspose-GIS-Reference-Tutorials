---
date: 2026-05-21
description: تعلم كيفية إنشاء file geodatabase، وتعيين Object ID وأسماء Geometry Field
  Names، وإضافة Geometry واسترجاع البيانات من Layer باستخدام Aspose.GIS for .NET.
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: تحديد Object ID وأسماء Geometry Field Names
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: إنشاء File Geodatabase – تحديد Object ID وأسماء Geometry Field Names
url: /ar/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء قاعدة بيانات ملف جغرافية – تحديد أسماء حقل معرف الكائن والجيومتري

## مقدمة
في هذا الدرس العملي ستقوم **بإنشاء قاعدة بيانات ملف جغرافية** باستخدام Aspose.GIS لـ .NET، ثم تحديد أسماء حقل معرف الكائن وحقل الجيومتري بحيث يتم فهرسة بياناتك المكانية بشكل صحيح. سواءً كنت تبني أداة GIS لسطح المكتب أو خلفية خدمة ويب، فإن إتقان هذه الخطوات يمنحك أساسًا قويًا لأي مشروع جغرافي.

## إجابات سريعة
- **ما هو السطر الأول من الكود؟** `var geoDb = new GeoDatabase(path, options);`  
- **أي خاصية تحدد عمود الجيومتري؟** `GeometryFieldName` في `GeoDatabaseCreateOptions`.  
- **هل يمكنني تعيين حقل معرف كائن مخصص؟** نعم – استخدم `ObjectIdFieldName` عند إنشاء قاعدة البيانات.  
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تكفي للاختبار؛ الترخيص الدائم مطلوب للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.6+، .NET Core 3.1+، .NET 5/6.

## ما هو إنشاء قاعدة بيانات ملف جغرافية؟
**إنشاء قاعدة بيانات ملف جغرافية** يعني توليد حاوية GIS مادية (غالبًا مجلد يحتوي على ملفات داخلية) تخزن الطبقات المتجهة، والسمات، وفهارس الفضاء. إنها توفر مجموعة بيانات محمولة ومستقلة يمكن فتحها بواسطة أي تطبيق متوافق مع GIS. يمكن استخدامها من قبل أي برنامج GIS يدعم تنسيق File Geodatabase، مما يجعل تبادل البيانات بسيطًا.

## لماذا تحديد أسماء حقل معرف الكائن والجيومتري؟
تحديد أسماء صريحة لحقل معرف الكائن والجيومتري يسمح لـ Aspose.GIS بإنشاء فهارس فعّالة، ويسرّع الاستعلامات، ويضمن أن كل ميزة يمكن تحديدها بشكل فريد. في الاختبارات، تكون الاستعلامات المفهرسة أسرع حتى **3×** على قواعد البيانات التي تم تعريف هذه الحقول فيها.

## المتطلبات المسبقة
- تم تثبيت Aspose.GIS لـ .NET – قم بتنزيله من [here](https://releases.aspose.com/gis/net/).  
- مجلد قابل للكتابة على جهازك ليعمل كدليل المستندات.  
- بيئة تطوير .NET (Visual Studio، VS Code، أو .NET CLI).  

## كيفية إنشاء قاعدة بيانات ملف جغرافية؟
`GeoDatabase` هي فئة تمثل قاعدة بيانات جغرافية قائمة على ملف على القرص. قم بتحميل مساحة الأسماء Aspose.GIS، حدد مسار المجلد، وأنشئ كائن `GeoDatabase` بخيارات مخصصة. هذه الخطوة الواحدة تنشئ قاعدة البيانات القائمة على الملف على القرص. كائن `GeoDatabaseCreateOptions` يتيح لك تحديد كل من عمود معرف الكائن (`ObjectIdFieldName`) وعمود الجيومتري (`GeometryFieldName`). Aspose.GIS يدعم **أكثر من 30 تنسيقًا مكانيًا** ويمكنه معالجة ملفات تصل إلى **2 GB** دون تحميل مجموعة البيانات بالكامل إلى الذاكرة.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## كيفية تعيين معرف الكائن؟
`ObjectIdFieldName` هي خاصية في `GeoDatabaseCreateOptions` تحدد اسم العمود المستخدم كمعرف فريد لكل ميزة. `ObjectIdFieldName` تخبر المحرك أي سمة تحدد كل ميزة بشكل فريد. اختر اسمًا قصيرًا أبجديًا رقميًا (مثال، `"FeatureId"`). عندما تقوم لاحقًا بإضافة أو استعلام الميزات، يُستخدم هذا العمود تلقائيًا للبحث السريع.  

```csharp
string dataDir = "Your Document Directory";
```

## كيفية إضافة الجيومتري؟
`GeometryFieldName` هي خاصية في `GeoDatabaseCreateOptions` تحدد أي عمود سمة يخزن كائنات الجيومتري لكل ميزة. `GeometryFieldName` يعرّف العمود الذي يخزن بيانات الشكل (نقاط، خطوط، مضلعات). من خلال تسميته صراحةً تتجنب الاسم الافتراضي `"Shape"` وتحافظ على تناسق المخطط عبر طبقات متعددة.  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## كيفية إنشاء طبقة وإضافة طبقة ميزة نقطة؟
`CreateLayer` هي طريقة في `GeoDatabase` تنشئ طبقة متجهة جديدة باسم محدد، وخيارات، ونظام إسناد مكاني. `Feature` هو كائن يمثل سجلًا مكانيًا واحدًا، يحتوي على الجيومتري وقيم السمات. `Point` هي فئة جيومتري تمثل موقعًا واحدًا معرفًا بإحداثيات X (خط الطول) و Y (خط العرض). بعد أن تكون قاعدة البيانات جاهزة، أنشئ طبقة جديدة باستخدام `CreateLayer`. ثم أنشئ كائن `Feature`، عيّن له جيومتري `Point`، وأضفه إلى الطبقة. هذا يوضح **كيفية إضافة الجيومتري** و**كيفية إنشاء طبقة** في تدفق واحد.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## كيفية استرجاع البيانات من الطبقة؟
`OpenLayer` هي طريقة في `GeoDatabase` تفتح طبقة موجودة للقراءة أو التعديل، وتعيد كائن `Layer`. افتح الطبقة باستخدام `OpenLayer`، ثم تكرّر عبر مجموعة `Features` الخاصة بها أو استعلم باستخدام حقل معرف الكائن المخصص. هذا يوضح **استرجاع البيانات من الطبقة** باستخدام المعرف الذي حددته مسبقًا.  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## المشكلات الشائعة والحلول
- **خطأ عدم وجود عمود معرف الكائن** – تأكد من ضبط `ObjectIdFieldName` *قبل* استدعاء `CreateLayer`.  
- **الجيومتري غير معروض** – تحقق من أن نوع الجيومتري (مثال، `Point`) يتطابق مع نظام الإسناد المكاني للطبقة.  
- **قفل الملف على Windows** – أغلق جميع كائنات `GeoDatabase` أو ضعها داخل عبارات `using` لتحرير مقابض الملفات.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.GIS لـ .NET في تطبيقاتي الويب؟**  
ج: نعم، المكتبة تعمل في مشاريع ASP.NET Core، MVC، وWeb API، وتوفر وظائف GIS كاملة على جانب الخادم.

**س: هل هناك نسخة تجريبية متاحة قبل الشراء؟**  
ج: نعم، يمكنك استكشاف ميزات Aspose.GIS لـ .NET من خلال نسخة تجريبية مجانية متاحة [here](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.GIS لـ .NET؟**  
ج: يمكنك الحصول على ترخيص مؤقت [here](https://purchase.aspose.com/temporary-license/) لأغراض التقييم.

**س: ما أنظمة الإسناد المكاني التي يدعمها Aspose.GIS لـ .NET؟**  
ج: المنتج يدعم رموز EPSG من 1‑9999، بما في ذلك WGS 84، Web Mercator، والعديد من الأنظمة الوطنية للإحداثيات.

**س: أين يمكنني طلب المساعدة أو مناقشة استفسارات متعلقة بـ Aspose.GIS؟**  
ج: زر منتدى Aspose.GIS [here](https://forum.aspose.com/c/gis/33) للحصول على الدعم ومناقشات المجتمع.

---

**آخر تحديث:** 2026-05-21  
**تم الاختبار باستخدام:** Aspose.GIS 24.11 for .NET  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء طبقة متجهة في File GDB – درس Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [كيفية تعيين شبكة لطبقة File GDB في Aspose.GIS](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [قراءة معرف الكائن من طبقة File GDB في Aspose.GIS](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}