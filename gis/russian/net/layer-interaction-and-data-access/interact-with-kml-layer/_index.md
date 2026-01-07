---
date: 2026-01-07
description: Узнайте, как записывать файлы KML с помощью Aspose.GIS для .NET, как
  создавать KML, добавлять логический атрибут и создавать линии (LineString) в ваших
  приложениях.
linktitle: Interact with KML Layer
second_title: Aspose.GIS .NET API
title: Как записать KML‑файл с помощью Aspose.GIS для .NET
url: /ru/net/layer-interaction-and-data-access/interact-with-kml-layer/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как записать KML‑файл с помощью Aspose.GIS для .NET

## Введение
В современном мире, ориентированном на данные, возможность **write KML file** программно дает вам возможность делиться географической информацией между платформами, визуализировать маршруты на картах и интегрировать данные о местоположении в веб‑ или мобильные приложения. Aspose.GIS для .NET упрощает этот процесс, позволяя сосредоточиться на логике, а не на деталях формата файла. В этом руководстве мы пройдем процесс создания KML‑слоя, добавления атрибутов (включая булевый атрибут) и построения геометрии line string — всё с понятным пошаговым кодом.

## Быстрые ответы
- **What does “write KML file” mean?** Генерация документа KML (Keyhole Markup Language), описывающего географические объекты, такие как точки, линии и полигоны.  
- **Which library is best for .NET?** Aspose.GIS для .NET предоставляет удобный API для создания и редактирования KML‑файлов.  
- **Do I need a license for development?** Бесплатная пробная версия подходит для оценки; для использования в продакшене требуется лицензия.  
- **Can I add custom attributes?** Да — вы можете добавлять атрибуты типа string, integer, boolean и double к каждому объекту.  
- **Is geometry creation supported?** Конечно — вы можете создавать точки, line strings, полигоны и многое другое.

## Предварительные требования
Прежде чем начать, убедитесь, что у вас есть следующие предварительные требования:
- Aspose.GIS для .NET: загрузите и установите библиотеку со страницы [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).
- Среда разработки: настройте подходящую среду разработки, например Visual Studio, для бесшовной интеграции Aspose.GIS в ваши .NET‑проекты.

## Импорт пространств имён
Прежде чем начать взаимодействовать с KML‑слоями, убедитесь, что включили необходимые пространства имён в ваш проект. Этот шаг гарантирует доступ к классам и методам, необходимым для работы с геопространственными данными.

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

## Шаг 1: Установите каталог документа
Определите путь к каталогу, где будут храниться KML‑файлы.

```csharp
string dataDir = "Your Document Directory";
```

## Шаг 2: Создайте KML‑слой
Инициализируйте KML‑слой с помощью Aspose.GIS, указав путь к KML‑файлу.

```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```

## Шаг 3: Определите атрибуты (добавьте булевый атрибут)
Добавьте атрибуты к KML‑слою для представления различных типов данных, таких как string, integer, **boolean** и double. Здесь вы “add boolean attribute” к каждому объекту.

```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```

## Шаг 4: Создайте и заполните объекты (create line string)
Создайте объекты, представляющие геопространственные сущности, и задайте значения для определённых атрибутов. Здесь мы **create line string** геометрию, чтобы проиллюстрировать простой путь.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```

## Шаг 5: Добавьте другой объект
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

## Как записать KML‑файл — собрать всё вместе
Следуя описанным выше шагам, вы получаете полностью рабочий KML‑файл, содержащий пользовательские атрибуты (включая булевый флаг) и геометрию line string. Полученный `Kml_File_out.kml` можно открыть в Google Earth, ArcGIS или любом GIS‑просмотрщике, поддерживающем KML.

## Распространённые проблемы и их решение
- **File path errors** – Убедитесь, что `dataDir` заканчивается разделителем пути (`\` или `/`), соответствующим вашей ОС.  
- **Missing license** – Пробная версия подходит для оценки, но для неограниченной записи KML‑файлов требуется лицензированная версия.  
- **Null geometry** – Установка `Geometry.Null` намеренно используется для объектов без пространственных данных; опустите её, если вам всегда нужна геометрия.

## Часто задаваемые вопросы
### Совместим ли Aspose.GIS с другими GIS‑форматами?
Да, Aspose.GIS поддерживает различные GIS‑форматы, включая shapefile, GeoJSON и KML.

### Могу ли я визуализировать геопространственные данные, созданные с помощью Aspose.GIS?
Безусловно! Aspose.GIS легко интегрируется с библиотеками карт, позволяя визуализировать ваши геоданные.

### Доступна ли пробная версия Aspose.GIS?
Да, вы можете изучить возможности Aspose.GIS, загрузив [free trial version](https://releases.aspose.com/).

### Как получить поддержку Aspose.GIS?
Посетите [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) для поддержки сообщества или изучите премиум‑поддержку [здесь](https://purchase.aspose.com/buy).

### Доступны ли временные лицензии для Aspose.GIS?
Да, временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/).

## Дополнительные часто задаваемые вопросы

**Q: Как я могу **how to create KML** файлы с пользовательским стилем?**  
A: Используйте пространство имён `Aspose.Gis.Formats.Kml.Styles` для определения иконок, цветов линий и стилей меток перед добавлением объектов.

**Q: Могу ли я эффективно записывать большие KML‑файлы?**  
A: Записывайте объекты пакетами и периодически сбрасывайте слой, чтобы снизить использование памяти.

**Q: Поддерживает ли Aspose.GIS .NET Core и .NET 6+?**  
A: Да, библиотека полностью совместима с .NET Core, .NET 5 и .NET 6.

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}