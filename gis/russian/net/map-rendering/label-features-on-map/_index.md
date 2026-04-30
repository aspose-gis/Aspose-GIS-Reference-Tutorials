---
date: 2026-01-15
description: Узнайте, как наносить подписи на элементы карты с помощью Aspose.GIS
  для .NET, используя пользовательские параметры стиля подписи для маркировки больших
  наборов данных.
linktitle: Label Features on Map
second_title: Aspose.GIS .NET API
title: Подписать объекты карты с помощью Aspose.GIS для .NET
url: /ru/net/map-rendering/label-features-on-map/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Маркировка объектов карты с помощью Aspose.GIS для .NET

## Introduction
Маркировка объектов карты имеет решающее значение для преобразования необработанных геопространственных данных в понятные, удобные визуализации. В этом руководстве вы узнаете **how to label map features** с помощью Aspose.GIS для .NET, изучите пользовательские стили меток и увидите техники, работающие даже с большими наборами данных. В конце вы сможете добавить информативный текст непосредственно на карты, делая их более полезными для аналитиков и конечных пользователей.

## Quick Answers
- **Какой основной класс используется для рендеринга?** `Map` (Aspose.Gis.Rendering)
- **Какой класс маркировки добавляет простой текст?** `SimpleLabeling`
- **Могу ли я стилизовать метки (ореол, шрифт, вращение)?** Yes – via properties like `HaloSize`, `FontStyle`, and `Placement`
- **Как работать с большими наборами данных?** Use `FeatureBasedConfiguration` to prioritize labels based on attribute values
- **Нужна ли лицензия?** A trial works for development; a commercial license is required for production

## What is label map features?
`label map features` означает прикрепление читаемого текста (например, названий городов, численности населения или пользовательских идентификаторов) к геометрическим объектам — точкам, линиям или полигонам — чтобы карта передавала как пространственную, так и атрибутивную информацию с первого взгляда.

## Why use Aspose.GIS for label map features?
- **Отсутствие внешних зависимостей** – чистая .NET библиотека, не требующая нативных GIS бинарных файлов.  
- **Широкие возможности стилизации** – ореолы, пользовательские шрифты, вращение и точки привязки позволяют точно настраивать внешний вид.  
- **Ориентированность на производительность** – встроенная маркировка на основе объектов позволяет отдавать приоритет самым важным меткам при рендеринге больших наборов данных.  
- **Поддержка множества форматов вывода** – SVG, PNG, PDF и др., с единообразными результатами маркировки.

## Prerequisites
Прежде чем начать, убедитесь, что у вас есть:

- Знание C# и платформы .NET.  
- Установленный Aspose.GIS для .NET. Вы можете скачать его **[здесь](https://releases.aspose.com/gis/net/)**.  
- Файл GeoJSON, содержащий точечные данные (или любой поддерживаемый векторный формат).  

## Import Namespaces
В вашем C# коде импортируйте необходимые пространства имён:

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

Далее мы пройдём несколько сценариев маркировки, каждый из которых опирается на предыдущий.

## Points Labeling – How to label points
### Step 1: Set the path to your documents directory
Шаг 1: Установите путь к каталогу документов

```csharp
string dataDir = "Your Document Directory";
```

### Step 2: Create a map with a simple marker symbol
Шаг 2: Создайте карту с простым символом маркера

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

В этом базовом примере мы **how to label points** с использованием атрибута `name` из файла GeoJSON.

## Points Labeling Styled – Custom label style
Следуйте шагам 1 и 2 из предыдущего примера, затем настройте стиль маркировки:

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

Добавленные ореол и курсивный шрифт придают меткам **custom label style**, который выделяется на загруженных фонах.

## Points Labeling Placed – Advanced placement options
Снова начните с шагов 1 и 2 из первого примера, затем отрегулируйте размещение:

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

Здесь мы управляем точками привязки, смещениями и вращением, предоставляя вам детальный контроль над **how to label points** в перегруженных областях карты.

## Points Labeling Feature Based – Large dataset labeling
При работе с большим количеством точек вы можете захотеть расставлять приоритеты меток на основе атрибута, например, населения. Выполните шаги 1 и 2 из первого примера, затем реализуйте маркировку на основе объектов:

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

Эта стратегия **large dataset labeling** гарантирует, что самые важные города (по населению) отображаются первыми, а менее значимые точки могут быть опущены при ограниченном пространстве.

## Conclusion
Поздравляем! Теперь вы знаете несколько способов **label map features** с помощью Aspose.GIS для .NET — от простой маркировки точек до сложной стилизации на основе объектов для больших наборов данных. Экспериментируйте с ореолами, вращением и правилами приоритета, чтобы создавать карты, точно передающие то, что необходимо вашей аудитории.

## Frequently Asked Questions

**Q: Можно ли маркировать объекты, используя пользовательские шрифты?**  
A: Да. Установите `FontFamily` и `FontStyle` в конфигурации `SimpleLabeling`, чтобы использовать любой установленный шрифт.

**Q: Совместим ли Aspose.GIS с другими форматами GIS‑данных?**  
A: Абсолютно. Он поддерживает GeoJSON, Shapefile, KML, GML и многие другие форматы.

**Q: Как работать с большими наборами данных при маркировке?**  
A: Используйте `FeatureBasedConfiguration` для назначения приоритетов и динамического изменения размеров шрифта в зависимости от значений атрибутов, как показано в примере маркировки на основе объектов.

**Q: Доступны ли расширенные параметры размещения меток?**  
A: Да. Вы можете точно настраивать размещение с помощью `PointLabelPlacement`, регулируя точки привязки, смещения и вращение.

**Q: Можно ли автоматизировать генерацию меток в пакетном процессе?**  
A: Конечно. Оберните код рендеринга карты в цикл или фоновый сервис для автоматической обработки нескольких слоёв или файлов.

---

**Последнее обновление:** 2026-01-15  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}