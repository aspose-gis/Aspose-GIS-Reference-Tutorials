---
date: 2026-07-19
description: Узнайте, как вычислять расстояние между геометриями с использованием
  Aspose.GIS для .NET. Это пошаговое руководство показывает, как использовать Aspose.GIS,
  получать расстояние до геометрии и интегрировать расчёты расстояний в ваши приложения.
keywords:
- how to calculate distance
- point to polygon distance
- euclidean distance gis
lastmod: 2026-07-19
linktitle: Как вычислить расстояние между геометриями
og_description: Как вычислять расстояние между геометриями с использованием Aspose.GIS
  для .NET. Узнайте о точных вычислениях евклидова расстояния, поддержке 3D и практических
  примерах.
og_image_alt: 'Developer guide: calculate distance between geometries using Aspose.GIS
  in .NET'
og_title: Как вычислить расстояние между геометриями с помощью Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to calculate distance between geometries using Aspose.GIS
    for .NET. This step‑by‑step guide shows how to use Aspose.GIS, get distance to
    geometry, and integrate distance calculations into your applications.
  headline: How to Calculate Distance Between Geometries with Aspose.GIS
  type: TechArticle
- description: Learn how to calculate distance between geometries using Aspose.GIS
    for .NET. This step‑by‑step guide shows how to use Aspose.GIS, get distance to
    geometry, and integrate distance calculations into your applications.
  name: How to Calculate Distance Between Geometries with Aspose.GIS
  steps:
  - name: Create a Polygon Geometry
    text: The `Polygon` class represents a planar area defined by a closed ring of
      points. We start with an empty polygon that will later represent a rectangular
      area.
  - name: Define the Polygon Exterior Ring
    text: The exterior ring is a closed loop of points that defines the polygon’s
      boundary. In this example we create a 1 × 1 square.
  - name: Create a LineString Geometry
    text: The `LineString` class is a sequence of connected line segments that models
      a road, river, or any linear feature.
  - name: Add Points to the LineString
    text: These two points give the line a slanted shape that does not intersect the
      polygon, which makes the distance calculation interesting.
  - name: Calculate the Distance
    text: '`GetDistanceTo` returns the shortest Euclidean distance between two geometries
      in the same CRS. Here we **get distance to geometry** by calling `GetDistanceTo`.
      Aspose.GIS computes the shortest distance between the polygon’s edge and the
      line.'
  - name: Output the Result
    text: The result is printed with two decimal places (`0.63`). This value represents
      the minimum Euclidean distance between the square and the line.
  type: HowTo
- questions:
  - answer: The method uses double‑precision arithmetic and follows the OGC Simple
      Features Specification, providing sub‑meter accuracy for typical planar coordinates.
    question: How accurate is the distance returned by `GetDistanceTo`?
  - answer: Yes—simply call `point.GetDistanceTo(polygon)` (or the reverse) and Aspose.GIS
      will return the shortest distance from the point to the polygon’s edge.
    question: Can I calculate distance between a `Point` and a `Polygon`?
  - answer: While there isn’t a single batch method, you can loop over collections
      of geometries and reuse the same `GetDistanceTo` call efficiently.
    question: Does the API support batch distance calculations?
  - answer: The method returns `0.0` because the shortest distance between intersecting
      geometries is zero.
    question: What happens if the geometries intersect?
  - answer: Yes—use `Geometry.GetNearestPoints(Geometry other)` which returns a tuple
      containing the closest points on both geometries.
    question: Is there a way to get the nearest points on each geometry?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- calculate distance
- Aspose.GIS
- .NET geometry analysis
title: Как вычислить расстояние между геометриями с помощью Aspose.GIS
url: /ru/net/geometry-analysis/calculate-distance-between-geometries/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как вычислить расстояние между геометриями с помощью Aspose.GIS

