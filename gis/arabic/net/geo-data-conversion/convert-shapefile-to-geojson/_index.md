---
title: تحويل ملف الشكل إلى GeoJSON
linktitle: تحويل ملف الشكل إلى GeoJSON
second_title: Aspose.GIS .NET API
description: تعرف على كيفية تحويل Shapefile إلى GeoJSON في .NET بسهولة باستخدام Aspose.GIS. اتبع دليلنا خطوة بخطوة للتشغيل البيني للبيانات بشكل سلس.
weight: 15
url: /ar/net/geo-data-conversion/convert-shapefile-to-geojson/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل ملف الشكل إلى GeoJSON

## مقدمة
في مجال نظم المعلومات الجغرافية (GIS)، تعد قابلية التشغيل البيني للبيانات أمرًا بالغ الأهمية لتحقيق التكامل والتحليل السلس. تتمثل إحدى المهام الشائعة في تحويل Shapefiles، وهو تنسيق بيانات متجه جغرافي مكاني مستخدم على نطاق واسع، إلى GeoJSON، وهو تنسيق خفيف الوزن لتبادل البيانات الجغرافية المكانية. سيرشدك هذا البرنامج التعليمي خلال عملية تحويل Shapefile إلى GeoJSON دون عناء باستخدام مكتبة Aspose.GIS for .NET.
## المتطلبات الأساسية
قبل الغوص في عملية التحويل، تأكد من توفر المتطلبات الأساسية التالية:
### 1. تثبيت Aspose.GIS لمكتبة .NET
 قم بزيارة[Aspose.GIS لتوثيق .NET](https://reference.aspose.com/gis/net/) للحصول على إرشادات مفصلة حول كيفية تثبيت المكتبة وإعدادها في بيئة .NET الخاصة بك.
### 2. تنزيل ملف أشكال الإدخال
قم بتنزيل ملف شكل الإدخال الذي تنوي تحويله إلى GeoJSON. يمكنك الحصول على Shapefiles من مصادر مختلفة، بما في ذلك الوكالات الحكومية أو بوابات البيانات المفتوحة أو إنشاء ملفات خاصة بك باستخدام برامج GIS مثل QGIS أو ArcGIS.
### 3. المعرفة الأساسية ببرمجة C#
تعرف على أساسيات لغة البرمجة C#، حيث سيستخدم هذا البرنامج التعليمي أمثلة على أكواد C# لعملية التحويل.

## استيراد مساحات الأسماء
قبل متابعة التحويل، تأكد من استيراد مساحات الأسماء الضرورية للوصول إلى وظائف Aspose.GIS for .NET:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

الآن، دعونا نقسم عملية التحويل إلى خطوات متعددة:
## الخطوة 1: تحديد مسارات الإدخال والإخراج
أولاً، حدد المسارات لملف شكل الإدخال وملف GeoJSON الناتج:
```csharp
string dataDir = "Your Document Directory";
string shapefilePath = dataDir + "InputShapeFile.shp";
string jsonPath = dataDir + "output_out.json";
```
 تأكد من الاستبدال`"Your Document Directory"` باستخدام مسار الدليل الفعلي حيث توجد ملفاتك.
## الخطوة 2: إجراء التحويل
 الاستفادة من`VectorLayer.Convert` طريقة تنفيذ عملية التحويل:
```csharp
VectorLayer.Convert(shapefilePath, Drivers.Shapefile, jsonPath, Drivers.GeoJson);
```
يقوم سطر التعليمات البرمجية هذا بتحويل ملف الشكل للإدخال (`shapefilePath` ) إلى تنسيق GeoJSON ويحفظ الإخراج إلى المحدد`jsonPath`.

## خاتمة
يعد تحويل ملفات الأشكال إلى تنسيق GeoJSON مهمة أساسية في معالجة بيانات GIS. وبمساعدة مكتبة Aspose.GIS for .NET، تصبح هذه العملية مبسطة وفعالة. باتباع هذا البرنامج التعليمي، يمكنك إجراء هذا التحويل بسهولة داخل تطبيقات .NET الخاصة بك، مما يتيح إمكانية التشغيل البيني السلس وتحليل البيانات الجغرافية المكانية.
## الأسئلة الشائعة
### هل يمكنني تحويل عدة ملفات أشكال إلى GeoJSON دفعة واحدة باستخدام Aspose.GIS for .NET؟
نعم، يمكنك تكرار ملفات Shapefiles المتعددة وتحويلها إلى تنسيق GeoJSON باستخدام أسلوب مماثل موضح في هذا البرنامج التعليمي.
### هل يتوافق Aspose.GIS for .NET مع كافة إصدارات .NET Framework؟
يدعم Aspose.GIS for .NET الإصدار .NET Framework 4.5 والإصدارات الأحدث.
### هل يوفر Aspose.GIS for .NET الدعم للتنسيقات الجغرافية المكانية الأخرى بخلاف Shapefile وGeoJSON؟
نعم، يدعم Aspose.GIS for .NET نطاقًا واسعًا من التنسيقات الجغرافية المكانية، بما في ذلك GeoTIFF وKML وGML والمزيد.
### هل يمكنني تخصيص عملية التحويل، مثل تحديد النظام الإحداثي أو تعيينات السمات؟
نعم، يوفر Aspose.GIS for .NET خيارات شاملة لتخصيص عملية التحويل وفقًا لمتطلباتك.
### هل هناك إصدار تجريبي متاح لـ Aspose.GIS for .NET؟
 نعم، يمكنك الاستفادة من الإصدار التجريبي المجاني من Aspose.GIS for .NET من[موقع إلكتروني](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
