---
title: حدد متغير WKT عند الترجمة باستخدام Aspose.GIS
linktitle: حدد متغير WKT عند الترجمة
second_title: Aspose.GIS .NET API
description: تعرف على كيفية تحديد متغيرات WKT في Aspose.GIS لـ .NET للتحكم في تنسيق تمثيل البيانات المكانية ودقتها بشكل فعال.
weight: 19
url: /ar/net/geometry-processing/specify-wkt-variant-on-translation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# حدد متغير WKT عند الترجمة باستخدام Aspose.GIS

## مقدمة
Aspose.GIS for .NET هي مكتبة قوية تتيح للمطورين العمل مع بيانات نظام المعلومات الجغرافية (GIS) في تطبيقات .NET الخاصة بهم دون عناء. إحدى الميزات الأساسية التي يوفرها Aspose.GIS هي القدرة على تحديد متغير النص المعروف (WKT) أثناء الترجمة، مما يمكّن المستخدمين من التحكم في تنسيق ودقة تمثيلات البيانات المكانية. في هذا البرنامج التعليمي، سنستكشف كيفية تحديد متغيرات WKT خطوة بخطوة باستخدام Aspose.GIS for .NET.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. Aspose.GIS for .NET: قم بتنزيل Aspose.GIS for .NET وتثبيته من[صفحة التحميل](https://releases.aspose.com/gis/net/).
2. بيئة التطوير: تأكد من إعداد بيئة تطوير .NET.
3. المعرفة الأساسية: الإلمام بلغة البرمجة C# وإطار عمل .NET.

## استيراد مساحات الأسماء
قبل استخدام وظيفة Aspose.GIS في التعليمات البرمجية الخاصة بك، قم باستيراد مساحات الأسماء الضرورية:
```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```
## الخطوة 1: إنشاء كائن نقطة
 أولاً، قم بإنشاء`Point` كائن ذو قيم خطوط الطول والعرض والقياس الاختياري (M):
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## الخطوة 2: تعيين نظام الإسناد المكاني (SRS)
قم بتعيين نظام مرجعي مكاني (SRS) لكائن النقطة. في هذا المثال، نستخدم نظام الإسناد المكاني WGS84:
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## الخطوة 3: تحديد متغير WKT
 الآن، حدد متغير WKT للترجمة. يدعم Aspose.GIS العديد من متغيرات WKT، بما في ذلك`Iso`, `SimpleFeatureAccessOutdated` ، و`ExtendedPostGis`. اختر البديل المناسب بناءً على متطلباتك:
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // النقطة م (23.5732، 25.3421، 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // نقطة (23.5732، 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```
## الخطوة 4: التحكم في التنسيق الرقمي
يمكنك التحكم في التنسيق الرقمي للإحداثيات في تمثيل WKT. يوفر Aspose.GIS خيارات لتحديد الدقة العشرية:
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // النقطة م (23.5732 25.3420999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // النقطة م (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // النقطة م (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // النقطة م (23.573 25.342 40.3)
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تحديد متغيرات WKT عند الترجمة باستخدام Aspose.GIS for .NET. باتباع الخطوات الموضحة أعلاه، يمكن للمطورين التحكم بشكل فعال في تنسيق ودقة تمثيلات البيانات المكانية في تطبيقات .NET الخاصة بهم، مما يعزز مرونة وسهولة استخدام أنظمة المعلومات الجغرافية.
## الأسئلة الشائعة
### هل Aspose.GIS متوافق مع جميع إصدارات .NET؟
نعم، يدعم Aspose.GIS .NET Framework 4.0 والإصدارات الأحدث.
### هل يمكنني استخدام Aspose.GIS للمشاريع التجارية؟
نعم، يمكن استخدام Aspose.GIS لكل من المشاريع الشخصية والتجارية.
### هل يوفر Aspose.GIS الدعم لتنسيقات البيانات المكانية الأخرى؟
نعم، يدعم Aspose.GIS مجموعة واسعة من تنسيقات البيانات المكانية، بما في ذلك ESRI Shapefile وGeoJSON وKML.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.GIS؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.GIS من[هنا](https://releases.aspose.com/).
### أين يمكنني الحصول على المساعدة أو الدعم لـ Aspose.GIS؟
 يمكنك نشر استفساراتك أو طلب المساعدة من مجتمع Aspose.GIS على[المنتدى](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
