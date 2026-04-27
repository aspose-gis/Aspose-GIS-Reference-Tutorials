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

# الإسناد المكاني wgs84 – قم بإضافته إلى GDB باستخدام Aspose.GIS

## مقدمة
هل انت صور بک سیر امل GIS هایس بک بیک بیک Aspose.GIS for .NET؟ ستتعلم في هذا الدرس **كيفية إضافة طبقة إلى مجموعة من ملفات البيانات GDB** أثناء العمل مع النظام الإحداثي **الإسناد المكاني wgs84**. لن نقوم بكل خطوة، بدءًا من إعداد مجموعة البيانات الخاصة بك وحتى التحقق من صحة الفصل الذي تم إنشاؤه مؤخرًا، حتى تتمكن من البدء في معالجة البيانات الجغرافية.

## إجابات سريعة
- **ما هو نزام قيادات عنيام المثيرة؟** الإسناد المكاني wgs84 (WGS84)
- **اي مكتبة توفر الـ API?** Aspose.GIS for .NET
- **هل أحتا إلى ترخيص للتخصص?** نعم –ترخيص Aspose Aspose.
- **هل إلى سمات الحديثة إلى تبقة?** استبديل, تعريف اي تعريف اي تحميل من سمات على التحميل.
- **ما استقراء .NET المدعومه؟** .NET Framework4.5+, .NET Core3.1+, .NET5/6.

## ما هو الإسناد المكاني wgs84؟
إصلاة المكانية wgs84 (النظام الجيوديسي العالمي 1984) هيزام القرآنيات الغرفورية الأملت يستقورًا. تُعرّف خطوط العرض والطول بالدرجات وتعمل كنظام إحداثي افتراضي للعديد من مجموعات بيانات نظم المعلومات الجغرافية، بما في ذلك تلك التي سنقوم بإنشائها في هذا الدليل.

## لماذا نستخدم Aspose.GIS لإضافة طبقة؟
- **بدون تعبايات براقة:** يعمل مباشرة مع كود .NET.
- **تخصيم كامل في الشراء:** يمكنك تحديد الميزات وأنواع التصميم المخصصة.
- **أنظمة أساسية متعددة:** متوافق مع أنظمة التشغيل Windows وLinux وmacOS.
- **ترخيص قوي:** التراخيص تحميل التلخيص التحميل السريع قبل عليبة.

## المتطلبات الأساسية
قبل البدء، تأكد من أن لديك:

- مؤسسة Aspose.GIS for .NET: قم بتعليقة التثبيت المؤسسة من [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).
- دليل الإكتمونات: أنشك مجلدًا مزدوجًا على التحكم مففولة GIS.

## استيراد مساحات الأسماء
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

## الخطوة 1: نسخ المجلد
أولاً، قم بنسخ المجلد الذي يحتوي على مجموعة بيانات GDB الأصلية. الحفاظ على نسخة يحمي البيانات المصدر أثناء التجربة.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## الخطوة 2: فتح مجموعة البيانات والتحقق من إمكانية الإنشاء
افتح مجموعة البيانات المنسوخة حديثًا وتأكد من أنها يمكنها إنشاء طبقات جديدة. يجب أن تُعيد خاصية `CanCreateLayers` القيمة **True**.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## الخطوة 3: إنشاء طبقة جديدة وتعبئتها بالإحداثيات المكانية WGS84
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

## الخطوة 4: فتح الطبقة المضافة والتحقق من صحتها
أخيرًا، افتح الطبقة التي أنشأتها للتو وتحقق من محتوياتها. سيظهر في وحدة التحكم أن الطبقة تحتوي على ميزة واحدة وأن سمة **Name** تتطابق مع ما حددناه.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## المشكلات والنصائح الشائعة
- **مسار غير صحيح:** تأكد من أن `dataDir` ينتهي بمسار فصل (`/` أو `\`) حتى تُنشئ السلاس غير المشروعات مشاريع مفولة صالحة.
- **أختراء الخلفية:** إذا ظهرت التحذيرات الخاصة بالترخيص، قم بزيارة مطلوبة لكنير من بعدة Aspose قبل تعريف الكود.
- **غير متوافق مع CRS:** عند فتح الفرنسية صحتًا في جديل GIS عرض المزيد، تأكد من أن الأداة تتعرف على WGS84 (EPSG:4326) كنظام القرآنيات.

## الأسئلة المتداولة
### س: هل يمكنني استخدام Aspose.GIS for .NET مع مكتبات GIS الأخرى؟
تم تصميم Aspose.GIS for .NET للعمل بشكل مستقل، ولكن يمكن دمجه مع مكتبات أخرى لتحسين الأداء الوظيفي.

### س: هل الترخيص المؤقت متاح لأغراض الاختبار؟
نعم، يمكنك الحصول على ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/) لأغراض الاختبار والتجربة.

## س: ما هي أنظمة الإسناد المكاني التي يدعمها Aspose.GIS لـ .NET؟

يدعم Aspose.GIS لـ .NET نطاقًا واسعًا من أنظمة الإسناد المكاني، مما يوفر مرونة في معالجة البيانات الجغرافية.

## س: هل يمكنني المساهمة في مجتمع Aspose.GIS؟

بالتأكيد! انضم إلى منتدى Aspose.GIS (https://forum.aspose.com/c/gis/33).

## س: أين يمكنني العثور على توثيق مفصل لـ Aspose.GIS لـ .NET؟
استكشف الوثائق الشاملة [here](https://reference.aspose.com/gis/net/) للحصول على معلومات متعمقة حول Aspose.GIS for .NET.

---

**آخر تحديث:** 2026-01-13  
**تم الاختبار باستخدام:** Aspose.GIS for .NET (latest stable version)  
**المؤلف:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
