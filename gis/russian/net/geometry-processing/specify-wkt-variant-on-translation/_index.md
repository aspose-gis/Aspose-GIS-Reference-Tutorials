---
date: 2026-09-15
description: Узнайте, как назначить систему координат, установить вариант WKT и контролировать
  десятичную точность при создании точечной геометрии в C# с помощью Aspose.GIS для
  .NET.
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: Указать вариант WKT при трансляции
og_description: Узнайте, как назначить систему координат, установить вариант WKT и
  контролировать десятичную точность при создании точечной геометрии в C# с помощью
  Aspose.GIS для .NET.
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: Назначить систему координат, установить вариант WKT с помощью Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: Назначить систему координат, установить вариант WKT с помощью Aspose.GIS
url: /ru/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Назначить систему координат, установить вариант WKT с помощью Aspose.GIS

## Введение
В этом руководстве вы узнаете, как **назначить систему координат**, выбрать правильный вариант WKT и управлять десятичной точностью при **создании точечной геометрии** в C# с помощью Aspose.GIS для .NET. Независимо от того, создаёте ли вы картографический сервис, выполняете пространственный анализ или обмениваетесь данными между GIS‑платформами, эти настройки гарантируют, что ваш вывод будет совместим и легко читаем.

## Быстрые ответы
- **Что означает «назначить систему координат»?** Это связывает геометрию с конкретной системой координат, например WGS‑84.  
- **Какие варианты WKT поддерживаются?** Iso, SimpleFeatureAccessOutdated и ExtendedPostGis.  
- **Как контролировать десятичную точность?** Используйте перечисление `NumericFormat` (`General`, `RoundTrip`, `Flat`).  
- **Нужна ли лицензия для Aspose.GIS?** Доступна бесплатная пробная версия; для коммерческого использования требуется платная лицензия.  
- **Какие версии .NET совместимы?** .NET Framework 4.0+ и .NET Core/5/6+.

## Что означает «назначить систему координат»?
Назначение пространственной привязки (или системы пространственных ссылок, SRS) сообщает GIS‑программному обеспечению, как интерпретировать координатные значения геометрии, связывая числа с реальной системой координат, такой как WGS‑84. Без SRS числа широты‑долготы точки не имеют реального смысла.

## Почему важно контролировать вариант WKT и числовой формат?
Более 30 GIS‑инструментов ожидают определённые синтаксисы WKT, поэтому выбор правильного варианта предотвращает ошибки импорта. Установка числового формата уменьшает шум округления и делает вывод более лаконичным, что особенно важно при программном разборе журналов или файлов.

## Требования
1. Aspose.GIS for .NET – загрузить со [страницы загрузки](https://releases.aspose.com/gis/net/).  
2. Среда разработки .NET (Visual Studio, VS Code или Rider).  
3. Базовые знания C# и платформы .NET.

## Импорт пространств имён
Перед использованием любых классов Aspose.GIS импортируйте необходимые пространства имён:

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## Как назначить систему координат точке?
Загрузите экземпляр `Point`, затем присоедините систему пространственной привязки (SRS) с помощью класса `SpatialReference`. Этот двухшаговый шаблон гарантирует, что геометрия будет содержать метаданные системы координат при экспорте, позволяя downstream‑инструментам правильно интерпретировать координаты. Класс `Point` представляет одну локацию, определённую координатами X (долгота) и Y (широта).

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Шаг 2: назначить систему пространственной привязки (SRS)
Теперь **назначаем пространственную привязку** точке. `SpatialReference` представляет систему координат, идентифицируемую SRID. Здесь мы используем широко поддерживаемую систему WGS‑84 (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Шаг 3: указать желаемый вариант WKT
Выберите вариант WKT, соответствующий вашему downstream‑приложению:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Как установить десятичную точность для вывода WKT?
Контролируйте количество знаков в итоговой строке, используя перечисление `NumericFormat`, которое определяет правила форматирования, такие как `General`, `RoundTrip` или `Flat`. Выбор `RoundTrip` сохраняет полную точность координат для сценариев обратного преобразования, тогда как `General` обеспечивает компактное представление, подходящее для большинства визуализаций. Перечисление `NumericFormat` управляет тем, как числовые координаты форматируются в выводе WKT.

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Распространённые подводные камни и советы
- **Подводный камень:** Если не установить SRS перед вызовом `AsText`, информация о SRID может отсутствовать.  
- **Совет:** Используйте `NumericFormat.RoundTrip`, когда требуется без потерь обратное преобразование координат.  
- **Совет:** Вариант `Iso` наиболее переносим; выбирайте `ExtendedPostGis` только при необходимости встроенного SRID.

## Заключение
Теперь вы знаете, как **назначить систему координат**, выбрать подходящий вариант WKT и **установить десятичную точность** при **создании точечной геометрии** с помощью Aspose.GIS. Эти настройки дают гибкость для удовлетворения точных требований любого GIS‑рабочего процесса, от простой визуализации до высокоточного пространственного анализа.

## Часто задаваемые вопросы

**Q:** Совместим ли Aspose.GIS со всеми версиями .NET?  
**A:** Да, Aspose.GIS поддерживает .NET Framework 4.0 и выше, а также .NET Core/5/6.

**Q:** Можно ли использовать Aspose.GIS в коммерческих проектах?  
**A:** Абсолютно. Для производственного использования требуется коммерческая лицензия, но доступна бесплатная пробная версия для оценки.

**Q:** Поддерживает ли Aspose.GIS другие форматы пространственных данных?  
**A:** Да, он работает с более чем 30 форматами, включая ESRI Shapefile, GeoJSON, KML, CSV и многие другие.

**Q:** Где можно скачать бесплатную пробную версию?  
**A:** Вы можете скачать бесплатную пробную версию Aspose.GIS со [страницы бесплатной пробной загрузки Aspose.GIS](https://releases.aspose.com/).

**Q:** Как получить помощь, если возникнут проблемы?  
**A:** Задавайте вопросы в сообществе Aspose.GIS на [форуме](https://forum.aspose.com/c/gis/33), где помогут сотрудники Aspose и участники сообщества.

---

**Последнее обновление:** 2026-09-15  
**Тестировано с:** Aspose.GIS for .NET (latest release)  
**Автор:** Aspose

## Связанные руководства

- [Создать векторный слой и установить его систему пространственной привязки](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Как преобразовать геометрию в WKT с помощью Aspose.GIS для .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [Как ограничить точность при записи геометрий с Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}