## Введение
Если вам когда‑нибудь нужно было узнать **как вычислить расстояние** между двумя пространственными объектами — будь то дорожная сеть, зоны доставки или экологические объекты — это руководство для вас. В .NET Aspose.GIS делает вычисление расстояний простым, точным и производительным. Мы пройдём через реальный пример, который покажет **как использовать Aspose.GIS**, создать простые геометрии и вызвать метод **GetDistanceTo**, чтобы получить расстояние между ними.

## Быстрые ответы
- **Что означает «вычислить расстояние» в ГИС?** Возвращает кратчайшее (евклидовое) расстояние между двумя геометриями.  
- **Какой класс Aspose.GIS предоставляет вычисление?** `Geometry.GetDistanceTo(Geometry other)`.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; лицензия требуется для продакшна.  
- **Можно ли вычислять расстояние для 3‑D геометрий?** Да, Aspose.GIS поддерживает как 2‑D, так и 3‑D вычисления.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## Как вычислить расстояние между геометриями
В этом руководстве мы сосредоточимся на измерении **расстояния между точкой и полигоном** — типичная задача, когда нужно знать, насколько далеко объект (например, датчик или местоположение клиента) находится от заданной области. Хотя в примере используется `Polygon` и `LineString`, тот же метод `GetDistanceTo` прекрасно работает и для сценария `Point`‑to‑`Polygon`.

## Что такое вычисление расстояния в геопространственном программировании?
Вычисление расстояния определяет кратчайший отрезок, соединяющий две геометрии, измеренный в той же системе координат. Это фундаментально для анализа близости, маршрутизации, кластеризации и пространственного индексирования, позволяя разработчикам оценивать, насколько близки объекты друг к другу, и инициировать действия, основанные на местоположении.

## Почему стоит использовать Aspose.GIS для вычисления расстояния?
Aspose.GIS предлагает высокоточное арифметическое вычисление с двойной точностью, нулевые внешние зависимости и кроссплатформенную поддержку Windows, Linux и macOS. Он работает как с 2‑D, так и с 3‑D геометриями, обрабатывает файлы размером более 2 ГБ и может управлять миллионами вершин без загрузки всего набора данных в память, что делает его идеальным для масштабных вычислений расстояний.

