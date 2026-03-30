---
date: 2025-12-20
description: تعلم كيفية إنشاء طبقة متجهة وتحديد الدقة عند قراءة الأشكال الهندسية باستخدام
  Aspose.GIS لـ .NET. دليل خطوة بخطوة لمعالجة البيانات الجغرافية المكانية بأفضل شكل.
linktitle: Limit Precision Reading Geometries
second_title: Aspose.GIS .NET API
title: إنشاء طبقة متجهة، تحديد الدقة باستخدام Aspose.GIS لـ .NET
url: /ar/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء طبقة متجهة، تحديد الدقة باستخدام Aspose.GIS لـ .NET

## المقدمة
عند العمل مع البيانات الجغرافية المكانية، غالبًا ما تحتاج إلى **إنشاء طبقة متجهة** والتحكم في مقدار التفاصيل الرقمية التي تُحتفظ بها أثناء قراءتها. تجعل Aspose.GIS لـ .NET عملية تحديد الدقة بسيطة، مما يمكن أن يحسن الأداء ويقلل حجم التخزين عندما لا تكون الدقة الفائقة مطلوبة. في هذا البرنامج التعليمي ستتعرف على كيفية إنشاء طبقة متجهة، كتابة شكل هندسي بسيط من نوع نقطة، ثم قراءته مرة أخرى بدقة دقيقة ومقتصرة.

## إجابات سريعة
- **ماذا يعني “تحديد الدقة”؟** يقوم بتقريب قيم الإحداثيات إلى عدد محدد من المنازل العشرية.  
- **لماذا نحتاج إلى إنشاء طبقة متجهة أولاً؟** طبقة المتجهة هي الحاوية التي تخزن الأشكال الهندسية مثل النقاط، الخطوط، والمضلعات.  
- **ما نماذج الدقة المتاحة؟** `PrecisionModel.Exact` (بدون تقريب) و `PrecisionModel.Rounding(n)` (تقريب إلى *n* منازل عشرية).  
- **هل أحتاج إلى ترخيص لتجربة ذلك؟** نسخة تجريبية مجانية متاحة من صفحة الإصدارات.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core، و .NET 5/6+.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من توفر المتطلبات التالية:
1. **التثبيت** – يجب تثبيت مكتبة Aspose.GIS لـ .NET في بيئة التطوير الخاصة بك. إذا لم يكن مثبتًا، يمكنك تحميله من [صفحة الإصدارات](https://releases.aspose.com/gis/net/).
2. **الإلمام بـ .NET** – معرفة أساسية بـ C# وإطار عمل .NET ضرورية لفهم وتنفيذ أمثلة الشيفرة المقدمة.
3. **بيئة التطوير** – تحتاج إلى بيئة تطوير .NET تعمل، مثل Visual Studio.
4. **دليل المستندات** – أنشئ دليلًا يمكنك من خلاله تخزين والوصول إلى ملف shapefile الذي سيتم إنشاؤه خلال العملية.

## استيراد المساحات الاسمية
قبل البدء في تنفيذ الوظيفة التي تحدد الدقة عند قراءة الأشكال الهندسية، دعنا نتأكد من استيراد المساحات الاسمية اللازمة:
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
الخطوة الأولى هي **إنشاء طبقة متجهة** ستحتوي على الشكل الهندسي الخاص بنا. سيتم حفظ هذه الطبقة كملف Shapefile حتى نتمكن من إعادة فتحه لاحقًا بإعدادات دقة مختلفة.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## تحديد خيارات الدقة
بعد ذلك، نحتاج إلى تعريف خيارات قراءة الأشكال الهندسية، مع تحديد نموذج الدقة المطلوب. يمكننا البدء بدقة دقيقة:
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## قراءة الأشكال الهندسية بدقة دقيقة
الآن، لنفتح طبقة المتجهة باستخدام الخيارات المحددة لقراءة الأشكال الهندسية بدقة دقيقة:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## تقليل الدقة
إذا أردنا تقليل الدقة إلى عدد معين من المنازل العشرية، يمكننا تعديل نموذج الدقة وفقًا لذلك:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## المشكلات الشائعة والحلول
- **قيم إحداثيات غير متوقعة** – تأكد من ضبط `options.XYPrecisionModel` *قبل* فتح الطبقة. التغيير بعد الفتح لا يؤثر.
- **الملف غير موجود** – تحقق من أن المتغير `path` يشير إلى دليل صالح وأن ملف Shapefile تم إنشاؤه بنجاح في الخطوة السابقة.
- **نوع الشكل الهندسي غير صحيح** – المثال يستخدم `Point`. بالنسبة لأنواع أخرى (مثل `LineString`)، يجب أن يتطابق التحويل مع النوع الفعلي.

## الخاتمة
في الختام، إدارة الدقة عند قراءة الأشكال الهندسية تُعد جانبًا حيويًا في معالجة البيانات الجغرافية المكانية. توفر Aspose.GIS لـ .NET وظائف قوية لتحقيق ذلك بكفاءة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك بسهولة **إنشاء طبقة متجهة** وتحديد الدقة وفقًا لمتطلباتك، مما يضمن معالجة بيانات مثالية في تطبيقاتك.

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.GIS لـ .NET مع أطر .NET أخرى مثل .NET Core أو .NET Standard؟
نعم، Aspose.GIS لـ .NET متوافق مع أطر .NET المختلفة، بما في ذلك .NET Core و .NET Standard.  
### هل هناك نسخة تجريبية متاحة لـ Aspose.GIS لـ .NET؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من [صفحة الإصدارات](https://releases.aspose.com/).  
### أين يمكنني العثور على وثائق شاملة لـ Aspose.GIS لـ .NET؟
يمكنك الرجوع إلى [الوثائق](https://reference.aspose.com/gis/net/) للحصول على معلومات مفصلة وأمثلة.  
### كيف يمكنني الحصول على تراخيص مؤقتة لـ Aspose.GIS لـ .NET؟
يمكن الحصول على تراخيص مؤقتة من [صفحة الشراء](https://purchase.aspose.com/temporary-license/) لـ Aspose.GIS.  
### أين يمكنني طلب المساعدة أو الدعم لـ Aspose.GIS لـ .NET؟
يمكنك زيارة منتدى Aspose.GIS [المنتدى](https://forum.aspose.com/c/gis/33) لأي استفسارات أو مناقشات أو احتياجات دعم.

## الأسئلة المتكررة
**س: هل يؤثر تحديد الدقة على ملف shapefile الأصلي؟**  
ج: لا. يتم تطبيق الدقة فقط عند قراءة الشكل الهندسي؛ يبقى الملف المصدر دون تغيير.  

**س: هل يمكنني استخدام نموذج دقة مختلف لإحداثيات X و Y؟**  
ج: حاليًا، Aspose.GIS يطبق نفس `XYPrecisionModel` على المحورين.  

**س: هل يمكن تعيين دالة تقريب مخصصة؟**  
ج: تدعم الواجهة البرمجية فقط الطريقة المدمجة `PrecisionModel.Rounding(int)`. إذا كنت تحتاج إلى منطق مخصص، سيتعين عليك معالجة الإحداثيات بعد القراءة.

---

**آخر تحديث:** 2025-12-20  
**تم الاختبار مع:** Aspose.GIS 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}