---
title: تحويل GeoJSON إلى TopoJSON مع اسم كائن محدد
linktitle: تحويل GeoJSON إلى TopoJSON مع اسم كائن محدد
second_title: Aspose.GIS .NET API
description: تعرف على كيفية تحويل GeoJSON إلى TopoJSON باسم كائن محدد باستخدام Aspose.GIS for .NET. يوفر هذا البرنامج التعليمي دليلاً خطوة بخطوة لمعالجة البيانات الجغرافية بكفاءة.
type: docs
weight: 12
url: /ar/net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/
---
## مقدمة
يعد Aspose.GIS for .NET أداة قوية للتعامل مع البيانات الجغرافية في تطبيقات .NET. سواء كنت تقوم بتطوير تطبيق رسم خرائط، أو تحليل البيانات المكانية، أو معالجة ملفات Geojson، فإن Aspose.GIS يوفر مجموعة شاملة من الميزات لتبسيط سير عملك.
## المتطلبات الأساسية
قبل أن نتعمق في تحويل GeoJSON إلى TopoJSON باسم كائن محدد باستخدام Aspose.GIS for .NET، تأكد من أن لديك ما يلي:
### 1. قم بتثبيت Aspose.GIS لـ .NET
 توجه إلى[صفحة التحميل](https://releases.aspose.com/gis/net/) واحصل على أحدث إصدار من Aspose.GIS لـ .NET.
### 2. قم بإعداد بيئة التطوير الخاصة بك
تأكد من إعداد Visual Studio أو أي بيئة تطوير .NET أخرى على نظامك.
### 3. جهز ملف GeoJSON الخاص بك
لديك ملف GeoJSON الذي تريد تحويله إلى TopoJSON. إذا لم يكن لديك واحد، يمكنك استخدام أي نموذج لملف GeoJSON لهذا البرنامج التعليمي.

## استيراد مساحات الأسماء
قبل أن نبدأ عملية التحويل، فلنستورد مساحات الأسماء الضرورية:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## الخطوة 1: تحديد مسارات الملفات
```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithObjectName_out.topojson";
```
 يستبدل`"Your Document Directory"`باستخدام مسار الدليل الفعلي حيث يوجد ملف GeoJSON الخاص بك والمكان الذي تريد حفظ ملف TopoJSON المحول فيه.
## الخطوة 2: ضبط خيارات التحويل
```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // حدد اسم الكائن الذي يجب كتابة الميزات فيه
        DefaultObjectName = "name_of_the_object",
    }
};
```
 في هذه الخطوة نقوم بإنشاء`ConversionOptions` الكائن وتحديد`DefaultObjectName`، وهو اسم الكائن حيث يجب كتابة الميزات في ملف TopoJSON الناتج.
## الخطوة 3: إجراء التحويل
```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```
 وأخيراً نسمي`Convert` طريقة`VectorLayer` فئة، وتمرير مسار ملف GeoJSON المدخلات، وبرامج تشغيل الإدخال والإخراج، وخيارات التحويل.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تحويل GeoJSON إلى TopoJSON باسم كائن محدد باستخدام Aspose.GIS for .NET. باتباع هذه الخطوات، يمكنك إدارة البيانات الجغرافية ومعالجتها بكفاءة في تطبيقات .NET الخاصة بك.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.GIS for .NET في مشاريعي التجارية؟
نعم، يمكنك استخدام Aspose.GIS for .NET في كل من المشاريع التجارية والشخصية.
### هل تتوفر نسخة تجريبية مجانية من Aspose.GIS for .NET؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على دعم لـ Aspose.GIS لـ .NET؟
 يمكنك الحصول على الدعم من[منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33).
### كيف يمكنني شراء ترخيص Aspose.GIS لـ .NET؟
 يمكنك شراء ترخيص من[هنا](https://purchase.aspose.com/buy).
### هل أحتاج إلى ترخيص مؤقت للتقييم؟
 نعم يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).