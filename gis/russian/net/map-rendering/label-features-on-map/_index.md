---
title: Освоение маркировки объектов с помощью Aspose.GIS for .NET
linktitle: Метки объектов на карте
second_title: API Aspose.GIS .NET
description: Изучите Aspose.GIS для .NET и овладейте искусством маркировки объектов на картах. Улучшите свои геопространственные визуализации без особых усилий. #Aspose #ГИС
type: docs
weight: 11
url: /ru/net/map-rendering/label-features-on-map/
---
## Введение
В мире визуализации геопространственных данных маркировка объектов на карте играет решающую роль в эффективной передаче информации. Aspose.GIS for .NET предоставляет мощный набор инструментов для беспрепятственного достижения этой цели. В этом уроке мы рассмотрим различные методы маркировки точек на карте с помощью Aspose.GIS, улучшая визуализацию карты информативными надписями.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
- Практическое знание C# и .NET Framework.
-  Установлен Aspose.GIS для .NET. Вы можете скачать его[здесь](https://releases.aspose.com/gis/net/).
- Файл GeoJSON, содержащий данные точек. Если у вас его нет, вы можете использовать образец файла для тестирования.
## Импортировать пространства имен
Убедитесь, что в вашем коде C# импортированы необходимые пространства имен для работы с Aspose.GIS:
```csharp
using System;
using System.Drawing;
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Labelings;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.GIS.Examples.CSharp;
using FontStyle = Aspose.Gis.Rendering.Labelings.FontStyle;
```
Теперь давайте разобьем каждый пример на несколько этапов в формате пошагового руководства.
##  Маркировка очков

### Шаг 1. Установите путь к каталогу ваших документов:
```csharp
string dataDir = "Your Document Directory";
```
### Шаг 2. Создайте карту с простым символом-маркером:
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Добавьте векторный слой и примените маркировку.
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Преобразуйте карту в файл SVG.
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## Стиль маркировки точек

Выполните шаги 1 и 2 из предыдущего примера.

### Шаг 1. Настройте стиль маркировки:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Остальные шаги остаются прежними
```
## Маркировка точек размещена

Выполните шаги 1 и 2 из первого примера.
### Шаг 2. Настройте размещение метки:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        HorizontalOffset = 2,
        VerticalOffset = 2,
        Rotation = 10,
    }
};
// Остальные шаги остаются прежними
```
## Маркировка точек на основе функций

Выполните шаги 1 и 2 из первого примера.

### Шаг 1. Внедрите маркировку на основе объектов:
```csharp
var pointLabeling = new SimpleLabeling("name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        VerticalOffset = 4,
        HorizontalOffset = 4,
    },
    FeatureBasedConfiguration = (feature, labeling) =>
    {
        // Получить население из объекта.
        var population = feature.GetValue<int>("population");
        // Размер шрифта рассчитывается и зависит от численности населения.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // Приоритет метки также зависит от численности населения.
        // Чем выше приоритет, тем более вероятно, что метка появится на выходном изображении.
        labeling.Priority = population;
    }
};
// Остальные шаги остаются прежними
```
## Заключение
Поздравляем! Вы узнали, как улучшить визуализацию карты путем надписывания объектов с помощью Aspose.GIS for .NET. Экспериментируйте с различными стилями и местами размещения, чтобы создавать привлекательные карты, адаптированные к вашим данным.
## Часто задаваемые вопросы
### Могу ли я маркировать объекты, используя собственные шрифты?
Да, вы можете настроить стиль и размер шрифта в конфигурации маркировки.
### Совместим ли Aspose.GIS с другими форматами данных ГИС?
Aspose.GIS поддерживает различные геопространственные форматы, включая GeoJSON, Shapefile и другие.
### Как я могу обрабатывать большие наборы данных для маркировки?
Aspose.GIS оптимизирован по производительности, но рассмотрите возможность использования конфигураций на основе объектов для определения приоритета меток на основе атрибутов данных.
### Доступны ли расширенные возможности размещения этикеток?
Да, вы можете точно настроить размещение меток, используя такие параметры, как вращение, опорные точки и смещения.
### Могу ли я автоматизировать создание этикеток в пакетном режиме?
Конечно, вы можете интегрировать Aspose.GIS в свои автоматизированные рабочие процессы для пакетного создания этикеток.