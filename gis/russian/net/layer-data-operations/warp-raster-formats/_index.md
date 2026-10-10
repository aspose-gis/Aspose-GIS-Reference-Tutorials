---
date: 2026-10-10
description: Узнайте, как получить размер ячейки raster и изменить разрешение raster,
  преобразуя форматы raster с помощью Aspose.GIS for .NET – пошаговое руководство
  по визуализации пространственных данных.
keywords:
- get raster cell size
- change raster resolution
- convert geotiff .net
lastmod: 2026-10-10
linktitle: Преобразование форматов raster
og_description: Получите размер ячейки raster после преобразования растрa с помощью
  Aspose.GIS for .NET. В этом руководстве показано, как изменить разрешение raster,
  конвертировать файлы GeoTIFF и извлечь подробные метаданные raster за несколько
  простых шагов.
og_image_alt: 'Developer guide: Get raster cell size and warp raster formats using
  Aspose.GIS for .NET'
og_title: Получить размер ячейки raster и преобразовать растр с помощью Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to get raster cell size and change raster resolution by warping
    raster formats using Aspose.GIS for .NET – a step‑by‑step guide for spatial data
    visualization.
  headline: Get raster cell size – warp raster formats
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS supports a wide range of raster formats, providing flexibility
      in handling various spatial datasets.
    question: Is Aspose.GIS compatible with all raster formats?
  - answer: Aspose.GIS is designed to handle georeferenced data, ensuring accurate
      transformations. Ensure your raster images have proper spatial reference information.
    question: Can I perform raster warping on non‑georeferenced images?
  - answer: Join the discussion on the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      to share your experiences, ask questions, and collaborate with other developers.
    question: How can I contribute to the Aspose.GIS community?
  - answer: Yes, you can explore the capabilities of Aspose.GIS by downloading a free
      trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.GIS?
  - answer: Yes, if you need a temporary license, you can obtain one [here](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- raster processing
- Aspose.GIS
- .NET GIS
- geotiff warp
title: Получить размер ячейки raster – преобразование форматов raster
url: /ru/net/layer-data-operations/warp-raster-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Получить размер ячейки растра – преобразование форматов растра

## Введение
В этом руководстве вы **получите размер ячейки растра** после выполнения операции преобразования и узнаете, как **изменить разрешение растра** для любого GeoTIFF с помощью Aspose.GIS для .NET. Независимо от того, готовите ли вы данные для веб‑картографической службы, выравниваете слои для пространственного анализа или просто хотите убедиться, что репроекция сохранила требуемую детализацию, эти шаги дадут вам полный контроль над геометрией растра и его метаданными. Давайте пройдём процесс от загрузки растра до извлечения его размера ячейки и других ключевых свойств.

## Быстрые ответы
- **Какова основная цель?** Получить размер ячейки растра после выполнения операции преобразования.  
- **Какая библиотека используется?** Aspose.GIS для .NET.  
- **Нужна ли лицензия?** Доступна бесплатная пробная версия; для продакшн требуется лицензия.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Сколько времени занимает выполнение примера?** Менее минуты на типичной машине.

## Предварительные требования
Прежде чем мы начнём, убедитесь, что у вас есть следующие предварительные требования:
- Aspose.GIS для .NET: Если вы ещё этого не сделали, скачайте и установите библиотеку Aspose.GIS. Последнюю версию можно найти [здесь](https://releases.aspose.com/gis/net/).
- Ваш каталог документов: Создайте каталог для хранения ваших документов. Это будет важно для управления файлами во время процесса преобразования растра.

Теперь, когда всё готово, давайте погрузимся в код.

## Импорт пространств имён
`Aspose.GIS` namespace provides the core classes for raster and vector operations. Import the necessary namespaces to start your geospatial adventure.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Raster;
using Aspose.Gis.SpatialReferencing;
```

## Шаг 1: инициализировать путь
Начните с установки пути к вашему каталогу документов. Здесь будет происходить всё волшебство:

```csharp
string dataDir = "Your Document Directory";
```

## Шаг 2: открыть слой растра
Класс `RasterLayer` представляет один набор данных растра, загруженный в память. Открытие GeoTIFF подготавливает его к последующим преобразованиям.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(dataDir, "raster_float32.tif")))
```

## Шаг 3: преобразовать растр
Метод `Warp` репроецирует и пересэмплирует растр в новую систему координат и разрешение. Он абстрагирует сложные вычисления, позволяя указать целевые размеры и целевую пространственную ссылочную систему в одном вызове.  
`WarpOptions` позволяет задать параметры, такие как ширина и высота вывода, а также целевая пространственная ссылочная система для операции преобразования.

```csharp
using (var warped = layer.Warp(new WarpOptions(){Height = 40, Width = 40, TargetSpatialReferenceSystem = SpatialReferenceSystem.Wgs84}))
```

## Шаг 4: извлечь информацию о растре
После преобразования вы можете запросить у полученного растра важные метаданные, такие как размер ячейки, система пространственной ссылки, границы и количество полос. Эти свойства позволяют проверить, что трансформация прошла как ожидалось.

```csharp
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
var bandCount = warped.BandCount;
```

## Шаг 5: вывести детали растра
Выведем ключевые детали, которые мы извлекли, предоставив вам быстрый обзор геометрии и содержимого преобразованного растра.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
Console.WriteLine($"bandCount: {bandCount}");
```

## Шаг 6: исследовать полосы растра
`RasterBand` представляет отдельную полосу (слой) растровых данных, такие как красный, зелёный, синий или значения высот. Каждая полоса содержит отдельный канал данных, который можно проверить на тип данных, статистику и обработку NoData.

```csharp
for (int i = 0; i < warped.BandCount; i++)
{
    var dataType = warped.GetBand(i).DataType;
    var hasNoData = !warped.NoDataValues.IsNull();
    var statistics = warped.GetStatistics(i);
    Console.WriteLine();
    Console.WriteLine($"Band: {i}");
    Console.WriteLine($"dataType: {dataType}");
    Console.WriteLine($"statistics: {statistics}");
    Console.WriteLine($"hasNoData: {hasNoData}");
    if (hasNoData)
        Console.WriteLine($"noData: {warped.NoDataValues[i]}");
}
```

## Зачем получать размер ячейки растра?
Получение размера ячейки растра после преобразования показывает расстояние на местности, представляемое каждым пикселем. Эта информация важна, когда необходимо выровнять несколько слоёв, выполнить анализы, основанные на расстояниях, или подтвердить, что преобразование сохранило требуемое пространственное разрешение.

## Как эффективно преобразовывать форматы растра
Метод `Warp` абстрагирует сложную логику репроекции, позволяя сосредоточиться на входных параметрах, таких как целевые размеры и целевая пространственная ссылочная система. Это упрощает преобразование данных между системами координат, пересэмплирование до другого разрешения или обрезку до конкретной области.

## Количественные преимущества Aspose.GIS
Aspose.GIS поддерживает **более 30 форматов растра** и может обрабатывать файлы размером до **2 ГБ** без загрузки всего изображения в память, обеспечивая быстрые и экономные по памяти преобразования на типичном серверном оборудовании.

## Распространённые проблемы и решения
- **Неожиданные значения размера ячейки:** Убедитесь, что параметры `Height` и `Width` соответствуют желаемому разрешению вывода.  
- **Отсутствует пространственная ссылка:** Если `spatialRefSys` возвращает null, проверьте, содержит ли исходный GeoTIFF корректные метаданные CRS.  
- **Обработка NoData:** Используйте `warped.NoDataValues.IsNull()` для обнаружения отсутствующих данных; также можно задать пользовательское значение NoData перед преобразованием.

## Часто задаваемые вопросы

**В: Совместим ли Aspose.GIS со всеми форматами растра?**  
**О:** Да, Aspose.GIS поддерживает широкий спектр форматов растра, обеспечивая гибкость при работе с различными пространственными наборами данных.

**В: Можно ли выполнять преобразование растра для негеореференцированных изображений?**  
**О:** Aspose.GIS предназначен для работы с геореференцированными данными, обеспечивая точные преобразования. Убедитесь, что ваши растровые изображения имеют корректную информацию о пространственной ссылке.

**В: Как я могу внести свой вклад в сообщество Aspose.GIS?**  
**О:** Присоединяйтесь к обсуждению на [форуме Aspose.GIS](https://forum.aspose.com/c/gis/33), делитесь опытом, задавайте вопросы и сотрудничайте с другими разработчиками.

**В: Доступна ли бесплатная пробная версия Aspose.GIS?**  
**О:** Да, вы можете изучить возможности Aspose.GIS, скачав бесплатную пробную версию [здесь](https://releases.aspose.com/).

**В: Доступны ли временные лицензии для Aspose.GIS?**  
**О:** Да, если вам нужна временная лицензия, её можно получить [здесь](https://purchase.aspose.com/temporary-license/).

---

**Последнее обновление:** 2026-10-10  
**Тестировано с:** Aspose.GIS для .NET (последний релиз)  
**Автор:** Aspose

## Связанные руководства

- [Операции с данными слоёв](/gis/net/layer-data-operations/)
- [Как добавить слой в набор данных File GDB с пространственной ссылкой WGS84 с помощью Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)
- [Как создать векторный слой с SRS с помощью Aspose.GIS для .NET](/gis/net/layer-management/create-vector-layer-with-srs/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}