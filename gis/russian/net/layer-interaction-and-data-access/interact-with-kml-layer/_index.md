---
date: 2026-05-26
description: Узнайте, как создать слой KML в C# с использованием Aspose.GIS для .NET.
  Пошаговое руководство по работе с геопространственными данными, с примерами кода
  и лучшими практиками. Скачайте бесплатную пробную версию сейчас!
keywords:
- create kml layer c#
- Aspose.GIS .NET
- geospatial data C#
linktitle: Взаимодействие со слоем KML
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to create KML layer C# using Aspose.GIS for .NET. Step‑by‑step
    guide to manipulate geospatial data, with code snippets and best practices. Download
    the free trial now!
  headline: How to Create KML Layer in C# with Aspose.GIS
  type: TechArticle
- questions:
  - answer: Yes – Aspose.GIS lets you create KML layers programmatically.
    question: Can I generate KML files with C#?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: A free trial works for evaluation; a license is required for production.
    question: Do I need a license for development?
  - answer: Over 30 input and output formats, including KML, Shapefile, GeoJSON, and
      GML.
    question: How many GIS formats does Aspose.GIS handle?
  - answer: Files up to 2 GB are processed without loading the entire document into
      memory.
    question: Is there a size limit for KML files?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Как создать слой KML в C# с Aspose.GIS
url: /ru/net/layer-interaction-and-data-access/interact-with-kml-layer/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать слой KML в C# с помощью Aspose.GIS

## Введение
Если вам нужно **create KML layer C#** быстро и надёжно, Aspose.GIS для .NET предоставляет полнофункциональный API, который работает на любой платформе .NET. В этом руководстве мы пройдём точные шаги, необходимые для создания слоя KML, добавления атрибутов, заполнения объектов и сохранения файла — всё без выхода из Visual Studio. К концу вы поймёте, почему Aspose.GIS является готовым к производству решением для манипуляций с геопространственными данными.

## Быстрые ответы
- **Могу ли я генерировать файлы KML с помощью C#?** Yes – Aspose.GIS lets you create KML layers programmatically.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Нужна ли лицензия для разработки?** A free trial works for evaluation; a license is required for production.  
- **Сколько форматов GIS поддерживает Aspose.GIS?** Over 30 input and output formats, including KML, Shapefile, GeoJSON, and GML.  
- **Есть ли ограничение размера файлов KML?** Files up to 2 GB are processed without loading the entire document into memory.

## Что такое слой KML?
Слой KML — это контейнер географических данных, который хранит метки, стили и геометрию в формате Keyhole Markup Language, широко используемом для веб‑карт и Google Earth. Он может включать точки, линии, полигоны и связанные метаданные, обеспечивая богатую визуализацию в браузерах, GIS‑приложениях и Google Earth. Формат основан на XML, что делает его как человекочитаемым, так и машинно‑обрабатываемым.

## Почему стоит использовать Aspose.GIS для создания слоёв KML?
Aspose.GIS поддерживает **30+ GIS formats** и может обрабатывать **multi‑hundred‑megabyte files** при использовании памяти менее 100 MB благодаря своей потоковой архитектуре. Библиотека также гарантирует **100 % schema compliance**, поэтому генерируемый KML работает безупречно во всех основных просмотрщиках. Кроме того, библиотека предоставляет встроенную валидацию и автоматическую обработку систем координат, так что вам не нужны внешние инструменты для обеспечения соответствия.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующие требования:
- Aspose.GIS for .NET: загрузите и установите библиотеку со страницы [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).
- Среда разработки: настройте подходящую среду разработки, например Visual Studio, чтобы бесшовно интегрировать Aspose.GIS в ваши проекты .NET.

Теперь давайте погрузимся в руководство.

