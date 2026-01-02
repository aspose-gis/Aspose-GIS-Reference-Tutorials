---
date: 2026-01-02
description: تعلم كيفية إضافة ميزة نقطة مع تعيين أسماء الحقول وقراءة معرف الكائن باستخدام
  Aspose.GIS لـ .NET. دليل خطوة بخطوة للمطورين.
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
title: إضافة ميزة نقطة وتحديد أسماء حقل معرف الكائن وحقل الهندسة
url: /ar/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة ميزة نقطة وتحديد أسماء معرف الكائن وحقل الهندسة

## Introduction
الانطلاق في رحلة إلى عالم نظم المعلومات الجغرافية (GIS) باستخدام Aspose.GIS for .NET يفتح أمام المطورين والهواة آفاقًا واسعة. في هذا الدرس، **ستتعلم كيفية إضافة ميزة نقطة** مع **تحديد أسماء الحقول** و**قراءة قيم معرف الكائن**، مما يمنحك سيطرة كاملة على بياناتك المكانية.

## Quick Answers
- **ما هو الهدف الأساسي من هذا الدليل؟** إظهار كيفية إضافة ميزة نقطة وتكوين أسماء معرف الكائن وحقل الهندسة.  
- **أي مكتبة يتم استخدامها؟** Aspose.GIS for .NET.  
- **هل أحتاج إلى ترخيص؟** يتوفر إصدار تجريبي مجاني؛ الترخيص مطلوب للاستخدام في بيئة الإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6+.  
- **هل يمكنني قراءة معرف الكائن بعد الإدخال؟** نعم – يوضح الدرس كيفية قراءة معرف الكائن من الطبقة.

## Prerequisites
قبل الغوص في الدرس، تأكد من توفر المتطلبات التالية:
- Aspose.GIS for .NET: قم بتنزيل وتثبيت المكتبة من [هنا](https://releases.aspose.com/gis/net/).
- دليل المستندات: أنشئ دليلًا لتخزين قواعد البيانات الجغرافية.
- بيئة .NET: تأكد من وجود بيئة .NET تعمل بشكل صحيح.

## Import Namespaces
لبدء العمل، تحتاج إلى استيراد المساحات الاسمية الضرورية إلى مشروعك. توفر هذه المساحات الاسمية الفئات والطرق الأساسية للتفاعل مع Aspose.GIS for .NET.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Step 1: Add point feature and specify Object ID and Geometry Field Names
في هذه الخطوة، ستتعلم كيفية إعداد أسماء معرف الكائن وحقل الهندسة لبيانات GIS الخاصة بك. هذا أمر حاسم لإدارة البيانات بفعالية ولتمكين **قراءة معرف الكائن** لاحقًا.

### Step 1.1: Set Document Directory
ابدأ بتحديد مسار دليل المستندات الخاص بك:

```csharp
string dataDir = "Your Document Directory";
```

### Step 1.2: Create a GeoDatabase and Define Options
أنشئ قاعدة بيانات جغرافية مع **تحديد أسماء الحقول** المطلوبة لمعرفة الكائن والهندسة:

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

### Step 1.3: Create and Add a Layer
أنشئ طبقة داخل قاعدة البيانات الجغرافية وأضف ميزة تمثل هندسة نقطة:

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

### Step 1.4: Open and Retrieve Data from the Layer
افتح الطبقة واسترجع الميزة التي أضفتها للتو. يوضح هذا كيفية **قراءة معرف الكائن** من مجموعة البيانات:

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Why set custom field names?
تخصيص أسماء معرف الكائن وحقل الهندسة يمنحك مرونة عند التكامل مع قواعد بيانات موجودة أو عند الالتزام باتفاقيات التسمية المطلوبة من التطبيقات اللاحقة. كما يجعل البيانات أكثر وصفًا ذاتيًا، مما يبسط الصيانة والتعاون.

## Common pitfalls and troubleshooting
- **الدليل غير موجود** – تأكد من أن `dataDir` يشير إلى مجلد موجود؛ وإلا سيحدث استثناء عند استدعاء `Dataset.Create`.  
- **تعارض أسماء الحقول** – إذا كان هناك حقل بنفس الاسم موجودًا مسبقًا في قاعدة البيانات الجغرافية، سيفشل الإنشاء. اختر أسماء فريدة.  
- **عدم توافق نظام الإحداثيات** – احرص دائمًا على مطابقة نظام الإحداثيات (مثل WGS84) مع البيانات التي تنوي تخزينها.

## Conclusion
تهانينا! لقد تعلمت بنجاح كيفية **إضافة ميزة نقطة**، **تحديد أسماء الحقول**، و**قراءة معرف الكائن** باستخدام Aspose.GIS for .NET. هذه الأساسيات تمكنك من بناء تطبيقات GIS قوية وإدارة البيانات المكانية بثقة.

## Frequently Asked Questions
### Q: Can I use Aspose.GIS for .NET in my web applications?
A: نعم، Aspose.GIS for .NET مناسب لكل من تطبيقات سطح المكتب والويب، ويوفر قدرات جغرافية متعددة.

### Q: Is there a trial version available before purchasing?
A: نعم، يمكنك تجربة ميزات Aspose.GIS for .NET من خلال نسخة تجريبية مجانية متاحة [هنا](https://releases.aspose.com/).

### Q: How can I obtain a temporary license for Aspose.GIS for .NET?
A: يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/) لأغراض التقييم.

### Q: What spatial reference systems does Aspose.GIS for .NET support?
A: يدعم Aspose.GIS for .NET أنظمة إحداثيات متعددة، مما يوفر مرونة لمجموعات البيانات الجغرافية المختلفة.

### Q: Where can I seek help or discuss Aspose.GIS-related queries?
A: زر منتدى Aspose.GIS [هنا](https://forum.aspose.com/c/gis/33) للحصول على الدعم والنقاش.

## Additional Frequently Asked Questions

**Q: Can I change the Object ID field after the layer is created?**  
A: لا. يتم تعريف اسم الحقل عند إنشاء الطبقة؛ يجب إعادة إنشاء الطبقة باستخدام كائن `FileGdbOptions` جديد لتغييره.

**Q: How do I retrieve other attribute values besides the Object ID?**  
A: استخدم `feature.GetValue<T>("FieldName")` حيث `FieldName` هو اسم السمة التي تريد قراءتها.

**Q: Is it possible to add multiple point features in one batch?**  
A: نعم. كرّر العملية على بياناتك، أنشئ ميزة لكل نقطة، عيّن هندستها، واستدعِ `layer.Add(feature)` داخل نفس كتلة `using`.

**Q: Does Aspose.GIS support other geometry types?**  
A: بالتأكيد. يمكنك العمل مع `LineString`، `Polygon`، `MultiPoint`، وغير ذلك بإنشاء كائنات الهندسة المناسبة.

**Q: What happens if I try to read an Object ID that doesn’t exist?**  
A: محاولة الوصول إلى فهرس خارج النطاق (مثل `layer[10]` عندما توجد ميزة واحدة فقط) ستؤدي إلى رمي استثناء `IndexOutOfRangeException`. تحقق دائمًا من `layer.Count` أولاً.

---

**Last Updated:** 2026-01-02  
**Tested With:** Aspose.GIS for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}