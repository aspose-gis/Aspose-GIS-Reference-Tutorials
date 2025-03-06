---
title: Преобразование GeoJSON в файл GDB раскрыто
linktitle: Преобразование слоя GeoJSON в файл GDB
second_title: API Aspose.GIS .NET
description: Откройте для себя геопространственные чудеса с помощью Aspose.GIS для .NET! Легко конвертируйте слои GeoJSON в файловые базы геоданных. Попробуй это сейчас! #Aspose #ГИС
weight: 17
url: /ru/net/layer-management/convert-geojson-layer-to-file-gdb/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Преобразование GeoJSON в файл GDB раскрыто

## Введение
В динамичной сфере географических информационных систем (ГИС) возможность плавного преобразования данных между различными форматами имеет решающее значение. Aspose.GIS for .NET становится мощным союзником, предлагая полный набор инструментов для легкой обработки геопространственных данных. В этом уроке мы углубимся в процесс преобразования слоя GeoJSON в файловую базу геоданных (файл GDB) с использованием Aspose.GIS для .NET.
## Предварительные условия
Прежде чем отправиться в это геопространственное путешествие, убедитесь, что у вас есть следующие предварительные условия:
- Практические знания программирования .NET.
-  Установлен Aspose.GIS для .NET. Если нет, загрузите его с[здесь](https://releases.aspose.com/gis/net/) и следуйте инструкциям по установке.
## Импортировать пространства имен
Чтобы начать процесс преобразования, начните с импорта необходимых пространств имен:
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
Теперь давайте разобьем весь процесс на пошаговое руководство:
## Шаг 1. Настройте слой GeoJSON.
Начните с создания слоя GeoJSON с соответствующими атрибутами и функциями. Вот фрагмент, который поможет вам:
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Добавить атрибуты
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //Создайте и добавьте функции
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
## Шаг 2. Скопируйте набор тестовых данных
Чтобы сохранить целостность тестовых данных, создайте копию набора данных. Используйте следующий фрагмент кода:
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## Шаг 3. Преобразование GeoJSON в файл GDB
Теперь пришло время выполнить преобразование. Используйте следующий код:
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Копировать атрибуты
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Добавить функции
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## Заключение
В этом уроке мы рассмотрели интригующую область преобразования слоя GeoJSON в файловую базу геоданных с использованием Aspose.GIS для .NET. Вооружившись этими знаниями, вы теперь можете легко манипулировать геопространственными данными в своих .NET-приложениях.
## Часто задаваемые вопросы
### Совместим ли Aspose.GIS с последней версией .NET Framework?
Да, Aspose.GIS совместим с последними версиями .NET Framework.
### Могу ли я конвертировать другие геопространственные форматы с помощью Aspose.GIS?
Абсолютно! Aspose.GIS поддерживает широкий спектр геопространственных форматов для универсального манипулирования данными.
### Доступна ли пробная версия для Aspose.GIS?
 Да, вы можете изучить функциональные возможности Aspose.GIS, загрузив пробную версию.[здесь](https://releases.aspose.com/).
### Как я могу получить поддержку по запросам, связанным с Aspose.GIS?
 Перейдите в Aspose.GIS.[Форум](https://forum.aspose.com/c/gis/33) за специальную поддержку.
### Могу ли я получить временную лицензию на Aspose.GIS?
 Да, вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