## Импорт пространств имён
Пространство имён `Aspose.Gis` предоставляет основные классы для работы с GIS‑данными. Его импорт даёт доступ к `KmlLayer`, `Feature` и утилитам обработки атрибутов.

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Drawing;
using System.Threading;
using Aspose.Gis.Formats.Kml;
using Aspose.Gis.Formats.Kml.Styles;
using Aspose.Gis.Geometries;
using Point = Aspose.Gis.Geometries.Point;
```

## Как создать слой KML в C#?
Загрузите целевой каталог, создайте объект `KmlLayer` с желаемым именем файла и вызовите `Save()` — и всё, что нужно для генерации корректного файла KML. API автоматически записывает необходимую XML‑структуру, так что вам не придётся управлять разметкой низкого уровня вручную.

## Шаг 1: Установите каталог документов
Определите путь к каталогу документов, где будут храниться файлы KML.

```csharp
string dataDir = "Your Document Directory";
```

## Шаг 2: Создайте слой KML
Класс `KmlLayer` — это представление Aspose.GIS файла KML на диске. Инициализация его с путём к файлу создаёт пустой слой, готовый к добавлению объектов.

```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```

## Шаг 3: Определите атрибуты
`FeatureAttribute` представляет определение столбца для объекта, указывая его имя и тип данных. Добавьте атрибуты в слой KML, чтобы представить различные типы данных, такие как string, integer, boolean и double.

```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```

## Шаг 4: Создайте и заполните объекты
`Feature` — это объект, содержащий геометрию и значения атрибутов для одной GIS‑записи. Создавайте объекты, представляющие геопространственные сущности, и задавайте значения для определённых атрибутов.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```

## Шаг 5: Добавьте ещё один объект
Повторите процесс, чтобы добавить второй объект с другими значениями атрибутов и null‑геометрией.

```csharp
Feature feature2 = layer.ConstructFeature();
feature2.SetValue("string_data", "string value2");
feature2.SetValue("int_data", 100);
feature2.SetValue("bool_data", false);
feature2.SetValue("float_data", 3.1415);
feature2.Geometry = Geometry.Null;
layer.Add(feature2);
```

## Распространённые проблемы и решения
- **Предупреждение о null‑геометрии** – Если у объекта нет геометрии, убедитесь, что вы явно задаёте геометрию `null` перед сохранением; иначе API может вызвать исключение.  
- **Несоответствие типа атрибута** – Присваиваемое значение должно соответствовать объявленному типу атрибута; иначе возникнет ошибка выполнения.  
- **Ошибки пути к файлу** – Используйте абсолютные пути или проверьте, что приложение имеет права записи в целевую папку.

## Часто задаваемые вопросы

### Совместим ли Aspose.GIS с другими форматами GIS?
Да, Aspose.GIS поддерживает различные форматы GIS, включая shapefile, GeoJSON и KML.

### Могу ли я визуализировать геопространственные данные, созданные с помощью Aspose.GIS?
Конечно! Aspose.GIS бесшовно интегрируется с библиотеками карт, позволяя визуализировать ваши геопространственные данные.

### Доступна ли пробная версия Aspose.GIS?
Да, вы можете изучить возможности Aspose.GIS, загрузив [бесплатную пробную версию](https://releases.aspose.com/).

### Как я могу получить поддержку Aspose.GIS?
Посетите [форум Aspose.GIS](https://forum.aspose.com/c/gis/33) для получения поддержки от сообщества или изучите варианты премиум‑поддержки [здесь](https://purchase.aspose.com/buy).

### Доступны ли временные лицензии для Aspose.GIS?
Да, вы можете получить временную лицензию [здесь](https://purchase.aspose.com/temporary-license/).

---

**Последнее обновление:** 2026-05-26  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Как изменить слой – Aspose.GIS .NET Layer Interaction](/gis/net/layer-interaction-and-data-access/)
- [Получить атрибуты слоя – Retrieve Layer Attribute Information with Aspose.GIS for .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Как обрезать объекты слоя с помощью Aspose.GIS for .NET](/gis/net/layer-management/crop-layer-features/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}