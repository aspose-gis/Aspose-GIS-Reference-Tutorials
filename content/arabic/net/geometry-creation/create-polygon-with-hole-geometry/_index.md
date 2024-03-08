---
title: إنشاء مضلع بهندسة الفتحات باستخدام Aspose.GIS
linktitle: إنشاء مضلع بهندسة الثقب
second_title: Aspose.GIS .NET API
description: تعرف على كيفية إنشاء مضلع بهندسة الفتحات باستخدام Aspose.GIS for .NET. برنامج تعليمي خطوة بخطوة مع أمثلة التعليمات البرمجية.
type: docs
weight: 13
url: /ar/net/geometry-creation/create-polygon-with-hole-geometry/
---
## مقدمة
في هذا البرنامج التعليمي، سنتعرف على عملية إنشاء مضلع بهندسة ثقب باستخدام Aspose.GIS for .NET. Aspose.GIS هي مكتبة قوية تمكن المطورين من العمل مع البيانات الجغرافية المكانية في تطبيقات .NET الخاصة بهم. 
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. Aspose.GIS for .NET Library: يمكنك تنزيله من[هنا](https://releases.aspose.com/gis/net/).
2. بيئة التطوير: تأكد من أن لديك بيئة تطوير تم إعدادها باستخدام Visual Studio أو أي برنامج .NET IDE آخر مثبت.
## استيراد مساحات الأسماء
أولاً، تحتاج إلى استيراد مساحات الأسماء اللازمة للعمل مع وظائف Aspose.GIS. هيريس كيفية القيام بذلك:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

الآن، لنبدأ في إنشاء مضلع بهندسة ثقب باستخدام Aspose.GIS for .NET.
## الخطوة 1: إنشاء كائن مضلع
```csharp
Polygon polygon = new Polygon();
```
## الخطوة 2: تحديد الحلقة الخارجية
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## الخطوة 3: تحديد الحلقة الداخلية (الفتحة)
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## الخطوة 4: تعيين الحلقة الخارجية وإضافة الحلقة الداخلية إلى المضلع
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إنشاء مضلع بهندسة ثقب باستخدام Aspose.GIS for .NET. ستكون هذه المعرفة مفيدة لمختلف التطبيقات الجغرافية المكانية حيث تكون هذه الأشكال الهندسية ضرورية.
## الأسئلة الشائعة
### 1. ما هو Aspose.GIS؟
Aspose.GIS هي مكتبة .NET تمكن المطورين من العمل مع البيانات الجغرافية المكانية، مما يسمح لهم بإنشاء وقراءة ومعالجة تنسيقات الملفات الجغرافية المكانية المختلفة.
### 2. هل يمكنني استخدام Aspose.GIS للمشاريع التجارية؟
 نعم، يمكنك استخدام Aspose.GIS لكل من المشاريع الشخصية والتجارية عن طريق شراء ترخيص. يزور[هنا](https://purchase.aspose.com/buy) لمزيد من التفاصيل.
### 3. هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.GIS؟
 نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من Aspose.GIS من[هنا](https://releases.aspose.com/).
### 4. أين يمكنني العثور على الدعم لـ Aspose.GIS؟
 يمكنك العثور على دعم لـ Aspose.GIS على الموقع[منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33).
### 5. كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.GIS؟
 يمكنك الحصول على ترخيص مؤقت لـ Aspose.GIS من[هنا](https://purchase.aspose.com/temporary-license/).