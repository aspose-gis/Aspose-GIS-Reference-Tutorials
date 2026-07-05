---
date: 2026-07-05
description: Узнайте, как генерировать SVG-карту и добавлять города, используя Aspose.GIS
  for .NET. Создавайте впечатляющие визуализации быстро.
keywords:
- generate svg map
- draw vector layer
- add base map
- load geojson
- set map dimensions
linktitle: Отобразить карту
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to generate SVG map and add cities using Aspose.GIS for .NET.
    Create stunning visualizations quickly.
  headline: How to Generate SVG Map and Add Cities with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS for .NET works seamlessly in ASP.NET, Blazor, and other
      .NET web frameworks, producing SVG output that browsers render instantly.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the free trial version [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for assistance
      and community discussions.
    question: Where can I find support for Aspose.GIS for .NET?
  - answer: Yes, a temporary license is available [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for short‑term projects?
  - answer: Yes, check the [documentation](https://reference.aspose.com/gis/net/)
      for comprehensive guides and sample projects.
    question: Are there additional tutorials for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Как создать SVG-карту и добавить города с помощью Aspose.GIS for .NET
url: /ru/net/map-rendering/render-a-map/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать SVG‑карту и добавить города с помощью Aspose.GIS для .NET

## Введение
Добро пожаловать в захватывающий мир Aspose.GIS для .NET! В этом пошаговом руководстве вы узнаете **как добавить города на карту** и **создать SVG‑карту**, вывод которой выглядит отлично на любом экране. Независимо от того, создаёте ли вы настольную панель управления, веб‑портал GIS или печатный отчёт, один и тот же код работает в .NET Framework, .NET Core и .NET 5/6. Давайте пройдём весь процесс — от задания размеров карты до экспорта чистого, масштабируемого SVG‑файла.

## Быстрые ответы
- **Что охватывает этот учебник?** Добавление точек городов на карту и экспорт результата в файл SVG.  
- **Какая библиотека требуется?** Aspose.GIS for .NET (доступна бесплатная пробная версия).  
- **Нужна ли лицензия?** Пробная версия подходит для разработки; коммерческая лицензия требуется для использования в продакшене.  
- **Можно ли использовать это в веб‑приложениях?** Да — тот же код работает в ASP.NET, Blazor и других веб‑фреймворках .NET.  
- **Какой формат вывода создаётся?** Высококачественная SVG‑карта, которую браузеры отображают мгновенно, а векторные редакторы могут дальше редактировать.

## Что означает «создание SVG‑карты»?
*Создание SVG‑карты* означает преобразование географических данных в файл Scalable Vector Graphics, который сохраняет геометрию, стили и интерактивность без растеризации изображения. SVG‑файлы остаются чёткими при любом уровне масштабирования и идеальны для веб‑визуализаций.

## Почему создавать SVG‑карту с помощью Aspose.GIS?
Aspose.GIS поддерживает **70+ input and output formats** (включая Shapefile, GeoJSON, KML и GML) и может отрисовывать карты с **sub‑pixel precision**, при этом потребление памяти остаётся низким. Библиотека обрабатывает **multi‑hundred‑page datasets** без загрузки всего файла в память, что делает её идеальной для крупномасштабных GIS‑проектов.

## Требования
- Aspose.GIS for .NET Library: Убедитесь, что библиотека Aspose.GIS for .NET установлена. Вы можете скачать её [здесь](https://releases.aspose.com/gis/net/).
- Data Files: Подготовьте необходимые shapefile‑ы и данные GeoJSON для учебника. Примеры данных можно найти в документации или использовать свои файлы.
- Development Environment: Настройте среду разработки .NET, включая редактор кода, например Visual Studio.

## Импорт пространств имён
Пространство имён `Aspose.Gis` предоставляет всю базовую GIS‑функциональность, а `Aspose.Gis.Rendering` содержит классы, специфичные для рендеринга.

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

## Как задать размеры карты?
`Map` — основной класс, который хранит поверхность рендеринга и управляет слоями.  
Сначала задайте размер холста карты, чтобы рендерер знал, сколько места выделить. Вы создаёте объект `Map`, передаёте ширину и высоту в пикселях и, при желании, задаёте цвет фона. Этот шаг контролирует соотношение сторон конечного SVG, размер файла и визуальную чёткость на разных устройствах.

```csharp
string dataDir = "Your Document Directory";
using (var map = new Map(800, 476))
{
    // Additional code for map setup can be added here.
}
```

## Как нарисовать векторный слой для базовой карты?
`DrawVectorLayer` отрисовывает векторный слой на карте с использованием заданного символизатора.  
Класс `Map` предоставляет метод `DrawVectorLayer`, который читает shapefile и отрисовывает каждую особенность с помощью стиля `SimpleFill`. Вы можете настроить цвет заливки, толщину контура и непрозрачность в соответствии с вашей визуальной темой, а также применить прозрачность или узорные заливки для более богатых картографических эффектов.

```csharp
var baseMapSymbolizer = new SimpleFill { FillColor = Color.Salmon, StrokeWidth = 0.75 };
map.Add(VectorLayer.Open(dataDir + "basemap.shp", Drivers.Shapefile), baseMapSymbolizer);
```

## Как загрузить GeoJSON и добавить города на карту?
`FeatureBasedConfiguration` — делегат, позволяющий задавать стиль каждой особенности на основе её атрибутов.  
Загрузка файла GeoJSON даёт вам набор точечных особенностей, представляющих города. Передавая делегат `FeatureBasedConfiguration`, вы можете стилизовать каждый маркер города в зависимости от атрибутов, таких как население или регион. Также можно фильтровать особенности или динамически менять размер символа, отражая дополнительные измерения данных.

```csharp
var citiesSymbolizer = new SimpleMarker() { FillColor = Color.LightBlue };
citiesSymbolizer.FeatureBasedConfiguration = (feature, symbolizer) =>
{
    // Additional configuration logic can be added here.
};
map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), citiesSymbolizer);
```

## Как экспортировать карту в файл SVG?
`Map.Save` выводит отрисованную карту в файл в указанном формате.  
Вызов `Map.Save` с аргументом `SaveFormat.Svg` записывает векторные данные в SVG‑файл на диск. Полученный `cities_out.svg` можно открыть напрямую в любом современном браузере или отредактировать с помощью таких инструментов, как Inkscape. Также можно указать DPI или встроить CSS для дальнейшего стилизования.

```csharp
map.Render(dataDir + "cities_out.svg", Renderers.Svg);
```

## Распространённые проблемы и решения
- **Ошибка: отсутствует файл данных** – Убедитесь, что относительные пути к вашему shapefile и GeoJSON правильные; используйте абсолютные пути при отладке.  
- **Города не видны** – Убедитесь, что система координат GeoJSON совпадает с CRS базовой карты, либо пере‑проецируйте данные с помощью `Geometry.Transform`.  
- **SVG выглядит пустым** – Проверьте, что цвет фона карты не установлен в полностью прозрачный; задайте светлую заливку, чтобы подтвердить рендеринг.

## Часто задаваемые вопросы

**Q: Можно ли использовать Aspose.GIS for .NET в моих веб‑приложениях?**  
A: Да, Aspose.GIS for .NET работает без проблем в ASP.NET, Blazor и других веб‑фреймворках .NET, создавая SVG‑вывод, который браузеры отображают мгновенно.

**Q: Доступна ли пробная версия?**  
A: Да, вы можете изучить бесплатную пробную версию [здесь](https://releases.aspose.com/).

**Q: Где я могу найти поддержку Aspose.GIS for .NET?**  
A: Посетите [форум Aspose.GIS](https://forum.aspose.com/c/gis/33) для получения помощи и обсуждения с сообществом.

**Q: Можно ли приобрести временную лицензию для краткосрочных проектов?**  
A: Да, временная лицензия доступна [здесь](https://purchase.aspose.com/temporary-license/).

**Q: Есть ли дополнительные учебники по Aspose.GIS for .NET?**  
A: Да, ознакомьтесь с [документацией](https://reference.aspose.com/gis/net/) для комплексных руководств и примеров проектов.

---

**Последнее обновление:** 2026-07-05  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные учебники

- [Создать векторный слой и установить допуск линейризации с помощью Aspose.GIS for .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Как прочитать GeoJSON из потока с помощью Aspose.GIS for .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Создать векторный слой и установить систему пространственной привязки слоя](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}