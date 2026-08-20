---
date: 2026-06-30
description: تعلم كيفية إنشاء shapefile باستخدام Aspose.GIS for .NET. يوضح لك هذا
  الدليل خطوة بخطوة كيفية تعريف طبقة Vector layer، إضافة خاصية date attribute، وإدارة
  البيانات spatial data بكفاءة.
keywords:
- how to create shapefile
- temporal gis shapefile
- Aspose.GIS vector layer
- GIS data automation
linktitle: إنشاء Shapefile جديد
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create shapefile using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to define a vector layer, add a date attribute, and manage
    spatial data efficiently.
  headline: How to Create Shapefile with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS primarily supports .NET, but there are versions available for
      Java as well.
    question: Can I use Aspose.GIS with other programming languages?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I find support for Aspose.GIS?
  - answer: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license?
  - answer: You can buy the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: كيفية إنشاء Shapefile باستخدام Aspose.GIS for .NET
url: /ar/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء ملف Shapefile جديد

## مقدمة
إذا كنت تتعمق في تطوير نظم المعلومات الجغرافية (GIS) باستخدام .NET، فإن Aspose.GIS هو الحل المثالي لك **كيفية إنشاء shapefile** برمجيًا. توفر لك هذه المكتبة تحكمًا كاملاً في الطبقات المتجهة، مخططات السمات، والامتثال لتنسيق الملفات، بحيث يمكنك أتمتة خطوط البيانات أو إنشاء مجموعات بيانات اختبارية في دقائق.

## إجابات سريعة
- **ما الذي يدرسه هذا الدرس؟** كيفية إنشاء ملف shapefile جديد، تعريف طبقة متجهة، وإضافة السمات (بما في ذلك حقل تاريخ).  
- **ما المكتبة المطلوبة؟** Aspose.GIS لـ .NET.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتعلم؛ يتطلب الترخيص التجاري للإنتاج.  
- **ما بيئة التطوير المتكاملة التي يجب أن أستخدمها؟** Visual Studio (أي نسخة حديثة).  
- **كم من الوقت تستغرق العملية؟** حوالي 10‑15 دقيقة للمثال الأساسي.

## كيفية إنشاء ملف shapefile باستخدام Aspose.GIS لـ .NET؟
قم بتحميل مكتبة Aspose.GIS، حدد مجلد الإخراج، أنشئ `VectorLayer`، عرّف السمات، وأضف الميزات—يمكن كتابة سير العمل بالكامل بأقل من 30 سطرًا من C#. تتولى المكتبة إنشاء الهندسة، تحديد نوع السمات، وكتابة الملف تلقائيًا، لذا لا تحتاج إلى إدارة مواصفات Shapefile منخفضة المستوى بنفسك.

## المتطلبات المسبقة
قبل أن نبدأ الدرس، تأكد من توفر المتطلبات التالية:
- فهم أساسي للغة برمجة C#.
- تثبيت Visual Studio على جهازك.
- مكتبة Aspose.GIS لـ .NET. يمكنك تنزيلها [هنا](https://releases.aspose.com/gis/net/).

## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية للاستفادة من وظائف Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## الخطوة 1: إعداد مشروعك
ابدأ بإنشاء مشروع C# جديد في Visual Studio وتضمين مكتبة Aspose.GIS.

## الخطوة 2: تعريف دليل المستند
```csharp
string dataDir = "Your Document Directory";
```
استبدل *Your Document Directory* بالمسار الفعلي حيث تريد حفظ ملف shapefile الجديد.

## الخطوة 3: إنشاء VectorLayer
تمثل فئة `VectorLayer` طبقة shapefile واحدة تخزن بيانات الهندسة والسمات.  
في هذه الخطوة نُعرّف طبقة متجهة ونعلن عن ثلاث سمات: حقل نصي (`name`)، حقل عدد صحيح (`age`)، وحقل تاريخ‑وقت (`dob`). إضافة سمة التاريخ أمر حاسم لتحليلات **shapefile GIS الزمني**.

```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

## الخطوة 4: إضافة الميزات
### الحالة 1: تعيين القيم بشكل فردي
طريقة `SetValues` تُعيّن قيم السمات لميزة وفقًا للترتيب الذي تم تعريفها به.  
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
هنا ننشئ نقطتين، نعيّن كل سمة على حدة، ونضيف الميزات إلى الطبقة.

### الحالة 2: تعيين قيم جديدة لجميع السمات
بدلاً من ذلك، يمكنك توفير جميع قيم السمات مرة واحدة باستخدام `SetValues` مع مصفوفة كائنات.  
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
في هذا النهج نملأ جميع قيم السمات في استدعاء واحد باستخدام مصفوفة كائنات—مفيد عندما يكون لديك العديد من السمات.

## لماذا هذا مهم؟
إنشاء ملف shapefile برمجيًا يتيح لك أتمتة خطوط البيانات، إنشاء مجموعات بيانات اختبارية، أو دمج مخرجات GIS مباشرةً في خدمات الويب. تدعم Aspose.GIS **أكثر من 30 تنسيقًا متجهًا ورستريًا** ويمكنها كتابة ملفات shapefile مئات الصفحات دون تحميل الملف بالكامل في الذاكرة، مما يوفر السرعة والقابلية للتوسع.

## الأخطاء الشائعة والنصائح
- **فواصل المسارات:** استخدم `Path.Combine` لتوافق عبر الأنظمة بدلاً من دمج السلاسل.  
- **ترتيب السمات:** يجب أن يتطابق ترتيب القيم في `SetValues` مع الترتيب الذي أضفت به السمات.  
- **معالجة التاريخ:** استخدم دائمًا `DateTimeKind.Utc` إذا كانت بيانات GIS ستُشارك عبر مناطق زمنية.

## الخاتمة
تهانينا! لقد نجحت في إنشاء ملف shapefile جديد باستخدام Aspose.GIS لـ .NET. يغطي هذا الدرس الأساسيات لتكوين مشروعك، تعريف طبقة متجهة، وإضافة الميزات—بما في ذلك سمة التاريخ. أثناء استكشافك المزيد، راجع [التوثيق](https://reference.aspose.com/gis/net/) للحصول على ميزات ووظائف متقدمة.

## الأسئلة المتكررة
**س: هل يمكنني استخدام Aspose.GIS مع لغات برمجة أخرى؟**  
ج: يدعم Aspose.GIS أساسًا .NET، ولكن هناك إصدارات متاحة لـ Java أيضًا.  

**س: هل هناك نسخة تجريبية مجانية متاحة؟**  
ج: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).  

**س: أين يمكنني العثور على دعم Aspose.GIS؟**  
ج: زر [منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33) للحصول على دعم المجتمع والنقاشات.  

**س: كيف يمكنني الحصول على ترخيص مؤقت؟**  
ج: احصل على ترخيصك المؤقت [هنا](https://purchase.aspose.com/temporary-license/).  

**س: أين يمكنني شراء Aspose.GIS لـ .NET؟**  
ج: يمكنك شراء المكتبة [هنا](https://purchase.aspose.com/buy).

**آخر تحديث:** 2026-06-30  
**تم الاختبار مع:** Aspose.GIS 24.11 لـ .NET  
**المؤلف:** Aspose

## دروس ذات صلة

- [الحصول على سمات الطبقة – استرجاع معلومات سمات الطبقة باستخدام Aspose.GIS لـ .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [إنشاء طبقة متجهة وتعيين نظام الإسناد المكاني للطبقة](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [إنشاء طبقة متجهة في File GDB – درس Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}