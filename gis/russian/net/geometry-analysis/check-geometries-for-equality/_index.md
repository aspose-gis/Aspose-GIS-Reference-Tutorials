---
date: 2026-06-05
description: Узнайте, как сравнивать геометрии в .NET с использованием Aspose.GIS,
  обнаруживать дублирующие геометрии и проверять равенство геометрий в ваших приложениях.
keywords:
- how to compare geometries
- detect duplicate geometries
- Aspose.GIS geometry equality
linktitle: Как сравнивать геометрии на равенство
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to compare geometries in .NET using Aspose.GIS, detect duplicate
    geometries, and check geometry equality in your applications.
  headline: How to Compare Geometries for Equality using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard
      projects.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. Download a trial from the [Aspose.GIS releases page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Detailed docs are on the [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).
    question: Where can I find the full API documentation?
  - answer: Post your question on the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How do I get help if I run into an issue?
  - answer: Yes, temporary licenses are available on the [purchase page](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Как сравнивать геометрии на равенство с помощью Aspose.GIS для .NET
url: /ru/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сравнить геометрии на равенство с помощью Aspose.GIS для .NET

## Введение
В этом руководстве вы узнаете **как сравнить геометрии** с помощью Aspose.GIS для .NET, задача, которая важна, когда необходимо обнаружить дублирующие геометрии, проверить пространственные данные или обеспечить соблюдение топологических правил. Независимо от того, создаёте ли вы сервис карт, выполняете пакетный пространственный анализ или просто проверяете, что две формы находятся в одном и том же месте, это руководство проведёт вас через создание, модификацию и тестирование равенства геометрий с чистым, готовым к продакшену C# кодом.

## Быстрые ответы
- **Что означает “compare geometries”?** Он проверяет, занимают ли два геометрических объекта одно и то же пространство, независимо от того, как они построены.  
- **Какой метод используется?** `SpatiallyEquals` из API Aspose.GIS.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; для продакшена требуется коммерческая лицензия.  
- **Поддерживаемые версии .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Типичное время реализации?** Около 5‑10 минут для базовой проверки равенства.

## Что такое равенство геометрий?
Равенство геометрий, также называемое пространственным равенством, означает, что две геометрии представляют точно одинаковый набор точек на поверхности Земли. Даже если одна геометрия построена как `MultiLineString`, а другая как одиночный `LineString`, они считаются равными, когда каждая координата совпадает в пределах заданного допуска. Такое определение позволяет разработчикам надёжно обнаруживать дублирующие геометрии в разнородных источниках данных.

## Почему использовать Aspose.GIS для сравнения геометрий?
Aspose.GIS предоставляет высокопроизводительный автономный движок геометрии, который устраняет необходимость во внешних сервисах. Он **поддерживает более 30 векторных и растровых форматов** (включая WKT, GeoJSON, Shapefile, KML, GML) и может обрабатывать файлы с **сотнями тысяч вершин**, при этом потребление памяти остаётся ниже 50 МБ. Метод `SpatiallyEquals` библиотеки учитывает точность, обеспечивая детерминированные результаты даже при работе с координатами с плавающей запятой.

### Почему это важно для разработчиков
Когда необходимо **обнаружить дублирующие геометрии** в пакетных процессах, конвейерах реального времени или при миграции GIS‑данных, проверенная библиотека устраняет догадки и гарантирует согласованные результаты независимо от поставщика данных.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

- **.NET Framework или .NET Core установлен** – любая версия, поддерживаемая Aspose.GIS.  
- **Библиотека Aspose.GIS для .NET** – скачайте со страницы [Aspose.GIS download page](https://releases.aspose.com/gis/net/).  
- **Среда разработки IDE** – Visual Studio, Rider или VS Code с расширениями C#.

## Импорт пространств имён
В вашем .NET проекте добавьте необходимые директивы `using`, чтобы компилятор знал, где находятся классы GIS:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Шаг 1: Определение геометрий
`MultiLineString` представляет собой набор линейных компонентов, тогда как `LineString` определяет одну непрерывную линию. Обе класса наследуются от базового типа `Geometry`.

Сначала мы создаём две геометрии, которые будем сравнивать. В этом примере `geometry1` — это `MultiLineString`, состоящий из двух отрезков, а `geometry2` — одиночный `LineString`, охватывающий те же начальные и конечные точки.

```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```

## Шаг 2: Проверка геометрий на равенство
`SpatiallyEquals` оценивает, занимают ли две геометрии один и тот же набор точек, при необходимости принимая значение допуска для неточностей плавающей запятой.

Теперь мы используем метод `SpatiallyEquals`, чтобы увидеть, считаются ли две формы равными движком GIS.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

Консоль выводит `True`, потому что, несмотря на различную конструкцию, обе геометрии покрывают одну и ту же линию от (0,0) до (2,2).

## Шаг 3: Модификация одной геометрии
Чтобы продемонстрировать, как изменение влияет на равенство, мы добавляем дополнительную точку к `geometry2`.

```csharp
geometry2.AddPoint(3, 3);
```

## Шаг 4: Повторная проверка равенства после модификации
После модификации геометрии больше не одинаковы, поэтому `SpatiallyEquals` возвращает `False`.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

Вывод `False` подтверждает, что добавленная точка нарушила пространственное равенство.

## Как обнаружить дублирующие геометрии?
Загрузите каждую геометрию, вызовите `SpatiallyEquals` с подходящим допуском и отфильтруйте те, которые возвращают `True`. Этот шаблон хорошо масштабируется с LINQ, позволяя идентифицировать дублирующие формы в больших коллекциях всего несколькими строками кода. Вы также можете комбинировать его с `GroupBy` для агрегации одинаковых геометрий и снижения затрат на хранение.

## Распространённые проблемы и советы
- **Проблемы с точностью** – Если вы работаете с координатами высокой точности, рассмотрите возможность округления или использования перегрузки `SpatiallyEquals` с допуском.  
- **Разные SRID** – Убедитесь, что обе геометрии используют один и тот же идентификатор системы координат (SRID) перед сравнением.  
- **Производительность** – Для больших коллекций пакетные сравнения с использованием LINQ или параллельных циклов могут значительно снизить нагрузку.

## Часто задаваемые вопросы
**В: Можно ли использовать Aspose.GIS для .NET с другими .NET фреймворками?**  
О: Да, Aspose.GIS работает с проектами .NET Framework, .NET Core и .NET Standard.

**В: Доступна ли бесплатная пробная версия?**  
О: Конечно. Скачайте пробную версию со страницы [Aspose.GIS releases page](https://releases.aspose.com/).

**В: Где можно найти полную документацию API?**  
О: Подробная документация доступна на странице [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).

**В: Как получить помощь, если возникнет проблема?**  
О: Опубликуйте свой вопрос на форуме сообщества Aspose.GIS [здесь](https://forum.aspose.com/c/gis/33).

**В: Можно ли приобрести временную лицензию для оценки?**  
О: Да, временные лицензии доступны на [странице покупки](https://purchase.aspose.com/temporary-license/).

## Заключение
Теперь вы знаете **как сравнить геометрии** с помощью Aspose.GIS для .NET, от создания объектов до проверки пространственного равенства и обработки модификаций. Эта возможность является фундаментом для более продвинутых пространственных анализов, таких как проверка топологии, обнаружение дубликатов и фильтрация на основе геометрий.

---

**Последнее обновление:** 2026-06-05  
**Тестировано с:** Aspose.GIS for .NET 24.11  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Создать полигональную геометрию C# и проверить пересечение с Aspose.GIS для .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Как выполнить анализ пространственного перекрытия геометрий с Aspose.GIS для .NET](/gis/net/geometry-analysis/check-geometries-overlap/)
- [Проверка сетевого маршрутизации: соприкасающиеся геометрии с Aspose.GIS](/gis/net/geometry-analysis/check-geometries-touching/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}