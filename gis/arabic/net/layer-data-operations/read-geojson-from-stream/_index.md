---
date: 2025-12-28
description: تعلم كيفية قراءة GeoJSON من تدفق باستخدام Aspose.GIS لـ .NET. يقدم هذا
  الدليل لقراءة GeoJSON بلغة C# مثالًا خطوة بخطوة لتكامل البيانات الجغرافية.
linktitle: Read GeoJSON from Stream
second_title: Aspose.GIS .NET API
title: كيفية قراءة GeoJSON من تدفق باستخدام Aspose.GIS لـ .NET
url: /ar/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية قراءة GeoJSON من تدفق باستخدام Aspose.GIS لـ .NET

## المقدمة
إذا كنت تتساءل **كيفية قراءة geojson** في تطبيق .NET، فقد وجدت المكان المناسب. في هذا الدرس سنستعرض مثالًا كاملًا **c# geojson example** يوضح كيفية تحويل سلسلة GeoJSON، فتح طبقة GeoJSON من تدفق الذاكرة، واستخراج خصائص GeoJSON باستخدام Aspose.GIS. في النهاية ستحصل على نمط قابل لإعادة الاستخدام يمكنك إدراجه في أي مشروع يحتاج إلى التعامل مع البيانات الجغرافية.

## إجابات سريعة
- **ما المكتبة التي يجب أن أستخدمها؟** Aspose.GIS for .NET  
- **هل يمكنني قراءة GeoJSON مباشرةً من تدفق؟** نعم – استخدم `VectorLayer.Open` مع `AbstractPath.FromStream`.  
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تكفي للاختبار؛ الترخيص مطلوب للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **هل استخراج الخصائص بسيط؟** نعم – استدعِ `GetValue<T>(columnName)` على العنصر.

## ما هو “كيفية قراءة geojson”؟
قراءة GeoJSON تعني تحليل التنسيق القائم على JSON الذي يصف الميزات الجغرافية (نقاط، خطوط، مضلعات) وجعل هذه الميزات متاحة ككائنات يمكنك الاستعلام عنها، تعديلها، أو عرضها في تطبيقك.

## لماذا تستخدم Aspose.GIS **لفتح طبقة geojson**؟
Aspose.GIS يخفف تفاصيل التحليل منخفضة المستوى ويقدم لك واجهة برمجة تطبيقات متسقة للعديد من صيغ GIS. يتيح لك **فتح طبقة geojson** مباشرةً من تدفق، معالجة ملفات كبيرة بكفاءة، والوصول إلى سمات العناصر دون الحاجة إلى كتابة محللات JSON مخصصة.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من أن لديك:

1. **معرفة أساسية بـ C#** – يجب أن تكون مرتاحًا مع صsyntax .NET وبيئة Visual Studio.  
2. **تثبيت Aspose.GIS** – حمّل المكتبة من [here](https://releases.aspose.com/gis/net/).  
3. **بيئة تطوير** – Visual Studio، Visual Studio Code، أو JetBrains Rider ستعمل بشكل جيد.  

## استيراد المساحات الاسمية
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## الخطوة 1: **تحويل سلسلة GeoJSON** – مثال **c# geojson**
أولاً نقوم بإنشاء سلسلة JSON تمثل `FeatureCollection` بسيطة. هذه هي خطوة **تحويل سلسلة GeoJSON** في سير العمل.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## الخطوة 2: **فتح طبقة GeoJSON** من تدفق و **استخراج خصائص geojson**
الآن نمرر السلسلة إلى `MemoryStream`، نفتحها كطبقة GIS، ونظهر كيفية قراءة قيم السمات (خطوة **استخراج خصائص geojson**).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **نصيحة احترافية:** `VectorLayer.Open` يكتشف تلقائيًا تنسيق GeoJSON عندما تمرر `Drivers.GeoJson`. يمكنك أيضًا فتح الملفات مباشرةً بتوفير مسار الملف بدلاً من التدفق.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **تنسيق JSON غير صالح** | تحقق من أن سلسلة GeoJSON مُشكَّلة بشكل صحيح؛ استخدم أداة تحقق من JSON. |
| **مشكلات الترميز** | تأكد من أن التدفق يستخدم UTF‑8 (`Encoding.UTF8.GetBytes`). |
| **خصائص مفقودة** | تحقق من كتابة اسم الخاصية بشكل صحيح (`"name"` في المثال). |
| **استثناء الترخيص** | استخدم ترخيص تجريبي للاختبار؛ طبّق ترخيص دائم للإنتاج. |

## الأسئلة المتكررة
### هل Aspose.GIS متوافق مع صيغ GIS أخرى؟
نعم، Aspose.GIS يدعم GeoJSON، Shapefile، KML، GML، والعديد من الصيغ الأخرى.

### هل يمكنني تجربة Aspose.GIS قبل الشراء؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.GIS من [here](https://releases.aspose.com/).

### أين يمكنني العثور على وثائق Aspose.GIS؟
يمكنك العثور على وثائق Aspose.GIS [here](https://reference.aspose.com/gis/net/).

### كيف يمكنني الحصول على دعم لـ Aspose.GIS؟
يمكنك الحصول على الدعم لـ Aspose.GIS عبر منتديات Aspose [here](https://forum.aspose.com/c/gis/33).

### هل أحتاج إلى ترخيص مؤقت لاستخدام Aspose.GIS؟
يمكنك الحصول على ترخيص مؤقت لـ Aspose.GIS من [here](https://purchase.aspose.com/temporary-license/).

## الخلاصة
في هذا الدليل غطينا **كيفية قراءة geojson** من تدفق الذاكرة باستخدام Aspose.GIS لـ .NET، عرضنا سير عمل **c# read geojson**، وأظهرنا كيفية **استخراج خصائص geojson** من الطبقة المفتوحة. باستخدام هذه الخطوات يمكنك دمج معالجة البيانات الجغرافية بسلاسة في أي تطبيق .NET.

---

**آخر تحديث:** 2025-12-28  
**تم الاختبار مع:** Aspose.GIS 24.11 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}