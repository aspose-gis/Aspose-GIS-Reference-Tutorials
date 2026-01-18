---
date: 2026-01-18
description: Узнайте, как добавить города на карту и сгенерировать SVG‑карту с помощью
  Aspose.GIS для .NET. Создавайте потрясающие визуализации быстро.
linktitle: Render a Map
second_title: Aspose.GIS .NET API
title: Как добавить города на карту с помощью Aspose.GIS для .NET
url: /ru/net/map-rendering/render-a-map/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как добавить города на карту с помощью Aspose.GIS для .NET

## Introduction
Добро пожаловать в захватывающий мир Aspose.GIS для .NET! В этом пошаговом руководстве вы узнаете **как добавить города на карту** и создать высококачественный SVG‑файл. Независимо от того, создаёте ли вы настольную панель управления или веб‑портал GIS, этот учебник покажет, как рисовать векторные слои, задавать размеры карты и загружать карту в формате GeoJSON без усилий.

## Quick Answers
- **Что покрывает этот учебник?** Добавление городов на карту и экспорт её в файл SVG.  
- **Какая библиотека требуется?** Aspose.GIS для .NET.  
- **Нужна ли лицензия?** Доступна бесплатная пробная версия; для продакшн‑использования требуется лицензия.  
- **Можно ли использовать в веб‑приложениях?** Да — тот же код работает в ASP.NET, Blazor и других .NET‑веб‑фреймворках.  
- **Какой формат вывода получается?** SVG‑карта, которую можно отображать в браузерах или дальше редактировать.

## Prerequisites
Прежде чем приступить к учебнику, убедитесь, что у вас есть следующее:
- Библиотека Aspose.GIS для .NET: Убедитесь, что библиотека Aspose.GIS для .NET установлена. Вы можете скачать её [здесь](https://releases.aspose.com/gis/net/).
- Файлы данных: Подготовьте необходимые shapefile‑ы и данные GeoJSON для учебника. Примеры данных можно найти в документации или использовать свои файлы.
- Среда разработки: Настройте .NET‑среду разработки, включая редактор кода, например Visual Studio.

## Import Namespaces
Чтобы начать, импортируйте необходимые пространства имён в ваш .NET‑проект. Эти пространства имён необходимы для работы с функциональностью Aspose.GIS.

```csharp
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.Drawing.Text;
using System.IO;
using System.Linq;
```

## Step 1: Set Up the Map (set map dimensions)
```csharp
string dataDir = "Your Document Directory";
using (var map = new Map(800, 476))
{
    // Additional code for map setup can be added here.
}
```
В этом шаге мы инициализируем новую карту шириной 800 пикселей и высотой 476 пикселей. При необходимости измените размеры в соответствии с требованиями вашего дизайна.

## Step 2: Add a Base Map (draw vector layer)
```csharp
var baseMapSymbolizer = new SimpleFill { FillColor = Color.Salmon, StrokeWidth = 0.75 };
map.Add(VectorLayer.Open(dataDir + "basemap.shp", Drivers.Shapefile), baseMapSymbolizer);
```
Здесь мы **рисуем векторный слой** для базовой карты, используя shapefile. При желании измените свойства `SimpleFill`, чтобы они соответствовали вашему визуальному стилю.

## Step 3: Add Cities to the Map (add cities to map, load GeoJSON map)
```csharp
var citiesSymbolizer = new SimpleMarker() { FillColor = Color.LightBlue };
citiesSymbolizer.FeatureBasedConfiguration = (feature, symbolizer) =>
{
    // Additional configuration logic can be added here.
};
map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), citiesSymbolizer);
```
Этот шаг загружает файл GeoJSON, содержащий данные о точках городов, и **добавляет города на карту**. Вы можете расширить делегат `FeatureBasedConfiguration`, чтобы стилизовать города в зависимости от атрибутов, например, населения.

## Step 4: Render the Map (export map SVG, generate SVG map)
```csharp
map.Render(dataDir + "cities_out.svg", Renderers.Svg);
```
Наконец, мы **экспортируем карту в файл SVG**. Полученный `cities_out.svg` можно открыть в любом современном браузере или векторном графическом редакторе.

## Conclusion
Поздравляем! Вы успешно **добавили города на карту** и сгенерировали SVG‑карту с помощью Aspose.GIS для .NET. Этот учебник продемонстрировал, как задавать размеры карты, рисовать векторные слои, загружать данные GeoJSON и экспортировать результат в масштабируемый SVG — идеально как для веба, так и для печати.

## FAQs
### Можно ли использовать Aspose.GIS для .NET в моих веб‑приложениях?
Да, Aspose.GIS для .NET подходит как для настольных, так и для веб‑приложений.

### Доступна ли пробная версия?
Да, вы можете ознакомиться с бесплатной пробной версией [здесь](https://releases.aspose.com/).

### Где я могу получить поддержку по Aspose.GIS для .NET?
Посетите [форум Aspose.GIS](https://forum.aspose.com/c/gis/33) для получения помощи или ответов на вопросы.

### Можно ли приобрести временную лицензию для краткосрочных проектов?
Да, временная лицензия доступна [здесь](https://purchase.aspose.com/temporary-license/).

### Есть ли дополнительные учебники по Aspose.GIS для .NET?
Да, ознакомьтесь с [документацией](https://reference.aspose.com/gis/net/) для получения полного набора учебных материалов и руководств.

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}