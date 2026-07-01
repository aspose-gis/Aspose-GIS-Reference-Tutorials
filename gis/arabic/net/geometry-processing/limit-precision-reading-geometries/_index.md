---
date: 2026-04-03
description: تعلم كيفية إنشاء طبقة متجهة وتحديد الدقة عند قراءة الأشكال الهندسية باستخدام
  Aspose.GIS لـ .NET. دليل خطوة بخطوة للتعامل المثالي مع البيانات الجغرافية المكانية.
keywords:
- create vector layer
- reduce shapefile size
- set precision model
linktitle: تحديد دقة قراءة الأشكال الهندسية
second_title: Aspose.GIS .NET API
title: إنشاء طبقة متجهة، تحديد الدقة باستخدام Aspose.GIS لـ .NET
url: /ar/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء طبقة متجهة، تحديد الدقة مع Aspose.GIS لـ .NET

## المقدمة
عند العمل مع البيانات الجغرافية المكانية، غالبًا ما تحتاج إلى **create vector layer** كائنات وتقرر عدد المنازل العشرية لتفاصيل الإحداثيات التي تحتاجها فعلاً. تحديد الدقة لا يسرّع المعالجة فحسب، بل يمكنه أيضًا **reduce shapefile size**، مما يجعل التخزين والنقل أكثر كفاءة. في هذا البرنامج التعليمي سنستعرض إنشاء طبقة متجهة، كتابة هندسة نقطة بسيطة، ثم قراءتها مرة أخرى باستخدام نماذج الدقة الدقيقة والمقربة. في النهاية ستفهم كيفية **set precision model** الخيارات التي تناسب متطلبات دقة تطبيقك.

## إجابات سريعة
- **What does “limit precision” mean?** يقوم بتقريب قيم الإحداثيات إلى عدد محدد من المنازل العشرية.  
- **Why create a vector layer first?** الطبقة المتجهة هي الحاوية التي تخزن الهندسات مثل النقاط والخطوط والمتعددات.  
- **Which precision models are available?** `PrecisionModel.Exact` (بدون تقريب) و `PrecisionModel.Rounding(n)` (تقريب إلى *n* منازل عشرية).  
- **Do I need a license to try this?** نسخة تجريبية مجانية متاحة من صفحة الإصدارات.  
- **Which .NET versions are supported?** .NET Framework 4.5+، .NET Core، و .NET 5/6+.

## لماذا تحديد الدقة وكيف يساعد ذلك؟
- **Performance boost** – عدد أقل من الأرقام يعني بيانات أقل للتحليل والتسلسل.  
- **Smaller files** – تقريب الإحداثيات يمكن أن يقلص حجم ملف shapefile بشكل ملحوظ، خاصةً للمجموعات الكبيرة.  
- **Sufficient accuracy** – العديد من تحليلات GIS لا تتطلب دقة تحت المليمتر، لذا فإن التقريب إلى 2‑3 منازل عشرية يكون كافيًا في كثير من الأحيان.

