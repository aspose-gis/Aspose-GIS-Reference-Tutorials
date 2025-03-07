---
title: تحويل ملف الشكل المضلع إلى Linestring
linktitle: تحويل ملف الشكل المضلع إلى Linestring
second_title: Aspose.GIS .NET API
description: اكتشف قوة Aspose.GIS لـ .NET وقم بتحويل ملفات الأشكال المضلعة إلى Linestrings بسهولة. تعزيز تطوير نظم المعلومات الجغرافية الخاصة بك اليوم!
weight: 18
url: /ar/net/layer-management/convert-polygon-shapefile-to-linestring/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل ملف الشكل المضلع إلى Linestring

## مقدمة
إذا كنت تعمل مع أنظمة المعلومات الجغرافية (GIS) في .NET، فإن Aspose.GIS هي مكتبة قوية يمكنها تبسيط مهامك. في هذا البرنامج التعليمي، سنرشدك خلال عملية تحويل ملف شكل مضلع إلى سلسلة خطوط باستخدام Aspose.GIS. يمكن أن يكون هذا مفيدًا بشكل خاص عندما تحتاج إلى استخراج الميزات الخطية من البيانات متعددة الأضلاع لتطبيقات متنوعة مثل تخطيط المسار أو تحليل الشبكة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
-  مكتبة Aspose.GIS: قم بتنزيل وتثبيت مكتبة Aspose.GIS من ملف[موقع إلكتروني](https://releases.aspose.com/gis/net/).
- بيانات ملف الشكل: احصل على ملف شكل مضلع جاهز للتحويل. إذا لم يكن لديك واحدة، يمكنك العثور على بيانات نموذجية أو إنشاء البيانات الخاصة بك.
- بيئة التطوير: قم بإعداد بيئة تطوير .NET الخاصة بك باستخدام الأدوات اللازمة.
## استيراد مساحات الأسماء
في كود C# الخاص بك، تحتاج إلى استيراد مساحات أسماء Aspose.GIS للوصول إلى الفئات والأساليب المطلوبة. أضف مساحات الأسماء التالية في بداية ملف التعليمات البرمجية الخاص بك:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## الخطوة 1: قم بتعيين دليل المستندات
```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
```
استبدل "دليل المستندات الخاص بك" بالمسار إلى الدليل الذي يوجد به ملف الشكل الخاص بك.
## الخطوة 2: افتح ملف الشكل المصدر
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // سيتم وضع بقية الكود هنا
}
```
تفتح هذه الخطوة ملف الأشكال المضلع المصدر للقراءة.
## الخطوة 3: إنشاء ملف شكل خط الوجهة
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // سيتم وضع بقية الكود هنا
}
```
هنا، نقوم بإنشاء ملف Linestring Shapefile جديد لكتابة البيانات المحولة.
## الخطوة 4: التكرار من خلال ميزات المصدر
```csharp
foreach (Feature sourceFeature in source)
{
    // سيتم وضع بقية الكود هنا
}
```
تتكرر هذه الحلقة خلال كل ميزة في ملف الشكل المضلع المصدر.
## الخطوة 5: تحويل المضلع إلى Linestring والكتابة إلى الوجهة
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
في هذه الخطوة، يتم تحويل كل ميزة مضلعة إلى سلسلة خطوط، وتتم كتابة ميزة سلسلة الخطوط الناتجة إلى ملف الشكل الوجهة.
## خاتمة
باتباع هذه الخطوات، يمكنك بسهولة تحويل Polygon Shapefile إلى Linestring باستخدام Aspose.GIS for .NET. تفتح هذه العملية إمكانيات جديدة لتحليل البيانات وتصورها في تطبيقات نظم المعلومات الجغرافية.

## الأسئلة الشائعة
### هل Aspose.GIS متوافق مع جميع إصدارات .NET؟
نعم، يدعم Aspose.GIS إصدارات مختلفة من .NET، مما يضمن التوافق مع بيئة التطوير الخاصة بك.
### هل يمكنني استخدام Aspose.GIS للمشاريع التجارية؟
 نعم يمكنك ذلك. لاستخدام Aspose.GIS في المشاريع التجارية، فكر في شراء ترخيص[هنا](https://purchase.aspose.com/buy).
### هل هناك أي أمثلة أو وثائق متاحة؟
 نعم، يمكنك العثور على وثائق وأمثلة شاملة على الموقع[صفحة التوثيق](https://reference.aspose.com/gis/net/).
### هل هناك نسخة تجريبية متاحة؟
 نعم، يمكنك استكشاف Aspose.GIS مع نسخة تجريبية مجانية من خلال زيارة الموقع[هذا الرابط](https://releases.aspose.com/).
### أين يمكنني طلب المساعدة أو الدعم؟
 قم بزيارة[منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33) لأي مساعدة أو استفسارات متعلقة بالدعم.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
