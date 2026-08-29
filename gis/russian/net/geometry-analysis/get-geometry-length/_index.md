---
date: 2026-08-13
description: Узнайте, как вычислять geometry length в .NET с помощью Aspose.GIS для
  эффективной обработки spatial data. Включает примеры get line length C# и calculate
  line length C#.
keywords:
- calculate geometry length .net
- Aspose.GIS length calculation
- C# geometry length
lastmod: 2026-08-13
linktitle: Получить Geometry Length
og_description: Вычислите geometry length в .NET с использованием Aspose.GIS. Примеры
  get line length C# и polygon perimeter в кратком, высокопроизводительном руководстве
  для .NET разработчиков.
og_image_alt: Developer guide showing how to calculate geometry length in .NET with
  Aspose.GIS
og_title: Вычислите geometry length в .NET с Aspose.GIS – Быстрые spatial measurements
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to calculate geometry length .NET using Aspose.GIS for efficient
    spatial data handling. Includes get line length C# and calculate line length C#
    examples.
  headline: How to Calculate Geometry Length .NET with Aspose.GIS
  type: TechArticle
- description: Learn how to calculate geometry length .NET using Aspose.GIS for efficient
    spatial data handling. Includes get line length C# and calculate line length C#
    examples.
  name: How to Calculate Geometry Length .NET with Aspose.GIS
  steps:
  - name: Create geometry objects
    text: To begin with, create the geometry objects representing the shapes for which
      you want to calculate the length. This can include lines, polygons, or any other
      geometrical shapes.
  - name: Calculate line length in C#
    text: Once you have created the line geometry, you can calculate its length using
      the `GetLength()` method. This demonstrates **calculate line length c#** in
      a single line of code.
  - name: Create polygon geometry
    text: Similarly, you can create polygon geometry objects using the `Polygon` and
      `LinearRing` classes.
  - name: Get length of a polygon
    text: For polygons, the `GetLength()` method returns the perimeter, which is effectively
      the **how to get length** of the shape.
  type: HowTo
