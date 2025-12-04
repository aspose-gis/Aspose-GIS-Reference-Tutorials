---
date: 2025-12-04
description: تعلم كيفية فحص التماس بين الأشكال الهندسية باستخدام Aspose.GIS لـ .NET،
  وهي مكتبة قوية للتعامل مع البيانات المكانية وإجراء التحليل المكاني .NET.
language: ar
linktitle: How to Check Touching Geometries
second_title: Aspose.GIS .NET API
title: كيفية التحقق من التماس الأشكال الهندسية باستخدام Aspose.GIS لـ .NET
url: /net/geometry-analysis/check-geometries-touching/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية التحقق من التلامس بين الأشكال الهندسية

## المقدمة
إذا كنت بحاجة إلى **كيفية التحقق من التلامس** بين كائنين مكانيين، فإن Aspose.GIS for .NET يوفّر لك واجهة برمجة تطبيقات نظيفة وآمنة من حيث النوع تجعل المهمة بسيطة. في هذا الدرس ستتعلم كيفية إنشاء سلاسل خطوط (LineString) ونقاط، ثم استخدام طريقة `Touches` لتحديد ما إذا كانت الأشكال الهندسية تشترك فقط في حدٍّ واحد. هذه عملية أساسية في العديد من سيناريوهات التحليل المكاني على .NET، مثل توجيه الشبكات، والتحقق من تراكب الخرائط، وفحوصات القرب.

## إجابات سريعة
- **ماذا يعني “التلامس”؟** تشترك شكلان هندسيان في نقطة حدٍّ واحدة على الأقل لكن داخلهما لا يتقاطع.  
- **ما الطريقة التي تتحقق من ذلك؟** `Geometry.Touches(otherGeometry)`.  
- **هل أحتاج إلى ترخيص لهذه الميزة؟** النسخة التجريبية تعمل للتطوير؛ الترخيص الدائم مطلوب للإنتاج.  
- **الإصدارات المدعومة من .NET؟** .NET Framework، .NET Core، .NET 5/6/7 – جميعها مدعومة من Aspose.GIS.  
- **كم يستغرق تنفيذ هذه العملية؟** حوالي 5‑10 دقائق لمثال أساسي.

## ما هو “التلامس” في التحليل المكاني؟
في مصطلحات نظم المعلومات الجغرافية، *التلامس* يصف علاقة مكانية حيث يلتقي شكلان هندسيان على حوافهما دون أن يتداخلا. وهو يختلف عن *intersects* (الذي يشمل التداخل الداخلي) وغالبًا ما يُستخدم عندما تحتاج إلى التحقق من أن المعالم تلتقي فقط على حدٍّ، مثل قطع الطرق التي تتصل عند تقاطع دون عبور بعضها البعض.

## لماذا نستخدم Aspose.GIS للتحليل المكاني على .NET؟
توفر Aspose.GIS مكتبة .NET مُدارة بالكامل تتيح لك **معالجة البيانات المكانية** دون الحاجة إلى تثبيت نظم معلومات جغرافية محلية. تدعم مجموعة واسعة من الصيغ (Shapefile، GeoJSON، KML، إلخ) وتقدم عمليات هندسية عالية الأداء مثل `Touches`، `Intersects`، `Contains`، وغيرها. وبما أنها مكتوبة بالكامل بـ .NET، يمكنك دمجها مباشرةً في خدمات الويب، التطبيقات المكتبية، أو وظائف السحابة.

## المتطلبات المسبقة
قبل البدء، تأكد من توفر ما يلي:

