---
date: 2026-11-12
description: Узнайте, как конвертировать geojson в topojson с группировкой, задать
  атрибут имени объекта и группировать функции GeoJSON с помощью Aspose.GIS для .NET.
images:
- /net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/og-image.png
keywords:
- convert geojson to topojson
- how to group features
- group features by attribute
- group geojson features
- asp.net core geojson
lastmod: 2026-11-12
linktitle: Как конвертировать GeoJSON в TopoJSON с группировкой, используя Aspose.GIS
og_description: Узнайте, как конвертировать geojson в topojson с группировкой, задать
  атрибут имени объекта и эффективно группировать функции GeoJSON с помощью Aspose.GIS
  для .NET.
og_image_alt: Screenshot of Aspose.GIS conversion code showing GeoJSON to TopoJSON
  with grouping
og_title: Конвертировать geojson в topojson с группировкой, используя Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-11-12'
  description: Learn how to convert geojson to topojson with grouping, set object
    name attribute, and group GeoJSON features using Aspose.GIS for .NET.
  headline: How to convert geojson to topojson with grouping using Aspose.GIS
  type: TechArticle
- description: Learn how to convert geojson to topojson with grouping, set object
    name attribute, and group GeoJSON features using Aspose.GIS for .NET.
  name: How to convert geojson to topojson with grouping using Aspose.GIS
  steps:
  - name: Define file paths
    text: 'Specify where the source GeoJSON lives and where the TopoJSON should be
      written: > **Pro tip:** Use `Path.Combine` for cross‑platform path building
      if you target .NET Core.'
  - name: Configure conversion options (set object name attribute)
    text: '`ConversionOptions` is the Aspose.GIS class that defines how a conversion
      should be performed, including grouping and precision settings. It lets you
      set the grouping attribute, define a default object name, and tweak topology
      precision. The `ObjectNameAttribute` property (string) defines the GeoJSON field
      used for grouping, while `De'
  - name: Perform the conversion (convert GeoJSON to TopoJSON)
    text: '`Conversion.Convert` is a static method that reads the source file, applies
      the provided options, and writes the converted TopoJSON output. It internally
      builds a topology graph, deduplicates shared edges, and writes the result in
      the compact TopoJSON format.'
  type: HowTo
- questions:
  - answer: Yes, you can concatenate several fields into a single virtual attribute
      or run multiple conversion passes with different `ObjectNameAttribute` values.
    question: Can I group features based on multiple attributes?
  - answer: Absolutely – the library works with ASP.NET Core, .NET 5, .NET 6, and
      the classic .NET Framework.
    question: Is Aspose.GIS compatible with ASP.NET Core?
  - answer: Yes, Aspose.GIS supports more than 30 input and output formats—including
      Shapefile, KML, GML, CSV, and DXF—for both import and export.
    question: Can I convert other geographic formats besides GeoJSON?
  - answer: Yes, you can get a free trial of Aspose.GIS from the [Aspose.GIS free
      trial page](https://releases.aspose.com/).
    question: Does Aspose.GIS offer a free trial?
  - answer: You can get support from the Aspose.GIS community forum [Aspose.GIS community
      forum](https://forum.aspose.com/c/gis/33).
    question: Where can I get support for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert geojson
- Aspose.GIS
- C# GIS processing
- geojson conversion
- topojson grouping
title: Как конвертировать geojson в topojson с группировкой, используя Aspose.GIS
url: /ru/net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как преобразовать geojson в topojson с группировкой с использованием Aspose.GIS

## Введение

В этом пошаговом руководстве вы узнаете **как преобразовать geojson в topojson**, группируя объекты на основе выбранного атрибута. Использование Aspose.GIS .NET API делает преобразование быстрым (обрабатывает до 2 000 объектов в секунду) и полностью управляемым из вашего кода C#. Независимо от того, создаёте ли вы сервис преобразования geojson на ASP.NET Core, настольный GIS‑инструмент или автоматизированный конвейер данных, это руководство покажет вам точно, что нужно сделать, чтобы **преобразовать geojson в topojson** эффективно и надёжно.

## Быстрые ответы
- **Какая библиотека выполняет преобразование?** Aspose.GIS for .NET  
- **Сколько времени занимает реализация?** Обычно 5‑10 минут для базовой настройки  
- **Нужна ли лицензия для продакшна?** Да, требуется коммерческая лицензия (доступна бесплатная пробная версия)  
- **Можно ли группировать объекты по любому атрибуту?** Да – установите `ObjectNameAttribute` в поле, по которому хотите группировать  
- **Поддерживается ли .NET Core?** Абсолютно – API работает с .NET Core, .NET 5/6 и классическим .NET Framework  

## Как преобразовать geojson в topojson с группировкой в C#

Загрузите ваш исходный GeoJSON, настройте `ConversionOptions`, указав нужный `ObjectNameAttribute`, и вызовите `Conversion.Convert` – этот единственный вызов создаст полностью сгруппированный файл TopoJSON менее чем за секунду для типичных наборов данных городского масштаба. Вы можете внедрить этот шаблон в консольное приложение, фоновой сервис или конечную точку преобразования geojson в ASP.NET Core. API абстрагирует все низкоуровневые топологические вычисления, позволяя вам сосредоточиться на бизнес‑логике, а не на математике геометрии.

## Что такое GeoJSON и TopoJSON?

GeoJSON — это формат на основе JSON, который кодирует географические объекты, такие как точки, линии и полигоны. TopoJSON расширяет GeoJSON, сохраняя общие линейные сегменты (топология) вместо повторения координат для каждого объекта. Это уменьшает размер файлов, устраняет избыточность и повышает производительность рендеринга в веб‑картах.

## Зачем группировать объекты GeoJSON?

Группировка объектов GeoJSON во время преобразования создаёт именованные объекты в выводе TopoJSON, что позволяет downstream‑инструментам карт воспринимать связанные геометрии как один слой. Это упрощает стилизацию, уменьшает количество вызовов отрисовки и устраняет дублирование границ между соседними объектами, что приводит к более быстрой отрисовке и меньшим файлам.

## Установите атрибут имени объекта для группировки

`ObjectNameAttribute` указывает Aspose.GIS, какое свойство в исходном GeoJSON следует использовать в качестве имени объекта в выводе TopoJSON. Правильная настройка этого атрибута — ключ к успешному **группированию объектов geojson**.

## Предварительные требования

1. **Aspose.GIS for .NET** – загрузите и установите со страницы [Aspose.GIS for .NET release page](https://releases.aspose.com/gis/net/).  
2. **Среда разработки** – Visual Studio, Visual Studio Code или любой IDE, поддерживающий C#.  
3. **Пример файла GeoJSON** – файл, содержащий объекты, которые вы хотите преобразовать.  

## Импорт пространств имён

Сначала включите необходимые пространства имён в ваш проект:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```

