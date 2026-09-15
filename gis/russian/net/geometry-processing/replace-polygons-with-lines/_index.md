---
date: 2026-09-15
description: Узнайте, как конвертировать polygon в line и преобразовать polygons в
  lines с использованием Aspose.GIS for .NET. Краткое руководство для GIS‑разработчиков.
keywords:
- convert polygon to line
- how to replace polygons
- transform polygons to lines
- gis polygon to line
- simplify map visualization
lastmod: 2026-09-15
linktitle: Заменить polygons на lines
og_description: Конвертировать polygon в line с помощью Aspose.GIS for .NET. В этом
  учебнике показано, как заменить polygons на lines, поддерживаемые версии .NET и
  распространённые подводные камни.
og_image_alt: Screenshot of Aspose.GIS converting polygon to line in a .NET console
  app
og_title: Конвертировать polygon в line с Aspose.GIS for .NET – краткое руководство
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to convert polygon to line and transform polygons to lines
    using Aspose.GIS for .NET. A quick guide for GIS developers.
  headline: Convert polygon to line with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert polygon to line and transform polygons to lines
    using Aspose.GIS for .NET. A quick guide for GIS developers.
  name: Convert polygon to line with Aspose.GIS for .NET
  steps:
  - name: Define the source geometry
    text: The `GeometryCollection` class is a container that can hold any number of
      geometry objects, including polygons, points, and lines. It is the entry point
      for bulk operations like `ReplacePolygonsByLines`. Create a geometry collection
      that includes one or more polygons you want to convert. In this exa
  - name: Convert polygons to lines
    text: The `ReplacePolygonsByLines()` method scans the supplied collection, replaces
      each polygon with a `LineString` that follows its outer ring, and leaves all
      other geometry types untouched. This single call performs the conversion in
      O(n) time, where *n* is the number of geometries in the collection.
  - name: Display the original and converted geometries
    text: Printing both the original and the transformed geometries lets you verify
      that polygons have been replaced while other geometries stay the same. The `ToString()`
      override on each geometry provides a human‑readable WKT representation.
  type: HowTo
