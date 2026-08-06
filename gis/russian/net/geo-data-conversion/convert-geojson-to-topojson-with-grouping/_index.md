---
date: 2026-08-03
description: Узнайте, как конвертировать geojson в topojson с группировкой, задать
  атрибут имени объекта и группировать функции GeoJSON с помощью Aspose.GIS для .NET.
keywords:
- convert geojson to topojson
- group features by attribute
- asp.net core geojson
- set object name attribute
- asp.net geojson conversion
lastmod: 2026-08-03
linktitle: Как конвертировать GeoJSON в TopoJSON с группировкой с помощью Aspose.GIS
og_description: Узнайте, как конвертировать geojson в topojson с группировкой, задать
  атрибут имени объекта и эффективно группировать функции GeoJSON с помощью Aspose.GIS
  для .NET.
og_image_alt: Screenshot of Aspose.GIS conversion code showing GeoJSON to TopoJSON
  with grouping
og_title: Конвертировать geojson в topojson с группировкой с помощью Aspose.GIS для
  .NET
schemas:
- author: Aspose
  dateModified: '2026-08-03'
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
    text: '`ConversionOptions` is the configuration object that controls how Aspose.GIS
      performs the conversion. It lets you set the grouping attribute, define a default
      object name, and tweak topology precision. The `ObjectNameAttribute` property
      (string) defines the GeoJSON field used for grouping, while `De'
  - name: Perform the conversion (convert GeoJSON to TopoJSON)
    text: '`Conversion.Convert` is a single‑line API call that reads the source file,
      applies the options, and writes the TopoJSON output. It internally builds a
      topology graph, deduplicates shared edges, and writes the result in the compact
      TopoJSON format. After execution, `convertedSampleWithGrouping_out.to'
  type: HowTo
- questions:
  - answer: Yes, you can concatenate several fields into a single virtual attribute
      or run multiple conversion passes with different `ObjectNameAttribute` values.
    question: Can I group features based on multiple attributes?
  - answer: Absolutely – the library works with ASP.NET Core, .NET 5, .NET 6, and
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
title: Как конвертировать geojson в topojson с группировкой с помощью Aspose.GIS
url: /ru/net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как конвертировать geojson в topojson с группировкой с использованием Aspose.GIS

## Введение

В этом пошаговом руководстве вы узнаете **как конвертировать geojson в topojson**, группируя объекты на основе выбранного атрибута. Использование Aspose.GIS .NET API делает преобразование быстрым (обрабатывает до 2 000 объектов в секунду) и полностью управляемым из вашего кода C#. Независимо от того, создаёте ли вы сервис конвертации geojson на ASP.NET Core, настольный GIS‑инструмент или автоматизированный конвейер данных, это руководство покажет вам точно, что нужно сделать, чтобы **конвертировать geojson в topojson** эффективно и надёжно.

## Быстрые ответы
- **Какая библиотека обрабатывает конвертацию?** Aspose.GIS for .NET  
- **Сколько времени занимает реализация?** Обычно 5‑10 минут для базовой настройки  
- **Нужна ли лицензия для продакшн?** Да, требуется коммерческая лицензия (доступна бесплатная пробная версия)  
- **Можно ли группировать объекты по любому атрибуту?** Да — установите `ObjectNameAttribute` в поле, по которому хотите группировать  
- **Поддерживается ли .NET Core?** Абсолютно — API работает с .NET Core, .NET 5/6 и классическим .NET Framework  

## Как конвертировать geojson в topojson с группировкой в C#

Загрузите ваш исходный GeoJSON, настройте `ConversionOptions`, указав нужный `ObjectNameAttribute`, и вызовите `Conversion.Convert` — этот единственный вызов создаст полностью сгруппированный файл TopoJSON менее чем за секунду для типичных наборов данных городского масштаба.

Вы можете встроить этот шаблон в консольное приложение, фоновой сервис или конечную точку конвертации geojson в ASP.NET Core. API абстрагирует все низкоуровневые расчёты топологии, позволяя сосредоточиться на бизнес‑логике, а не на геометрических вычислениях.

## Что такое GeoJSON и TopoJSON?

GeoJSON — это лёгкий формат JSON, представляющий географические объекты, такие как точки, линии и полигоны. TopoJSON расширяет GeoJSON, сохраняя общие линейные сегменты (топология), что уменьшает размер файла до 80 % для сложных карт и повышает скорость отрисовки в веб‑визуализациях.

## Почему группировать объекты GeoJSON?

Группировка объектов GeoJSON позволяет объединять связанные геометрии в один именованный объект в выводе TopoJSON, что упрощает последующее стилизование и взаимодействие. Это полезно, когда нужны отдельные слои для административных регионов, когда библиотека карт ожидает именованные объекты для обработки кликов, или когда необходимо избавиться от дублирующих данных границ между соседними объектами.

## Установите атрибут имени объекта для группировки

`ObjectNameAttribute` указывает Aspose.GIS, какое свойство в исходном GeoJSON следует использовать в качестве имени объекта в выводе TopoJSON. Правильная настройка этого атрибута — ключ к успешному **группированию объектов geojson**.

## Предварительные требования

Прежде чем начать, убедитесь, что у вас есть следующие требования:

