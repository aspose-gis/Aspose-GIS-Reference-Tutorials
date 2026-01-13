---
date: 2026-01-13
description: تعلم كيفية إنشاء ملف shapefile جديد باستخدام Aspose.GIS لـ .NET. يوضح
  لك هذا الدليل خطوة بخطوة كيفية تعريف طبقة متجهة، وإضافة سمة تاريخ، وإدارة البيانات
  المكانية.
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: إنشاء ملف شكل جديد
url: /ar/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء Shapefile جديد

## المقدمة
إذا كنت تتعمق في تطوير نظم المعلومات الجغرافية (GIS) باستخدام .NET، فإن Aspose.GIS هو الحل المثالي لك. تتيح هذه المكتبة القوية للمطورين العمل بسلاسة مع البيانات المكانية، وفي هذا البرنامج التعليمي، سنرشدك إلى كيفية **إنشاء shapefile جديد** باستخدام Aspose.GIS لـ .NET. ستتعرف على سبب أهمية تعريف طبقة متجهة وإضافة سمة تاريخ كخطوات أساسية لمشاريع GIS قوية.

## إجابات سريعة
- **ماذا يعلمك هذا البرنامج التعليمي؟** كيفية إنشاء shapefile جديد، تعريف طبقة متجهة، وإضافة السمات (بما في ذلك حقل التاريخ).  
- **ما المكتبة المطلوبة؟** Aspose.GIS لـ .NET.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتعلم؛ يلزم ترخيص تجاري للإنتاج.  
- **ما بيئة التطوير المتكاملة التي يجب استخدامها؟** Visual Studio (أي نسخة حديثة).  
- **كم من الوقت تستغرق العملية؟** حوالي 10‑15 دقيقة للمثال الأساسي.

## المتطلبات المسبقة
قبل أن نبدأ البرنامج التعليمي، تأكد من توفر المتطلبات التالية:
- فهم أساسي للغة البرمجة C#.
- تثبيت Visual Studio على جهازك.
- مكتبة Aspose.GIS لـ .NET. يمكنك تنزيلها [هنا](https://releases.aspose.com/gis/net/).

## استيراد المساحات الاسمية
ابدأ باستيراد المساحات الاسمية الضرورية للاستفادة من وظائف Aspose.GIS:

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

## الخطوة 2: تعريف دليل المستندات
```csharp
string dataDir = "Your Document Directory";
```
استبدل *Your Document Directory* بالمسار الفعلي حيث تريد حفظ الـ shapefile الجديد.

## الخطوة 3: إنشاء VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
هذا الجزء من الكود **يعرف طبقة متجهة** ويعلن عن ثلاث سمات: حقل نصي (`name`)، حقل عدد صحيح (`age`)، وحقل تاريخ‑وقت (`dob`). إضافة سمة التاريخ أمر حاسم للتحليلات الزمنية في GIS.

## الخطوة 4: إضافة الميزات
### الحالة 1: تعيين القيم بشكل فردي
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
هنا نقوم بإنشاء نقطتين، تعيين كل سمة على حدة، وإضافة الميزات إلى الطبقة.

### الحالة 2: تعيين قيم جديدة لجميع السمات
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
في هذا النهج نقوم بملء جميع قيم السمات في استدعاء واحد باستخدام مصفوفة كائنات—مفيد عندما يكون لديك العديد من السمات.

## لماذا هذا مهم
إنشاء shapefile برمجياً يتيح لك أتمتة خطوط البيانات، إنشاء مجموعات بيانات اختبارية، أو دمج مخرجات GIS مباشرةً في خدمات الويب. من خلال إتقان **كيفية إنشاء shapefile** باستخدام Aspose.GIS، ستحصل على تحكم كامل في هندسة الميزة، مخطط السمات، والامتثال لتنسيق الملف.

## الأخطاء الشائعة والنصائح
- **فواصل المسار:** استخدم `Path.Combine` لتوافق عبر الأنظمة بدلاً من دمج السلاسل.  
- **ترتيب السمات:** يجب أن يتطابق ترتيب القيم في `SetValues` مع ترتيب السمات التي أضفتها.  
- **معالجة التاريخ:** استخدم دائمًا `DateTimeKind.Utc` إذا كانت بيانات GIS ستُشارك عبر مناطق زمنية.

## الخلاصة
تهانينا! لقد نجحت في إنشاء shapefile جديد باستخدام Aspose.GIS لـ .NET. غطى هذا البرنامج التعليمي الأساسيات المتعلقة بإعداد مشروعك، تعريف طبقة متجهة، وإضافة الميزات—بما في ذلك سمة التاريخ. أثناء استكشافك للمزيد، راجع [التوثيق](https://reference.aspose.com/gis/net/) للحصول على ميزات ووظائف متقدمة.

## الأسئلة المتكررة
### س: هل يمكنني استخدام Aspose.GIS مع لغات برمجة أخرى؟
يدعم Aspose.GIS أساسًا .NET، ولكن هناك إصدارات متاحة لـ Java أيضًا.  

### س: هل تتوفر نسخة تجريبية مجانية؟
نعم، يمكنك الوصول إلى النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).  

### س: أين يمكنني العثور على دعم Aspose.GIS؟
قم بزيارة [منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33) للحصول على دعم المجتمع والنقاشات.  

### س: كيف يمكنني الحصول على ترخيص مؤقت؟
احصل على ترخيصك المؤقت [هنا](https://purchase.aspose.com/temporary-license/).  

### س: أين يمكنني شراء Aspose.GIS لـ .NET؟
يمكنك شراء المكتبة [هنا](https://purchase.aspose.com/buy).

---

**آخر تحديث:** 2026-01-13  
**تم الاختبار مع:** Aspose.GIS 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}