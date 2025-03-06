---
title: حساب الأشكال الهندسية في الهندسة باستخدام Aspose.GIS
linktitle: عد الأشكال الهندسية في الهندسة
second_title: Aspose.GIS .NET API
description: تعرف على كيفية حساب الأشكال الهندسية في الشكل الهندسي باستخدام Aspose.GIS for .NET. برنامج تعليمي خطوة بخطوة مع أمثلة التعليمات البرمجية للمطورين.
weight: 23
url: /ar/net/geometry-creation/count-geometries-in-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# حساب الأشكال الهندسية في الهندسة باستخدام Aspose.GIS

## مقدمة
يعد Aspose.GIS for .NET أداة قوية للمطورين الذين يسعون إلى دمج الوظائف الجغرافية المكانية في تطبيقات .NET الخاصة بهم. سواء كنت تقوم بإنشاء برامج رسم خرائط، أو خدمات تعتمد على الموقع، أو أدوات التحليلات المكانية، فإن Aspose.GIS يوفر مجموعة شاملة من الميزات لتلبية احتياجاتك. في هذا البرنامج التعليمي، سوف نستكشف كيفية حساب الأشكال الهندسية داخل الشكل الهندسي باستخدام Aspose.GIS for .NET.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1. Visual Studio: تأكد من تثبيت Visual Studio على نظامك.
2. Aspose.GIS for .NET: قم بتنزيل Aspose.GIS for .NET وتثبيته من[صفحة التحميل](https://releases.aspose.com/gis/net/).
3. المعرفة الأساسية بـ C#: تعرف على أساسيات لغة البرمجة C#.

## استيراد مساحات الأسماء
قبل البدء في البرمجة، تحتاج إلى استيراد مساحات الأسماء الضرورية للوصول إلى وظيفة Aspose.GIS.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## الخطوة 2: إنشاء هندسة النقطة
```csharp
Point point = new Point(40.7128, -74.006);
```
 هنا نقوم بإنشاء`Point` الهندسة مع خط العرض 40.7128 وخط الطول -74.006.
## الخطوة 3: إنشاء هندسة LineString
```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```
 هذه الخطوة تخلق`LineString` الهندسة ويضيف نقطتين إليها.
## الخطوة 4: إنشاء مجموعة هندسية
```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```
 نقوم بعد ذلك بإنشاء ملف`GeometryCollection` وأضف إليها الأشكال الهندسية للنقطة والخط التي تم إنشاؤها مسبقًا.
## الخطوة 5: عد الأشكال الهندسية
```csharp
int geometriesCount = geometryCollection.Count;
```
 تقوم هذه الخطوة بحساب عدد الأشكال الهندسية داخل`GeometryCollection`.
## الخطوة 6: عرض العدد
```csharp
Console.WriteLine(geometriesCount); // 2
```
 وأخيرًا، نقوم بطباعة عدد الأشكال الهندسية، وهو في هذه الحالة`2`.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية حساب الأشكال الهندسية داخل الشكل الهندسي باستخدام Aspose.GIS for .NET. باتباع هذه الخطوات، يمكنك دمج وظائف الجغرافيا المكانية في تطبيقات .NET الخاصة بك بسهولة.
## الأسئلة الشائعة
### هل Aspose.GIS for .NET مناسب لكل من تطبيقات سطح المكتب والويب؟
نعم، يمكن استخدام Aspose.GIS for .NET في كل من تطبيقات سطح المكتب والويب بسلاسة.
### هل يمكنني إجراء استعلامات مكانية باستخدام Aspose.GIS لـ .NET؟
بالتأكيد، يوفر Aspose.GIS for .NET دعمًا قويًا لإجراء الاستعلامات المكانية على الأشكال الهندسية.
### هل يدعم Aspose.GIS for .NET تنسيقات ملفات GIS المختلفة؟
نعم، يدعم Aspose.GIS for .NET نطاقًا واسعًا من تنسيقات ملفات GIS بما في ذلك SHP، وKML، وGeoJSON.
### هل تتوفر نسخة تجريبية مجانية من Aspose.GIS for .NET؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[موقع إلكتروني](https://releases.aspose.com/).
### أين يمكنني العثور على دعم لـ Aspose.GIS لـ .NET؟
 يمكنك العثور على الدعم على[منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
