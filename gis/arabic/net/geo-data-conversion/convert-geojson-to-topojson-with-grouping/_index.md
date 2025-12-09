---
date: 2025-12-06
description: تعلم كيفية تحويل GeoJSON إلى TopoJSON مع التجميع، وتعيين خاصية اسم الكائن،
  وتجميع ميزات GeoJSON باستخدام Aspose.GIS لـ .NET.
linktitle: How to Convert GeoJSON to TopoJSON with Grouping using Aspose.GIS
second_title: Aspose.GIS .NET API
title: كيفية تحويل GeoJSON إلى TopoJSON مع التجميع باستخدام Aspose.GIS
url: /ar/net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تحويل GeoJSON إلى TopoJSON مع التجميع باستخدام Aspose.GIS

## المقدمة

في هذا الدليل خطوة بخطوة ستتعلم **كيفية تحويل ملفات GeoJSON** إلى TopoJSON مع تجميع العناصر بناءً على سمة مختارة. استخدام Aspose.GIS .NET API يجعل التحويل سريعًا، موثوقًا، وقابلاً للتحكم بالكامل من خلال كود C# الخاص بك. سواءً كنت تبني خدمة تحويل GeoJSON في ASP.NET أو أداة GIS سطح مكتب، يوضح لك هذا الدليل ما تحتاج إلى القيام به بالضبط.

## إجابات سريعة
- **ما المكتبة التي تتعامل مع التحويل؟** Aspose.GIS for .NET  
- **كم من الوقت تستغرق عملية التنفيذ؟** عادةً 5‑10 دقائق لإعداد أساسي  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، يلزم الحصول على ترخيص تجاري (يتوفر تجربة مجانية)  
- **هل يمكنني تجميع العناصر حسب أي سمة؟** نعم – قم بتعيين `ObjectNameAttribute` إلى الحقل الذي تريد التجميع بناءً عليه  
- **هل .NET Core مدعوم؟** بالتأكيد – تعمل الواجهة البرمجية مع .NET Core، .NET 5/6، وإطار .NET الكلاسيكي  

## ما هو GeoJSON وTopoJSON؟

GeoJSON هو تنسيق JSON شائع الاستخدام لتشفير الميزات الجغرافية مثل النقاط، الخطوط، والمضلعات. TopoJSON يوسع GeoJSON عن طريق تخزين الطوبولوجيا (القطاعات الخطية المشتركة) مما يقلل حجم الملف ويحسن أداء العرض للخرائط المعقدة. التحويل بينهما خطوة شائعة عندما تحتاج إلى بيانات خريطة مضغوطة لتصوير الويب.

## لماذا نجمع ميزات GeoJSON؟

تجميع (`group geojson features`) يتيح لك تنظيم الهندسات المرتبطة تحت كائن مسمى واحد في TopoJSON الناتج. هذا مفيد خصوصًا عندما:
- تريد إنشاء طبقات منفصلة لمناطق إدارية مختلفة.  
- مكتبة الخرائط في الواجهة الأمامية تتوقع كائنات مسماة للتنسيق أو التفاعل.  
- تحتاج إلى تقليل التكرار عبر مشاركة الحدود بين العناصر المتجاورة.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من توفر المتطلبات التالية:

1. **Aspose.GIS for .NET** – قم بتنزيله وتثبيته من الموقع الرسمي [هنا](https://releases.aspose.com/gis/net/).  
2. **بيئة التطوير** – Visual Studio، Visual Studio Code، أو أي IDE يدعم C#.  
3. **ملف GeoJSON تجريبي** – ملف يحتوي على العناصر التي تريد تحويلها.  

## استيراد المساحات الاسمية

أولًا، أضف المساحات الاسمية الضرورية إلى مشروعك:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```

## دليل خطوة بخطوة

### الخطوة 1: تحديد مسارات الملفات

حدد مكان وجود ملف GeoJSON المصدر وأين يجب كتابة ملف TopoJSON الناتج:

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

> **نصيحة احترافية:** استخدم `Path.Combine` لبناء مسارات متوافقة عبر الأنظمة إذا كنت تستهدف .NET Core.

### الخطوة 2: تكوين خيارات التحويل (تعيين سمة اسم الكائن)

أنشئ كائن `ConversionOptions` وأخبر Aspose.GIS كيف يجمع العناصر:

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // Specify the attribute in GeoJSON layer by which we are going to group into objects
        ObjectNameAttribute = "group",
        // Specify the default object name for features with unknown attribute values
        DefaultObjectName = "unnamed",
    }
};
```

استبدل `"group"` باسم الخاصية الفعلي في ملف GeoJSON الذي تريد استخدامه لـ **تجميع ميزات geojson**. يضمن `DefaultObjectName` أن كل عنصر ينتهي به المطاف في كائن TopoJSON، حتى إذا كانت السمة مفقودة.

### الخطوة 3: تنفيذ التحويل (تحويل GeoJSON إلى TopoJSON)

نفّذ التحويل باستدعاء API واحد:

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

بعد التنفيذ، سيحتوي `convertedSampleWithGrouping_out.topojson` على تمثيل TopoJSON، مع تجميع العناصر وفق السمة التي حددتها.

## المشكلات الشائعة واستكشاف الأخطاء وإصلاحها

| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| **جميع العناصر تنتهي في “unnamed”** | `ObjectNameAttribute` لا يتطابق مع أي خاصية في GeoJSON | تحقق من اسم الخاصية بدقة (حسّاس لحالة الأحرف) وقم بتحديث الخيار |
| **ملف الإخراج فارغ** | مسار ملف غير صحيح أو نقص في أذونات القراءة | استخدم مسارات مطلقة أو تأكد من أن التطبيق يملك صلاحية الوصول إلى نظام الملفات |
| **التحويل يطرح استثناء `NotSupportedException`** | محاولة تحويل GeoJSON يحتوي على أنواع هندسة غير مدعومة (مثل GeometryCollection) | بسط البيانات المصدر أو حدّث إلى أحدث إصدار من Aspose.GIS |

## الأسئلة المتكررة

**س: هل يمكنني تجميع العناصر بناءً على عدة سمات؟**  
ج: نعم، يمكنك دمج عدة حقول في سمة افتراضية واحدة أو إجراء عدة عمليات تحويل باستخدام قيم مختلفة لـ `ObjectNameAttribute`.

**س: هل Aspose.GIS متوافق مع ASP.NET Core؟**  
ج: بالتأكيد – المكتبة تعمل مع ASP.NET Core، .NET 5، .NET 6، وإطار .NET الكلاسيكي.

**س: هل يمكنني تحويل صيغ جغرافية أخرى غير GeoJSON؟**  
ج: نعم، يدعم Aspose.GIS Shapefile، KML، GML، CSV، والعديد من الصيغ الأخرى للاستيراد والتصدير.

**س: هل يقدم Aspose.GIS تجربة مجانية؟**  
ج: نعم، يمكنك الحصول على تجربة مجانية من Aspose.GIS عبر [هنا](https://releases.aspose.com/).

**س: أين يمكنني الحصول على دعم لـ Aspose.GIS؟**  
ج: يمكنك الحصول على الدعم من منتدى مجتمع Aspose.GIS عبر [هنا](https://forum.aspose.com/c/gis/33).

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**آخر تحديث:** 2025-12-06  
**تم الاختبار مع:** Aspose.GIS for .NET (أحدث إصدار)  
**المؤلف:** Aspose  

---