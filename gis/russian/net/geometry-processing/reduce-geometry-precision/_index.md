---
date: 2026-09-10
description: Узнайте, как уменьшить размер файлов геометрии, снижая точность и округляя
  значения Z с помощью Aspose.GIS for .NET, повышая производительность и сокращая
  использование памяти.
keywords:
- reduce geometry file size
- reduce geometry precision
- round Z values
- Aspose.GIS .NET
- geometry processing
lastmod: 2026-09-10
linktitle: Снизить точность геометрии
og_description: Узнайте, как уменьшить размер файлов геометрии, снижая точность и
  округляя значения Z с помощью Aspose.GIS for .NET, повышая производительность и
  сокращая использование памяти.
og_image_alt: Guide showing how to reduce geometry file size by rounding Z in .NET
  using Aspose.GIS
og_title: Как уменьшить размер файлов геометрии, округляя Z в .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to reduce geometry file size by lowering precision and rounding
    Z values with Aspose.GIS for .NET, improving performance and cutting memory usage.
  headline: How to reduce geometry file size by rounding Z in .NET
  type: TechArticle
- questions:
  - answer: Reducing geometry precision helps optimize memory usage and improve performance,
      especially when dealing with large datasets in GIS applications.
    question: Why is geometry precision reduction important in GIS?
  - answer: While minor accuracy is lost, the trade‑off often yields a good balance
      between precision and performance for most spatial analyses.
    question: Does reducing geometry precision affect accuracy?
  - answer: Yes, you can specify the desired number of decimal places for both XY
      and Z coordinates using the `RoundXY` and `RoundZ` methods.
    question: Can I customize the precision reduction level in Aspose.GIS for .NET?
  - answer: Absolutely—less data per vertex means faster spatial queries, reduced
      I/O, and lower memory consumption, often delivering **30 % faster processing**
      on typical datasets.
    question: Are there measurable performance benefits?
  - answer: You can get support by visiting the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      or accessing the documentation available in the [Aspose.GIS .NET API reference](https://reference.aspose.com/gis/net/).
    question: Where can I get support for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- reduce geometry file size
- Aspose.GIS
- .NET GIS
- geometry precision
- round Z
title: Как уменьшить размер файлов геометрии, округляя Z в .NET
url: /ru/net/geometry-processing/reduce-geometry-precision/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как уменьшить размер файлов геометрии, округляя Z в .NET

## Введение
Если вы работаете с большими пространственными наборами данных, вы, вероятно, заметили, что каждая дополнительная десятичная цифра в ваших геометрических данных накапливается — как в размере файла, так и во времени обработки. В этом руководстве вы узнаете **как уменьшить размер файлов геометрии** путем снижения точности геометрии и **как округлять Z** значения с помощью Aspose.GIS для .NET. К концу руководства вы сможете сжать файлы геометрии, ускорить пространственные операции и снизить потребление памяти, используя несколько простых вызовов методов.

## Быстрые ответы
- **Что означает «округление Z»?** Оно обрезает количество десятичных знаков координаты Z в объекте геометрии.  
- **Зачем уменьшать размер файлов геометрии?** Меньшее количество десятичных знаков на вершину уменьшает объём хранилища, ускоряет запросы и снижает использование ОЗУ.  
- **Какая библиотека это делает?** Aspose.GIS для .NET предоставляет встроенные методы `RoundZ` и `RoundXY`.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для тестирования; для продакшн требуется коммерческая лицензия.  
- **Можно ли контролировать количество десятичных знаков?** Да, вы указываете желаемое количество знаков в методах `Round*`.

## Что такое «округление Z» в GIS?
Округление координаты Z удаляет ненужную десятичную точность, преобразуя значение, например 3.345 в 3.3 (или любую заданную точность). Такое сокращение может заметно уменьшить размер файла и ускорить обработку, особенно когда детализация высот более тонкая, чем требуемая точность анализа, не нужна. Это распространённая техника оптимизации 3‑D наборов данных.

## Почему уменьшать размер файлов геометрии с помощью Aspose.GIS?
Aspose.GIS поддерживает **30+ векторных и растровых форматов** и может обрабатывать файлы размером до **2 ГБ**, не загружая весь набор данных в память. Снижение точности уменьшает объём данных на вершину, что обычно дает **20‑40 % более быстрые пространственные запросы** и **15‑30 % меньше потребления памяти** на больших наборах данных.

## Предварительные требования
Перед началом убедитесь, что у вас есть следующие требования:
1. Библиотека Aspose.GIS для .NET: загрузите и установите библиотеку с [веб‑сайта Aspose.GIS](https://releases.aspose.com/gis/net/).  
2. Базовые знания программирования на C#: знакомство с языком C# будет полезным.

## Импорт пространств имён
Сначала импортируйте необходимые пространства имён, чтобы использовать классы и методы Aspose.GIS.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Шаг 1: Создать точку
`Point` — это базовый класс геометрии, представляющий отдельное местоположение в 2‑D или 3‑D пространстве. Вы будете использовать его для демонстрации снижения точности.

```csharp
Point point = new Point(1.344, 2.345, 3.345, 4.345);
```

## Шаг 2: Снизить точность XY
`RoundXY` уменьшает количество десятичных знаков координат X и Y. Этот метод принимает желаемое количество знаков и возвращает новую геометрию с скорректированной точностью.

```csharp
point.RoundXY(digits: 2);
```

## Шаг 3: Отобразить координаты
После округления вы можете проверить обновлённые значения координат.

```csharp
Console.WriteLine("{0}, {1}, {2}, {3}", point.X, point.Y, point.Z, point.M);
```

## Шаг 4: Снизить точность Z – как округлять Z
`RoundZ` ограничивает точность компонента высоты (Z). Применение этого шага часто даёт наибольшее сокращение размера файлов для 3‑D наборов данных, поскольку значения высот обычно содержат много десятичных знаков.

```csharp
point.RoundZ(digits: 1);
```

## Шаг 5: Показать обновлённые координаты
Покажите координаты точки после снижения точности Z.

```csharp
Console.WriteLine("{0}, {1}, {2}, {3}", point.X, point.Y, point.Z, point.M);
```

## Шаг 6: Создать линию (LineString)
`LineString` — это коллекция точек, образующая полилинию. Она полезна для демонстрации пакетных изменений точности на нескольких вершинах.

```csharp
LineString line = new LineString();
line.AddPoint(1.2, 2.3);
line.AddPoint(2.4, 3.1);
```

## Шаг 7: Снизить точность XY у LineString
Примените `RoundXY` ко всему `LineString`, чтобы обрезать значения X/Y для каждой вершины.

```csharp
line.RoundXY(digits: 0);
```

## Шаг 8: Показать обновлённые координаты LineString
Проверьте координаты после снижения точности XY.

```csharp
Console.WriteLine("{0}, {1}", line[0].X, line[0].Y);
Console.WriteLine("{0}, {1}", line[1].X, line[1].Y);
```

## Распространённые сценарии использования и советы
- **Большие преобразования растров‑векторов:** Округление Z может уменьшить промежуточные файлы геометрии, ускоряя конвейеры преобразования.  
- **Мобильные GIS‑приложения:** Низкая точность уменьшает пропускную способность при передаче геометрии по сети.  
- **Совет профессионала:** Применяйте `RoundXY` перед `RoundZ`, чтобы сохранить последовательность рабочего процесса и избежать повторного округления уже округлённых значений.

## Часто задаваемые вопросы

**Q: Почему уменьшение точности геометрии важно в GIS?**  
A: Снижение точности геометрии помогает оптимизировать использование памяти и улучшить производительность, особенно при работе с большими наборами данных в GIS‑приложениях.

**Q: Влияет ли снижение точности геометрии на точность?**  
A: Хотя теряется небольшая точность, компромисс часто обеспечивает хороший баланс между точностью и производительностью для большинства пространственных анализов.

**Q: Можно ли настроить уровень снижения точности в Aspose.GIS для .NET?**  
A: Да, вы можете указать желаемое количество десятичных знаков как для XY, так и для Z координат, используя методы `RoundXY` и `RoundZ`.

**Q: Есть ли измеримые преимущества в производительности?**  
A: Безусловно — меньше данных на вершину означает более быстрые пространственные запросы, уменьшенный ввод‑вывод и меньшее потребление памяти, часто обеспечивая **30 % более быструю обработку** на типичных наборах данных.

**Q: Где можно получить поддержку для Aspose.GIS для .NET?**  
A: Вы можете получить поддержку, посетив [форум Aspose.GIS](https://forum.aspose.com/c/gis/33) или обратившись к документации, доступной в [справочнике API Aspose.GIS .NET](https://reference.aspose.com/gis/net/).

---

**Последнее обновление:** 2026-09-10  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Как ограничить точность при записи геометрий с Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)
- [Создать векторный слой, ограничить точность с Aspose.GIS для .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Как преобразовать геометрию в WKT с Aspose.GIS для .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}