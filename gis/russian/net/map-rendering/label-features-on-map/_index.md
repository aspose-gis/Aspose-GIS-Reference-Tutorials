---
date: 2026-07-14
description: Узнайте, как создать маркированную карту на C# с использованием Aspose.GIS
  для .NET, с custom label style options для large dataset labeling.
keywords:
- create labeled map csharp
- label points on map
- label map features
lastmod: 2026-07-14
linktitle: Label Features на карте
og_description: Создайте маркированную карту на C# с использованием Aspose.GIS для
  .NET. Откройте fast labeling, custom styles и large‑dataset handling в кратком руководстве.
og_image_alt: Screenshot of a labeled map generated with Aspose.GIS in C#
og_title: Создание маркированной карты на C# с Aspose.GIS – Quick Guide
schemas:
- author: Aspose
  dateModified: '2026-07-14'
  description: Learn how to create labeled map C# using Aspose.GIS for .NET, with
    custom label style options for large dataset labeling.
  headline: Create Labeled Map in C# with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes. Set `FontFamily` and `FontStyle` in the `SimpleLabeling` configuration
      to any TrueType or OpenType font installed on the host machine.
    question: Can I label features using custom fonts?
  - answer: Absolutely. It natively reads and writes GeoJSON, Shapefile, KML, GML,
      CSV, and more than 30 additional formats.
    question: Is Aspose.GIS compatible with other GIS data formats?
  - answer: Use `FeatureBasedConfiguration` to assign a numeric priority (e.g., population)
      and let the engine automatically drop low‑priority labels when space is constrained.
    question: How can I handle large datasets for labeling?
  - answer: Yes. `PointLabelPlacement` lets you control anchor points, offsets, rotation,
      and even curvature for line and polygon labels.
    question: Are there advanced label placement options available?
  - answer: Certainly. Wrap the map rendering code in a loop or background service
      to process multiple layers or files without manual intervention.
    question: Can I automate label generation in a batch process?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- label map
- Aspose.GIS
- C# mapping
- GIS rendering
title: Создание маркированной карты на C# с Aspose.GIS для .NET
url: /ru/net/map-rendering/label-features-on-map/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание карты с метками в C# с помощью Aspose.GIS для .NET

## Введение
В этом руководстве вы узнаете, как **create labeled map C#** приложения с использованием Aspose.GIS для .NET. Добавление меток к объектам карты превращает сырые геопространственные координаты в читаемые, информационно‑насыщенные визуализации, которые аналитики и конечные пользователи могут сразу понять. Мы пройдём через базовое добавление меток к точкам, пользовательскую стилизацию, расширенные варианты размещения и стратегии, основанные на свойствах объектов, для массивных наборов данных, чтобы вы могли создавать готовые к производству карты всего за несколько строк кода.

## Быстрые ответы
- **Какой основной класс для рендеринга?** `Map` (Aspose.Gis.Rendering)  
- **Какой класс маркировки добавляет простой текст?** `SimpleLabeling`  
- **Могу ли я стилизовать метки (ореол, шрифт, вращение)?** Yes – via properties such as `HaloSize`, `FontStyle`, and `Placement`  
- **Как работать с большими наборами данных?** Use `FeatureBasedConfiguration` to prioritize labels based on attribute values like population  
- **Нужна ли лицензия?** A trial works for development; a commercial license is required for production deployments  

## Что такое функции меток карты?
`label map features` означает привязку читаемого текста — например, названий городов, численности населения или пользовательских идентификаторов — к геометрическим объектам (точкам, линиям или полигонам), чтобы карта передавала как пространственное расположение, так и атрибутивную информацию в одном визуальном слое. Такой подход позволяет пользователям мгновенно распознавать, что представляет каждый объект, без необходимости открывать отдельные таблицы атрибутов, что существенно повышает удобство использования карты.

## Почему использовать Aspose.GIS для меток на карте?
Aspose.GIS предлагает полностью управляемую .NET библиотеку, поддерживающую **более 30 форматов ввода и вывода** (включая GeoJSON, Shapefile, KML, GML и CSV) и способную рендерить в SVG, PNG, PDF и другие форматы без внешних нативных бинарных файлов. Встроенный движок маркировки обрабатывает **сотни тысяч объектов менее чем за секунду** на типичном серверном оборудовании благодаря приоритизации на основе свойств объектов и экономному использованию памяти при потоковой обработке. Эти измеримые преимущества делают её лучшим выбором для корпоративных решений в области картографии.

