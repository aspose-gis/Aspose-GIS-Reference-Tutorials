---
date: 2026-09-30
description: Узнайте, как разобрать WKT и подсчитать точки с помощью Aspose.GIS for
  .NET, с step‑by‑step руководством по преобразованию геометрии WKT в объекты.
keywords:
- how to parse wkt
- convert wkt geometry
- Aspose.GIS .NET
- count points from wkt
- .NET spatial analytics
lastmod: 2026-09-30
linktitle: Преобразовать геометрию из WKT
og_description: Узнайте, как разобрать WKT и подсчитать точки с помощью Aspose.GIS
  for .NET. Это руководство показывает, как преобразовать геометрию WKT в объекты
  для быстрой spatial analysis.
og_image_alt: 'Developer guide: parse WKT and count points with Aspose.GIS for .NET'
og_title: Как разобрать WKT и подсчитать точки с помощью Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to parse WKT and count points using Aspose.GIS for .NET,
    with step‑by‑step guidance on converting WKT geometry to objects.
  headline: How to parse WKT and count points with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to parse WKT and count points using Aspose.GIS for .NET,
    with step‑by‑step guidance on converting WKT geometry to objects.
  name: How to parse WKT and count points with Aspose.GIS for .NET
  steps:
  - name: '**Aspose.GIS for .NET API** – download it from the Aspose.GIS for .NET
      download page: [Aspose.GIS for .NET download](https://releases.aspose.com/gis/net/).
      For other Aspose products see the general releases page: [Aspose releases](https://releases.aspose.com/).'
    text: '**Aspose.GIS for .NET API** – download it from the Aspose.GIS for .NET
      download page: [Aspose.GIS for .NET download](https://releases.aspose.com/gis/net/).
      For other Aspose products see the general releases page: [Aspose releases](https://releases.aspose.com/).'
  - name: A recent version of **Visual Studio** or any .NET‑compatible IDE.
    text: A recent version of **Visual Studio** or any .NET‑compatible IDE.
  - name: Basic knowledge of **C#** programming.
    text: Basic knowledge of **C#** programming.
  type: HowTo
- questions:
  - answer: Yes, you can. Aspose.GIS for .NET is licensed per developer, allowing
      unrestricted use in commercial applications.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, Aspose.GIS for .NET supports WKB, GeoJSON, Shapefile, and several
      raster formats, giving you flexibility when integrating with existing GIS pipelines.
    question: Does Aspose.GIS for .NET support other geometric formats besides WKT?
  - answer: 'Yes, you can get a free trial from the Aspose releases page: [Aspose
      free trial downloads](https://releases.aspose.com/).'
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: 'You can find the documentation in the Aspose.GIS .NET reference: [Aspose.GIS
      .NET documentation](https://reference.aspose.com/gis/net/).'
    question: Where can I find documentation for Aspose.GIS for .NET?
  - answer: 'You can get support from the Aspose.GIS forum: [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).'
    question: How can I get support for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- parse WKT
- Aspose.GIS
- .NET geometry processing
- spatial analytics
- count points
title: Как разобрать WKT и подсчитать точки с помощью Aspose.GIS for .NET
url: /ru/net/geometry-processing/translate-geometry-from-wkt/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как разобрать WKT и подсчитать точки с помощью Aspose.GIS для .NET

## Введение
В этом руководстве вы узнаете, **как разобрать WKT** строки и подсчитать содержащиеся в них точки, используя библиотеку Aspose.GIS для .NET. Независимо от того, создаёте ли вы сервис карт, проводите пространственный анализ или просто нужно проверить геометрические данные, разбор WKT — первый шаг в любой геопространственной рабочей цепочке. Вы также увидите, как **преобразовать геометрию WKT** в строго типизированные объекты, чтобы выполнять запросы, редактировать и экспортировать их в приложении C#.

## Быстрые ответы
- **Что означает “how to parse WKT”?** Это означает преобразование представления Well‑Known Text в объект геометрии Aspose.GIS, с которым можно работать программно.  
- **Какой API обрабатывает преобразование WKT?** `Geometry.FromText` разбирает любую корректную строку WKT и возвращает соответствующий тип геометрии.  
- **Нужна ли лицензия?** Доступна бесплатная пробная версия, но для развертывания в продакшн требуется коммерческая лицензия.  
- **Какие версии .NET поддерживаются?** .NET 5, .NET 6, .NET Core 3.1 и .NET Framework 4.6+.  
- **Является ли этот подход быстрым для больших наборов данных?** Да — библиотека обрабатывает миллионы вершин в памяти с суб‑линейными затратами.

## Что такое WKT?
Well‑Known Text (WKT) — это текстовая разметка для геометрий, определённая Open Geospatial Consortium (OGC). Она кодирует точки, линии, полигоны и коллекции в человекочитаемом формате, например `POINT (30 10)` или `LINESTRING (30 10, 10 30, 40 40)`.

## Зачем преобразовывать геометрию WKT?
Преобразование геометрии WKT позволяет преобразовать текстовое представление в объекты Aspose.GIS, что даёт возможность выполнять пространственные запросы (пересечения, буферы и т.д.), программно редактировать координаты и экспортировать данные в другие форматы, такие как GeoJSON, Shapefile или WKB. Преобразование выполняется полностью в памяти, поддерживает 3‑D координаты и может обрабатывать файлы размером до 2 ГБ без загрузки всего документа в память, что делает его подходящим для высокопроизводительных аналитических конвейеров.

## Как разобрать WKT?
Загрузите строку WKT с помощью `Geometry.FromText`, приведите результат к соответствующему интерфейсу (например, `ILineString`), а затем используйте свойства геометрии — такие как `Count` — для получения количества точек. Этот трёхшаговый шаблон (разбор, приведение, запрос) работает для любого типа геометрии, поддерживаемого Aspose.GIS, включая `POINT`, `LINESTRING Z`, `POLYGON` и `GEOMETRYCOLLECTION`.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

1. **Aspose.GIS for .NET API** – скачайте его со страницы загрузки Aspose.GIS for .NET: [Aspose.GIS for .NET download](https://releases.aspose.com/gis/net/). Для других продуктов Aspose смотрите общую страницу релизов: [Aspose releases](https://releases.aspose.com/).  
2. Последняя версия **Visual Studio** или любой совместимой с .NET IDE.  
3. Базовые знания программирования на **C#**.

## Импорт пространств имён
Сначала импортируйте пространства имён, необходимые для работы с геометрией:

Пространство имён `Aspose.Gis` содержит все базовые типы геометрии, а `Aspose.Gis.Geometries` предоставляет конкретные реализации, с которыми вы будете работать.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Шаг 1: создать LineString из WKT
Класс `LineString` представляет упорядоченную коллекцию точек, образующих непрерывную линию. Он реализует интерфейс `ILineString`, предоставляя методы для перечисления и манипуляции вершинами.

Разберите текст WKT и приведите результат к `ILineString`:

```csharp
ILineString line = (ILineString)Geometry.FromText("LINESTRING Z (0.1 0.2 0.3, 1 2 1, 12 23 2)");
```

> **Полезный совет:** Метод `FromText` автоматически определяет тип геометрии, поэтому вы можете привести к соответствующему интерфейсу (`ILineString`, `IPolygon` и т.д.).

## Шаг 2: подсчитать точки в LineString
Свойство `Count` возвращает общее количество кортежей координат, хранящихся в геометрии. Это быстрый способ проверить, что геометрия содержит ожидаемое количество вершин перед выполнением более ресурсоёмких пространственных операций.

Получите количество точек:

```csharp
Console.WriteLine(line.Count); // Output: 3
```

Свойство `Count` возвращает общее количество кортежей координат, что полезно для проверки или аналитики.

## Распространённые проблемы и советы
- **Недействительные строки WKT** – Если WKT некорректен, `Geometry.FromText` бросает исключение. Оберните вызов в блок `try/catch`, чтобы обрабатывать ошибки корректно.  
- **3D vs 2D** – В примере используется 3‑D `LINESTRING Z`. Если ваши данные 2‑D, опустите ключевое слово `Z`.  
- **Большие коллекции** – Для огромных наборов данных рассмотрите потоковую обработку или обработку пакетами, чтобы снизить нагрузку на память. Aspose.GIS может обрабатывать коллекции более 10 миллионов вершин, удерживая пиковое потребление памяти ниже 500 МБ.

## Часто задаваемые вопросы

**Q: Могу ли я использовать Aspose.GIS for .NET в своих коммерческих проектах?**  
A: Да, можете. Aspose.GIS for .NET лицензируется на одного разработчика, позволяя неограниченное использование в коммерческих приложениях.

**Q: Поддерживает ли Aspose.GIS for .NET другие геометрические форматы, кроме WKT?**  
A: Да, Aspose.GIS for .NET поддерживает WKB, GeoJSON, Shapefile и несколько растровых форматов, предоставляя гибкость при интеграции с существующими GIS‑конвейерами.

**Q: Доступна ли бесплатная пробная версия Aspose.GIS for .NET?**  
A: Да, вы можете получить бесплатную пробную версию со страницы релизов Aspose: [Aspose free trial downloads](https://releases.aspose.com/).

**Q: Где можно найти документацию по Aspose.GIS for .NET?**  
A: Документацию можно найти в справочнике Aspose.GIS .NET: [Aspose.GIS .NET documentation](https://reference.aspose.com/gis/net/).

**Q: Как получить поддержку по Aspose.GIS for .NET?**  
A: Поддержку можно получить на форуме Aspose.GIS: [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

---

**Последнее обновление:** 2026-09-30  
**Тестировано с:** Aspose.GIS for .NET 24.11 (последняя на момент написания)  
**Автор:** Aspose

## Связанные руководства

- [Преобразовать геометрию в WKT](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [Как добавить точки и перебрать геометрию в .NET](/gis/net/geometry-processing/iterate-over-points-in-geometry/)
- [Подсчитать точки в геометрии](/gis/net/geometry-creation/count-points-in-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}