---
date: 2026-08-03
description: Узнайте, как создать linestring c# с помощью Aspose.GIS для .NET, добавить
  точки в linestring и выполнить проверку точки на линии с использованием метода covers.
keywords:
- create linestring c#
- point on line check
- add points to linestring
- use covers method
lastmod: 2026-08-03
linktitle: Создать linestring c# – Проверить, покрывает ли геометрия другую
og_description: Создайте linestring c# и проверьте точку на линии с помощью метода
  covers из Aspose.GIS. Узнайте о точных проверках геометрии для приложений .NET.
  (150‑160 chars)
og_image_alt: Developer guide showing linestring creation and covers check in C# with
  Aspose.GIS
og_title: Создать linestring c# – Проверить, покрывает ли геометрия другую (50‑60
  chars)
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  headline: Create linestring c# – Check geometry covers another
  type: TechArticle
- description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  name: Create linestring c# – Check geometry covers another
  steps:
  - name: create a linestring object
    text: The `LineString` class represents a sequence of points connected by straight
      line segments in a two‑dimensional plane. Here, we instantiate a new `LineString`
      object, which represents a sequence of connected line segments in a two‑dimensional
      space.
  - name: add points to linestring
    text: '`AddPoint` appends a coordinate pair to the end of the `LineString` collection,
      preserving the order of insertion. We **add points to linestring** using the
      `AddPoint` method. In this example, we add two points: (0, 0) and (1, 1), forming
      a simple diagonal line segment.'
  - name: create a point object
    text: The `Point` class models a single location in a two‑dimensional coordinate
      system. Instantiate a `Point` object representing a single point in a two‑dimensional
      space. Here, we create a point at coordinates (0, 0).
  - name: perform a point on line check – does the line cover the point?
    text: '`Covers` determines whether the first geometry completely contains the
      second geometry, returning true only when every point of the second geometry
      lies inside the first. Use the `Covers` method to check if the line covers the
      point. In this case, it returns `True` because the point (0, 0) lies exac'
  - name: verify the reverse relationship – is the point covered by the line?
    text: '`CoveredBy` is the inverse of `Covers`; it returns true when the invoking
      geometry is entirely inside the target geometry. Similarly, use the `CoveredBy`
      method to check if the point is covered by the line. Since the point (0, 0)
      lies on the line, it also returns `True`.'
  type: HowTo
