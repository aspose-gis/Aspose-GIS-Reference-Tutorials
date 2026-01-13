---
date: 2026-01-13
description: تعلم كيفية إضافة طبقة إلى مجموعة بيانات File GDB باستخدام Aspose.GIS،
  مع دعم الإسناد المكاني WGS84. اتبع هذا الدليل خطوة بخطوة لإضافة طبقة إلى GDB في
  .NET.
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: المرجع المكاني WGS84 – إضافة طبقة إلى قاعدة البيانات الجغرافية باستخدام Aspose.GIS
url: /ar/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# spatial reference wgs84 – إضافة طبقة إلى GDB باستخدام Aspose.GIS

## Introduction
هل أنت مستعد لتعزيز سير عمل GIS الخاص بك باستخدام Aspose.GIS for .NET؟ في هذا الدرس ستتعلم **كيفية إضافة طبقة إلى مجموعة بيانات File GDB** أثناء العمل مع نظام الإحداثيات **spatial reference wgs84**. سنستعرض كل خطوة، من إعداد مجلد البيانات الخاص بك إلى التحقق من صحة الطبقة التي تم إنشاؤها حديثًا، حتى تتمكن من بدء معالجة البيانات الجغرافية بثقة.

## Quick Answers
- **ما هو نظام الإحداثيات الأساسي المستخدم؟** spatial reference wgs84 (WGS 84)  
- **أي مكتبة توفر الـ API؟** Aspose.GIS for .NET  
- **هل أحتاج إلى ترخيص للاختبار؟** نعم – ترخيص Aspose مؤقت متاح.  
- **هل يمكنني إضافة سمات إلى الطبقة الجديدة؟** بالتأكيد، يمكنك تعريف أي عدد من سمات الميزة.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## What is spatial reference wgs84?
الإشارة المكانية wgs84 (World Geodetic System 1984) هي نظام الإحداثيات الجغرافية الأكثر استخدامًا. تُعرّف خطوط العرض والطول بالدرجات وتعمل كنظام إحداثيات افتراضي للعديد من مجموعات بيانات GIS، بما في ذلك تلك التي سننشئها في هذا الدليل.

## Why use Aspose.GIS to add a layer?
- **بدون تبعيات خارجية:** يعمل مباشرةً مع كود .NET النقي.  
- **تحكم كامل في المخطط:** يمكنك تعريف سمات مخصصة وأنواع هندسية.  
- **متعدد المنصات:** متوافق مع بيئات تشغيل Windows وLinux وmacOS.  
- **ترخيص قوي:** تسمح التراخيص المؤقتة بتقييم سريع قبل الالتزام.

## Prerequisites
قبل البدء، تأكد من أن لديك:

- مكتبة Aspose.GIS for .NET: قم بتنزيل وتثبيت المكتبة من [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- دليل المستندات: أنشئ مجلدًا مخصصًا على جهازك لتخزين ملفات GIS.

## Import Namespaces
أضف عبارات `using` المطلوبة إلى مشروع C# الخاص بك حتى تتمكن من الوصول إلى فئات Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Copy Directory
أولاً، قم بنسخ المجلد الذي يحتوي على مجموعة بيانات GDB الأصلية. الحفاظ على نسخة يحمي البيانات المصدر أثناء التجربة.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Step 2: Open Dataset and Verify Creation Capability
افتح مجموعة البيانات المنسوخة حديثًا وتأكد من أنها يمكنها إنشاء طبقات جديدة. يجب أن تُعيد خاصية `CanCreateLayers` القيمة **True**.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Step 3: Create and Populate a New Layer with spatial reference wgs84
الآن نقوم بإنشاء طبقة باسم **data** ونحدد صراحةً إشارةها المكانية إلى **Wgs84**. نضيف أيضًا سمة بسيطة تسمى **Name** ونُدرج ميزة نقطة واحدة.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## Step 4: Open and Validate the Added Layer
أخيرًا، افتح الطبقة التي أنشأتها للتو وتحقق من محتوياتها. سيظهر في وحدة التحكم أن الطبقة تحتوي على ميزة واحدة وأن سمة **Name** تتطابق مع ما حددناه.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Common Issues & Tips
- **مسار غير صحيح:** تأكد من أن `dataDir` ينتهي بفاصل مسار (`/` أو `\`) حتى تُكوّن السلاسل المتصلة مسارات ملفات صالحة.  
- **أخطاء الترخيص:** إذا ظهرت تحذيرات ترخيص، قم بتطبيق ترخيص مؤقت من بوابة Aspose قبل تشغيل الكود.  
- **عدم تطابق CRS:** عند فتح الطبقة لاحقًا في أداة GIS أخرى، تأكد من أن الأداة تتعرف على WGS 84 (EPSG:4326) كنظام الإحداثيات.

## Frequently Asked Questions
### Q: Can I use Aspose.GIS for .NET with other GIS libraries?
تم تصميم Aspose.GIS for .NET للعمل بشكل مستقل، ولكن يمكن دمجه مع مكتبات أخرى لتعزيز الوظائف.

### Q: Is a temporary license available for testing purposes?
نعم، يمكنك الحصول على ترخيص مؤقت من [here](https://purchase.aspose.com/temporary-license/) للاختبار والتقييم.

### Q: What spatial reference systems does Aspose.GIS for .NET support?
يدعم Aspose.GIS for .NET مجموعة واسعة من أنظمة الإشارة المكانية، مما يوفر مرونة في معالجة البيانات الجغرافية.

### Q: Can I contribute to the Aspose.GIS community?
بالطبع! انضم إلى المناقشات وشارك تجاربك على [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### Q: Where can I find detailed documentation for Aspose.GIS for .NET?
استكشف الوثائق الشاملة [here](https://reference.aspose.com/gis/net/) للحصول على معلومات متعمقة حول Aspose.GIS for .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-01-13  
**تم الاختبار باستخدام:** Aspose.GIS for .NET (latest stable version)  
**المؤلف:** Aspose