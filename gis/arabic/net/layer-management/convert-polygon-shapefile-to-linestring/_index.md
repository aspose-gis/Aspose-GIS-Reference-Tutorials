---
date: 2026-01-10
description: تعلم كيفية قراءة ملفات shapefile باستخدام C# وتحويل ملف shapefile متعدد
  الأضلاع إلى خط باستخدام Aspose.GIS لـ .NET. عزّز تطوير نظم المعلومات الجغرافية الخاص
  بك بإرشادات واضحة خطوة بخطوة.
linktitle: Convert Polygon Shapefile to Linestring
second_title: Aspose.GIS .NET API
title: قراءة Shapefile بـ C# – تحويل Shapefile متعدد الأضلاع إلى خط
url: /ar/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قراءة Shapefile C# – تحويل ملف Shapefile متعدد الأضلاع إلى Linestring

## مقدمة
إذا كنت تعمل مع نظم المعلومات الجغرافية (GIS) في .NET، فإن **read shapefile c#** هي خطوة أولى شائعة قبل أن تتمكن من معالجة البيانات. تجعل Aspose.GIS هذه العملية بسيطة، مما يتيح لك تحويل ملف Shapefile متعدد الأضلاع إلى Linestring ببضع أسطر من الشيفرة فقط. هذه القدرة مفيدة بشكل خاص عندما تحتاج إلى استخراج الميزات الخطية من مجموعات البيانات المتعددة الأضلاع لمهام مثل تخطيط المسارات، تحليل الشبكات، أو تصور البيانات.

## إجابات سريعة
- **أي مكتبة تساعدك على قراءة shapefile c#؟** Aspose.GIS for .NET  
- **هل يمكنك تحويل مضلع إلى خط؟** نعم – استخدم `LineString` مع الحلقة الخارجية للمضلع.  
- **هل أحتاج إلى ترخيص للإنتاج؟** يلزم ترخيص تجاري للاستخدام في الإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6+.  
- **هل تتوفر نسخة تجريبية؟** بالتأكيد – قم بتحميل نسخة تجريبية مجانية من موقع Aspose.

## ما هو “read shapefile c#”؟
قراءة ملف shapefile في C# تعني تحميل ملف `.shp` إلى الذاكرة حتى تتمكن من الاستعلام أو التعديل أو تحويل هندساته. توفر Aspose.GIS واجهة برمجة تطبيقات بسيطة تُجرد التفاصيل منخفضة المستوى وتتيح لك التركيز على منطق GIS.

## لماذا تحويل المضلع إلى خط باستخدام Aspose.GIS؟
- **الحفاظ على الطوبولوجيا** – التحويل يحافظ على الحد الخارجي الدقيق لكل مضلع.  
- **الأداء** – المكتبة مُحسّنة لمجموعات البيانات الكبيرة، مما يجعل التحويلات الدفعية سريعة.  
- **المرونة** – يمكنك لاحقًا كتابة الخطوط إلى ملف shapefile آخر، GeoJSON، أو أي تنسيق مدعوم.

## المتطلبات المسبقة
قبل أن نبدأ في الشرح، تأكد من توفر ما يلي:

- **مكتبة Aspose.GIS** – قم بتحميل وتثبيت مكتبة Aspose.GIS من [الموقع الإلكتروني](https://releases.aspose.com/gis/net/).  
- **بيانات Shapefile** – احرص على وجود ملف Shapefile متعدد الأضلاع جاهز للتحويل. إذا لم يكن لديك واحد، يمكنك العثور على بيانات عينة أو إنشاء ملف خاص بك.  
- **بيئة التطوير** – قم بإعداد بيئة تطوير .NET الخاصة بك مع الأدوات اللازمة (Visual Studio، .NET SDK، إلخ).

## استيراد مساحات الأسماء
في شفرة C# الخاصة بك، تحتاج إلى استيراد مساحات أسماء Aspose.GIS للوصول إلى الفئات والطرق المطلوبة. أضف مساحات الأسماء التالية في بداية ملف الشيفرة الخاص بك:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## كيفية تحويل shapefile من مضلع إلى خط؟
فيما يلي دليل خطوة بخطوة يوضح **كيفية تحويل بيانات shapefile** من مضلع إلى خط باستخدام Aspose.GIS.

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
هذا السطر **يفتح ملف Shapefile المصدر المتعدد الأضلاع** حتى تتمكن من قراءة ميزاته.

### الخطوة 3: إنشاء ملف Shapefile الخط الوجهة
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
هنا **ننشئ ملف Shapefile جديد للخط** الذي سيخزن الهندسات المحوّلة.

### الخطوة 4: التكرار عبر ميزات المصدر
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
تقوم الحلقة بالتجول عبر كل ميزة مضلع في الملف الأصلي.

### الخطوة 5: تحويل المضلع إلى خط وكتابة النتيجة إلى الوجهة
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
في هذا الجزء **نحوّل المضلع إلى خط** (`LineString`) ونضيف الميزة الجديدة إلى ملف shapefile الوجهة.

## المشكلات الشائعة والنصائح
- **عدم تطابق نظام الإحداثيات** – تأكد من أن طبقات المصدر والوجهة تستخدم نفس المرجع المكاني؛ وإلا قد تظهر الخطوط مشوشة.  
- **الملفات الكبيرة** – عند معالجة shapefiles ضخمة، فكر في تدفق الميزات بدلاً من تحميلها جميعًا إلى الذاكرة مرة واحدة.  
- **الهندسات الفارغة** – احرص على تجنب الميزات ذات الهندسات الفارغة لتفادي الاستثناءات أثناء التشغيل.

## الأسئلة المتكررة

**س: هل Aspose.GIS متوافق مع جميع إصدارات .NET؟**  
ج: نعم، يدعم Aspose.GIS إصدارات .NET المختلفة، مما يضمن التوافق مع بيئة التطوير الخاصة بك.

**س: هل يمكنني استخدام Aspose.GIS في المشاريع التجارية؟**  
ج: نعم، يمكنك ذلك. لاستخدام Aspose.GIS في المشاريع التجارية، فكر في شراء ترخيص [من هنا](https://purchase.aspose.com/buy).

**س: هل هناك أمثلة أو توثيق متاح؟**  
ج: نعم، يمكنك العثور على توثيق شامل وأمثلة على [صفحة التوثيق](https://reference.aspose.com/gis/net/).

**س: هل تتوفر نسخة تجريبية؟**  
ج: نعم، يمكنك تجربة Aspose.GIS بنسخة تجريبية مجانية عبر زيارة [هذا الرابط](https://releases.aspose.com/).

**س: أين يمكنني طلب المساعدة أو الدعم؟**  
ج: زر [منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33) لأي استفسارات أو طلبات دعم.

---

**آخر تحديث:** 2026-01-10  
**تم الاختبار مع:** Aspose.GIS for .NET (أحدث إصدار)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}