## Требования
- Владение C# и .NET (Core 3.1+ или .NET 6 рекомендуется)  
- Aspose.GIS for .NET установлен – скачайте его **[here](https://releases.aspose.com/gis/net/)**  
- Векторный источник данных, например файл GeoJSON, содержащий точечные объекты (поддерживается любой поддерживаемый GIS‑формат)

## Импорт пространств имён
В вашем C# файле исходного кода импортируйте необходимые пространства имён Aspose.GIS:

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

Теперь мы пройдём несколько сценариев маркировки, каждый из которых строится на предыдущем.

## Маркировка точек – Как маркировать точки
`Map` — это основной объект рендеринга, который содержит слои, стили и настройки вывода. Чтобы добавить метки к точечным объектам, вам сначала нужен экземпляр карты и простая конфигурация маркировки, читающая атрибут `name` из вашего источника данных. Эта базовая настройка отображает каждую точку с маркером по умолчанию и выводит соответствующее название города непосредственно рядом с ней, предоставляя мгновенный визуальный указатель для каждой локации.

```csharp
string dataDir = "Your Document Directory";
```

## Маркировка точек со стилем – Пользовательский стиль метки
`SimpleLabeling` — класс маркировки, который добавляет простые текстовые метки к объектам. После создания базовой карты вы можете улучшить внешний вид меток, настроив размер ореола, стиль шрифта и цвет. Настройка этих свойств создаёт **пользовательский стиль метки**, который выделяется на загруженных фонах, повышая читаемость в плотных городских районах.

```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Add a vector layer and apply labeling
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Render the map to an SVG file
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```

## Маркировка точек с размещением – Расширенные варианты размещения
`PointLabelPlacement` управляет тем, как метки привязываются, смещаются и вращаются относительно своих объектов. Когда множество точек скоплено вместе, может потребоваться точная настройка этих параметров, чтобы избежать наложения. Указывая точные позиции привязки и углы вращения, каждая метка остаётся разборчивой даже в переполненных областях карты.

```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Rest of the steps remain the same
```

## Маркировка точек на основе объектов – Маркировка больших наборов данных
`FeatureBasedConfiguration` позволяет назначать числовой приоритет (например, население) каждому объекту и автоматически скрывать метки с низким приоритетом, когда пространство экрана ограничено. Для массивных наборов данных (например, национальные слои городов с десятками тысяч точек) эта стратегия гарантирует, что самые важные города отображаются первыми, а небольшие поселения опускаются, если места недостаточно, обеспечивая чистую и информативную карту.

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
// Rest of the steps remain the same
```

## Распространённые проблемы и решения
- **Перекрывающиеся метки** – Увеличьте `HaloSize` или включите `CollisionDetection` в конфигурации маркировки.  
- **Отсутствующие шрифты** – Убедитесь, что указанный вами шрифт установлен на сервере; в противном случае будет использован системный шрифт.  
- **Снижение производительности при работе с очень большими файлами** – Используйте `FeatureBasedConfiguration` с функцией приоритета, чтобы ограничить количество меток, обрабатываемых на каждый тайл.  
- **Неправильная система координат** – Проверьте, что CRS исходных данных соответствует проекции карты; при необходимости используйте утилиты преобразования `SpatialReference`.

## Часто задаваемые вопросы

**Q: Can I label features using custom fonts?**  
A: Yes. Set `FontFamily` and `FontStyle` in the `SimpleLabeling` configuration to any TrueType or OpenType font installed on the host machine.

**Q: Is Aspose.GIS compatible with other GIS data formats?**  
A: Absolutely. It natively reads and writes GeoJSON, Shapefile, KML, GML, CSV, and more than 30 additional formats.

**Q: How can I handle large datasets for labeling?**  
A: Use `FeatureBasedConfiguration` to assign a numeric priority (e.g., population) and let the engine automatically drop low‑priority labels when space is constrained.

**Q: Are there advanced label placement options available?**  
A: Yes. `PointLabelPlacement` lets you control anchor points, offsets, rotation, and even curvature for line and polygon labels.

**Q: Can I automate label generation in a batch process?**  
A: Certainly. Wrap the map rendering code in a loop or background service to process multiple layers or files without manual intervention.

{{< blocks/products/products-backtop-button >}}

**Последнее обновление:** 2026-07-14  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Как добавить города на карту с помощью Aspose.GIS для .NET](/gis/net/map-rendering/render-a-map/)
- [Создание векторного слоя в File GDB – руководство Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Как обрезать объекты слоя с помощью Aspose.GIS для .NET](/gis/net/layer-management/crop-layer-features/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

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
        // Retrieve population from the feature.
        var population = feature.GetValue<int>("population");
        // Font size is computed and is based on the population.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // Priority of the label is also based on the population.
        // The greater the priority is, the more likely label will appear on the output image.
        labeling.Priority = population;
    }
};
// Rest of the steps remain the same
```