---
date: 2026-01-02
description: تعلم كيفية كتابة GeoJSON إلى تدفق في C# باستخدام Aspose.GIS لـ .NET.
  اعرض أمثلة GeoJSON بلغة C# وعزّز تطبيقاتك الجغرافية.
linktitle: Write GeoJSON to Stream
second_title: Aspose.GIS .NET API
title: كيفية كتابة GeoJSON إلى تدفق باستخدام Aspose.GIS لـ .NET
url: /ar/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية كتابة GeoJSON إلى Stream

## المقدمة
إذا كنت بحاجة إلى **كيفية كتابة geojson** مباشرةً إلى ذاكرة أو ملف Stream في تطبيق .NET، فأنت في المكان الصحيح. في هذا البرنامج التعليمي سنستعرض الخطوات الدقيقة لكتابة GeoJSON إلى Stream باستخدام مكتبة Aspose.GIS لـ .NET، وسنظهر لك أيضًا كيفية **عرض GeoJSON C#** في وحدة التحكم. في النهاية، ستحصل على نمط قابل لإعادة الاستخدام يمكنك إدراجه في أي مشروع جغرافي.

## إجابات سريعة
- **ماذا يعني “كتابة GeoJSON إلى Stream”؟** يعني ذلك تسلسل طبقة متجهة إلى صيغة GeoJSON وإرسال البايتات إلى كائن `Stream` (مثل `MemoryStream`).  
- **أي مكتبة تتولى ذلك؟** توفر Aspose.GIS لـ .NET برنامج تشغيل GeoJSON مدمج.  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **هل يمكن تشغيله على Linux؟** نعم – Aspose.GIS متعدد المنصات ويعمل على Windows وLinux وmacOS.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.

## ما هو “كيفية كتابة geojson” في .NET؟
تتيح لك Aspose.GIS إنشاء `VectorLayer`، إضافة ميزات، ثم تسلسل الطبقة باستخدام برنامج تشغيل `Drivers.GeoJson`. يكتب برنامج التشغيل نص GeoJSON مباشرةً إلى أي `Stream`، مما يمنحك التحكم الكامل في مكان توجيه البيانات (ذاكرة، ملف، شبكة، إلخ).

## لماذا نستخدم Aspose.GIS لهذه المهمة؟
- **تسلسل بدون تبعيات** – لا تحتاج إلى مكتبات JSON خارجية.  
- **التوافق الكامل مع مواصفات GeoJSON** – يدعم FeatureCollections، الخصائص، ودقة الإحداثيات.  
- **متعدد المنصات** – يعمل بنفس الطريقة على Windows وLinux وmacOS.  
- **محسن للأداء** – يكتب مباشرةً إلى الـ Stream دون سلاسل وسيطة.

## المتطلبات المسبقة
1. **Aspose.GIS لـ .NET** – حمّله من [هنا](https://releases.aspose.com/gis/net/).  
2. **دليل المستندات** – حدد المكان الذي تريد حفظ الملفات المؤقتة أو تدفقات الإخراج فيه.

الآن، دعنا نتعمق في الشيفرة.

## استيراد المساحات الاسمية
أولاً، أدرج المساحات الاسمية التي تمنحك الوصول إلى فئات Aspose.GIS وأدوات الإدخال/الإخراج القياسية في .NET:

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## الخطوة 1: إعداد دليل المستندات
عرّف المجلد الذي سيستضيف أي ملفات مؤقتة قد تحتاجها.

```csharp
string dataDir = "Your Document Directory";
```

استبدل `"Your Document Directory"` بالمسار الفعلي على جهازك.

## الخطوة 2: إنشاء Memory Stream
يتيح لك `MemoryStream` الاحتفاظ بـ GeoJSON في الذاكرة، وهو مثالي لواجهات برمجة التطبيقات أو عندما تريد إرجاع البيانات مباشرةً إلى العميل.

```csharp
using (var memoryStream = new MemoryStream())
{
    // Subsequent steps will be placed inside this block
}
```

## الخطوة 3: إنشاء طبقة متجهة باستخدام برنامج تشغيل GeoJSON
داخل كتلة الـ memory‑stream، أنشئ `VectorLayer` يستخدم برنامج تشغيل GeoJSON. هذا يخبر Aspose.GIS بتسلسل الطبقة كـ GeoJSON.

```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Feature creation goes here
}
```

## الخطوة 4: تعريف سمات الميزة
أضف تعريفات السمات التي ستظهر كخصائص في الناتج النهائي لـ GeoJSON.

```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## الخطوة 5: إنشاء وإضافة الميزات
أنشئ نقطتين تجريبيتين، عيّن قيم السمات، وأضفهما إلى الطبقة.

```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);

// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## الخطوة 6: عرض ناتج GeoJSON C#
بعد ملء الطبقة، حوّل بايتات الـ stream إلى سلسلة UTF‑8 واكتبها إلى وحدة التحكم. هذا يوضح كيفية **عرض GeoJSON C#**.

```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

سترى مجموعة FeatureCollection صالحة تُطبع في الطرفية.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|---------|--------|------|
| إخراج فارغ | موضع الـ stream في النهاية عند القراءة | استدعِ `memoryStream.Position = 0;` قبل التحويل إلى سلسلة. |
| هندسة غير صالحة | الإحداثيات خارج النطاقات المسموح بها | تحقق أن خط العرض بين -90 و90، وخط الطول بين -180 و180. |
| استثناء الترخيص | تشغيل بدون ترخيص صالح في الإنتاج | طبّق ترخيصًا مؤقتًا أو كاملًا باستخدام `License license = new License(); license.SetLicense("Aspose.GIS.lic");` |

## الأسئلة المتكررة
### هل يمكنني استخدام Aspose.GIS لـ .NET في بيئتي Windows وLinux؟
نعم، Aspose.GIS لـ .NET متوافق مع كل من Windows وLinux.  

### هل هناك نسخة تجريبية مجانية متاحة؟
بالطبع! يمكنك تجربة النسخة التجريبية من [هنا](https://releases.aspose.com/).  

### أين يمكنني العثور على الوثائق التفصيلية؟
اطلع على الوثائق من [هنا](https://reference.aspose.com/gis/net/).  

### كيف يمكنني الحصول على ترخيص مؤقت؟
التراخيص المؤقتة متوفرة من [هنا](https://purchase.aspose.com/temporary-license/).  

### هل تحتاج إلى مساعدة أو لديك أسئلة إضافية؟
زر منتدى الدعم الخاص بنا من [هنا](https://forum.aspose.com/c/gis/33).

## الأسئلة المتكررة (FAQ)
**س: هل يمكنني كتابة GeoJSON مباشرةً إلى ملف بدلاً من Memory Stream؟**  
ج: نعم—استبدل `MemoryStream` بـ `FileStream` وقدم مسار الملف. يعمل نفس برنامج التشغيل.

**س: كيف أتحكم في المسافات البادئة أو تنسيق GeoJSON المُولد؟**  
ج: يكتب Aspose.GIS JSON مضغوطًا بشكل افتراضي. للحصول على تنسيق مُنَسَّق، عالج السلسلة لاحقًا باستخدام `JsonSerializerOptions { WriteIndented = true }`.

**س: هل يمكن إضافة أشكال هندسية أكثر تعقيدًا (مثل المضلعات) إلى الطبقة؟**  
ج: بالتأكيد. أنشئ كائن `Polygon` أو `LineString`، عيّنها إلى `Feature.Geometry`، وأضف الميزة كما هو موضح أعلاه.

**س: هل ستتناسب مجموعات البيانات الكبيرة مع MemoryStream؟**  
ج: بالنسبة للمجموعات الضخمة، يُفضَّل البث مباشرةً إلى ملف أو استخدام `BufferedStream` لتقليل استهلاك الذاكرة.

**س: هل يدعم برنامج تشغيل GeoJSON تعريفات CRS (نظام الإحداثيات المرجعي)؟**  
ج: نعم—عيّن خاصية `SpatialReferenceSystem` للطبقة قبل إضافة الميزات إذا كنت تحتاج إلى CRS غير WGS84.

## الخاتمة
الآن لديك نمط كامل وجاهز للإنتاج **كيفية كتابة geojson** إلى أي Stream في .NET باستخدام Aspose.GIS. سواء كنت تحتاج لإرجاع GeoJSON من واجهة برمجة تطبيقات ويب، حفظه إلى ملف، أو مجرد عرضه في وحدة التحكم، تغطي الخطوات أعلاه سير العمل بالكامل. استكشف المكتبة أكثر للعمل مع صيغ أخرى مثل Shapefile، KML، أو GML، وواصل بناء تطبيقات جغرافية أكثر غنى.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-01-02  
**تم الاختبار مع:** Aspose.GIS 24.11 لـ .NET  
**المؤلف:** Aspose  

---