## المتطلبات المسبقة
قبل أن نبدأ هذه الرحلة، تأكد من أن لديك المتطلبات المسبقة التالية جاهزة:
1. **Installation** – يجب تثبيت مكتبة Aspose.GIS for .NET في بيئة التطوير الخاصة بك. إذا لم يكن كذلك، يمكنك تنزيلها من [releases page](https://releases.aspose.com/gis/net/).
2. **Familiarity with .NET** – معرفة أساسية بـ C# وإطار .NET ضرورية لفهم وتنفيذ أمثلة الشيفرة المقدمة.
3. **Development Environment** – بيئة تطوير .NET تعمل، مثل Visual Studio، مطلوبة.
4. **Document Directory** – احرص على إعداد دليل يمكنك من خلاله تخزين والوصول إلى ملف shapefile الذي تم إنشاؤه خلال العملية.

## استيراد مساحات الأسماء
قبل أن نبدأ بتنفيذ الوظيفة لتحديد الدقة عند قراءة الهندسات، دعنا نتأكد من استيراد مساحات الأسماء اللازمة:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## كيفية إنشاء طبقة متجهة
الخطوة الأولى هي **create vector layer** التي ستحمل هندستنا. سيتم حفظ هذه الطبقة كملف Shapefile حتى نتمكن لاحقًا من إعادة فتحه بإعدادات دقة مختلفة.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## إعداد خيارات الدقة
بعد ذلك، نحتاج إلى تعريف خيارات لقراءة الهندسات، مع تحديد نموذج الدقة المطلوب. يمكننا البدء بالدقة الدقيقة:
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## قراءة الهندسات بالدقة الدقيقة
الآن، لنفتح طبقة المتجهة باستخدام الخيارات المحددة لقراءة الهندسات بالدقة الدقيقة:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## تقليل الدقة
إذا أردنا تقليل الدقة إلى عدد محدد من المنازل العشرية، يمكننا تعديل نموذج الدقة وفقًا لذلك:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## كيفية تعيين نموذج الدقة لسيناريوهات مختلفة
قد تتساءل متى تستخدم `Exact` مقابل `Rounding`. إليك سيناريوهين شائعين:

| السيناريو | النموذج الموصى به | السبب |
|----------|-------------------|--------|
| تحليل علمي عالي الدقة | `PrecisionModel.Exact` | لا فقدان لتفاصيل الإحداثيات |
| خرائط الويب أو التطبيقات المحمولة | `PrecisionModel.Rounding(2)` | يقلل حجم الملف ويسرّع عملية العرض |

اختيار النموذج المناسب هو جزء من عملية اتخاذ القرار **set precision model** التي توازن بين الدقة والأداء.

## المشكلات الشائعة والحلول
- **Unexpected coordinate values** – تأكد من ضبط `options.XYPrecisionModel` *قبل* فتح الطبقة. التغيير بعد الفتح لا يؤثر.  
- **File not found** – تحقق من أن المتغير `path` يشير إلى دليل صالح وأن ملف Shapefile تم إنشاؤه بنجاح في الخطوة السابقة.  
- **Incorrect geometry type** – المثال يستخدم `Point`. للأنواع الهندسية الأخرى (مثل `LineString`)، يجب أن يتطابق التحويل مع النوع الفعلي.  

## نصائح لتقليل حجم Shapefile
- استخدم `PrecisionModel.Rounding` بأقل عدد من المنازل العشرية التي لا تزال تلبي احتياجات الدقة لديك.  
- احذف حقول السمات غير الضرورية قبل كتابة الطبقة.  
- اضغط ملفات `.shp` و`.shx` و`.dbf` الناتجة باستخدام أدوات ZIP القياسية إذا كنت بحاجة إلى نقلها.

## الخلاصة
في الختام، إدارة الدقة عند قراءة الهندسات هي جانب حاسم في معالجة البيانات الجغرافية المكانية. توفر Aspose.GIS for .NET وظائف قوية لتحقيق ذلك بكفاءة. باتباع الخطوات أعلاه يمكنك بسهولة إنشاء كائنات **create vector layer**، **set precision model**، وحتى **reduce shapefile size** عندما يكون ذلك مناسبًا، مما يضمن معالجة بيانات مثالية في تطبيقاتك.

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.GIS for .NET مع أطر .NET أخرى مثل .NET Core أو .NET Standard؟
نعم، Aspose.GIS for .NET متوافق مع أطر .NET المختلفة، بما في ذلك .NET Core و .NET Standard.

### هل هناك نسخة تجريبية متاحة لـ Aspose.GIS for .NET؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من [releases page](https://releases.aspose.com/).

### أين يمكنني العثور على وثائق شاملة لـ Aspose.GIS for .NET؟
يمكنك الرجوع إلى [documentation](https://reference.aspose.com/gis/net/) للحصول على معلومات مفصلة وأمثلة.

### كيف يمكنني الحصول على تراخيص مؤقتة لـ Aspose.GIS for .NET؟
يمكن الحصول على تراخيص مؤقتة من [purchase page](https://purchase.aspose.com/temporary-license/) لـ Aspose.GIS.

### أين يمكنني طلب المساعدة أو الدعم لـ Aspose.GIS for .NET؟
يمكنك زيارة [forum](https://forum.aspose.com/c/gis/33) الخاص بـ Aspose.GIS لأي استفسارات أو مناقشات أو احتياجات دعم.

## الأسئلة المتكررة
**س: هل يؤثر تحديد الدقة على ملف shapefile الأصلي؟**  
ج: لا. يتم تطبيق الدقة فقط عند قراءة الهندسة؛ يبقى ملف المصدر دون تغيير.

**س: هل يمكنني استخدام نموذج دقة مختلف لإحداثيات X و Y؟**  
ج: حاليًا Aspose.GIS يطبق نفس `XYPrecisionModel` على كلا المحورين.

**س: هل من الممكن تعيين دالة تقريب مخصصة؟**  
ج: تدعم الواجهة البرمجية فقط الطريقة المدمجة `PrecisionModel.Rounding(int)`. لتطبيق منطق مخصص، سيتعين عليك معالجة الإحداثيات بعد القراءة.

---

**آخر تحديث:** 2026-04-03  
**تم الاختبار مع:** Aspose.GIS 24.11 for .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}