1. **Aspose.GIS for .NET** — загрузите и установите со страницы [Aspose.GIS for .NET release page](https://releases.aspose.com/gis/net/).  
2. **Среда разработки** — Visual Studio, Visual Studio Code или любой IDE, поддерживающий C#.  
3. **Пример файла GeoJSON** — файл, содержащий объекты, которые вы хотите конвертировать.  

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

> **Полезный совет:** Используйте `Path.Combine` для построения путей кросс‑платформенно, если вы нацелены на .NET Core.

### Шаг 2: Настройте параметры конвертации (установите атрибут имени объекта)

`ConversionOptions` — объект конфигурации, контролирующий, как Aspose.GIS выполняет конвертацию. Он позволяет задать атрибут группировки, определить имя объекта по умолчанию и настроить точность топологии.

Свойство `ObjectNameAttribute` (string) определяет поле GeoJSON, используемое для группировки, а `DefaultObjectName` (string) задаёт резервное имя для объектов, у которых отсутствует этот атрибут.

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

Замените `"group"` реальным именем свойства в вашем GeoJSON, которое вы хотите использовать для **группировки объектов geojson**. `DefaultObjectName` гарантирует, что каждый объект попадёт в объект TopoJSON, даже если атрибут отсутствует.

### Шаг 3: Выполните конвертацию (конвертировать GeoJSON в TopoJSON)

`Conversion.Convert` — однострочный вызов API, который читает исходный файл, применяет параметры и записывает вывод TopoJSON. Он внутренне строит граф топологии, удаляет дублирующиеся общие ребра и записывает результат в компактном формате TopoJSON.

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

После выполнения `convertedSampleWithGrouping_out.topojson` будет содержать представление TopoJSON, где объекты сгруппированы согласно указанному вами атрибуту.

## Распространённые проблемы и их устранение

| Симптом | Вероятная причина | Решение |
|---------|-------------------|---------|
| **Все объекты попадают в “unnamed”** | `ObjectNameAttribute` не соответствует ни одному свойству в GeoJSON | Проверьте точное имя свойства (с учётом регистра) и обновите параметр |
| **Файл вывода пустой** | Неправильный путь к файлу или отсутствие прав на чтение | Используйте абсолютные пути или убедитесь, что приложение имеет доступ к файловой системе |
| **Конвертация бросает `NotSupportedException`** | Попытка конвертировать GeoJSON с неподдерживаемыми типами геометрии (например, GeometryCollection) | Упростите исходные данные или обновитесь до последней версии Aspose.GIS |

## Лучшие практики конвертации GeoJSON в C#

- **Проверьте исходный GeoJSON** перед конвертацией, чтобы заранее обнаружить отсутствующие атрибуты.  
- **Используйте `Path.Combine`** для путей к файлам, чтобы избежать проблем с разделителями, специфичными для платформы.  
- **Обёрните вызов конвертации в блок try‑catch** для корректной обработки ошибок ввода‑вывода.  
- **Ведите журнал появлений `DefaultObjectName`**; они могут указывать на проблемы качества данных, которые стоит исправить на этапе подготовки.  

## Часто задаваемые вопросы

**В: Можно ли группировать объекты по нескольким атрибутам?**  
О: Да, вы можете объединить несколько полей в один виртуальный атрибут или выполнить несколько проходов конвертации с разными значениями `ObjectNameAttribute`.

**В: Совместим ли Aspose.GIS с ASP.NET Core?**  
О: Абсолютно — библиотека работает с ASP.NET Core, .NET 5, .NET 6 и классическим .NET Framework.

**В: Можно ли конвертировать другие географические форматы, кроме GeoJSON?**  
О: Да, Aspose.GIS поддерживает более 30 форматов ввода и вывода, включая Shapefile, KML, GML, CSV и DXF для импорта и экспорта.

**В: Предлагает ли Aspose.GIS бесплатную пробную версию?**  
О: Да, вы можете получить бесплатную пробную версию Aspose.GIS со страницы [Aspose.GIS free trial page](https://releases.aspose.com/).

**В: Где можно получить поддержку Aspose.GIS?**  
О: Вы можете получить поддержку на форуме сообщества Aspose.GIS [Aspose.GIS community forum](https://forum.aspose.com/c/gis/33).

## Заключение

Теперь у вас есть полный, готовый к продакшн рецепт для **конвертации geojson в topojson** с группировкой объектов с помощью Aspose.GIS для .NET. Устанавливая `ObjectNameAttribute`, вы контролируете организацию объектов, что упрощает последующее стилизование и взаимодействие в веб‑картах. Не стесняйтесь исследовать другие драйверы, экспериментировать с различными атрибутами группировки и интегрировать эту конвертацию в более крупные GIS‑конвейеры.

---

**Последнее обновление:** 2026-08-03  
**Тестировано с:** Aspose.GIS for .NET (latest release)  
**Автор:** Aspose  

---

## Связанные руководства

- [Как конвертировать GeoJSON в TopoJSON с помощью Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Как конвертировать GeoJSON в TopoJSON с конкретным именем объекта](/gis/net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/)
- [Разблокировка функций TopoJSON с Aspose.GIS для .NET](/gis/net/layer-management/access-features-in-topojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}