## Предварительные требования
- **Aspose.GIS for .NET** установлен (скачать со страницы [Aspose.GIS for .NET releases page](https://releases.aspose.com/gis/net/)).  
- Базовые знания C# и структуры проекта .NET.  
- Среда разработки, например Visual Studio 2022 или VS Code.

## Импорт пространств имён
Прежде чем начать использовать Aspose.GIS, добавьте необходимые пространства имён в ваш файл C#:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Шаг 1: Создать геометрию Polygon
Класс `Polygon` представляет плоскую область, определённую замкнутым кольцом точек.

```csharp
var polygon = new Polygon();
```

Мы начинаем с пустого полигона, который позже будет представлять прямоугольную область.

### Шаг 2: Определить внешний контур полигона
Внешний контур — это замкнутый цикл точек, определяющий границу полигона. В этом примере мы создаём квадрат 1 × 1.

```csharp
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
});
```

### Шаг 3: Создать геометрию LineString
Класс `LineString` — последовательность соединённых отрезков, моделирующая дорогу, реку или любую линейную характеристику.

```csharp
var line = new LineString();
```

### Шаг 4: Добавить точки в LineString
Эти две точки придают линии наклонённую форму, которая не пересекает полигон, делая вычисление расстояния интересным.

```csharp
line.AddPoint(2, 0);
line.AddPoint(1, 3);
```

### Шаг 5: Вычислить расстояние
`GetDistanceTo` возвращает кратчайшее евклидовое расстояние между двумя геометриями в одной системе координат. Здесь мы **получаем расстояние до геометрии**, вызывая `GetDistanceTo`. Aspose.GIS вычисляет кратчайшее расстояние между краем полигона и линией.

```csharp
double distance = polygon.GetDistanceTo(line);
```

### Шаг 6: Вывести результат
Результат выводится с двумя знаками после запятой (`0.63`). Это значение представляет минимальное евклидовое расстояние между квадратом и линией.

```csharp
Console.WriteLine(distance.ToString("F")); // 0.63
```

## Типичные сценарии использования
- **Логистика:** Найти ближайший склад к маршруту доставки.  
- **Экологический мониторинг:** Измерить, насколько далеко плазма загрязнителя находится от охраняемой территории.  
- **Градостроительство:** Определить расстояние между планируемой инфраструктурой и существующими объектами.

## Устранение неполадок и советы
- **Система координат имеет значение:** Убедитесь, что обе геометрии используют одну и ту же CRS (система координат) перед вычислением расстояния.  
- **Производительность:** Для больших наборов данных рассмотрите пространственное индексирование (R‑tree), чтобы избежать сравнений O(N²).  
- **Точность:** Если нужны геодезические (по большой окружности) расстояния, сначала преобразуйте координаты в подходящую проекцию.

## FAQ's
### Совместима ли Aspose.GIS for .NET со всеми версиями .NET?
Да, Aspose.GIS for .NET совместима с .NET Framework 4.6 и выше.

### Могу ли я использовать Aspose.GIS for .NET для выполнения сложных пространственных анализов?
Абсолютно! Aspose.GIS for .NET предлагает широкий набор функций для продвинутых задач пространственного анализа.

### Поддерживает ли Aspose.GIS for .NET как 2D, так и 3D геометрии?
Да, вы можете работать как с 2D, так и с 3D геометриями, используя Aspose.GIS for .NET.

### Можно ли интегрировать Aspose.GIS for .NET с другими GIS‑библиотеками?
Aspose.GIS for .NET обеспечивает совместимость с другими GIS‑библиотеками, позволяя использовать дополнительные возможности.

### Доступна ли техническая поддержка для пользователей Aspose.GIS for .NET?
Да, пользователи Aspose.GIS for .NET могут получить техническую поддержку через [форумы Aspose](https://forum.aspose.com/c/gis/33).

## Часто задаваемые вопросы

**В: Насколько точным является расстояние, возвращаемое `GetDistanceTo`?**  
О: Метод использует арифметику двойной точности и следует спецификации OGC Simple Features, обеспечивая субметровую точность для типичных плоских координат.

**В: Можно ли вычислить расстояние между `Point` и `Polygon`?**  
О: Да — просто вызовите `point.GetDistanceTo(polygon)` (или наоборот), и Aspose.GIS вернёт кратчайшее расстояние от точки до границы полигона.

**В: Поддерживает ли API пакетные вычисления расстояний?**  
О: Хотя отдельного пакетного метода нет, вы можете перебрать коллекции геометрий и эффективно переиспользовать вызов `GetDistanceTo`.

**В: Что происходит, если геометрии пересекаются?**  
О: Метод возвращает `0.0`, поскольку кратчайшее расстояние между пересекающимися геометриями равно нулю.

**В: Есть ли способ получить ближайшие точки на каждой геометрии?**  
О: Да — используйте `Geometry.GetNearestPoints(Geometry other)`, который возвращает кортеж с ближайшими точками обеих геометрий.

## Заключение
Вычисление расстояния между геометриями — фундаментальная операция в любом .NET‑приложении с поддержкой ГИС. Следуя приведённым шагам, вы теперь знаете **как вычислить расстояние** с помощью Aspose.GIS, **как использовать Aspose** для создания и манипуляции геометриями и **как получить расстояние до геометрии** одним вызовом метода. Экспериментируйте с разными формами, системами координат и большими наборами данных, чтобы увидеть, как эта возможность может усилить ваш следующий проект пространственного анализа.

---

**Последнее обновление:** 2026-07-19  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose

## Связанные руководства

- [How to Calculate Geometry Length .NET with Aspose.GIS](/gis/net/geometry-analysis/get-geometry-length/)
- [How to Calculate Area with Aspose.GIS for .NET](/gis/net/geometry-analysis/get-geometry-area/)
- [How to Perform Spatial Overlap Analysis of Geometries with Aspose.GIS for .NET](/gis/net/geometry-analysis/check-geometries-overlap/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}