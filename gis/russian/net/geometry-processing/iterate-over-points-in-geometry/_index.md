---
date: 2026-06-10
description: Узнайте, как добавить points и добавить coordinates к shape, перебирая
  geometry с помощью Aspose.GIS for .NET, мощного GIS toolkit для .NET developers.
keywords:
- how to add points
- add coordinates to shape
- Aspose.GIS geometry
linktitle: Как добавить points и перебрать Geometry в .NET
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  headline: How to Add Points and Iterate Over Geometry in .NET
  type: TechArticle
- description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  name: How to Add Points and Iterate Over Geometry in .NET
  steps:
  - name: Create a `LineString` object
    text: '`LineString` is Aspose.GIS''s geometry type that represents an ordered
      collection of points forming a polyline.'
  - name: Add points to the `LineString`
    text: The `AddPoint` method inserts a new vertex (longitude, latitude) at the
      end of the line. Call it repeatedly to **add coordinates to shape** objects.
  - name: Iterate over the points
    text: '`LineString` implements `IEnumerable<IPoint>`, allowing you to loop through
      each point with a `foreach` statement. This makes extracting X (longitude) and
      Y (latitude) values trivial. The loop prints each point’s X (longitude) and
      Y (latitude) values to the console, allowing you to verify that the p'
  type: HowTo
- questions:
  - answer: '`LineString`'
    question: What is the primary class for point collections?
  - answer: Use `AddPoint(longitude, latitude)`
    question: How do you add a point?
  - answer: Yes, `LineString` implements `IEnumerable<IPoint>`
    question: Can you iterate with a foreach loop?
  - answer: .NET 6+ (or .NET Core 3.1/Framework 4.6+) and Aspose.GIS for .NET library
    question: Prerequisites?
  - answer: Building routes, visualizing tracks, or preprocessing data for spatial
      analysis
    question: Typical use case?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Как добавить points и перебрать Geometry в .NET
url: /ru/net/geometry-processing/iterate-over-points-in-geometry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как добавить точки и перебрать геометрию в .NET

## Введение

Если вы работаете с GIS‑данными в среде .NET, одной из первых вещей, которую вам нужно знать, является **как добавить точки** в геометрию и затем работать с этими точками. Aspose.GIS for .NET предоставляет чистый, объектно‑ориентированный API, который делает этот процесс простым. В этом руководстве мы пройдем создание `LineString`, добавление точек в него и перебор этих точек, чтобы вы могли извлекать координаты или выполнять дальнейший анализ. Вы также увидите, как эффективно **добавлять координаты в shape** объекты.

## Быстрые ответы
- **Какой основной класс для коллекций точек?** `LineString`
- **Как добавить точку?** Используйте `AddPoint(longitude, latitude)`
- **Можно ли перебрать с помощью цикла foreach?** Да, `LineString` реализует `IEnumerable<IPoint>`
- **Требования?** .NET 6+ (или .NET Core 3.1/Framework 4.6+) и библиотека Aspose.GIS for .NET
- **Типичный сценарий использования?** Построение маршрутов, визуализация треков или предварительная обработка данных для пространственного анализа
- **IPoint** представляет геометрию одной точки с координатами X (долгота) и Y (широта).

## Что означает «добавление точек» в GIS?

Добавление точек означает вставку отдельных пар координат (долгота, широта) в геометрический контейнер, такой как `LineString`, `Polygon` или `MultiPoint`. Каждая точка становится вершиной, определяющей форму или путь, который вы моделируете, позволяя выполнять пространственные операции и визуализации. Эти вершины позже можно использовать для анализа, экспортировать в различные GIS‑форматы или применять в пространственных вычислениях, таких как измерение расстояний или проверка пересечений.

## Почему добавлять точки с помощью Aspose.GIS?

Вы добавляете точки с помощью Aspose.GIS, потому что библиотека гарантирует **безопасную типизацию обработки геометрии**, поддерживает **более 30 векторных и растровых форматов** и может обрабатывать **многостраничные наборы данных** без загрузки всего файла в память. API также предоставляет встроенный перебор, пространственные операции и конвертацию форматов (Shapefile, GeoJSON, KML и т.д.) на любой поддерживаемой платформе.