1. **Visual Studio** (أي نسخة حديثة) مثبت على جهازك.  
2. **Aspose.GIS for .NET** – حمّل أحدث حزمة من [صفحة التحميل الرسمية](https://releases.aspose.com/gis/net/).  
3. **ترخيص صالح** (أو نسخة تجريبية مجانية) – احصل عليه من [هنا](https://releases.aspose.com/).  

### إعداد البيئة
1. ثبّت Visual Studio إذا لم يكن مثبتًا بالفعل.  
2. حمّل Aspose.GIS for .NET من الرابط أعلاه وأضف حزمة NuGet إلى مشروعك.  
3. طبّق ملف الترخيص في الشيفرة (أو استخدم ترخيصًا مؤقتًا للاختبار).

## استيراد المساحات الاسمية
لبدء استخدام الواجهة، استورد المساحات الاسمية المطلوبة:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## الخطوة 1: إنشاء سلاسل خطوط (ونقطة)
فيما يلي **إنشاء line string** كائنات ونقطة ستُستخدم لاختبار علاقة التلامس.

```csharp
var geometry1 = new LineString();
geometry1.AddPoint(0, 0);
geometry1.AddPoint(2, 2);
var geometry2 = new LineString();
geometry2.AddPoint(2, 2);
geometry2.AddPoint(3, 3);
var geometry3 = new Point(2, 2);
var geometry4 = new LineString();
geometry4.AddPoint(1, 1);
geometry4.AddPoint(4, 4);
```

*شرح*:  
- `geometry1` و `geometry2` يشتركان في نقطة النهاية `(2, 2)`.  
- `geometry3` هي نقطة تقع بالضبط عند تلك النقطة المشتركة.  
- `geometry4` يقطع نفس المنطقة لكنه **لا** يشارك حدًا مع `geometry1`.

## الخطوة 2: فحص علاقات التلامس
الآن نستدعي طريقة `Touches` لمعرفة أي أزواج تُعتبر متلامسة.

```csharp
Console.WriteLine(geometry1.Touches(geometry2)); // True
Console.WriteLine(geometry2.Touches(geometry1)); // True
Console.WriteLine(geometry1.Touches(geometry3)); // True
Console.WriteLine(geometry1.Touches(geometry4)); // False
```

*النتيجة*:  
- الفحوصات الثلاث الأولى تُعيد **True** لأن الأشكال الهندسية تلتقي عند نقطة واحدة دون تداخل داخلي.  
- الفحص الأخير يُعيد **False** لأن سلاسل الخطين تتقاطع على قطعة خط، وليس فقط عند نقطة حدّ.

## المشكلات الشائعة والنصائح
- **مشكلات الدقة** – حسابات GIS تعتمد على الأعداد العائمة. إذا صادفت نتائج `False` غير متوقعة، فكر في تطبيع الإحداثيات أو استخدام هامش tolerance مع `Geometry.EqualsExact(other, tolerance)`.  
- **أنواع الأشكال المختلطة** – `Touches` يعمل عبر النقاط، الخطوط، والمضلعات، لكن الدلالات تختلف؛ تحقق دائمًا من العلاقة المتوقعة لبياناتك.  
- **الأداء** – بالنسبة لمجموعات البيانات الكبيرة، قم بدمج الفحوصات أو استخدم الفهارس المكانية (مثل R‑tree) التي توفرها Aspose.GIS لتجنب مقارنات O(N²).

## الأسئلة المتكررة

**س: هل Aspose.GIS متوافق مع جميع أطر .NET؟**  
ج: نعم. يدعم .NET Framework، .NET Core، .NET 5+، و .NET 6+، مما يمنحك مرونة عبر المشاريع المكتبية، الويب، والسحابة.

**س: هل يمكنني تجربة Aspose.GIS قبل شراء الترخيص؟**  
ج: بالتأكيد. يمكنك الحصول على نسخة تجريبية مجانية من موقع Aspose **[هنا](https://purchase.aspose.com/temporary-license/)** لاستكشاف جميع الميزات، بما في ذلك عملية `Touches`.

**س: أين يمكنني العثور على الدعم للاستفسارات المتعلقة بـ Aspose.GIS؟**  
ج: زر **[منتدى Aspose.GIS الرسمي](https://forum.aspose.com/c/gis/33)** لطرح الأسئلة، مشاركة الأمثلة، والحصول على مساعدة من المجتمع ومهندسي Aspose.

**س: كم مرة تُصدر تحديثات لـ Aspose.GIS؟**  
ج: تصدر Aspose تحديثات منتظمة تضيف دعم صيغ جديدة، تحسينات أداء، وإصلاحات أخطاء، لضمان التوافق مع أحدث إصدارات .NET.

**س: هل يمكنني الحصول على ترخيص مؤقت لـ Aspose.GIS؟**  
ج: نعم، الترخيص المؤقت متاح **[هنا](https://purchase.aspose.com/temporary-license/)** لأغراض التقييم.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2025-12-04  
**تم الاختبار مع:** Aspose.GIS for .NET 24.11 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

---