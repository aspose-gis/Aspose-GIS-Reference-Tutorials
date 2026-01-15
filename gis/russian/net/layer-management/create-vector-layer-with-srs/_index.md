---
date: 2026-01-15
description: Изучите Aspose.GIS для .NET, чтобы создать векторный слой с системой
  пространственных координат. Узнайте, как задать СК, создать слой и управлять GIS‑данными.
  Скачайте сейчас!
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: Создать векторный слой с СКС
url: /ru/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание векторного слоя с СКП

## Введение
Aspose.GIS for .NET — мощная библиотека, позволяющая разработчикам **создавать векторные слои** и работать с данными геоинформационных систем (GIS) непосредственно в .NET‑приложениях. В этом руководстве мы пошагово покажем, как создать векторный слой с системой координат (СКП), зачем это нужно и какие преимущества это даёт в реальных проектах. К концу руководства вы сможете уверенно интегрировать возможности GIS в свои .NET‑решения.

## Быстрые ответы
- **Какова основная цель этого руководства?** Показать, как создать векторный слой с указанным СКП, используя Aspose.GIS for .NET.  
- **Какая проекция используется в примере?** World Mercator (EPSG:3395).  
- **Нужна ли лицензия для запуска кода?** Для разработки достаточно бесплатной пробной версии; для продакшна требуется коммерческая лицензия.  
- **Можно ли применить тот же подход к другим форматам GIS?** Да, обработка СКП одинаково работает с Shapefile, GeoJSON, KML и др.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Что такое векторный слой и зачем задавать его систему координат?
**Векторный слой** хранит геометрические объекты (точки, линии, полигоны) вместе с атрибутными данными. Указание **системы координат** (СКП) сообщает GIS‑программам, как интерпретировать эти координаты на поверхности Земли. Правильный СКП обеспечивает точные измерения, корректное наложение слоёв и надёжную визуализацию карт.

## Предварительные требования
Прежде чем приступить, убедитесь, что у вас есть:

- Базовые знания C# и разработки под .NET.  
- Библиотека Aspose.GIS for .NET, установленная в проект. Скачать её можно **[здесь](https://releases.aspose.com/gis/net/)**.  
- Среда разработки (Visual Studio, VS Code или любой другой IDE для C#).  

## Подключение пространств имён
Убедитесь, что в начале вашего C#‑файла импортированы необходимые пространства имён:

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

## Как задать систему координат (СКП) — Шаг 1
Создадим **проецируемую систему координат**, используя проекцию World Mercator в качестве примера. Это демонстрирует, **как задать СКП** для слоя.

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

## Как создать слой — Шаг 2
Теперь **создадим векторный слой** (Shapefile) и добавим в него объекты, использующие только что определённый СКП. Этот раздел отвечает на вопрос, **как создать слой** с помощью Aspose.GIS.

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
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

> **Полезный совет:** Перед добавлением всегда проверяйте, что `SpatialReferenceSystem` геометрии совпадает с СКП слоя. Несоответствие вызывает `GisException`, как показано выше.

## Проверка системы координат — Шаг 3
В конце откроем слой и убедимся, что СКП была применена корректно.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Если вызов `IsEquivalent` возвращает `true`, вы успешно **создали векторный слой** с нужной системой координат.

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|----------|---------|---------|
| `GisException` при добавлении объекта | Геометрия использует другую СКП, чем слой | Установите `feature.Geometry.SpatialReferenceSystem` в СКП слоя перед добавлением |
| Слой пустой в GIS‑программе | Shapefile создан без корректного файла `.prj` | Передайте объект `projectedSrs` при создании слоя |
| Неправильные координаты | Ошибочные параметры проекции (например, центральный меридиан) | Проверьте параметры, передаваемые в `AddProjectionParameter` |

## Часто задаваемые вопросы
### Совместима ли Aspose.GIS со всеми форматами GIS‑файлов?
Aspose.GIS поддерживает различные форматы, включая Shapefile, GeoJSON, KML и другие. Полный список см. в **[документации](https://reference.aspose.com/gis/net/)**.

### Можно ли использовать Aspose.GIS в веб‑приложении?
Конечно! Aspose.GIS for .NET универсальна и подходит для веб‑, настольных и даже мобильных приложений.

### Где получить поддержку по Aspose.GIS?
Вопросы и проблемы можно обсудить в сообществе **[форум Aspose.GIS](https://forum.aspose.com/c/gis/33)**.

### Есть ли бесплатная пробная версия?
Да, её можно получить **[здесь](https://releases.aspose.com/)**.

### Как приобрести лицензию на Aspose.GIS?
Для покупки перейдите на страницу **[покупки](https://purchase.aspose.com/buy)**.

## Дополнительные часто задаваемые вопросы

**В: Что произойдёт, если попытаться добавить геометрию с иной СКП?**  
О: Aspose.GIS бросит `GisException`. Нужно либо пере проецировать геометрию, либо обеспечить совпадение СКП с слоем.

**В: Можно ли изменить СКП уже существующего слоя?**  
О: Да, создайте новый слой с нужной СКП и скопируйте в него объекты, при необходимости пере проецировав их.

**В: Поддерживает ли библиотека 3‑мерные координаты?**  
О: Да, Aspose.GIS работает с Z‑координатами; используйте конструкторы геометрий, принимающие значение Z.

**В: Выполняет ли библиотека автоматические трансформации датумов?**  
О: При пере проекции геометрий через `Geometry.Transform` Aspose.GIS автоматически применяет необходимые смещения датумов.

**В: Какие версии .NET официально протестированы?**  
О: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Заключение
Теперь вы знаете, как **создать векторный слой** с пользовательской системой координат, используя Aspose.GIS for .NET. Правильная настройка СКП, согласованная работа с геометрией и проверка метаданных слоя позволяют создавать надёжные GIS‑приложения, совместимые со всеми стандартными GIS‑инструментами.

---

**Последнее обновление:** 2026-01-15  
**Тестировано с:** Aspose.GIS 24.11 for .NET (на момент написания)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}