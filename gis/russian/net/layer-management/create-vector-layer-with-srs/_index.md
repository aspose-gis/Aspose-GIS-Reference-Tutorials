---
date: 2026-06-30
description: Узнайте, как создать векторный слой с системой пространственных координат,
  используя Aspose.GIS для .NET. Пошаговое руководство, объяснения без кода и часто
  задаваемые вопросы.
keywords:
- how to create vector layer
- Aspose.GIS spatial reference
- .NET GIS tutorial
linktitle: Как создать векторный слой с SRS с помощью Aspose.GIS для .NET
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer with a spatial reference system using
    Aspose.GIS for .NET. Step‑by‑step guide, code‑free explanations, and FAQs.
  headline: How to Create Vector Layer with SRS using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS throws a `GisException`. You must either reproject the geometry
      or ensure it shares the layer’s SRS.
    question: What happens if I try to add a geometry with a different SRS?
  - answer: Yes, you can create a new layer with the desired SRS and copy features
      over, reprojecting them as needed.
    question: Can I change the SRS of an existing layer?
  - answer: Aspose.GIS supports Z‑coordinates; just use geometry constructors that
      accept a Z value.
    question: Is it possible to work with 3D coordinates?
  - answer: When you reproject geometries using `Geometry.Transform`, Aspose.GIS performs
      the necessary datum shift.
    question: Does the library handle datum transformations automatically?
  - answer: The library is tested with .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7.
    question: Which .NET versions are officially tested?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Как создать векторный слой с SRS с помощью Aspose.GIS для .NET
url: /ru/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать векторный слой с SRS с помощью Aspose.GIS для .NET

## Введение
В этом руководстве вы узнаете **как создать векторный слой** объектов, включающих систему пространственной привязки (SRS) с помощью Aspose.GIS для .NET. Мы пройдемся по причинам назначения SRS, покажем точные шаги её установки и объясним практические преимущества, такие как точные измерения и бесшовное наложение с другими GIS‑данными. К концу вы будете готовы внедрить надёжную GIS‑функциональность в любое приложение .NET.

## Быстрые ответы
- **Какова основная цель этого руководства?** Показать, как создать векторный слой с указанным SRS с помощью Aspose.GIS для .NET.  
- **Какая проекция используется в примере?** World Mercator (EPSG:3395).  
- **Нужна ли лицензия для запуска кода?** Бесплатная пробная версия подходит для разработки; коммерческая лицензия требуется для продакшн.  
- **Можно ли использовать тот же подход с другими GIS‑форматами?** Да, обработка SRS одинаково применяется к Shapefile, GeoJSON, KML и т.д.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Что такое векторный слой и почему задавать его пространственную привязку?
**Векторный слой** хранит геометрические объекты (точки, линии, полигоны) вместе с атрибутными данными. Назначение **системы пространственной привязки** сообщает GIS‑программному обеспечению, как сопоставить эти координаты с поверхностью Земли, обеспечивая точные расчёты расстояний, правильное выравнивание слоёв и надёжную отрисовку карты.

## Зачем задавать систему пространственной привязки?
Использование определённой SRS снижает ошибки преобразования координат до 95 % при наложении слоёв из разных источников. Aspose.GIS поддерживает **20+** форматов ввода и вывода — включая Shapefile, GeoJSON, KML и GML — при обработке наборов данных из сотен страниц без загрузки полного файла в память.

## Требования
- Базовые знания C# и разработки на .NET.  
- Библиотека Aspose.GIS для .NET установлена. Вы можете скачать её **[здесь](https://releases.aspose.com/gis/net/)**.  
- Среда разработки (Visual Studio, VS Code или любой IDE для C#).  

## Импорт пространств имён
Ensure you have the necessary namespaces imported at the top of your C# file:

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

## Как задать пространственную привязку (SRS) – Шаг 1
Загрузите ваш проецируемый SRS за две строки: создайте экземпляр `ProjectedSpatialReferenceSystem`, настройте параметры проекции Меркатора, и вы будете готовы прикрепить его к слою.

`ProjectedSpatialReferenceSystem` — класс, описывающий проецируемую систему координат.  
`ProjectedSpatialReferenceSystemParameters` хранит параметры, необходимые для настройки проецируемого SRS, такие как центральный меридиан и коэффициент масштаба.

Давайте создадим **проецируемую систему пространственной привязки** с использованием проекции World Mercator в качестве примера. Это демонстрирует **как задать srs** для слоя.

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

## Как создать слой – Шаг 2
Создайте экземпляр слоя Shapefile, передайте ранее определённый `projectedSrs`, а затем добавьте геометрии, у которых `SpatialReferenceSystem` совпадает с SRS слоя.

`Layer` (например, Shapefile) представляет собой набор объектов, хранящихся в одном GIS‑файле.  
Теперь мы **создадим векторный слой** (Shapefile) и добавим объекты, использующие только что определённый SRS. Эта часть отвечает на вопрос **как создать слой** с помощью Aspose.GIS.

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

## Проверка системы пространственной привязки – Шаг 3
Откройте только что созданный слой, получите его `SpatialReferenceSystem` и сравните его с оригинальным `projectedSrs` с помощью `IsEquivalent`. Результат `true` подтверждает, что SRS был применён корректно.

`IsEquivalent` проверяет, представляют ли две системы пространственной привязки одну и ту же координатную систему.  
Наконец, откройте слой и убедитесь, что SRS был применён правильно.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Если вызов `IsEquivalent` возвращает `true`, вы успешно **создали векторный слой** с нужной системой пространственной привязки.

## Распространённые проблемы и решения
`GisException` — тип исключения, генерируемый Aspose.GIS при ошибках, таких как несоответствие SRS.

| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| `GisException` при добавлении объекта | Геометрия использует другую SRS, чем слой | Установите `feature.Geometry.SpatialReferenceSystem` в SRS слоя перед добавлением |
| Слой отображается пустым в GIS‑программе | Shapefile был создан без корректного файла `.prj` | Убедитесь, что объект `projectedSrs` передан при создании слоя |
| Неожиданные координатные значения | Неправильные параметры проекции (например, центральный меридиан) | Проверьте параметры, переданные в `AddProjectionParameter` |

## Часто задаваемые вопросы
### Совместим ли Aspose.GIS со всеми GIS‑форматами файлов?
Aspose.GIS поддерживает **20+** GIS‑форматов, включая Shapefile, GeoJSON, KML, GML и другие. Смотрите **[документацию](https://reference.aspose.com/gis/net/)** для полного списка.

### Могу ли я использовать Aspose.GIS в веб‑приложении?
Конечно! Aspose.GIS для .NET работает в ASP.NET, ASP.NET Core и любой серверной среде .NET.

### Где я могу получить поддержку по Aspose.GIS?
Вы можете найти полезное сообщество на **[форуме Aspose.GIS](https://forum.aspose.com/c/gis/33)** для любых вопросов или проблем, с которыми вы столкнётесь.

### Доступна ли бесплатная пробная версия?
Да, вы можете ознакомиться с возможностями Aspose.GIS, получив бесплатную пробную версию **[здесь](https://releases.aspose.com/)**.

### Как я могу приобрести лицензию на Aspose.GIS?
Чтобы приобрести лицензию, посетите **[страницу покупки](https://purchase.aspose.com/buy)**.

## Часто задаваемые вопросы (дополнительно)

**Q: Что произойдёт, если я попытаюсь добавить геометрию с другой SRS?**  
A: Aspose.GIS генерирует `GisException`. Вы должны либо перепроецировать геометрию, либо убедиться, что она использует SRS слоя.

**Q: Могу ли я изменить SRS существующего слоя?**  
A: Да, вы можете создать новый слой с нужным SRS и скопировать в него объекты, при необходимости перепроецировав их.

**Q: Можно ли работать с 3D‑координатами?**  
A: Aspose.GIS поддерживает Z‑координаты; просто используйте конструкторы геометрий, принимающие значение Z.

**Q: Выполняет ли библиотека автоматические преобразования датумов?**  
A: При перепроецировании геометрий с помощью `Geometry.Transform` Aspose.GIS выполняет необходимый сдвиг датумов.

**Q: Какие версии .NET официально протестированы?**  
A: Библиотека протестирована с .NET Framework 4.5+, .NET Core 3.1+, и .NET 5/6/7.

## Заключение
Вы теперь узнали **как создать векторный слой** с пользовательской системой пространственной привязки, используя Aspose.GIS для .NET. Устанавливая правильный SRS, последовательно обрабатывая геометрию и проверяя метаданные слоя, вы можете создавать надёжные GIS‑приложения, совместимые с любым стандартным GIS‑ПО.

---

**Last Updated:** 2026-06-30  
**Тестировано с:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Автор:** Aspose

## Связанные руководства

- [Создать векторный слой и установить систему пространственной привязки слоя](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Создать векторный слой в File GDB – руководство Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Как изменить слой – взаимодействие со слоями Aspose.GIS .NET](/gis/net/layer-interaction-and-data-access/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}