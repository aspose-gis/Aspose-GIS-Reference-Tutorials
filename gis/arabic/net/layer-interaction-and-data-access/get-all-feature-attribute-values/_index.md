---
date: 2026-01-05
description: تعلم كيفية قراءة ملف shapefile باستخدام C# و Aspose.GIS لـ .NET، واسترجاع
  جميع قيم سمات الكائنات، وتفريغ السمات بكفاءة.
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: قراءة ملف Shapefile C# – الحصول على جميع قيم سمات العنصر
url: /ar/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# احصل على جميع قيم سمات العنصر

## مقدمة
مرحبًا بك في عالم تطوير الجغرافيا المكانية مع Aspose.GIS لـ .NET! في هذا الدرس ستتعلم **كيفية قراءة shapefile باستخدام C#** واسترجاع كل قيمة سمة من عناصره. سواءً كنت تبني تطبيقًا للخرائط أو تعالج بيانات مكانية على دفعات، فإن إتقان استخراج السمات أمر أساسي. هيا نغوص في التفاصيل ونرى الكود يعمل.

## إجابات سريعة
- **ماذا يفعل هذا الكود؟** يفتح ملف Shapefile ويقرأ جميع القيم أو بعض القيم أو القيم المصدرة للسمات من كل عنصر.  
- **ما المكتبة المطلوبة؟** Aspose.GIS لـ .NET (متوافقة مع .NET Framework و .NET Core).  
- **هل أحتاج إلى ترخيص؟** الترخيص المؤقت يكفي للاختبار؛ الترخيص الكامل مطلوب للإنتاج.  
- **هل يمكنني قراءة صيغ أخرى؟** نعم – نفس الـ API يدعم GeoJSON و KML والعديد غيرها.  
- **كيف أقوم بتصدير السمات؟** استخدم `feature.GetValuesDump()` للحصول على مصفوفة كائنات مرنة.

## ما هو “قراءة shapefile باستخدام C#”؟
قراءة ملف Shapefile باستخدام C# يعني فتح ملف .shp باستخدام مكتبة GIS، وتكرار عناصره المتجهية، والوصول إلى بيانات السمات المخزنة في ملف .dbf المرافق. تقوم Aspose.GIS بتجريد التعامل منخفض المستوى مع الملفات، مما يتيح لك التركيز على قيم السمات التي تحتاجها.

## لماذا نستخدم Aspose.GIS لقراءة السمات؟
- **واجهة برمجة تطبيقات بسيطة** – طرق بديهية مثل `GetValues` و `GetValuesDump`.  
- **متعددة المنصات** – تعمل على Windows و Linux و macOS مع .NET Core.  
- **دعم صيغ غني** – التعامل مع Shapefile و GeoJSON و GML وغيرها دون الحاجة إلى إضافات.  
- **محسّن للأداء** – تكرار سريع على مجموعات بيانات كبيرة.

## المتطلبات المسبقة
قبل أن نبدأ هذه الرحلة المثيرة، تأكد من توفر المتطلبات التالية:
- Aspose.GIS لـ .NET: قم بتحميل وتثبيت المكتبة من [صفحة تحميل Aspose.GIS لـ .NET](https://releases.aspose.com/gis/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير .NET، مثل Visual Studio.
- Shapefile: احرص على وجود ملف Shapefile تجريبي (مثال: "InputShapeFile.shp") جاهز في دليل المستندات الخاص بك.

## استيراد مساحات الأسماء
في كود C# الخاص بك، ابدأ باستيراد مساحات الأسماء اللازمة للاستفادة من وظائف Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

## الخطوة 1: تعيين دليل المستندات
استبدل "Your Document Directory" بالمسار الفعلي حيث يقع ملف Shapefile الخاص بك.
```csharp
string dataDir = "Your Document Directory";
```

## الخطوة 2: فتح طبقة المتجهات
تتضمن هذه الخطوة فتح ملف Shapefile باستخدام Aspose.GIS، مع تحديد مسار الملف والصيغة (في هذه الحالة، Shapefile).
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```

## الخطوة 3: استرجاع جميع قيم سمات العنصر
المقتطف يوضح **كيفية قراءة السمات** لكل عنصر عن طريق تحميلها في مصفوفة ذات حجم ثابت.
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```

## الخطوة 4: استرجاع قيم سمات عدة عناصر
هنا نوضح **كيفية قراءة قيم سمات محددة** عندما تحتاج فقط إلى مجموعة فرعية من الحقول.
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```

## الخطوة 5: استرجاع قيم السمات كمجموعة كائنات مُصدَّرة
تُظهر هذه الخطوة الأخيرة **كيفية تصدير السمات** باستخدام `GetValuesDump()`، التي تُعيد مجموعة مرنة يمكنك فحصها أو تسلسلها.
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```

## المشكلات الشائعة والحلول
- **عدم تطابق حجم المصفوفة** – تأكد من أن المصفوفة التي تمررها إلى `GetValues` تتطابق مع عدد السمات المتوقعة؛ وإلا ستحصل على قيم `null`.  
- **الملف غير موجود** – تحقق من أن `dataDir` يشير إلى المجلد الصحيح وأن اسم ملف Shapefile مكتوب بدقة.  
- **استثناء الترخيص** – إذا ظهرت لك رسالة خطأ ترخيص، قم بتطبيق ترخيص مؤقت أو كامل قبل استدعاء أي من طرق الـ API.

## الأسئلة المتكررة
### هل Aspose.GIS متوافق مع .NET Core؟
نعم، Aspose.GIS متوافق بالكامل مع .NET Core، مما يتيح لك بناء تطبيقات متعددة المنصات.

### هل يمكنني العمل مع صيغ ملفات GIS مختلفة باستخدام Aspose.GIS؟
بالطبع! يدعم Aspose.GIS صيغًا متعددة، بما في ذلك Shapefile و GeoJSON وغيرها.

### هل هناك منتدى مجتمع لدعم Aspose.GIS؟
نعم، يمكنك العثور على المساعدة والتفاعل مع مجتمع Aspose.GIS عبر [منتدى الدعم](https://forum.aspose.com/c/gis/33).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.GIS؟
يمكنك الحصول على ترخيص مؤقت لأغراض الاختبار [من هنا](https://purchase.aspose.com/temporary-license/).

### أين يمكنني العثور على وثائق مفصلة لـ Aspose.GIS؟
الوثائق الشاملة متوفرة [هنا](https://reference.aspose.com/gis/net/).

### كيف يمكنني استرجاع سمة "Name" فقط من كل عنصر؟
استخدم `GetValues` مع مصفوفة بحجم عنصر واحد ومرّر فهرس حقل "Name"، أو استدعِ `feature["Name"]` مباشرة.

### ما الفرق بين `GetValues` و `GetValuesDump`؟
`GetValues` يملأ مصفوفة مُخصصة مسبقًا بالقيم الخام، بينما `GetValuesDump` يُعيد مصفوفة كائنات يمكن تعدادها دون الحاجة لمعرفة المخطط مسبقًا.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

---