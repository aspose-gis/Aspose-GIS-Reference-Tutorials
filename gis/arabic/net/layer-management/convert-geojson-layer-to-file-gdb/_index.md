---
title: تم إزالة الغموض عن GeoJSON لتحويل ملف GDB
linktitle: تحويل طبقة GeoJSON إلى ملف GDB
second_title: Aspose.GIS .NET API
description: أطلق العنان للعجائب الجغرافية المكانية باستخدام Aspose.GIS لـ .NET! قم بتحويل طبقات GeoJSON بسهولة إلى قواعد بيانات جغرافية ملفية. جربه الآن! #Aspose #GIS
weight: 17
url: /ar/net/layer-management/convert-geojson-layer-to-file-gdb/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تم إزالة الغموض عن GeoJSON لتحويل ملف GDB

## مقدمة
في المجال الديناميكي لأنظمة المعلومات الجغرافية (GIS)، تعد القدرة على تحويل البيانات بسلاسة بين التنسيقات المختلفة أمرًا بالغ الأهمية. يظهر Aspose.GIS for .NET كحليف قوي، حيث يقدم مجموعة شاملة من الأدوات للتعامل مع البيانات الجغرافية المكانية دون عناء. في هذا البرنامج التعليمي، سنتعمق في عملية تحويل طبقة GeoJSON إلى قاعدة بيانات جغرافية ملفية (File GDB) باستخدام Aspose.GIS for .NET.
## المتطلبات الأساسية
قبل الشروع في هذه الرحلة الجغرافية المكانية، تأكد من توفر المتطلبات الأساسية التالية:
- معرفة عملية ببرمجة .NET.
-  تم تثبيت Aspose.GIS لـ .NET. إذا لم يكن الأمر كذلك، قم بتنزيله من[هنا](https://releases.aspose.com/gis/net/) واتبع تعليمات التثبيت.
## استيراد مساحات الأسماء
لبدء عملية التحويل، ابدأ باستيراد مساحات الأسماء الضرورية:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
الآن، دعونا نقسم العملية إلى دليل خطوة بخطوة:
## الخطوة 1: إعداد طبقة GeoJSON
ابدأ بإنشاء طبقة GeoJSON ذات السمات والميزات ذات الصلة. إليك مقتطف لإرشادك:
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // أضف السمات
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //بناء وإضافة الميزات
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```
## الخطوة 2: نسخ مجموعة بيانات الاختبار
للحفاظ على سلامة بيانات الاختبار الخاصة بك، قم بإنشاء نسخة من مجموعة البيانات. استخدم مقتطف الكود التالي:
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## الخطوة 3: تحويل GeoJSON إلى ملف GDB
الآن، حان الوقت لإجراء التحويل. استخدم الكود التالي:
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // نسخ السمات
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // إضافة ميزات
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## خاتمة
في هذا البرنامج التعليمي، استعرضنا التضاريس المثيرة للاهتمام لتحويل طبقة GeoJSON إلى قاعدة بيانات جغرافية ملفية باستخدام Aspose.GIS for .NET. مسلحًا بهذه المعرفة، أنت الآن مجهز للتعامل بسلاسة مع البيانات الجغرافية المكانية في تطبيقات .NET الخاصة بك.
## الأسئلة الشائعة
### هل Aspose.GIS متوافق مع أحدث إطار عمل .NET؟
نعم، Aspose.GIS متوافق مع أحدث إصدارات .NET Framework.
### هل يمكنني تحويل التنسيقات الجغرافية المكانية الأخرى باستخدام Aspose.GIS؟
قطعاً! يدعم Aspose.GIS مجموعة واسعة من التنسيقات الجغرافية المكانية لمعالجة البيانات المتنوعة.
### هل هناك نسخة تجريبية متاحة لـ Aspose.GIS؟
 نعم، يمكنك استكشاف وظائف Aspose.GIS عن طريق تنزيل الإصدار التجريبي[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على الدعم للاستفسارات المتعلقة بـ Aspose.GIS؟
 توجه إلى Aspose.GIS[المنتدى](https://forum.aspose.com/c/gis/33) للحصول على الدعم المخصص.
### هل يمكنني الحصول على ترخيص مؤقت لـ Aspose.GIS؟
 نعم، يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
