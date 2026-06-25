---
date: 2026-06-25
description: تعلم كيفية قراءة shapefile وتحويل shapefile متعدد الأضلاع إلى linestring
  باستخدام Aspose.GIS لـ .NET. عزّز تطوير GIS الخاص بك من خلال إرشادات واضحة خطوة
  بخطوة.
keywords:
- how to read shapefile
- convert polygon to line
- shapefile to geojson c#
- extract lines from polygon
linktitle: تحويل Polygon Shapefile إلى Linestring
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  headline: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  type: TechArticle
- description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  name: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  steps:
  - name: Set the Document Directory
    text: Replace `"Your Document Directory"` with the actual path where your shapefile
      resides.
  - name: Open the Source Shapefile
    text: This line opens the source Polygon Shapefile so you can read its features.
  - name: Create the Destination Linestring Shapefile
    text: Here we create a new Linestring Shapefile that will store the converted
      geometries.
  - name: Iterate Through Source Features
    text: The loop walks through each polygon feature in the original file.
  - name: Convert Polygon to Linestring and Write to Destination
    text: The `ExteriorRing` property returns the outer boundary of a polygon as a
      `LineString`. In this block we convert polygon to line (`LineString`) and add
      the new feature to the destination shapefile.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS supports .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7, ensuring seamless integration with modern development stacks.
    question: Is Aspose.GIS compatible with all versions of .NET?
  - answer: Yes, you can. Purchase a license [here](https://purchase.aspose.com/buy)
      to remove evaluation limitations and obtain full support.
    question: Can I use Aspose.GIS for commercial projects?
  - answer: Yes, you can find comprehensive documentation and code samples on the
      [documentation page](https://reference.aspose.com/gis/net/).
    question: Are there any examples or documentation available?
  - answer: Absolutely – explore Aspose.GIS with a free trial by visiting [this link](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      assistance and official support.
    question: Where can I seek help or support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: كيفية قراءة Shapefile C# – تحويل Polygon Shapefile إلى Linestring
url: /ar/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قراءة Shapefile C# – تحويل Shapefile متعدد الأضلاع إلى Linestring

## مقدمة
إذا كنت بحاجة إلى **how to read shapefile** البيانات في بيئة .NET، فأنت في المكان المناسب. تقوم Aspose.GIS for .NET بتجريد تنسيق Shapefile الثنائي منخفض المستوى، مما يتيح لك تحميل، استعلام، وتحويل الميزات الجغرافية ببضع نداءات API فقط. تحويل ملف Shapefile متعدد الأضلاع إلى linestring مفيد بشكل خاص عندما تريد استخراج تمثيلات خطية للتوجيه، تحليل الشبكات، أو التصور البسيط.

## إجابات سريعة
- **ما المكتبة التي تساعدك على قراءة shapefile c#؟** Aspose.GIS for .NET – it supports 50+ GIS formats and handles files up to several hundred megabytes without loading the whole file into memory.  
- **هل يمكنك تحويل مضلع إلى خط؟** Yes – call `LineString` on the polygon’s exterior ring and write the result to a new shapefile.  
- **هل أحتاج إلى ترخيص للإنتاج؟** A commercial license is required for production deployments; a free trial works for evaluation.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **هل يتوفر نسخة تجريبية؟** Absolutely – download a free trial from the Aspose site.

`LineString` هو نوع هندسي يمثل سلسلة من القطع الخطية المتصلة.

## ما هو “read shapefile c#”؟
`Document` هو الفئة الأساسية التي تمثل مجموعة بيانات GIS وتوفر الوصول إلى ميزاتها.  
قراءة shapefile في C# تعني تحميل ملف `.shp` إلى الذاكرة حتى تتمكن من الاستعلام، التعديل، أو تحويل هندساته. **كل ما عليك هو إنشاء كائن من فئة `Document` باستخدام مسار الملف، وتقوم Aspose.GIS بتحليل البنية الثنائية لك نيابةً عنك**، مكشوفةً الميزات عبر مجموعة سهلة الاستخدام. هذا النهج يلغي الحاجة إلى التعامل مع رؤوس الملفات منخفضة المستوى أو مصفوفات الإحداثيات يدويًا.

## لماذا تحويل مضلع إلى خط باستخدام Aspose.GIS؟
تحويل مضلع إلى linestring يحافظ على الحدود الخارجية الدقيقة مع إزالة الحلقات الداخلية، مما يمنحك تمثيلًا خطيًا نظيفًا. تقوم Aspose.GIS بمعالجة **مجموعات البيانات التي تصل إلى 500 ميغابايت في أقل من ثانيتين على خادم عادي**، مما يجعل التحويلات الدفعية سريعة وكفء من حيث الذاكرة. كما تحتفظ المكتبة بالمرجع المكاني الأصلي، لذا فإن الخطوط الناتجة تتطابق تمامًا مع أي طبقات GIS موجودة.

## المتطلبات المسبقة
قبل أن نغوص في البرنامج التعليمي، تأكد من توفر ما يلي:

- **Aspose.GIS Library** – قم بتنزيل وتثبيت مكتبة Aspose.GIS من [الموقع](https://releases.aspose.com/gis/net/).  
- **Shapefile Data** – احصل على ملف Shapefile متعدد الأضلاع جاهز للتحويل. إذا لم يكن لديك واحد، يمكنك العثور على بيانات عينة أو إنشاء ملف خاص بك.  
- **Development Environment** – قم بإعداد بيئة تطوير .NET الخاصة بك مع الأدوات اللازمة (Visual Studio، .NET SDK، إلخ).

## استيراد مساحات الأسماء
الفئة `Document` هي الكائن الأساسي في Aspose.GIS الذي يمثل مجموعة بيانات GIS وتوفر طرقًا لقراءة وكتابة ملفات shapefile. أضف مساحات الأسماء التالية في بداية ملف الكود الخاص بك:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## كيف تقرأ shapefile وتحول المضلع إلى linestring؟
حمّل ملف shapefile المضلع المصدر، استخرج الحلقة الخارجية لكل مضلع، أنشئ `LineString` من تلك الحلقة، واكتب النتيجة إلى ملف shapefile جديد – كل ذلك في خمس خطوات بسيطة. هذا النمط يعمل مع أي حجم مجموعة بيانات ويضمن الحفاظ على نظام الإحداثيات للمصدر في الوجهة.

### الخطوة 1: تعيين دليل المستند
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
استبدل `"Your Document Directory"` بالمسار الفعلي حيث يوجد ملف shapefile الخاص بك.

### الخطوة 2: فتح ملف Shapefile المصدر
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
هذا السطر يفتح ملف Shapefile المصدر من نوع Polygon حتى تتمكن من قراءة ميزاته.

### الخطوة 3: إنشاء ملف Shapefile الوجهة من نوع Linestring
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
هنا نقوم بإنشاء ملف Shapefile جديد من نوع Linestring لتخزين الهندسات المحوّلة.

### الخطوة 4: التكرار عبر ميزات المصدر
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
تقوم الحلقة بالتجول عبر كل ميزة مضلع في الملف الأصلي.

### الخطوة 5: تحويل المضلع إلى Linestring والكتابة إلى الوجهة
خاصية `ExteriorRing` تُعيد الحد الخارجي للمضلع كـ `LineString`.  
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
في هذا الكود نقوم بتحويل المضلع إلى خط (`LineString`) وإضافة الميزة الجديدة إلى ملف shapefile الوجهة.

## المشكلات الشائعة والنصائح
- **عدم تطابق نظام الإحداثيات** – تأكد من أن طبقات المصدر والوجهة تستخدم نفس المرجع المكاني؛ وإلا قد تظهر الخطوط مشوشة.  
- **ملفات كبيرة** – عند معالجة shapefiles ضخمة جدًا، فكر في تدفق الميزات بدلاً من تحميلها جميعًا إلى الذاكرة مرة واحدة.  
- **هندسات فارغة** – احرص على تجنب الميزات ذات الهندسات الفارغة لتفادي استثناءات وقت التشغيل.  
- **استخراج خطوط من المضلع** – إذا كنت تحتاج فقط إلى الحلقة الخارجية، استخدم خاصية `ExteriorRing`؛ بالنسبة للحلقات الداخلية، قم بالتكرار عبر `InteriorRings`.  

## الأسئلة المتكررة

**س: هل Aspose.GIS متوافق مع جميع إصدارات .NET؟**  
ج: نعم، يدعم Aspose.GIS .NET Framework 4.5+، .NET Core 3.1+، و .NET 5/6/7، مما يضمن تكاملًا سلسًا مع أطر التطوير الحديثة.

**س: هل يمكنني استخدام Aspose.GIS في المشاريع التجارية؟**  
ج: نعم، يمكنك ذلك. اشترِ ترخيصًا [هنا](https://purchase.aspose.com/buy) لإزالة قيود التقييم والحصول على الدعم الكامل.

**س: هل هناك أمثلة أو وثائق متاحة؟**  
ج: نعم، يمكنك العثور على وثائق شاملة وعينات كود على [صفحة الوثائق](https://reference.aspose.com/gis/net/).

**س: هل تتوفر نسخة تجريبية؟**  
ج: بالتأكيد – استكشف Aspose.GIS بنسخة تجريبية مجانية بزيارة [هذا الرابط](https://releases.aspose.com/).

**س: أين يمكنني طلب المساعدة أو الدعم؟**  
ج: زر [منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33) للحصول على مساعدة المجتمع والدعم الرسمي.

---

**آخر تحديث:** 2026-06-25  
**تم الاختبار مع:** Aspose.GIS for .NET (latest release)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [كيفية تحويل Shapefile إلى GeoJSON باستخدام Aspose.GIS for .NET](/gis/net/layer-management/extract-features-to-geojson/)
- [كيفية قراءة GeoJSON من تدفق باستخدام Aspose.GIS for .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [كيفية إنشاء هندسة مضلع باستخدام Aspose.GIS for .NET](/gis/net/geometry-creation/create-polygon-geometry/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}