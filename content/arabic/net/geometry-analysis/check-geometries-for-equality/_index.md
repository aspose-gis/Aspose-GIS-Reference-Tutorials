---
title: التحقق من الأشكال الهندسية للمساواة
linktitle: التحقق من الأشكال الهندسية للمساواة
second_title: Aspose.GIS .NET API
description: تعرف على كيفية استخدام Aspose.GIS for .NET للتحقق من الأشكال الهندسية للمساواة في تطبيقات .NET الخاصة بك من خلال هذا البرنامج التعليمي الشامل.
type: docs
weight: 10
url: /ar/net/geometry-analysis/check-geometries-for-equality/
---
## مقدمة
Aspose.GIS for .NET هي مكتبة قوية تمكن المطورين من العمل مع البيانات الجغرافية المكانية بكفاءة في تطبيقات .NET الخاصة بهم. سواء كنت تقوم بإنشاء تطبيقات رسم الخرائط، أو أدوات التحليل المكاني، أو دمج الوظائف الجغرافية المكانية في البرامج الموجودة، فإن Aspose.GIS يوفر الأدوات التي تحتاجها لإنجاز المهمة.
## المتطلبات الأساسية
قبل الغوص في استخدام Aspose.GIS for .NET، تأكد من توفر المتطلبات الأساسية التالية:
### تم تثبيت .NET Framework
تأكد من تثبيت .NET Framework على نظامك. يمكنك تنزيله من موقع مايكروسوفت.
### Aspose.GIS لمكتبة .NET
 قم بتنزيل وتثبيت مكتبة Aspose.GIS for .NET من[صفحة التحميل](https://releases.aspose.com/gis/net/). اتبع تعليمات التثبيت المتوفرة في الوثائق.
### بيئة التطوير
قم بإعداد بيئة التطوير المفضلة لديك، مثل Visual Studio، لتطوير .NET.

## استيراد مساحات الأسماء
في تطبيق .NET الخاص بك، قم باستيراد مساحات الأسماء الضرورية لاستخدام وظيفة Aspose.GIS:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## الخطوة 1: تحديد الأشكال الهندسية
أولاً، حدد الأشكال الهندسية التي تريد مقارنتها. في هذا المثال، لدينا شكلان هندسيان:`geometry1` و`geometry2`.
```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```
## الخطوة 2: التحقق من الأشكال الهندسية للمساواة
 الآن، تحقق مما إذا كانت الأشكال الهندسية متساوية مكانيًا باستخدام`SpatiallyEquals` الطريقة المقدمة من Aspose.GIS.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // حقيقي
```
 سيتم طباعة هذا`True` إلى وحدة التحكم منذ ذلك الحين`geometry1` و`geometry2` متساوية مكانيا.
## الخطوة 3: تعديل الهندسة
 بعد ذلك، دعونا تعديل`geometry2` وذلك بإضافة نقطة جديدة.
```csharp
geometry2.AddPoint(3, 3);
```
## الخطوة 4: إعادة التحقق من المساواة
الآن، أعد التحقق من مساواة الأشكال الهندسية بعد التعديل.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // خطأ شنيع
```
 هذه المرة سيكون الناتج`False` نظرًا لأن الأشكال الهندسية لم تعد متساوية مكانيًا بسبب التعديل الذي تم إجراؤه`geometry2`.

## خاتمة
في الختام، يوفر Aspose.GIS for .NET أدوات قوية للعمل مع البيانات الجغرافية المكانية في تطبيقات .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة، يمكنك بسهولة التحقق من الأشكال الهندسية للمساواة باستخدام طرق Aspose.GIS.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.GIS for .NET مع أطر عمل .NET الأخرى؟
نعم، Aspose.GIS for .NET متوافق مع أطر عمل .NET المتنوعة، بما في ذلك .NET Core و.NET Standard.
### هل تتوفر نسخة تجريبية مجانية من Aspose.GIS for .NET؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[صفحة الإصدارات](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق Aspose.GIS for .NET؟
 يمكنك العثور على وثائق مفصلة عن[صفحة وثائق Aspose.GIS](https://reference.aspose.com/gis/net/).
### كيف يمكنني الحصول على دعم Aspose.GIS لـ .NET؟
 يمكنك الحصول على الدعم من منتدى مجتمع Aspose.GIS[هنا](https://forum.aspose.com/c/gis/33).
### هل يمكنني شراء ترخيص مؤقت لـ Aspose.GIS لـ .NET؟
 نعم، يمكنك شراء ترخيص مؤقت من[صفحة الشراء](https://purchase.aspose.com/temporary-license/).