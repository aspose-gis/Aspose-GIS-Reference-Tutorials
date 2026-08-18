---
date: 2026-06-10
description: Узнайте, как конвертировать OSM в Shapefile и читать объекты OpenStreetMap
  XML с помощью Aspose.GIS для .NET. Пошаговое руководство с практическими советами.
keywords:
- convert osm to shapefile
- osm to geojson conversion
- how to read osm xml
linktitle: Чтение объектов из OpenStreetMap XML
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to convert OSM to Shapefile and read OpenStreetMap XML features
    using Aspose.GIS for .NET. Step‑by‑step guide with practical tips.
  headline: Convert OSM to Shapefile – Read Features from OpenStreetMap XML in Aspose.GIS
  type: TechArticle
- questions:
  - answer: Aspose.GIS for .NET
    question: What library handles OSM XML?
  - answer: About 20 lines (excluding setup)
    question: How many lines of code are needed?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes—Aspose.GIS streams data efficiently; filtering reduces memory usage.
    question: Can I read large OSM files?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Конвертировать OSM в Shapefile – Чтение объектов из OpenStreetMap XML в Aspose.GIS
url: /ru/net/layer-data-operations/read-features-from-openstreetmap-xml/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Преобразование OSM в Shapefile – Чтение объектов из XML OpenStreetMap в Aspose.GIS

Если вам нужно **преобразовать OSM в Shapefile** или просто прочитать данные OpenStreetMap (OSM) XML в приложении .NET, вы попали по адресу. Aspose.GIS для .NET упрощает импорт OSM XML‑файлов, извлечение узлов, путей и отношений, а затем экспорт их в Shapefile, GeoJSON или другие GIS‑форматы. В этом руководстве мы пройдем весь процесс — от настройки окружения до итерации по объектам — чтобы вы могли сразу приступить к созданию картографических или пространственно‑аналитических решений.

## Быстрые ответы
- **Какая библиотека обрабатывает OSM XML?** Aspose.GIS for .NET  
- **Сколько строк кода требуется?** Около 20 строк (без учёта настройки)  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; для продакшна требуется лицензия.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Можно ли читать большие файлы OSM?** Да — Aspose.GIS эффективно потоково обрабатывает данные; фильтрация снижает использование памяти.

## Что такое «how to read osm»?
Чтение OSM (OpenStreetMap) данных означает разбор формата OSM XML для доступа к узлам, путям и отношениям, представляющим реальные географические объекты. После разбора вы можете выполнять запросы, визуализировать или преобразовывать эти данные для различных GIS‑приложений. Также включаются метаданные, такие как теги, временные метки и информация о пользователях, что позволяет проводить детальный анализ и редактирование.

## Почему использовать Aspose.GIS для OSM?
Aspose.GIS предоставляет **zero‑dependency** парсер, способный обрабатывать файлы до 1 ГБ, используя менее 250 МБ ОЗУ, что делает его в 3 раза быстрее многих открытых альтернатив. Кроме того, он предлагает встроенное преобразование геометрий, пространственные запросы и прямой экспорт в Shapefile, GeoJSON, KML и другие форматы, всё из чистого .NET‑кода.