## Пошаговое руководство

### Шаг 1: Определите пути к файлам

Укажите, где находится исходный GeoJSON и куда следует записать TopoJSON:

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

> **Полезный совет:** Используйте `Path.Combine` для построения кросс‑платформенных путей, если вы нацелены на .NET Core.

### Шаг 2: Настройте параметры преобразования (установите атрибут имени объекта)

`ConversionOptions` — класс Aspose.GIS, определяющий, как должно выполняться преобразование, включая настройки группировки и точности. Он позволяет задать атрибут группировки, определить имя объекта по умолчанию и настроить точность топологии.

`ObjectNameAttribute` (string) определяет поле GeoJSON, используемое для группировки, а `DefaultObjectName` (string) предоставляет запасное имя для объектов, у которых отсутствует атрибут. Так происходит группировка объектов по атрибуту с помощью свойства ObjectNameAttribute. Замените `"group"` на фактическое имя свойства в вашем GeoJSON, которое вы хотите использовать для **группировки объектов geojson**. `DefaultObjectName` гарантирует, что каждый объект попадёт в объект TopoJSON, даже если атрибут отсутствует.

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // Specify the attribute in GeoJSON layer by which we are going to group into objects
        ObjectNameAttribute = "group",
        // Specify the default object name for features with unknown attribute values
        DefaultObjectName = "unnamed",
    }
};
```

### Шаг 3: Выполните преобразование (преобразовать GeoJSON в TopoJSON)

`Conversion.Convert` — статический метод, который читает исходный файл, применяет переданные параметры и записывает преобразованный вывод TopoJSON. Внутри он строит топологический граф, удаляет дублирующиеся общие ребра и записывает результат в компактном формате TopoJSON.

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

После выполнения `convertedSampleWithGrouping_out.topojson` будет содержать представление TopoJSON, с объектами, сгруппированными согласно указанному атрибуту.

## Распространённые проблемы и их устранение

| Симптом | Возможная причина | Решение |
|---------|-------------------|---------|
| **Все объекты попадают в “unnamed”** | `ObjectNameAttribute` не совпадает ни с одним свойством в GeoJSON | Проверьте точное имя свойства (с учётом регистра) и обновите параметр |
| **Файл вывода пустой** | Неправильный путь к файлу или отсутствие прав на чтение | Используйте абсолютные пути или убедитесь, что приложение имеет доступ к файловой системе |
| **Преобразование бросает `NotSupportedException`** | Попытка преобразовать GeoJSON с неподдерживаемыми типами геометрии (например, GeometryCollection) | Упростите исходные данные или обновите до последней версии Aspose.GIS |

## Лучшие практики преобразования GeoJSON в C#

- **Проверьте исходный GeoJSON** перед преобразованием, чтобы раннее обнаружить отсутствующие атрибуты.  
- **Используйте `Path.Combine`** для путей к файлам, чтобы избежать проблем с разделителями, специфичными для платформы.  
- **Обёрните вызов преобразования в блок try‑catch** для graceful обработки ошибок ввода‑вывода.  
- **Ведите журнал появлений `DefaultObjectName`**; они могут указывать на проблемы качества данных, которые следует исправить upstream.  

## Часто задаваемые вопросы

**Q: Можно ли группировать объекты по нескольким атрибутам?**  
A: Да, вы можете конкатенировать несколько полей в один виртуальный атрибут или выполнить несколько проходов преобразования с разными значениями `ObjectNameAttribute`.

**Q: Совместим ли Aspose.GIS с ASP.NET Core?**  
A: Абсолютно – библиотека работает с ASP.NET Core, .NET 5, .NET 6 и классическим .NET Framework.

**Q: Можно ли преобразовать другие географические форматы, кроме GeoJSON?**  
A: Да, Aspose.GIS поддерживает более 30 форматов ввода и вывода — включая Shapefile, KML, GML, CSV и DXF — как для импорта, так и для экспорта.

**Q: Предлагает ли Aspose.GIS бесплатную пробную версию?**  
A: Да, вы можете получить бесплатную пробную версию Aspose.GIS на странице [Aspose.GIS free trial page](https://releases.aspose.com/).

**Q: Где я могу получить поддержку по Aspose.GIS?**  
A: Вы можете получить поддержку на форуме сообщества Aspose.GIS [Aspose.GIS community forum](https://forum.aspose.com/c/gis/33).

## Заключение

Теперь у вас есть полный, готовый к продакшну рецепт для **преобразования geojson в topojson** с группировкой объектов с использованием Aspose.GIS для .NET. Устанавливая `ObjectNameAttribute`, вы контролируете организацию объектов, что упрощает downstream‑стилизацию и взаимодействие в веб‑картах. Не стесняйтесь исследовать другие драйверы, экспериментировать с различными атрибутами группировки и интегрировать это преобразование в более крупные GIS‑конвейеры.

---

**Last Updated:** 2026-11-12  
**Tested with:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

---

## Связанные руководства

- [Как преобразовать GeoJSON в TopoJSON с помощью Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Как преобразовать GeoJSON в TopoJSON с конкретным именем объекта](/gis/net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/)
- [Разблокировка функций TopoJSON с Aspose.GIS для .NET](/gis/net/layer-management/access-features-in-topojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}