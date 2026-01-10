---
date: 2026-01-10
description: تعلم كيفية إنشاء طبقة متجهة في قاعدة بيانات جغرافية ملفية باستخدام Aspose.GIS
  لـ .NET. إدارة البيانات الجغرافية باستخدام المرجع المكاني WGS84 وخيارات ملف gdb.
linktitle: Create File GDB with Single Layer
second_title: Aspose.GIS .NET API
title: إنشاء طبقة متجهة في ملف GDB – دليل Aspose.GIS .NET
url: /ar/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء طبقة متجهة في ملف GDB

## المقدمة
إذا كنت بحاجة إلى **create vector layer** داخل قاعدة بيانات جغرافية ملفية (GDB) وإدارة البيانات الجغرافية بفعالية، فإن Aspose.GIS for .NET يوفّر لك نهجًا نظيفًا يعتمد على الكود أولاً. في هذا الدليل خطوة بخطوة سنظهر لك كيفية كتابة ميزة خطية، تكوين خيارات ملف GDB، والعمل مع المرجع المكاني WGS84 — كل ذلك في بضع أسطر من C#. في النهاية ستتمكن من عدّ الميزات في طبقة ودمج ملف GDB الناتج في أي سير عمل للخرائط أو التحليل على .NET.

## إجابات سريعة
- **What does “create vector layer” mean?** يعني ذلك إضافة مجموعة بيانات متجهة جديدة (نقاط، خطوط، أو مضلعات) إلى ملف قاعدة بيانات جغرافية.  
- **Which library should I use?** Aspose.GIS for .NET يوفر دعمًا كاملاً لإنشاء وتحرير File GDB.  
- **Do I need a license for development?** نسخة تجريبية مجانية تكفي للاختبار؛ يلزم الحصول على ترخيص تجاري للإنتاج.  
- **Can I set the spatial reference?** نعم – استخدم `SpatialReferenceSystem.Wgs84` للمرجع المكاني الشائع WGS84.  
- **How many lines of code?** أقل من 30 سطرًا لإنشاء الـ GDB، إضافة ميزة خطية، وقراءة عدد الميزات مرة أخرى.

## ما هي عملية “create vector layer”؟
إنشاء طبقة متجهة يعني تعريف جدول جديد داخل قاعدة البيانات الجغرافية يخزن كائنات هندسية (نقاط، خطوط، مضلعات) مع سماتها. هذه العملية هي الأساس لأي تطبيق GIS يحتاج إلى **manage geospatial data**.

## لماذا تستخدم Aspose.GIS لإنشاء طبقة متجهة؟
- **Zero external dependencies** – الـ API يعمل مباشرةً على .NET Framework و .NET Core و .NET 5/6.  
- **Full support for File GDB** – يمكنك تكوين `FileGdbOptions` للتحكم في الضغط، الفهرسة المكانية، والمزيد.  
- **Built‑in spatial reference handling** – ما عليك سوى تمرير `SpatialReferenceSystem.Wgs84` للعمل في نظام الإحداثيات العالمي.  
- **Straightforward API** – اكتب ميزة خطية، أضفها إلى طبقة، واسترجع عدد الميزات ببضع نداءات للطرق.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من وجود ما يلي:

1. **Aspose.GIS for .NET** – حمّله من [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).  
2. **A .NET development environment** – Visual Studio أو Rider أو `dotnet` CLI.  
3. **A folder** حيث سيتم إنشاء File GDB (سنسميه *Your Document Directory*).

## استيراد مساحات الأسماء
أضف بيانات `using` المطلوبة في أعلى ملف C# الخاص بك:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```

## الخطوة 1: إعداد دليل المستند الخاص بك
```csharp
string dataDir = "Your Document Directory";
```
استبدل `"Your Document Directory"` بالمسار المطلق حيث تريد أن يعيش File GDB.

## الخطوة 2: إنشاء قاعدة بيانات جغرافية ملفية بطبقة واحدة
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
هذا المقتطف **creates a vector layer** باستخدام `FileGdbOptions`، يكتب ميزة خطية بسيطة، ويخزنها في File GDB يستخدم **spatial reference WGS84**.

## الخطوة 3: فتح قاعدة البيانات الجغرافية الملفية واسترجاع معلومات الطبقة
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```
هنا نقوم بـ **count features layer** بفتح مجموعة البيانات وطباعة عدد الميزات – في هذه الحالة، `1`.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **`File not found`** | متغيّر `path` غير صحيح | تحقق من أن `dataDir` يشير إلى مجلد موجود وأن `path` يجمعه مع اسم ملف، على سبيل المثال `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | استخدام نوع هندسة غير مسموح به في File GDB | التزم بـ `Point` أو `LineString` أو `Polygon` للطبقات الأساسية. |
| **`License not set`** | تشغيل بدون ترخيص صالح في بيئة الإنتاج | سجّل ترخيصك باستخدام `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.GIS for .NET في مشاريعي .NET الحالية؟
نعم، يمكن دمج Aspose.GIS for .NET بسلاسة في مشروعات .NET الحالية.

### هل تتوفر نسخة تجريبية من Aspose.GIS for .NET؟
نعم، يمكنك استكشاف ميزات Aspose.GIS for .NET بتحميل [free trial version](https://releases.aspose.com/).

### أين يمكنني العثور على وثائق مفصلة لـ Aspose.GIS for .NET؟
راجع [documentation](https://reference.aspose.com/gis/net/) للحصول على معلومات شاملة حول Aspose.GIS for .NET.

### كيف يمكنني الحصول على دعم لـ Aspose.GIS for .NET؟
زر [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) للحصول على دعم المجتمع والمساعدة.

### هل تتوفر تراخيص مؤقتة لـ Aspose.GIS for .NET؟
نعم، يمكنك الحصول على [temporary license](https://purchase.aspose.com/temporary-license/) لـ Aspose.GIS for .NET.

---

**آخر تحديث:** 2026-01-10  
**تم الاختبار مع:** Aspose.GIS 24.11 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}