## Требования

- Visual Studio 2022 (или любой IDE для C#)
- Установлен пакет NuGet Aspose.GIS for .NET
- Базовое понимание синтаксиса C#

## Импорт пространств имён

Начните с импорта необходимых пространств имён, чтобы получить доступ к функционалу Aspose.GIS в вашем приложении .NET:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Как добавить точки в геометрию?

Вы добавляете точки, создавая экземпляр `LineString`, вызывая его метод `AddPoint` для каждой пары координат, а затем при необходимости перебирая коллекцию. Этот трёхшаговый шаблон охватывает создание, заполнение и обход в лаконичном, читаемом виде. **LineString — тип геометрии, представляющий упорядоченную коллекцию точек, образующих полилинию.** Такой подход гарантирует, что геометрия остаётся корректной и готовой к дальнейшим пространственным операциям, таким как вычисление длины или экспорт.

### Шаг 1: Создать объект `LineString`  

`LineString` — тип геометрии Aspose.GIS, представляющий упорядоченную коллекцию точек, образующих полилинию.

```csharp
LineString line = new LineString();
```

### Шаг 2: Добавить точки в `LineString`  

Метод `AddPoint` вставляет новую вершину (долгота, широта) в конец линии. Вызывайте его многократно, чтобы **добавлять координаты в shape** объекты.

```csharp
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```

### Шаг 3: Перебрать точки  

`LineString` реализует `IEnumerable<IPoint>`, позволяя перебрать каждую точку с помощью оператора `foreach`. Это делает извлечение значений X (долгота) и Y (широта) тривиальным.

```csharp
foreach (IPoint point in line)
{
    Console.WriteLine(point.X + "," + point.Y);
}
```

Цикл выводит значения X (долгота) и Y (широта) каждой точки в консоль, позволяя убедиться, что точки были добавлены корректно.

## Распространённые сценарии использования

- **Планирование маршрута** – построить путь из GPS‑логов и затем проанализировать расстояния между контрольными точками.  
- **Проверка данных** – перебрать точки, чтобы убедиться, что они находятся в ожидаемых границах (например, внутри границ страны).  
- **Визуализация** – экспортировать `LineString` в GeoJSON или Shapefile для использования в картографических инструментах.

## Часто задаваемые вопросы

**Q1: Может ли Aspose.GIS for .NET работать с другими геометрическими формами, кроме `LineString`?**  
A: Да, Aspose.GIS поддерживает `Point`, `Polygon`, `MultiLineString`, `MultiPolygon` и многие другие типы геометрий.

**Q2: Подходит ли Aspose.GIS как для коммерческих, так и для личных проектов?**  
A: Безусловно. Лицензионные варианты охватывают коммерческие, личные и образовательные сценарии использования.

**Q3: Предоставляет ли Aspose.GIS for .NET полную документацию для начинающих?**  
A: Да, продукт включает обширную документацию, ссылки на API и десятки примеров кода, помогающих быстро начать работу.

**Q4: Могу ли я расширить функциональность Aspose.GIS for .NET с помощью пользовательской разработки?**  
A: Вы можете создавать методы‑расширения или оборачивать классы Aspose.GIS под конкретные рабочие процессы, получая полный контроль над пользовательскими геопространственными решениями.

**Q5: Доступна ли техническая поддержка для пользователей Aspose.GIS?**  
A: Специальная техническая поддержка предоставляется через форумы Aspose и систему тикетов, гарантируя быструю помощь.

---

**Последнее обновление:** 2026-06-10  
**Тестировано с:** Aspose.GIS for .NET 24.5 (latest at time of writing)  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Как подсчитать точки в геометрии с помощью Aspose.GIS for .NET](/gis/net/geometry-creation/count-points-in-geometry/)
- [Как добавить точку в LineString и преобразовать геометрию в редактируемый формат с Aspose.GIS](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [Создать геометрию MultiPoint с Aspose.GIS for .NET](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}