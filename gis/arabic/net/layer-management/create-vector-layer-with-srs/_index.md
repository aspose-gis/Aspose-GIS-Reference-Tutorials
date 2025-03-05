---
title: إنشاء طبقة متجهة باستخدام SRS
linktitle: إنشاء طبقة متجهة باستخدام SRS
second_title: Aspose.GIS .NET API
description: استكشف Aspose.GIS for .NET - مفتاحك للتكامل السلس لنظم المعلومات الجغرافية. قم بإنشاء طبقات متجهة دون عناء باستخدام أنظمة الإسناد المكاني المحددة. التحميل الان!
type: docs
weight: 13
url: /ar/net/layer-management/create-vector-layer-with-srs/
---
## مقدمة
Aspose.GIS for .NET هي مكتبة قوية تمكن المطورين من العمل مع بيانات نظام المعلومات الجغرافية (GIS) بسلاسة في تطبيقات .NET. في هذا البرنامج التعليمي، سنركز على إنشاء طبقة متجهة باستخدام نظام الإسناد المكاني (SRS). بحلول نهاية هذا الدليل، ستكون قادرًا على دمج إمكانات نظم المعلومات الجغرافية بسهولة في مشاريع .NET الخاصة بك.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- المعرفة الأساسية بتطوير C# و.NET.
-  تم تثبيت Aspose.GIS لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/gis/net/).
- تم إعداد بيئة التطوير وجاهزة.
## استيراد مساحات الأسماء
تأكد من استيراد مساحات الأسماء الضرورية في بداية ملف C# الخاص بك:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## الخطوة 1: إعداد نظام الإسناد المكاني المتوقع
لنقم بإنشاء نظام الإسناد المكاني المسقط (SRS) باستخدام إسقاط World Mercator كمثال. اتبع الخطوات التالية:
```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```
## الخطوة 2: إنشاء طبقة متجهة وإضافة ميزات
الآن، لنقم بإنشاء ملف شكل وإضافة ميزات باستخدام SRS المحدد:
```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // سيؤدي هذا إلى حدوث استثناء نظرًا لأن الشكل الهندسي له SRS مختلف
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## الخطوة 3: التحقق من نظام الإسناد المكاني
أخيرًا، دعونا نفتح الطبقة ونتحقق من نظام الإسناد المكاني الخاص بها:
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / ميركاتور العالمية"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // يجب أن يعود صحيحا
}
```
باتباع هذه الخطوات، تكون قد نجحت في إنشاء طبقة متجهة باستخدام نظام إسناد مكاني محدد باستخدام Aspose.GIS for .NET.
## خاتمة
لم يكن دمج وظائف نظم المعلومات الجغرافية في تطبيقات .NET أسهل من أي وقت مضى، وذلك بفضل Aspose.GIS. من خلال القدرة على إنشاء طبقات متجهة وإدارة أنظمة الإسناد المكاني دون عناء، يمكنك تحسين مشاريعك بإمكانات جغرافية مكانية قوية.
## الأسئلة الشائعة
### هل Aspose.GIS متوافق مع جميع تنسيقات ملفات GIS؟
 يدعم Aspose.GIS العديد من تنسيقات GIS، بما في ذلك Shapefile وGeoJSON وKML والمزيد. افحص ال[توثيق](https://reference.aspose.com/gis/net/) للحصول على القائمة الكاملة.
### هل يمكنني استخدام Aspose.GIS في تطبيق ويب؟
قطعاً! يعد Aspose.GIS for .NET متعدد الاستخدامات ويمكن استخدامه في تطبيقات الويب وتطبيقات سطح المكتب وحتى تطبيقات الهاتف المحمول.
### أين يمكنني الحصول على الدعم لـ Aspose.GIS؟
 يمكنك العثور على مجتمع مفيد في[منتدى Aspose.GIS](https://forum.aspose.com/c/gis/33) لأية استفسارات أو مشاكل قد تواجهها.
### هل هناك نسخة تجريبية مجانية متاحة؟
 نعم، يمكنك استكشاف ميزات Aspose.GIS من خلال الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
### كيف يمكنني شراء ترخيص Aspose.GIS؟
 لشراء ترخيص، قم بزيارة[صفحة الشراء](https://purchase.aspose.com/buy).