- questions:
  - answer: Yes, you can use Aspose.GIS for .NET in both commercial and non‑commercial
      projects after obtaining the appropriate license.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, Aspose.GIS for .NET is compatible with both .NET Framework and .NET
      Core environments.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Yes, Aspose.GIS for .NET supports a wide range of GIS formats including
      Shapefile, GeoJSON, KML, and more.
    question: Does Aspose.GIS for .NET support various GIS formats?
  - answer: Aspose.GIS for .NET is a proprietary library developed by Aspose, so external
      contributions are not accepted. However, you can provide feedback and suggestions
      to improve the library.
    question: Can I contribute to the development of Aspose.GIS for .NET?
  - answer: Updates for Aspose.GIS for .NET are released regularly to introduce new
      features, enhancements, and bug fixes. Check the [website](https://releases.aspose.com/gis/net/)
      for the latest releases.
    question: How often are updates released for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create linestring
- Aspose.GIS
- C# geometry analysis
title: Создать linestring c# – Проверить, покрывает ли геометрия другую
url: /ru/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Проверьте, покрывает ли геометрия другую

## Введение
В этом руководстве вы узнаете **как создать linestring c#** с помощью Aspose.GIS для .NET, добавлять точки в linestring и выполнять надёжную **проверку point on line** с методами `Covers` и `CoveredBy`. Независимо от того, создаёте ли вы инструмент картографирования, проводите пространственный анализ или просто хотите проверить геометрические отношения, освоение этих операций даст вашему приложению необходимую точность.

## Краткие ответы
- **Что означает “create linestring c#”?** Это означает создание объекта геометрии `LineString` и заполнение его координатными точками.  
- **Какой метод проверяет, находится ли точка на линии?** Используйте метод `Covers` у `LineString` или `CoveredBy` у `Point`.  
- **Нужна ли лицензия для запуска примера?** Временная лицензия подходит для оценки; полная лицензия требуется для продакшн.  
- **Можно ли использовать это с .NET Core?** Да, Aspose.GIS поддерживает .NET Framework и .NET Core.  
- **Сколько точек можно добавить в linestring?** Нет жёсткого ограничения; вы можете добавить столько точек, сколько необходимо для вашего пространственного анализа.

## Что такое create linestring c#?
`LineString` — это геометрическая фигура, состоящая из упорядоченного списка точек, соединённых прямыми отрезками. В C# вы создаёте её, создавая экземпляр класса `LineString` из пространства имён `Aspose.Gis.Geometries`, а затем **добавляете точки в linestring** с помощью метода `AddPoint`. Этот объект служит основой для любого линейного пространственного анализа, такого как построение маршрутов или трассировка сетей.

## Почему использовать Aspose.GIS для проверки точки на линии?
`Covers` — это метод пространственного предиката, который возвращает true, когда первая геометрия полностью содержит вторую геометрию.  
Aspose.GIS предоставляет детерминированную, высокоточную реализацию пространственных предикатов. Он поддерживает более 50 форматов ввода и вывода GIS, может обрабатывать многосоткилометровые линейные сети без загрузки всего набора данных в память и работает на .NET Framework, .NET Core и .NET 5/6+. Использование его метода `Covers` гарантирует учёт ошибок округления чисел с плавающей запятой, обеспечивая надёжные результаты проверки point‑on‑line даже в требовательных корпоративных сценариях.

## Требования
Прежде чем приступить к использованию Aspose.GIS для .NET, убедитесь, что у вас настроены следующие требования:

### 1. Установите Visual Studio
Убедитесь, что Visual Studio установлен на вашей системе. Aspose.GIS для .NET без проблем интегрируется с Visual Studio, обеспечивая удобный процесс разработки.

### 2. Получите Aspose.GIS для .NET
Скачайте библиотеку Aspose.GIS для .NET с [веб‑сайта](https://releases.aspose.com/gis/net/). Вы можете загрузить библиотеку напрямую или использовать менеджер пакетов, такой как NuGet, чтобы установить её в ваш проект.

### 3. Знание .NET Framework
Базовые знания .NET Framework и языка программирования C# необходимы для эффективного использования Aspose.GIS для .NET.

### 4. Доступ к документации и поддержке
Обратитесь к [документации](https://reference.aspose.com/gis/net/) для получения подробной информации об API и возможностях Aspose.GIS. Если у вас возникнут проблемы или вопросы, используйте [форум Aspose.GIS](https://forum.aspose.com/c/gis/33) для получения помощи.

### 5. Необязательно: временная лицензия
Если вы изучаете Aspose.GIS для .NET, вы можете получить временную лицензию со [страницы временной лицензии](https://purchase.aspose.com/temporary-license/), чтобы оценить возможности библиотеки.

## Импорт пространств имён
Прежде чем использовать Aspose.GIS для .NET в вашем проекте, необходимо импортировать требуемые пространства имён:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Теперь разберём предоставленный пример на несколько шагов, чтобы понять, как **проверить, покрывает ли одна геометрия другую** с помощью Aspose.GIS для .NET.

## Как создать linestring c# – пошаговое руководство
Загрузите ваш проект, импортируйте необходимые пространства имён и затем выполните пять коротких шагов ниже. Всего в нескольких строках кода вы получите объект `LineString`, объект `Point` и два булевых проверки, которые покажут, покрывает ли линия точку и покрыта ли точка линией.

### Шаг 1: создать объект linestring
The `LineString` class represents a sequence of points connected by straight line segments in a two‑dimensional plane.  
```csharp
var line = new LineString();
```
Здесь мы создаём новый объект `LineString`, который представляет последовательность соединённых отрезков в двумерном пространстве.

### Шаг 2: добавить точки в linestring
`AddPoint` добавляет пару координат в конец коллекции `LineString`, сохраняя порядок вставки.  
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
Мы **добавляем точки в linestring** с помощью метода `AddPoint`. В этом примере мы добавляем две точки: (0, 0) и (1, 1), образуя простой диагональный отрезок.

### Шаг 3: создать объект point
Класс `Point` моделирует одну позицию в двумерной системе координат.  
```csharp
var point = new Point(0, 0);
```
Создайте объект `Point`, представляющий одну точку в двумерном пространстве. Здесь мы создаём точку с координатами (0, 0).

### Шаг 4: выполнить проверку point on line – покрывает ли линия точку?
`Covers` определяет, полностью ли первая геометрия содержит вторую, возвращая true только когда каждая точка второй геометрии находится внутри первой.  
```csharp
Console.WriteLine(line.Covers(point));    // True
```
Используйте метод `Covers`, чтобы проверить, покрывает ли линия точку. В данном случае он возвращает `True`, потому что точка (0, 0) лежит точно на линии.

### Шаг 5: проверить обратную связь – покрыта ли точка линией?
`CoveredBy` является обратным к `Covers`; он возвращает true, когда вызывающая геометрия полностью находится внутри целевой геометрии.  
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
Аналогично, используйте метод `CoveredBy`, чтобы проверить, покрыта ли точка линией. Поскольку точка (0, 0) лежит на линии, он также возвращает `True`.

## Распространённые проблемы и решения
| Проблема | Почему происходит | Решение |
|-------|----------------|-----|
| `line.Covers(point)` returns `False` even though the point looks on the line | Координаты точки не совпадают точно из‑за точности чисел с плавающей запятой. | Используйте `Math.Round` для координат или проверку с допуском: `line.Distance(point) < epsilon`. |
| Missing `using Aspose.Gis.Geometries;` | Пространство имён не импортировано, вызывая ошибки компиляции. | Убедитесь, что оператор импорта присутствует (см. раздел **Импорт пространств имён**). |
| License exception at runtime | Не загружена действительная лицензия для продакшн. | Загрузите временную или полную лицензию с помощью `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Часто задаваемые вопросы

**В: Могу ли я использовать Aspose.GIS для .NET в коммерческих проектах?**  
О: Да, вы можете использовать Aspose.GIS для .NET как в коммерческих, так и в некоммерческих проектах после получения соответствующей лицензии.

**В: Совместим ли Aspose.GIS для .NET с .NET Core?**  
О: Да, Aspose.GIS для .NET совместим как с .NET Framework, так и с .NET Core.

**В: Поддерживает ли Aspose.GIS для .NET различные форматы GIS?**  
О: Да, Aspose.GIS для .NET поддерживает широкий спектр форматов GIS, включая Shapefile, GeoJSON, KML и другие.

**В: Могу ли я внести вклад в разработку Aspose.GIS для .NET?**  
О: Aspose.GIS для .NET — это проприетарная библиотека, разрабатываемая Aspose, поэтому внешние вклады не принимаются. Однако вы можете предоставить обратную связь и предложения по улучшению библиотеки.

**В: Как часто выпускаются обновления для Aspose.GIS для .NET?**  
О: Обновления Aspose.GIS для .NET выпускаются регулярно, добавляя новые функции, улучшения и исправления ошибок. Проверьте [веб‑сайт](https://releases.aspose.com/gis/net/) для получения последних релизов.

## Заключение
Следуя приведённым выше шагам, вы теперь знаете, как **создать linestring c#**, **добавлять точки в linestring** и выполнять надёжную **проверку point on line** с помощью методов `Covers` и `CoveredBy`. Эта возможность расширяет функции пространственного анализа вашего программного обеспечения и открывает путь к более продвинутым GIS‑операциям, таким как проверка маршрутов, проверка топологии сети и запросы близости.

---

**Последнее обновление:** 2026-08-03  
**Тестировано с:** Aspose.GIS for .NET (latest release)  
**Автор:** Aspose

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Узнайте, как создать геометрию LineString с помощью Aspose.GIS для .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Как добавить точку в LineString и преобразовать геометрию в редактируемый формат с Aspose.GIS](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [point inside polygon c# – Проверка, содержит ли геометрия другую](/gis/net/geometry-analysis/check-geometry-contains-another/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}