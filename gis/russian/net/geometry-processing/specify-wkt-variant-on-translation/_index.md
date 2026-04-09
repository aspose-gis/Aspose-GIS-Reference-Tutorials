---
date: 2026-04-09
description: Узнайте, как назначать пространственную привязку и задавать десятичную
  точность при создании точки C# с помощью Aspose.GIS for .NET в ваших .NET‑приложениях.
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: Указать вариант WKT при переводе
second_title: Aspose.GIS .NET API
title: Назначить пространственную привязку и установить вариант WKT с помощью Aspose.GIS
url: /ru/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Назначить пространственную привязку и установить вариант WKT с помощью Aspose.GIS

## Введение
В этом руководстве вы узнаете, как **назначать пространственную привязку** геометрии и управлять точным форматом вывода WKT с помощью Aspose.GIS для .NET. Независимо от того, нужно ли вам **создавать объекты point C#** для картографии, аналитики или обмена данными, возможность выбрать правильный вариант WKT и числовую точность делает ваши пространственные данные совместимыми и легко читаемыми. Давайте пошагово пройдем процесс.

## Быстрые ответы
- **Что означает «назначить пространственную привязку»?** Это связывает геометрию с конкретной системой координат, такой как WGS‑84.  
- **Какие варианты WKT поддерживаются?** Iso, SimpleFeatureAccessOutdated и ExtendedPostGis.  
- **Как я могу контролировать десятичную точность?** Используйте параметры `NumericFormat`, такие как `General`, `RoundTrip` или `Flat`.  
- **Нужна ли лицензия?** Доступна бесплатная пробная версия; для производства требуется коммерческая лицензия.  
- **Какие версии .NET совместимы?** .NET Framework 4.0+ и .NET Core/5/6+.

## Что такое «назначить пространственную привязку»?
Назначение пространственной привязки (или системы пространственной привязки, SRS) сообщает GIS‑программному обеспечению, как интерпретировать координатные значения геометрии. Без SRS числа широты‑долготы точки не имеют реального значения.

## Почему важно контролировать вариант WKT и числовой формат?
Разные GIS‑инструменты ожидают слегка различающиеся синтаксисы WKT. Выбор правильного варианта обеспечивает беспрепятственный обмен данными, а установка десятичной точности предотвращает ошибки округления или слишком длинные числа, которые загромождают журналы и файлы.

## Предварительные требования
1. Aspose.GIS для .NET — загрузить со страницы [страница загрузки](https://releases.aspose.com/gis/net/).  
2. Среда разработки .NET (Visual Studio, VS Code или Rider).  
3. Базовое знакомство с C# и .NET Framework.

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

## Шаг 1: Создать объект Point (create point C#)
Мы начинаем с создания `Point` с широтой, долготой и необязательным значением измерения (M):

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Шаг 2: Назначить систему пространственной привязки (SRS)
Теперь мы **назначаем пространственную привязку** точке. Здесь мы используем широко поддерживаемую систему WGS‑84 (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Шаг 3: Указать желаемый вариант WKT
Выберите вариант WKT, соответствующий вашему downstream‑приложению:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Шаг 4: Установить десятичную точность для вывода WKT
Контролируйте количество цифр в итоговой строке, используя `NumericFormat`:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Распространённые ошибки и советы
- **Подводный камень:** Если забыть установить SRS перед вызовом `AsText`, может отсутствовать информация о SRID.  
- **Совет:** Используйте `NumericFormat.RoundTrip`, когда требуется без потерь обратное преобразование координат.  
- **Совет:** Вариант `Iso` самый переносимый; выбирайте `ExtendedPostGis` только когда необходимо встроить SRID.

## Заключение
Теперь вы знаете, как **назначать пространственную привязку**, выбирать соответствующий вариант WKT и **устанавливать десятичную точность** при **создании объектов point C#** с помощью Aspose.GIS. Эти настройки дают вам гибкость для удовлетворения точных требований любого GIS‑рабочего процесса, от простой визуализации до высокоточной пространственной аналитики.

## Часто задаваемые вопросы

**Q:** Совместим ли Aspose.GIS со всеми версиями .NET?  
**A:** Да, Aspose.GIS поддерживает .NET Framework 4.0 и выше, а также .NET Core/5/6.

**Q:** Могу ли я использовать Aspose.GIS в коммерческих проектах?  
**A:** Конечно. Для использования в продакшене требуется коммерческая лицензия, но доступна бесплатная пробная версия для оценки.

**Q:** Поддерживает ли Aspose.GIS другие форматы пространственных данных?  
**A:** Да, он работает с ESRI Shapefile, GeoJSON, KML и многими другими форматами.

**Q:** Где можно загрузить бесплатную пробную версию?  
**A:** Вы можете загрузить бесплатную пробную версию Aspose.GIS с [здесь](https://releases.aspose.com/).

**Q:** Как получить помощь, если возникнут проблемы?  
**A:** Разместите свои вопросы на сообществе Aspose.GIS [forum](https://forum.aspose.com/c/gis/33), где могут помочь как сотрудники Aspose, так и участники сообщества.

---

**Последнее обновление:** 2026-04-09  
**Тестировано с:** Aspose.GIS for .NET (последний релиз)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}