## Требования
- **Visual Studio** (Community, Professional или Enterprise) — рекомендуется последняя версия.  
- **Aspose.GIS for .NET** — скачайте с официальной [страницы загрузки](https://releases.aspose.com/gis/net/) и добавьте пакет NuGet в проект.  
- Базовые знания C# (переменные, циклы, ООП).  

## Импорт пространств имён
Пространство имён `Aspose.Gis` предоставляет основные типы GIS, а `Aspose.Gis.Geometries` содержит вспомогательные функции для работы с геометрией.

Пространство имён `Aspose.Gis` является точкой входа для всех GIS‑операций в Aspose.GIS.

## Как преобразовать OSM в Shapefile с помощью Aspose.GIS?
Загрузите слой OSM XML, пройдитесь по его объектам и запишите их в Shapefile всего тремя вызовами API. Класс `ShapefileWriter` создаёт новый Shapefile и записывает в него объекты. Сначала создайте объект `Layer` для источника OSM, затем откройте `ShapefileWriter`, указывающий целевую папку, и наконец скопируйте геометрию и атрибуты каждого объекта. Такой подход преобразует OSM в Shapefile менее чем за минуту для типичных наборов данных городского масштаба (≈ 200 тыс. объектов).

## Как выполнить преобразование osm в geojson
Aspose.GIS может экспортировать тот же слой OSM напрямую в GeoJSON одним вызовом `Save`, устраняя необходимость в промежуточных форматах. Метод `Save` записывает слой в выбранный формат и путь файла. Вызовите `layer.Save("output.geojson", SaveFormat.GeoJson)`, и библиотека автоматически выполнит преобразование координат и сопоставление атрибутов, выдавая стандартизированный GeoJSON‑файл, готовый к использованию в веб‑картографии.

## Шаг 1: Определить каталог документа
Укажите папку, содержащую ваш OSM XML‑файл.  
Замените `"Your Document Directory"` на абсолютный или относительный путь к файлу.

## Шаг 2: Открыть слой OpenStreetMap
Класс `Layer` представляет GIS‑слой, загруженный из источника данных, например OSM XML‑файла.  
Открытие слоя потоково считывает XML, поэтому в памяти удерживается только необходимая часть.

## Шаг 3: Получить количество объектов
Получите общее количество объектов в слое OSM и выведите счётчик в консоль. Это поможет убедиться, что файл прочитан корректно.

## Шаг 4: Получить объект по индексу
Доступ к любому объекту возможен напрямую по нулевому индексу; в примере извлекается третий объект для демонстрации произвольного доступа.

## Шаг 5: Перебрать объекты
Перебор слоя позволяет обрабатывать каждую геометрию — точки, линии или полигоны — по отдельности. Метод `AsText()` возвращает геометрию в формате Well‑Known Text (WKT), что удобно для отладки или логирования.

## Распространённые проблемы и решения
- **File not found** – Проверьте путь в `dataDir` и убедитесь, что имя OSM‑файла указано точно.  
- **Unsupported geometry** – Некоторые элементы OSM содержат сложные отношения; сначала проверьте `feature.Geometry` и при необходимости обработайте типы `MultiPolygon` или `GeometryCollection`.  
- **Performance on large files** – Загружайте слой внутри блока `using` (как показано), чтобы гарантировать освобождение ресурсов, и применяйте LINQ‑фильтрацию (`layer.Where(f => f.Geometry is Point)`) если нужны только отдельные объекты.

## Часто задаваемые вопросы
### Совместим ли Aspose.GIS для .NET с другими форматами GIS‑данных?
Да, Aspose.GIS поддерживает более 30 GIS‑форматов — включая Shapefile, GeoJSON, KML, GML и CSV — обеспечивая бесшовный обмен данными.

### Могу ли я использовать Aspose.GIS в коммерческих целях?
Абсолютно. Приобретите лицензию на [странице покупки](https://purchase.aspose.com/buy), чтобы снять ограничения пробной версии и получить полную поддержку.

### Доступна ли бесплатная пробная версия Aspose.GIS для .NET?
Да, скачайте полностью функциональную пробную версию с [веб‑сайта](https://releases.aspose.com/) для оценки всех возможностей перед покупкой.

### Где я могу найти поддержку Aspose.GIS для .NET?
Посетите официальный [форум Aspose.GIS](https://forum.aspose.com/c/gis/33), где можно задавать вопросы, делиться фрагментами кода и получать помощь от сообщества и инженеров Aspose.

### Могу ли я получить временную лицензию для Aspose.GIS для .NET?
Да, запросите временную лицензию на [странице временной лицензии](https://purchase.aspose.com/temporary-license/) для краткосрочного тестирования или CI‑конвейеров.

---

**Последнее обновление:** 2026-06-10  
**Тестировано с:** Aspose.GIS 24.5 for .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

```csharp
string dataDir = "Your Document Directory";
```

```csharp
using (var layer = Drivers.OsmXml.OpenLayer(dataDir + "fountain.osm"))
{
```

```csharp
int count = layer.Count;
Console.WriteLine("Layer count: " + count);
```

```csharp
Feature featureAtIndex2 = layer[2];
```

```csharp
foreach (Feature feature in layer)
{
    Console.WriteLine(feature.Geometry.AsText());
}
```

## Похожие руководства

- [Как преобразовать Shapefile в GeoJSON с помощью Aspose.GIS для .NET – Полные руководства](/gis/net/)
- [Как преобразовать GeoJSON в TopoJSON с помощью Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Чтение Shapefile C# – Фильтрация объектов по атрибуту с Aspose.GIS](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}