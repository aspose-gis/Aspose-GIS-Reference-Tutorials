---
date: 2026-06-10
description: Узнайте, как создавать геометрию linestring в .NET и преобразовывать
  её в WKB с помощью Aspose.GIS для .NET, используя вариант ExtendedPostGis.
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: Указание варианта WKB при трансляции
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  headline: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  name: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  steps:
  - name: Creating a Geometry Object
    text: The `Geometry` class is Aspose.GIS's base type that represents any spatial
      object in memory. Linestring represents a series of connected points forming
      a linear geometry. In this step we instantiate a `Linestring` with a collection
      of coordinate pairs that model a simple road segment.
  - name: Generating WKB Representation
    text: '`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to
      include SRID in the output binary. Here we call the `AsBinary` method, passing
      the EWKB variant, which returns a `byte[]` containing the full binary representation.'
  - name: Writing to File
    text: '`File.WriteAllBytes` writes the binary array to disk. The resulting file
      (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB`
      function.'
  type: HowTo
- questions:
  - answer: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which
      PostGIS reads directly via `ST_GeomFromEWKB`.
    question: Can I use the EWKB file with PostGIS?
  - answer: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry
      from its binary form.
    question: Is it possible to read a WKB file back into a geometry object?
  - answer: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons,
      and many more spatial types.
    question: Does the library support other geometry types like polygons?
  - answer: Set the `SRID` property on the geometry object before calling `AsBinary`,
      e.g., `linestring.SRID = 4326;`.
    question: How do I specify a different SRID when creating the geometry?
  - answer: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6
      without modification.
    question: Will this code work on .NET Core?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Создание геометрии Linestring и варианта WKB в Aspose.GIS для .NET
url: /ru/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание геометрии Linestring и варианта WKB в Aspose.GIS для .NET

## Введение
Если вам нужно **create linestring geometry .NET** и затем преобразовать эту геометрию в бинарную форму, Aspose.GIS для .NET предоставляет чистый, высокопроизводительный API, работающий на .NET Framework, .NET Core и .NET 5/6+. В этом руководстве мы пройдём каждый шаг — от импорта пространств имён до записи EWKB‑файла — чтобы вы могли сохранять информацию SRID и интегрировать GIS‑данные в PostgreSQL/PostGIS или любой бинарный рабочий процесс без проблем.

## Быстрые ответы
- **Что означает WKB?** Well‑Known Binary, компактное бинарное представление геометрических объектов.  
- **Какой вариант WKB хранит SRID?** Вариант `ExtendedPostGis` (EWKB) встраивает SRID непосредственно в бинарный файл.  
- **Нужна ли лицензия?** Требуется временная или полная лицензия Aspose.GIS для развертывания в продакшене.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, и .NET 5/6+.  
- **Сколько времени занимает реализация?** Обычно менее 10 минут для базового примера.

## Что такое геометрия Linestring?
Геометрия linestring — это простая форма, состоящая из упорядоченного списка точек, соединённых прямыми отрезками. Это стандартное представление линейных объектов, таких как дороги, трубопроводы или русла рек в пространственных базах данных.

## Зачем указывать вариант WKB?
Использование правильного варианта WKB гарантирует, что критические метаданные — особенно идентификатор системы координат (SRID) — будут переданы вместе с вашей геометрией. Вариант `ExtendedPostGis` (EWKB) сохраняет SRID внутри бинарного полезного нагрузки, обеспечивая бесшовный обмен с PostGIS, Oracle Spatial или любой системой, ожидающей бинарные данные с учётом SRID.

## Предварительные требования
Перед началом убедитесь, что у вас есть следующее:

### Установка Aspose.GIS для .NET
1. Скачайте Aspose.GIS: перейдите по [download link](https://releases.aspose.com/gis/net/) чтобы получить последнюю версию пакета.  
2. Добавьте пакет NuGet в ваш проект (например, `Install-Package Aspose.GIS`).  

### Знакомство с программированием на C#
- Базовое понимание синтаксиса C# и структуры проекта.  
- Возможность запускать .NET консольный или библиотечный проект.

## Импорт пространств имён
Пространство имён `Aspose.GIS` предоставляет доступ ко всем классам, связанным с геометрией.  

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Эти пространства имён предоставляют базовый функционал GIS, включая создание геометрии, трансформацию и бинарную сериализацию.

## Как создать геометрию linestring?
Чтобы создать linestring, создайте объект `Linestring` с упорядоченным списком пар координат, при необходимости задайте его SRID, а затем сериализуйте его в нужный вариант WKB. Процесс состоит из трёх шагов: построение геометрии, выбор варианта `ExtendedPostGis` для сохранения SRID и запись полученного массива байтов в файл.

### Шаг 1: Создание объекта Geometry
Класс `Geometry` — базовый тип Aspose.GIS, представляющий любой пространственный объект в памяти.  
Linestring представляет собой последовательность соединённых точек, образующих линейную геометрию.  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
На этом шаге мы создаём `Linestring` с набором пар координат, моделирующих простой дорожный отрезок.

### Шаг 2: Генерация представления WKB
`WkbVariant.ExtendedPostGis` — значение перечисления, которое указывает Aspose.GIS включать SRID в выходной бинарный файл.  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Здесь мы вызываем метод `AsBinary`, передавая вариант EWKB, который возвращает `byte[]`, содержащий полное бинарное представление.

### Шаг 3: Запись в файл
`File.WriteAllBytes` записывает массив байтов на диск.  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
Полученный файл (`EWkbFile.ewkb`) можно импортировать напрямую в таблицу PostGIS с помощью функции `ST_GeomFromEWKB`.

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|----------|---------|----------|
| **Пустой файл** | `Path.Combine` указывает на несуществующий каталог. | Убедитесь, что целевой каталог существует, или создайте его с помощью `Directory.CreateDirectory`. |
| **Неправильный SRID** | Использование значения по умолчанию `WkbVariant.Standard` удаляет SRID. | Всегда используйте `WkbVariant.ExtendedPostGis`, когда необходимо сохранять SRID. |
| **Исключение лицензии** | Запуск без действующей лицензии в продакшене. | Примените временную или полную лицензию перед выполнением кода в продакшн‑среде. |

## Часто задаваемые вопросы
**В: Можно ли использовать файл EWKB с PostGIS?**  
**О:** Да, вариант `ExtendedPostGis` создает EWKB, включающий SRID, который PostGIS читает напрямую через `ST_GeomFromEWKB`.  

**В: Можно ли прочитать файл WKB обратно в объект геометрии?**  
**О:** Конечно. Используйте `Geometry.FromBinary(byteArray)`, чтобы восстановить геометрию из её бинарного представления.  

**В: Поддерживает ли библиотека другие типы геометрии, например полигоны?**  
**О:** Да, Aspose.GIS работает с точками, linestring, полигонами, мультиполигонами и многими другими типами пространственных объектов.  

**В: Как задать другой SRID при создании геометрии?**  
**О:** Установите свойство `SRID` у объекта геометрии перед вызовом `AsBinary`, например, `linestring.SRID = 4326;`.  

**В: Будет ли этот код работать на .NET Core?**  
**О:** Да, тот же API работает на .NET Framework, .NET Core и .NET 5/6 без изменений.

---

**Последнее обновление:** 2026-06-10  
**Тестировано с:** Aspose.GIS for .NET 23.9 (latest at time of writing)  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Перевод геометрии в формат WKB с помощью Aspose.GIS для .NET](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [Указание варианта WKT при переводе с использованием Aspose.GIS](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [Создание геометрии MultiLineString с помощью Aspose.GIS для .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}