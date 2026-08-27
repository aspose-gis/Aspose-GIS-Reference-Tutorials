---
date: 2026-08-08
description: Изучите анализ symmetric difference GIS overlay с использованием Aspose.GIS
  for .NET. Этот tutorial показывает, как выполнять overlay, polygon intersection,
  union, difference и symmetric difference на C#.
keywords:
- symmetric difference gis
- calculate polygon intersection
- how to perform overlay
lastmod: 2026-08-08
linktitle: Найти Geometry Overlays
og_description: Узнайте, как выполнять symmetric difference GIS overlay analysis с
  Aspose.GIS for .NET. Пошаговое руководство охватывает intersection, union, difference
  и многое другое.
og_image_alt: Screenshot of Aspose.GIS overlay operations in a .NET console app
og_title: Симметричная разность GIS overlay с Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn symmetric difference GIS overlay analysis using Aspose.GIS for
    .NET. This tutorial shows how to perform overlay, polygon intersection, union,
    difference, and symmetric difference in C#.
  headline: Symmetric difference GIS overlay with Aspose.GIS for .NET
  type: TechArticle
- description: Learn symmetric difference GIS overlay analysis using Aspose.GIS for
    .NET. This tutorial shows how to perform overlay, polygon intersection, union,
    difference, and symmetric difference in C#.
  name: Symmetric difference GIS overlay with Aspose.GIS for .NET
  steps:
  - name: create polygon objects
    text: A `Polygon` represents a closed shape defined by a series of coordinate
      points.
  - name: perform intersection operation
    text: '`Intersection` computes the common area shared by two polygons.'
  - name: print intersection points
    text: '`PrintRing` is a helper that prints each coordinate of a polygon’s exterior
      ring.'
  - name: perform union operation
    text: '`Union` merges two polygons into a single geometry covering all areas.'
  - name: print union points
    text: Output the coordinates of the united geometry.
  - name: perform difference operation
    text: '`Difference` subtracts the second polygon from the first, leaving the non‑overlapping
      portion.'
  - name: print difference points
    text: Show the remaining vertices after the subtraction.
  - name: perform symmetric difference operation
    text: '`SymmetricDifference` returns the parts belonging to either polygon but
      not both, producing a `MultiPolygon`.'
  - name: print symmetric difference polygons
    text: Iterate through each polygon in the `MultiPolygon` and print its points.
  type: HowTo