- questions:
  - answer: Aspose.GIS for .NET is compatible with .NET Framework 4.6.1 or later versions,
      as well as .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with all .NET frameworks?
  - answer: Yes, you can avail of a free trial of Aspose.GIS for .NET from [here](https://releases.aspose.com/).
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: You can find support and assistance from the Aspose.GIS community forum
      [here](https://forum.aspose.com/c/gis/33).
    question: Where can I find support for Aspose.GIS for .NET?
  - answer: You can acquire a temporary license from [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Yes, Aspose.GIS for .NET provides various formatting options to customize
      the output format as per your requirements.
    question: Can I customize the output format for geometry length calculations?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geometry length
- Aspose.GIS
- C# GIS
- spatial calculations
- line length
title: Как вычислить geometry length в .NET с Aspose.GIS
url: /ru/net/geometry-analysis/get-geometry-length/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как вычислить длину геометрии .NET с помощью Aspose.GIS

## Введение
Если вы ищете простой и практический способ **calculate geometry length .NET**, вы попали в нужное место. Aspose.GIS for .NET предоставляет богатый набор GIS‑ориентированных API, которые делают пространственные вычисления — такие как измерение длины линии или периметра полигона — простыми и производительными. В этом руководстве мы пройдем весь процесс, от настройки среды до написания кода C#, который возвращает точные значения длины.

## Быстрые ответы
- **Что возвращает “GetLength()”?** Для линий он возвращает длину линии; для полигонов — периметр.  
- **Какое пространство имён требуется?** `Aspose.Gis.Geometries`.  
- **Можно ли использовать это с .NET 6?** Да, Aspose.GIS поддерживает .NET 5, .NET 6 и более новые версии.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для оценки; лицензия требуется для продакшн.  
- **Учитываются ли единицы измерения?** Длина возвращается в единицах координатной системы (например, метры для проецируемой CRS).

## Что такое длина геометрии?
Geometry.GetLength() вычисляет общую линейную дистанцию геометрического объекта на основе его координат. Для LineString он суммирует расстояния между последовательными вершинами, возвращая длину линии. При применении к Polygon он складывает длины всех рёбер, эффективно предоставляя периметр фигуры.

## Почему использовать Aspose.GIS для вычисления длины?
Aspose.GIS предлагает полностью управляемую .NET‑библиотеку, выполняющую пространственные вычисления без необходимости в нативных бинарных файлах, что упрощает развертывание на Windows, Linux и macOS. Она поддерживает более пятидесяти систем координатных ссылок, обеспечивая высокоточные результаты двойной точности даже для линий длиной в сотни километров, и бесшовно интегрируется с проектами .NET 5/6/7, гарантируя стабильную производительность и точность.

## Предварительные требования
Перед началом убедитесь, что у вас есть следующее:

### 1. Библиотека Aspose.GIS для .NET
Во-первых, вам необходимо установить библиотеку Aspose.GIS для .NET в вашей среде разработки. Если вы ещё этого не сделали, вы можете скачать её со страницы [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).

### 2. Среда разработки .NET
Убедитесь, что на вашем компьютере настроена среда разработки .NET. Это включает наличие установленного Visual Studio или любой другой совместимой IDE.

### 3. Базовые знания C#
Базовое понимание языка программирования C# необходимо для следования этому руководству.

## Импорт пространств имён
Чтобы использовать функции, предоставляемые Aspose.GIS для .NET, необходимо импортировать необходимые пространства имён в ваш проект C#.

### Импорт пространства имён Aspose.GIS
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Как получить длину линии C#
`LineString` в Aspose.GIS представляет собой серию из двух и более точек, соединённых прямыми отрезками, моделируя линейные объекты такие как дороги, реки или коммуникационные линии в заданной системе координат. После создания `LineString` с нужными вершинами вызов метода `GetLength()` возвращает общую дистанцию, измеренную в единицах CRS геометрии, позволяя быстро получить точные измерения линии для маршрутизации, анализа по расстоянию или отчётности, а также при необходимости дальнейшей обработки или хранения.

### Шаг 1: Создать объекты геометрии
Для начала создайте объекты геометрии, представляющие формы, для которых вы хотите вычислить длину. Это могут быть линии, полигоны или любые другие геометрические фигуры.

```csharp
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(2, 2);
line.AddPoint(2, 0);
```

### Шаг 2: Вычислить длину линии в C#
После создания геометрии линии вы можете вычислить её длину с помощью метода `GetLength()`. Это демонстрирует **calculate line length c#** в одной строке кода.

```csharp
Console.WriteLine("{0:F}", line.GetLength()); // Output: 4.83
```

## Как вычислить длину линии C# для полигонов
`Polygon` в Aspose.GIS состоит из внешнего `LinearRing`, определяющего его границу, и необязательных внутренних колец для отверстий, представляющих площадные объекты такие как участки, озёра или административные зоны в конкретной пространственной ссылке. Создайте внешний `LinearRing`, указав угловые точки полигона, затем создайте `Polygon` с этим кольцом; вызов `GetLength()` у полигона вычисляет общий периметр, что полезно для оценки длины ограждения, отчётности по границам или преобразования значений периметра в другие единицы.

### Шаг 3: Создать геометрию полигона
Аналогично, вы можете создавать объекты геометрии полигона, используя классы `Polygon` и `LinearRing`.

```csharp
var rectangle = new Polygon(new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
}));
```

### Шаг 4: Получить длину полигона
Для полигонов метод `GetLength()` возвращает периметр, что по сути является **how to get length** фигуры.

```csharp
Console.WriteLine("{0:F}", rectangle.GetLength()); // Output: 4.00
```

## Распространённые проблемы и решения
| Issue | Solution |
|-------|----------|
| **Неожиданно нулевая длина** | Убедитесь, что система координат геометрии соответствует предоставленным данным; дублирующие точки могут вызывать сегменты нулевой длины. |
| **Неправильные единицы** | Помните, что `GetLength()` возвращает значения в единицах CRS. При необходимости преобразуйте в метры/футы. |
| **Производительность при больших наборах данных** | Повторно используйте объекты геометрии, когда это возможно, и избегайте создания тысяч временных точек внутри плотных циклов. |

## Часто задаваемые вопросы

**В: Совместим ли Aspose.GIS для .NET со всеми .NET фреймворками?**  
О: Aspose.GIS для .NET совместим с .NET Framework 4.6.1 и более поздними версиями, а также с .NET 5/6/7.

**В: Могу ли я попробовать Aspose.GIS для .NET перед покупкой?**  
О: Да, вы можете воспользоваться бесплатной пробной версией Aspose.GIS для .NET по [ссылке](https://releases.aspose.com/).

**В: Где я могу найти поддержку для Aspose.GIS для .NET?**  
О: Поддержку и помощь можно получить на форуме сообщества Aspose.GIS [здесь](https://forum.aspose.com/c/gis/33).

**В: Как я могу получить временную лицензию для Aspose.GIS для .NET?**  
О: Временную лицензию можно получить по [ссылке](https://purchase.aspose.com/temporary-license/).

**В: Могу ли я настроить формат вывода для вычисления длины геометрии?**  
О: Да, Aspose.GIS для .NET предоставляет различные параметры форматирования, позволяющие настроить формат вывода в соответствии с вашими требованиями.

## Заключение
В этом руководстве мы рассмотрели **how to calculate geometry length .NET** для геометрий линий и полигонов с использованием Aspose.GIS для .NET. Следуя пошаговым примерам, вы теперь можете интегрировать точные пространственные измерения в любое приложение .NET, будь то настольный GIS‑инструмент, веб‑служба или бекенд‑конвейер обработки данных.

---

**Last Updated:** 2026-08-13  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Связанные руководства

- [Узнайте, как создать геометрию LineString с Aspose.GIS для .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Как вычислить площадь с Aspose.GIS для .NET](/gis/net/geometry-analysis/get-geometry-area/)
- [Как создать точечную геометрию и получить тип геометрии с Aspose.GIS для .NET](/gis/net/geometry-analysis/get-geometry-type/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}