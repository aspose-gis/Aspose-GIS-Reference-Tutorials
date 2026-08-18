---
date: 2026-06-05
description: Узнайте, как выполнять пространственный анализ наложения, находить пересекающиеся
  полигоны и обнаруживать перекрывающиеся полигоны с помощью Aspose.GIS for .NET.
  Пошаговое руководство для разработчиков.
keywords:
- spatial overlap analysis
- find intersecting polygons
- detect overlapping polygons
- how to check overlap
- real-time overlap detection
linktitle: Проверить наложение геометрий
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to perform spatial overlap analysis, find intersecting polygons
    and detect overlapping polygons with Aspose.GIS for .NET. Step‑by‑step guide for
    developers.
  headline: How to Perform Spatial Overlap Analysis of Geometries with Aspose.GIS
    for .NET
  type: TechArticle
- questions:
  - answer: '`Geometry.Overlaps(otherGeometry)`'
    question: What is the primary method?
  - answer: A free trial works for development; a license is required for production.
    question: Do I need a license for testing?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Which .NET versions are supported?
  - answer: Roughly 5‑10 minutes for a basic overlap check.
    question: How long does the implementation take?
  - answer: Yes—Aspose.GIS integrates smoothly with most .NET GIS stacks.
    question: Can I use this with other GIS libraries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Как выполнить пространственный анализ наложения геометрий с помощью Aspose.GIS
  for .NET
url: /ru/net/geometry-analysis/check-geometries-overlap/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Анализ пространственного перекрытия геометрий с Aspose.GIS

## Введение

Если вам нужно **проверить перекрытие** между двумя пространственными объектами, Aspose.GIS for .NET предоставляет чистый, типобезопасный API, который делает всю тяжелую работу. Выполнение **анализа пространственного перекрытия** часто требуется при построении маршрутизаторов, валидаторов землепользования или любой GIS‑утилиты, которой необходимо понимать, как взаимодействуют геометрии. В этом руководстве мы пройдем через предпосылки, разбор кода и практические советы, чтобы вы могли уверенно обнаруживать перекрывающиеся полигоны и другие геометрии в своих проектах.

## Быстрые ответы
- **Каков основной метод?** `Geometry.Overlaps(otherGeometry)`  
- **Нужна ли лицензия для тестирования?** Бесплатная пробная версия подходит для разработки; лицензия требуется для продакшн.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Сколько времени занимает реализация?** Около 5‑10 минут для базовой проверки перекрытия.  
- **Можно ли использовать это с другими GIS‑библиотеками?** Да — Aspose.GIS легко интегрируется с большинством .NET GIS‑стеков.

## Что такое анализ пространственного перекрытия?
Предикат `Overlaps` следует определению OGC (Open Geospatial Consortium) и возвращает **true** только тогда, когда две геометрии имеют общие внутренние точки, но ни одна полностью не содержит другую. Другими словами, формы пересекаются *внутри*, но не полностью охватывают друг друга.

## Почему стоит выбрать Aspose.GIS для обнаружения перекрытия?
Aspose.GIS поддерживает **30+ типов геометрий** и может обрабатывать **многогигабайтные файлы** без загрузки всего документа в память, обеспечивая субмиллисекундные ответы для типичных пар полигонов. Его нулевое зависимое проектирование, кроссплатформенная поддержка .NET Core и встроенные OGC‑совместимые предикаты делают его надежным выбором для обнаружения перекрытия в реальном времени в производственных системах.

