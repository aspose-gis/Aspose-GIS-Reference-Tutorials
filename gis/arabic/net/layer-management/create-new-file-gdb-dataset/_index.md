---
title: إنشاء مجموعة بيانات ملف GDB جديدة
linktitle: إنشاء مجموعة بيانات ملف GDB جديدة
second_title: Aspose.GIS .NET API
description: استكشف Aspose.GIS for .NET لإنشاء مجموعات بيانات GIS وإدارتها بسهولة. قم بالتنزيل الآن للتطوير الجغرافي المكاني السلس. #Aspose #GIS
type: docs
weight: 10
url: /ar/net/layer-management/create-new-file-gdb-dataset/
---
## مقدمة
في مجال التطوير الجغرافي المكاني، يبرز Aspose.GIS for .NET كمجموعة أدوات قوية لإدارة بيانات نظام المعلومات الجغرافية (GIS) ومعالجتها. سواء كنت مطورًا متمرسًا أو بدأت رحلتك في نظم المعلومات الجغرافية، فسيرشدك هذا البرنامج التعليمي خلال عملية إنشاء مجموعة بيانات قاعدة بيانات جغرافية ملفية جديدة (GDB) باستخدام Aspose.GIS for .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
-  Aspose.GIS for .NET: تأكد من تثبيت مكتبة Aspose.GIS for .NET. يمكنك تنزيله من[صفحة تنزيل Aspose.GIS for .NET](https://releases.aspose.com/gis/net/).
- بيئة التطوير: قم بإعداد بيئة التطوير الخاصة بك باستخدام IDE متوافق، مثل Visual Studio، واحصل على فهم أساسي لبرمجة .NET.
- دليل المستندات: استبدل "دليل المستندات الخاص بك" في مقتطف التعليمات البرمجية بالمسار المناسب حيث تريد تخزين مجموعة بيانات GDB الخاصة بك.
- الإلمام بـ C#: يفترض هذا البرنامج التعليمي أنك على دراية بلغة البرمجة C#.
## استيراد مساحات الأسماء
في الخطوات الأولية، قم باستيراد مساحات الأسماء الضرورية للاستفادة من وظيفة Aspose.GIS في تطبيق .NET الخاص بك:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## الخطوة 1: إنشاء مجموعة بيانات ملف GDB جديدة
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // الإخراج: 0
    // تابع الخطوات اللاحقة...
}
```
 شرح: في هذه الخطوة، نقوم بإنشاء مجموعة بيانات GDB جديدة باستخدام`Dataset.Create` طريقة. نحدد المسار وبرنامج التشغيل (FileGdb) لإنشاء قاعدة بيانات جغرافية للملفات. يعرض إخراج وحدة التحكم عدد الطبقات الأولي، وهو صفر عند هذه النقطة.
## الخطوة 2: إنشاء وملء Layer_1
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
Explanation: تتضمن هذه الخطوة تكوين طبقة تسمى "layer_1" داخل مجموعة البيانات. وهي تحدد سمة تسمى "قيمة" من النوع الصحيح وتملأ الطبقة بعشرة معالم، كل منها لها شكل هندسي نقطي.
## الخطوة 3: إنشاء وملء Layer_2
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
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
شرح: هنا، نقوم بإنشاء طبقة ثانية تسمى "layer_2" ونضيف ميزة واحدة بهندسة سلسلة سطرية.
## الخطوة 4: التحقق من عدد الطبقات المحدثة
```csharp
Console.WriteLine(dataset.LayersCount); // الإخراج: 2
```
شرح: أخيرًا، نتحقق من عدد الطبقات المحدثة بعد إضافة الطبقتين. في هذه الحالة، يجب أن يكون الناتج 2.
## خاتمة
تهانينا! لقد نجحت في إنشاء مجموعة بيانات File GDB جديدة وملؤها بالطبقات باستخدام Aspose.GIS for .NET. يوفر هذا البرنامج التعليمي فهمًا أساسيًا للعمل مع البيانات الجغرافية المكانية في بيئة .NET.
## أسئلة مكررة
### س: هل يمكنني استخدام Aspose.GIS for .NET مع مكتبات GIS الأخرى؟
Aspose.GIS for .NET عبارة عن مجموعة أدوات مستقلة؛ ومع ذلك، يمكنك دمجها مع مكتبات .NET الأخرى لتحسين الأداء الوظيفي.
### س: هل يوجد منتدى مجتمعي لدعم Aspose.GIS؟
 نعم، يمكنك العثور على الدعم والمناقشات حول[منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33).
### س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.GIS؟
 قم بزيارة[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) صفحة للحصول على معلومات حول الحصول على ترخيص مؤقت.
### س: هل هناك أمثلة ووثائق إضافية متاحة؟
 اكتشف ال[وثائق Aspose.GIS](https://reference.aspose.com/gis/net/) لمزيد من الأمثلة والمعلومات التفصيلية.
### س: أين يمكنني شراء Aspose.GIS لـ .NET؟
 يمكنك شراء Aspose.GIS لـ .NET على[صفحة الشراء](https://purchase.aspose.com/buy).