- questions:
  - answer: Yes, a valid commercial license permits unrestricted use in production
      applications.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, you can download a free trial from the [Aspose releases page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.GIS for .NET?
  - answer: Support is available through the Aspose GIS forum [Aspose GIS forum](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS for .NET?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses offered for testing?
  - answer: You can buy a license directly from the website [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a full license for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- gis overlay
- Aspose.GIS
- .NET geometry analysis
title: Симметричная разность GIS overlay с Aspose.GIS for .NET
url: /ru/net/geometry-analysis/find-geometry-overlays/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Симметричная разность GIS: выполнение операций наложения с Aspose.GIS для .NET

Overlay analysis — это базовая техника в любом **spatial overlay tutorial** — она позволяет комбинировать, сравнивать и извлекать инсайты из нескольких географических слоёв. В этом руководстве вы узнаете **как выполнять операции наложения** такие как Intersection, Union, Difference и Symmetric Difference с помощью мощной библиотеки Aspose.GIS для .NET. К концу урока вы сможете применять эти методы к реальным GIS‑задачам, таким как планирование землепользования, экологические исследования и оптимизация маршрутов.

## Быстрые ответы
- **Что такое операция наложения?** Наложение объединяет две геометрии, создавая новую форму — пересечение, объединение, разность или симметричную разность.  
- **Какая .NET‑библиотека обрабатывает наложения?** Aspose.GIS для .NET предоставляет полностью управляемый API для всех операций над геометрией в теории множеств.  
- **Сколько времени занимает базовая реализация?** Около 10‑15 минут на написание, компиляцию и запуск примера кода.  
- **Нужна ли лицензия для продакшна?** Да — коммерческая лицензия требуется для производственных развертываний; доступна бесплатная пробная версия для оценки.  
- **Можно ли запускать это на .NET 6+?** Абсолютно — Aspose.GIS поддерживает .NET Core, .NET 5, .NET 6 и более новые версии.

## Что такое операция наложения?

Операции наложения вычисляют новую геометрию на основе пространственного отношения двух входных фигур. **Intersection** возвращает общую площадь, **Union** объединяет площади, **Difference** вычитает одну форму из другой, а **Symmetric Difference** даёт части, принадлежащие одной из фигур, но не обеим одновременно. Эти функции теории множеств являются математической основой GIS‑анализа, позволяя отвечать на вопросы вроде «где пересекаются два земельных участка?» или «какая площадь остаётся после удаления охраняемой зоны».

## Почему стоит использовать Aspose.GIS для наложения?

Aspose.GIS поддерживает **более 50 векторных и растровых форматов**, может обрабатывать **многосотстраничные наборы данных без загрузки всего файла в память** и работает на Windows, Linux и macOS. Его управляемый API устраняет необходимость в нативных GIS‑библиотеках, снижая сложность развертывания и позволяя держать всю логику в едином .NET‑решении.

## Распространённые сценарии использования
- **Планирование землепользования:** Выявление перекрывающихся зон между предлагаемыми проектами и охраняемыми территориями.  
- **Экологический анализ:** Расчёт пересечения местообитаний с источниками загрязнения.  
- **Маршрутизация инфраструктуры:** Определение точек пересечения новых дорог с существующими коммуникационными коридорами.  
- **Городская аналитика:** Объединение нескольких муниципальных границ для создания регионального обзора.

## Предварительные требования
- Рабочая среда разработки .NET (Visual Studio, VS Code или .NET CLI).  
- Библиотека Aspose.GIS для .NET — скачайте последнюю версию с [official site](https://releases.aspose.com/gis/net/).  

### Импорт пространств имён
Прежде чем начать использовать Aspose.GIS для .NET, необходимо импортировать нужные пространства имён в ваш проект.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Как выполнять операции наложения в .NET

`Polygon` представляет замкнутую плоскую форму, определённую внешним кольцом и, при необходимости, внутренними кольцами. Каждый метод наложения (`Intersection`, `Union`, `Difference`, `SymmetricDifference`) вычисляет конкретную операцию теории множеств над двумя геометриями.

Загрузите два объекта полигонов, затем вызовите соответствующий метод — Intersection, Union, Difference или SymmetricDifference. Весь процесс укладывается в несколько лаконичных строк кода, а каждый метод возвращает геометрию, которую можно дальше исследовать или экспортировать.

**Прямой ответ:** Чтобы выполнить наложение в Aspose.GIS, создайте два объекта `Polygon`, затем вызовите нужный метод (`Intersection`, `Union`, `Difference` или `SymmetricDifference`). Каждый вызов возвращает новую геометрию, представляющую результат, которую можно сериализовать в WKT, GeoJSON или любой поддерживаемый формат.

### Шаг 1: создать объекты полигонов
`Polygon` представляет замкнутую форму, определённую набором координатных точек.

```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```

### Шаг 2: выполнить операцию пересечения
`Intersection` вычисляет общую площадь, совместно занимаемую двумя полигонами.

```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Polygon
```

### Шаг 3: вывести точки пересечения
`PrintRing` — вспомогательная функция, выводящая каждую координату внешнего кольца полигона.

```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```

### Шаг 4: выполнить операцию объединения
`Union` объединяет два полигона в одну геометрию, покрывающую все области.

```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Polygon
```

### Шаг 5: вывести точки объединения
Вывести координаты объединённой геометрии.

```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```

### Шаг 6: выполнить операцию разности
`Difference` вычитает второй полигон из первого, оставляя неперекрывающуюся часть.

```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Polygon
```

### Шаг 7: вывести точки разности
Показать оставшиеся вершины после вычитания.

```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```

### Шаг 8: выполнить операцию симметричной разности
`SymmetricDifference` возвращает части, принадлежащие одному из полигонов, но не обоим одновременно, образуя `MultiPolygon`.

```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // MultiPolygon
```

### Шаг 9: вывести полигоны симметричной разности
Итерировать каждый полигон в `MultiPolygon` и вывести его точки.

```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```

## Распространённые проблемы и решения
| Проблема | Почему происходит | Исправление |
|----------|-------------------|-------------|
| `null` результат от `Intersection` | Полигоны фактически не перекрываются. | Проверьте координаты или используйте проверку `Intersects` перед вызовом `Intersection`. |
| Неожиданный `MultiPolygon` от `SymDifference` | Симметричная разность может создавать разрозненные компоненты. | Приведите к `IMultiPolygon` и итерируйте, как показано. |
| Замедление производительности на больших наборах данных | Каждая операция пересчитывает геометрию с нуля. | Переиспользуйте промежуточные результаты или упростите геометрии с помощью `Simplify()` перед наложением. |

## Часто задаваемые вопросы

**В: Можно ли использовать Aspose.GIS для .NET в коммерческих проектах?**  
О: Да, действующая коммерческая лицензия позволяет неограниченно использовать библиотеку в продакшн‑приложениях.

**В: Есть ли пробная версия Aspose.GIS для .NET?**  
О: Да, бесплатную пробную версию можно скачать со [страницы релизов Aspose](https://releases.aspose.com/).

**В: Как получить поддержку по Aspose.GIS для .NET?**  
О: Поддержка доступна через форум Aspose GIS — [Aspose GIS forum](https://forum.aspose.com/c/gis/33).

**В: Предлагаются ли временные лицензии для тестирования?**  
О: Да, временные лицензии можно получить на странице [temporary license page](https://purchase.aspose.com/temporary-license/).

**В: Где можно приобрести полную лицензию на Aspose.GIS для .NET?**  
О: Приобрести лицензию можно напрямую на сайте — [Aspose purchase page](https://purchase.aspose.com/buy).

---

**Последнее обновление:** 2026-08-08  
**Тестировано с:** Aspose.GIS 24.11 для .NET  
**Автор:** Aspose

## Связанные руководства

- [Create Polygon Geometry C# and Check Intersection with Aspose.GIS for .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [How to Perform Spatial Overlap Analysis of Geometries with Aspose.GIS for .NET](/gis/net/geometry-analysis/check-geometries-overlap/)
- [Create Geometry Buffer Using Aspose.GIS for .NET](/gis/net/geometry-analysis/create-geometry-buffer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}