## Предварительные требования
- **Основы C#** — знакомство с классами, методами и выводом в консоль.  
- **Aspose.GIS for .NET** — скачайте и установите его с официального сайта [здесь](https://releases.aspose.com/gis/net/) или со страницы общих релизов [здесь](https://releases.aspose.com/).  
- **IDE** — Visual Studio, Rider или VS Code с расширением C#.

## Импорт пространств имён
Добавьте необходимые `using`‑операторы, чтобы ваш код получил доступ к типам геометрий Aspose.GIS.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Шаг 1: Определите геометрии, которые хотите сравнить
`LineString` — тип геометрии, представляющий серию соединённых точек, образующих линейную форму. Мы начнём с двух объектов `LineString`, которые имеют общую конечную точку, но **не** перекрываются.

```csharp
var geometry1 = new LineString();
geometry1.AddPoint(0, 0);
geometry1.AddPoint(0, 2);

var geometry2 = new LineString();
geometry2.AddPoint(0, 2);
geometry2.AddPoint(0, 3);
```

## Шаг 2: Используйте метод `Overlaps` — первая проверка
`Geometry.Overlaps` — предикат, совместимый с OGC, который возвращает true, когда две геометрии имеют общие внутренние точки без полного включения одной в другую. Метод возвращает `false`, потому что линии касаются только в одной точке.

```csharp
Console.WriteLine(geometry1.Overlaps(geometry2)); // Output: False
```

## Шаг 3: Создайте другую геометрию, которая действительно перекрывается
Теперь мы создадим третью линию, проходящую через внутреннюю часть `geometry1`, гарантируя внутреннее пересечение.

```csharp
var geometry3 = new LineString();
geometry3.AddPoint(0, 1);
geometry3.AddPoint(0, 3);
```

## Шаг 4: Проверьте перекрытие снова — на этот раз должно вернуть true
Выполнение того же вызова `Overlaps` для новой пары возвращает `true`, подтверждая, что геометрии действительно перекрываются.

```csharp
Console.WriteLine(geometry1.Overlaps(geometry3)); // Output: True
```

## Как обнаружить перекрытие в более сложных случаях?
Загрузите ваши полигональные или мультигеометрические объекты и вызовите тот же предикат `Overlaps`; API автоматически выбирает подходящий алгоритм для каждого типа геометрии. `SpatialReference` — структура, позволяющая указать пользовательскую толерантность для операций с геометрией. Такой подход работает с большими наборами данных, обеспечивая обнаружение перекрытия в реальном времени для тысяч объектов.

## Распространённые проблемы и решения

| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| **Всегда возвращает `false`** | Геометрии только касаются (делят границу), а не перекрываются. | Используйте `Intersects` для любой общей точки или скорректируйте координаты, чтобы внутренние части пересекались. |
| **Исключение при больших наборах данных** | Нагрузка на память при загрузке большого количества геометрий одновременно. | Обрабатывайте геометрии пакетами или используйте `GeometryCollection` со стримингом. |
| **Неожиданный `true` для полигонов** | Внутренние части полигонов пересекаются, но они делят ребро. | Убедитесь, что вам действительно нужно определение OGC *overlaps*; иначе используйте `Crosses` или `Touches`. |

## Часто задаваемые вопросы

**В1: Можно ли использовать Aspose.GIS for .NET с другими .NET библиотеками?**  
Да, Aspose.GIS for .NET бесшовно интегрируется с другими .NET библиотеками, расширяя их возможности без трений.

**В2: Доступна ли бесплатная пробная версия Aspose.GIS for .NET?**  
Да, вы можете получить бесплатную пробную версию Aspose.GIS for .NET [здесь](https://releases.aspose.com/).

**В3: Где можно найти документацию по Aspose.GIS for .NET?**  
Полная документация по Aspose.GIS for .NET доступна [здесь](https://reference.aspose.com/gis/net/).

**В4: Как получить временные лицензии для Aspose.GIS for .NET?**  
Временные лицензии для Aspose.GIS for .NET можно получить [здесь](https://purchase.aspose.com/temporary-license/).

**В5: Где можно получить поддержку по Aspose.GIS for .NET?**  
Для любой помощи или вопросов посетите форум Aspose.GIS [здесь](https://forum.aspose.com/c/gis/33).

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [GIS Overlay Analysis — Как выполнять операции наложения с Aspose.GIS for .NET](/gis/net/geometry-analysis/find-geometry-overlays/)
- [Создание полигональной геометрии C# и проверка пересечения с Aspose.GIS for .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Проверка сетевого маршрутизации: касающиеся геометрии с Aspose.GIS](/gis/net/geometry-analysis/check-geometries-touching/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

---

**Последнее обновление:** 2026-06-05  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose