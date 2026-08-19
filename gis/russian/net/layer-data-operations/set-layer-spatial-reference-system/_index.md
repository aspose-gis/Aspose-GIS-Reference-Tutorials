---
date: 2026-06-15
description: Узнайте, как создать vector layer и установить layer spatial reference
  system с Aspose.GIS для .NET. Овладейте определением spatial reference, добавлением
  point feature и получением EPSG code.
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: Установить Layer Spatial Reference System
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Создать Vector Layer и установить Layer Spatial Reference System
url: /ru/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание векторного слоя и установка системы пространственных координат слоя

## Введение
В обширном мире географических информационных систем (GIS) **Aspose.GIS for .NET** выделяется как надёжная, высокопроизводительная библиотека, поддерживающая **более 70** векторных и растровых форматов и способная обрабатывать файлы размером более **10 ГБ** без загрузки всего набора данных в память. В этом руководстве вы **создадите векторный слой**, определите его пространственную привязку, **добавите точечный объект**, и получите код EPSG — всё с чёткими пошаговыми инструкциями. Независимо от того, создаёте ли вы сервис картографирования, конвейер преобразования данных или движок пространственного анализа, освоение этих основ обеспечит точность системы координат вашего shapefile и надёжность вашего GIS‑рабочего процесса.

## Быстрые ответы
- **Что означает «создание векторного слоя»?** Он создаёт новый GIS‑слой (например, Shapefile), который может хранить геометрии, такие как точки, линии или полигоны.  
- **Какой код EPSG используется в примере?** EPSG 26918 (NAD83 / UTM зона 18N).  
- **Могу ли я добавить точечный объект после создания слоя?** Да — используйте `ConstructFeature()` и назначьте геометрию `Point`.  
- **Как получить CRS слоя?** Прочитайте `layer.SpatialReferenceSystem.EpsgCode` или `.Name`.  
- **Нужна ли лицензия для Aspose.GIS?** Доступна бесплатная пробная версия; для использования в продакшене требуется лицензия.

## Что такое создание векторного слоя?
Операция **создания векторного слоя** создаёт новый векторный набор данных (например, Shapefile), который может содержать геометрические объекты и атрибутные данные. В Aspose.GIS это делается путем создания объекта `VectorLayer` с драйвером и системой пространственных ссылок.

## Почему важно правильно задавать систему координат слоя (CRS)?
Установка правильной системы координат (CRS) гарантирует, что каждая сохраняемая геометрия будет согласована с другими пространственными наборами данных. С помощью Aspose.GIS вы можете задать CRS, используя стандартный код EPSG, что обеспечивает совместимость с GIS‑программным обеспечением по всему миру. Например, EPSG 26918 определяет NAD83 / UTM зона 18N, распространённую проекцию для данных восточной части США.

## Требования
- Опыт разработки на .NET (C# или VB.NET).  
- Visual Studio 2022 или новее.  
- Библиотека Aspose.GIS for .NET – скачайте её **[здесь](https://releases.aspose.com/gis/net/)**.  
- Базовые знания о системах пространственных ссылок (CRS/EPSG).

## Импорт пространств имён
Пространство имён `Aspose.Gis` предоставляет основные GIS‑классы, а `Aspose.Gis.Geometries` — типы геометрий, такие как `Point`.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Как создать векторный слой в Aspose.GIS for .NET?
VectorLayer представляет векторный набор данных, такой как Shapefile, и предоставляет методы для создания, чтения и редактирования объектов.  
SpatialReferenceSystem определяет систему координат с помощью кода EPSG.  

Загрузите целевую папку, определите `SpatialReferenceSystem` с кодом EPSG и вызовите `VectorLayer.Create` с драйвером Shapefile. Этот единственный вызов создаёт новый файл `.shp`, записывает сопутствующие файлы `.shx` и `.dbf` и встраивает метаданные CRS, готовые к эффективному добавлению объектов.

### Шаг 1: Укажите каталог документа
Начните с указания пути к вашему каталогу документов. Это будет место, где хранятся файлы пространственных данных.

```csharp
string dataDir = "Your Document Directory";
```

### Шаг 2: Определите пространственную привязку и задайте систему координат Shapefile
`SpatialReferenceSystem` представляет CRS слоя, идентифицируемый кодом EPSG.  

Определите путь к Shapefile и **задать пространственную привязку** с использованием кода EPSG (26918 в данном примере). Этот шаг **устанавливает систему координат shapefile** для слоя.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Как добавить точечный объект в векторный слой?
`Point` — тип геометрии, представляющий одну пару координат X/Y.  

Создайте новый объект, назначьте ему геометрию `Point` с нужными координатами X/Y и добавьте объект в открытый `VectorLayer`. Операция записывает геометрию в файл `.shp` и запись атрибутов в файл `.dbf` в одной транзакции.

### Шаг 3: Создайте векторный слой
`ConstructFeature` создаёт новый объект функции, который может содержать геометрию и атрибутные данные.  

Теперь **создайте векторный слой** с указанным путём к Shapefile, типом драйвера (Shapefile) и только что определённой системой пространственной привязки.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### Шаг 4: Добавьте точечный объект в слой
Создайте новый объект функции и **добавьте точечный объект**, задав его геометрию ( `Point` с координатами 60, 24). Затем добавьте объект в векторный слой.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### Шаг 5: Получите информацию о системе пространственной привязки (получить код EPSG)
Откройте векторный слой и получите информацию о системе пространственной привязки, например код EPSG и человекочитаемое название. Это демонстрирует, как **получить код EPSG** и **задать CRS слоя**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## Распространённые проблемы и решения
| Проблема | Почему происходит | Решение |
|-------|----------------|-----|
| **Не удаётся открыть слой** | Неправильный драйвер или повреждённый путь к файлу | Проверьте `Drivers.Shapefile` и убедитесь, что `path` указывает на существующий файл `.shp`. |
| **Отображается неверный CRS** | Используется неправильный код EPSG | Проверьте код EPSG в надёжном источнике (например, EPSG.io). |
| **Объект не сохранён** | Не вызван `layer.Add(feature)` внутри блока `using` | Убедитесь, что метод `Add` выполнен до освобождения слоя. |

## Часто задаваемые вопросы
**В: Как изменить CRS существующего Shapefile?**  
О: Откройте слой, создайте новый `SpatialReferenceSystem` с нужным кодом EPSG, назначьте его `layer.SpatialReferenceSystem`, затем сохраните слой.

**В: Могу ли я добавить другие типы геометрий (например, полигоны) тем же подходом?**  
О: Да — замените `new Point(x, y)` на `new Polygon(...)` или `new LineString(...)` при необходимости.

**В: Можно ли эффективно работать с большими наборами данных?**  
О: Используйте потоковые API (`VectorLayer.Create` с `FeatureCollection`) и своевременно освобождайте слои, чтобы освободить ресурсы.

**В: Поддерживает ли Aspose.GIS преобразование координат?**  
О: Да — используйте `Geometry.Transform(targetSrs)`, чтобы переопределять проекции геометрий между разными системами координат.

**В: Какие версии .NET поддерживаются?**  
О: Aspose.GIS работает с .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

**Последнее обновление:** 2026-06-15  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Создать векторный слой и задать линейную толерантность с помощью Aspose.GIS for .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Создать векторный слой в File GDB – руководство Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [spatial reference wgs84 – Добавить слой в GDB с помощью Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}