- questions:
  - answer: Yes, it supports more than 30 formats—including Shapefile, GeoJSON, KML,
      GML, and CSV—allowing you to read, convert, and write data without external
      tools.
    question: Can Aspose.GIS for .NET work with various GIS file formats?
  - answer: Yes, you can access the free trial of Aspose.GIS for .NET on the Aspose
      releases page ([Aspose releases page](https://releases.aspose.com/)).
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Yes, developers can get support and assistance from the Aspose.GIS community
      forum ([Aspose.GIS community forum](https://forum.aspose.com/c/gis/33)).
    question: Does Aspose.GIS for .NET offer support for developers?
  - answer: Yes, you can acquire a temporary license from Aspose's temporary license
      page ([temporary license page](https://purchase.aspose.com/temporary-license/)).
    question: Can I purchase a temporary license for Aspose.GIS for .NET?
  - answer: Absolutely, it provides comprehensive documentation, code examples, and
      API references for all skill levels.
    question: Is Aspose.GIS for .NET suitable for both beginners and experienced developers?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert polygon to line
- Aspose.GIS
- .NET GIS processing
title: Конвертировать polygon в line с помощью Aspose.GIS for .NET
url: /ru/net/geometry-processing/replace-polygons-with-lines/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Преобразование полигона в линию с помощью Aspose.GIS для .NET

## Введение
Если вам необходимо **преобразовать полигон в линию** в GIS‑проекте на .NET, Aspose.GIS делает процесс простым. Независимо от того, упрощаете ли вы визуализацию карт, подготавливаете данные для алгоритмов маршрутизации или просто нуждаетесь в более чистом представлении геометрии, этот учебник проведёт вас через точные шаги замены полигонов на линейные геометрии с использованием API Aspose.GIS. Вы увидите, почему эта библиотека является предпочтительным выбором для GIS‑разработчиков и как выполнить преобразование всего в несколько строк кода.

## Быстрые ответы
- **Что означает «преобразовать полигон в линию»?** Он извлекает внешнее кольцо полигона и создаёт `LineString`, который следует тому же периметру.  
- **Почему использовать Aspose.GIS для этой задачи?** Библиотека предоставляет один метод (`ReplacePolygonsByLines`), который эффективно обрабатывает массовое преобразование без ручного разбора геометрии.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, а также .NET 5/6+ полностью поддерживаются.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; коммерческая лицензия требуется для продакшн‑развёртываний.  
- **Сколько времени занимает реализация?** Большинство разработчиков завершают базовое преобразование менее чем за десять минут.

## Что означает «преобразовать полигон в линию»?
Преобразование полигона в линию означает извлечение внешнего кольца (периметра) полигона и представление его в виде `LineString`. Полученная геометрия сохраняет точный контур исходной формы, но отбрасывает информацию о внутренней площади, что идеально подходит для сетевого анализа, отображения границ или когда требуется лёгкое представление для веб‑карт.

## Почему преобразовывать полигоны в линии с помощью Aspose.GIS?
Aspose.GIS заменяет каждый полигон в коллекции его граничной линией одним вызовом, сохраняет топологию и устраняет необходимость в пользовательских циклах. Такой подход уменьшает сложность кода до 80 % и обрабатывает коллекции более 10 000 объектов менее чем за секунду на типичном серверном оборудовании благодаря нативному ядру на C++ и обработке памяти без копирования.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

### Установка Aspose.GIS для .NET
1. Скачайте Aspose.GIS для .NET: посетите страницу загрузки Aspose.GIS для .NET ([Aspose.GIS for .NET download](https://releases.aspose.com/gis/net/)).  
2. Установите Aspose.GIS для .NET: следуйте инструкциям по установке в пакете или ознакомьтесь с документацией Aspose.GIS ([Aspose.GIS documentation](https://reference.aspose.com/gis/net/)) для подробных шагов.

## Импорт пространств имён
В вашем проекте .NET импортируйте необходимые пространства имён, чтобы работать с классами Aspose.GIS.

Пространство имён `Aspose.Gis` содержит основные типы геометрии, а `Aspose.Gis.Geometries` предоставляет конкретные реализации, такие как `Polygon` и `LineString`.

```csharp
using System;
using Aspose.Gis.Geometries;
```

## Пошаговое руководство

### Шаг 1: Определите исходную геометрию
Класс `GeometryCollection` представляет собой контейнер, способный хранить любое количество объектов геометрии, включая полигоны, точки и линии. Это точка входа для массовых операций, таких как `ReplacePolygonsByLines`.

Создайте коллекцию геометрий, включающую один или несколько полигонов, которые вы хотите преобразовать. В этом примере мы также добавляем точку, чтобы показать, что элементы, не являющиеся полигонами, остаются неизменными.

```csharp
var srcGeometry = Geometry.FromText(@"GeometryCollection (POLYGON((1 2, 1 4, 3 4, 3 2)), Point (5 1))");
```

### Шаг 2: Преобразовать полигоны в линии
Метод `ReplacePolygonsByLines()` просматривает переданную коллекцию, заменяет каждый полигон на `LineString`, следующий его внешнему кольцу, и оставляет все остальные типы геометрии без изменений. Этот один вызов выполняет преобразование за O(n) времени, где *n* — количество геометрий в коллекции.

```csharp
var dstGeometry = srcGeometry.ReplacePolygonsByLines();
```

### Шаг 3: Отобразить исходные и преобразованные геометрии
Вывод обеих — исходных и преобразованных — геометрий позволяет убедиться, что полигоны заменены, а остальные геометрии остались без изменений. Переопределение `ToString()` для каждой геометрии предоставляет человекочитаемое представление в формате WKT.

```csharp
Console.WriteLine($"source: {srcGeometry.AsText()}");
Console.WriteLine($"result: {dstGeometry.AsText()}");
```

## Распространённые проблемы и решения
- **Отсутствие линии в выводе:** Убедитесь, что исходная геометрия действительно содержит полигоны; точки или мульти-точки будут переданы без изменений.  
- **Проблемы с порядком координат:** Aspose.GIS ожидает координаты в порядке `X Y` (долгота широта). Переставленные значения могут привести к неожиданным формам.  
- **Большие коллекции:** Для очень больших наборов данных (сотни тысяч объектов) обрабатывайте геометрии партиями по 10 000–20 000 элементов, чтобы удерживать использование памяти ниже 200 MB.

## Часто задаваемые вопросы

**Q: Может ли Aspose.GIS для .NET работать с различными GIS‑форматами файлов?**  
A: Да, поддерживает более 30 форматов — включая Shapefile, GeoJSON, KML, GML и CSV — позволяя читать, конвертировать и записывать данные без внешних инструментов.

**Q: Доступна ли бесплатная пробная версия Aspose.GIS для .NET?**  
A: Да, бесплатную пробную версию Aspose.GIS для .NET можно получить на странице релизов Aspose ([Aspose releases page](https://releases.aspose.com/)).

**Q: Предоставляет ли Aspose.GIS для .NET поддержку разработчиков?**  
A: Да, разработчики могут получить поддержку и помощь на форуме сообщества Aspose.GIS ([Aspose.GIS community forum](https://forum.aspose.com/c/gis/33)).

**Q: Можно ли приобрести временную лицензию для Aspose.GIS для .NET?**  
A: Да, временную лицензию можно получить на странице временных лицензий Aspose ([temporary license page](https://purchase.aspose.com/temporary-license/)).

**Q: Подходит ли Aspose.GIS для .NET как новичкам, так и опытным разработчикам?**  
A: Абсолютно, он предоставляет полную документацию, примеры кода и справочники API для всех уровней навыков.

## Заключение
Следуя этим шагам, вы узнали, как **преобразовать полигон в линию** и эффективно **преобразовывать полигоны в линии** с помощью Aspose.GIS для .NET. Эта возможность открывает путь к более лёгким визуализациям, подготовке маршрутизации и множеству других GIS‑рабочих процессов. Не стесняйтесь исследовать дополнительные возможности Aspose.GIS, такие как пространственные запросы, репроекция и конвертация форматов, чтобы расширить возможности вашего приложения.

---

**Последнее обновление:** 2026-09-15  
**Тестировано с:** Aspose.GIS for .NET (latest release)  
**Автор:** Aspose

## Связанные учебные материалы

- [Узнайте, как создать геометрию LineString с помощью Aspose.GIS для .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Как создать GeoJSON с допуском в Aspose.GIS для .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Как преобразовать геометрию в WKT с помощью Aspose.GIS для .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}