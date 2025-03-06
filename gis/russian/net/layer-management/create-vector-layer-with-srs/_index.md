---
title: Создайте векторный слой с помощью SRS
linktitle: Создайте векторный слой с помощью SRS
second_title: API Aspose.GIS .NET
description: Изучите Aspose.GIS for .NET — ваш ключ к плавной интеграции с ГИС. Легко создавайте векторные слои с помощью заданных систем пространственной привязки. Скачать сейчас!
weight: 13
url: /ru/net/layer-management/create-vector-layer-with-srs/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создайте векторный слой с помощью SRS

## Введение
Aspose.GIS for .NET — это мощная библиотека, которая позволяет разработчикам беспрепятственно работать с данными географической информационной системы (ГИС) в приложениях .NET. В этом уроке мы сосредоточимся на создании векторного слоя с системой пространственной привязки (SRS). К концу этого руководства вы сможете легко интегрировать возможности ГИС в свои проекты .NET.
## Предварительные условия
Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:
- Базовые знания разработки на C# и .NET.
-  Установлена библиотека Aspose.GIS for .NET. Вы можете скачать его[здесь](https://releases.aspose.com/gis/net/).
- Среда разработки настроена и готова.
## Импортировать пространства имен
Убедитесь, что в начале вашего файла C# импортированы необходимые пространства имен:
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
## Шаг 1. Настройка проецируемой пространственной системы отсчета
Давайте создадим проецируемую пространственную систему отсчета (SRS) на примере мировой проекции Меркатора. Следуй этим шагам:
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
## Шаг 2. Создайте векторный слой и добавьте объекты
Теперь давайте создадим шейп-файл и добавим объекты с указанным SRS:
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
        layer.Add(feature); // Это вызовет исключение, поскольку геометрия имеет другой SRS.
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## Шаг 3. Проверка пространственной системы отсчета
Наконец, давайте откроем слой и проверим его пространственную систему привязки:
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / Мир Меркатора"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Должен вернуть истину
}
```
Выполнив эти шаги, вы успешно создали векторный слой с указанной системой пространственной привязки, используя Aspose.GIS for .NET.
## Заключение
Интеграция функций ГИС в ваши .NET-приложения еще никогда не была такой простой благодаря Aspose.GIS. Благодаря возможности легко создавать векторные слои и управлять системами пространственной привязки вы можете улучшить свои проекты с помощью мощных геопространственных возможностей.
## Часто задаваемые вопросы
### Совместим ли Aspose.GIS со всеми форматами файлов ГИС?
 Aspose.GIS поддерживает различные форматы ГИС, включая Shapefile, GeoJSON, KML и другие. Проверить[документация](https://reference.aspose.com/gis/net/) для полного списка.
### Могу ли я использовать Aspose.GIS в веб-приложении?
Абсолютно! Aspose.GIS for .NET универсален и может использоваться в веб-приложениях, настольных приложениях и даже в мобильных приложениях.
### Где я могу получить поддержку для Aspose.GIS?
 Вы можете найти полезное сообщество на[Форум Aspose.GIS](https://forum.aspose.com/c/gis/33) по любым вопросам или проблемам, с которыми вы можете столкнуться.
### Доступна ли бесплатная пробная версия?
 Да, вы можете изучить возможности Aspose.GIS, получив бесплатную пробную версию.[здесь](https://releases.aspose.com/).
### Как я могу приобрести лицензию на Aspose.GIS?
 Чтобы приобрести лицензию, посетите сайт[страница покупки](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
