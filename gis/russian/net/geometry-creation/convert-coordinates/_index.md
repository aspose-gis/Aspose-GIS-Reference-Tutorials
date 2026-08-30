---
date: 2026-08-18
description: Преобразуйте decimal degrees в dms с помощью Aspose.GIS for .NET. Это
  пошаговое руководство на C# показывает, как преобразовать latitude/longitude, decimal
  degrees в dms и многое другое.
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: Преобразовать координаты
og_description: Преобразование decimal degrees в dms стало простым с Aspose.GIS for
  .NET. Узнайте, как преобразовать latitude‑longitude значения в формат DMS в минутах.
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: Как преобразовать decimal degrees в dms с помощью Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: Как преобразовать decimal degrees в dms с помощью Aspose.GIS for .NET
url: /ru/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как преобразовать десятичные градусы в dms с помощью Aspose.GIS

## Введение
В этом руководстве вы узнаете **как преобразовать десятичные градусы в dms** с использованием мощной библиотеки Aspose.GIS для .NET. Независимо от того, нужно ли вам **c# convert lat long**, генерировать человекочитаемые строки местоположения для отчетов или просто исследовать различные форматы координат, это руководство проведёт вас через каждый шаг с понятными объяснениями и готовыми к запуску фрагментами C#.

## Быстрые ответы
- **Что означает “convert coordinates to dms”?** Он преобразует числовые значения широты/долготы в традиционную запись градусов‑минут‑секунд.  
- **Какая библиотека выполняет преобразование?** Aspose.GIS для .NET предоставляет класс `GeoConvert` со встроенной поддержкой форматов.  
- **Нужна ли лицензия для пробного использования?** Доступна бесплатная пробная версия; коммерческая лицензия требуется для использования в продакшене.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+ и .NET 5/6+.  
- **Могу ли я использовать тот же код для других форматов?** Да — просто измените значение перечисления `PointFormats` (например, `DecimalDegrees`, `GeoRef`).  

## Что такое преобразование координат в DMS?
Преобразование координат в DMS переписывает десятичные значения широты и долготы в формат, например `25°30'00"N 45°30'00"E`. Процесс разбивает каждую десятичную градусную величину на целые градусы, минуты (одна шестьдесят первая часть градуса) и секунды (одна шестьдесят первая часть минуты), затем добавляет соответствующий индикатор полушария (N, S, E, W). Эта человекочитаемая форма необходима для многих устаревших наборов данных и для передачи точных местоположений без использования десятичной нотации.

## Почему использовать Aspose.GIS для преобразования координат?
Aspose.GIS поддерживает **50+ input and output formats** и может обрабатывать многосотстраничные GIS‑файлы без загрузки всего набора данных в память. API обеспечивает субмиллиметровую точность для граничных случаев, таких как отрицательные значения и индикаторы полушарий, и стабильно работает на Windows, Linux и macOS .NET‑рантаймах.

## Требования
1. **Базовые знания C#** – знакомство с переменными, вызовами методов и выводом в консоль.  
2. **Aspose.GIS установлен** – загрузите последний пакет с [веб‑сайта Aspose.GIS](https://releases.aspose.com/gis/net/). Вы также можете изучить основной сайт релизов Aspose на [веб‑сайте релизов Aspose](https://releases.aspose.com/).  

## Импорт пространств имён
First, import the namespaces required for GIS operations:

Импорт пространств имён оставлен без изменений.

## Пошаговое руководство

### Что такое класс GeoConvert?
Класс `GeoConvert` предоставляет статические методы для преобразования между форматами координат, такими как десятичные градусы, DMS и GeoRef. Он включает перегрузки, принимающие сырые числовые значения или объекты `Point`, и возвращает отформатированные строки или новые экземпляры `Point`. Обрабатывая граничные случаи, такие как отрицательные координаты и округление, класс гарантирует, что вывод соответствует стандартным GIS‑спецификациям, упрощая интеграцию в любое .NET‑приложение карт.

### Шаг 1: начать процесс преобразования
Мы выводим дружелюбное сообщение, чтобы вы знали, что демонстрация началась.

```csharp
using System;
using Aspose.Gis;
```

### Шаг 2: преобразовать в десятичные градусы
Несмотря на то, что конечная цель — DMS, мы начинаем с показа исходного десятичного представления. Это также демонстрирует путь **decimal degrees to dms**, который вы будете использовать позже.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Шаг 3: преобразовать в градусы с десятичными минутами
Этот формат (`DD°MM.m'`) является распространённым промежуточным шагом, когда нужно **convert lat long degree minutes**.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Шаг 4: преобразовать в градусы‑минуты‑секунды (dms)
Вот ядро нашего руководства — **convert coordinates to dms**.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Шаг 5: преобразовать в GeoRef
Для полноты мы также демонстрируем формат `GeoRef`, полезный в рабочих процессах дистанционного зондирования.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## Распространённые проблемы и решения
- **Incorrect hemisphere letters** – Убедитесь, что вы передаёте положительные значения для север/восток и отрицательные для юг/запад; API автоматически добавляет правильный суффикс.  
- **Unexpected blank output** – Проверьте, что сборка `Aspose.Gis` правильно подключена и что проект нацелен на поддерживаемую версию .NET.  
- **License not found** – Поместите файл лицензии в корень приложения или задайте его программно с помощью `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.  

## Часто задаваемые вопросы

**Q: Совместим ли Aspose.GIS с другими языками программирования?**  
A: Aspose.GIS в первую очередь ориентирован на разработчиков .NET, но также доступна версия для Java.

**Q: Можно ли попробовать Aspose.GIS перед покупкой?**  
A: Да, вы можете получить бесплатную пробную версию Aspose.GIS с [веб‑сайта](https://releases.aspose.com/).

**Q: Как получить поддержку для Aspose.GIS?**  
A: Вы можете обратиться за помощью на форуме сообщества Aspose.GIS [здесь](https://forum.aspose.com/c/gis/33).

**Q: Доступны ли временные лицензии для Aspose.GIS?**  
A: Да, временные лицензии можно получить на странице [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Где можно приобрести Aspose.GIS?**  
A: Вы можете приобрести Aspose.GIS на [purchase page](https://purchase.aspose.com/buy).

## Заключение
Следуя этим шагам, вы теперь знаете, как **convert decimal degrees to dms** и другие распространённые GIS‑форматы с помощью Aspose.GIS для .NET. Эта возможность позволяет бесшовно интегрировать человекочитаемые строки местоположения в картографические приложения, отчёты или любой рабочий процесс с пространственными данными. Не стесняйтесь экспериментировать с различными значениями широты/долготы и исследовать другие форматы, предлагаемые классом `GeoConvert`.

---

**Last Updated:** 2026-08-18  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Связанные руководства

- [Как создать точечную геометрию и получить тип геометрии с Aspose.GIS для .NET](/gis/net/geometry-analysis/get-geometry-type/)
- [Как конвертировать GeoJSON – Aspose.GIS для .NET](/gis/net/geo-data-conversion/)
- [Создание многоточечной геометрии .NET с Aspose.GIS](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}