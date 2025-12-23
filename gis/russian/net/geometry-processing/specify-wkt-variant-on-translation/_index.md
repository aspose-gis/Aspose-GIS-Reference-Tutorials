---
date: 2025-12-23
description: Узнайте, как преобразовать геометрию в WKT с различными вариантами, установить
  числовой формат и настроить точность десятичных знаков с помощью Aspose.GIS для
  .NET.
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: Преобразование геометрии в варианты WKT с помощью Aspose.GIS
url: /ru/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Преобразование геометрии в варианты WKT с использованием Aspose.GIS

## Introduction
В современных приложениях .NET **преобразование геометрии в WKT** является обычным шагом, когда необходимо обмениваться пространственными данными с другими системами или сохранять их в текстовом формате. Aspose.GIS для .NET делает это преобразование простым, предоставляя полный контроль над вариантом WKT, форматом чисел и точностью десятичных знаков. В этом руководстве вы узнаете, как преобразовать геометрию в WKT, выбрать правильный вариант и точно настроить вывод в соответствии с требованиями вашего проекта.

## Quick Answers
- **Что означает «преобразование геометрии в WKT»?** Это преобразует геометрические объекты (точки, линии, полигоны) в представление Well‑Known Text.  
- **Какие варианты WKT поддерживаются?** `Iso`, `SimpleFeatureAccessOutdated` и `ExtendedPostGis`.  
- **Как контролировать точность десятичных знаков?** Используйте параметры `NumericFormat`, такие как `General`, `RoundTrip` или `Flat`.  
- **Нужна ли лицензия для продакшн?** Да, для использования в не‑тестовом режиме требуется коммерческая лицензия.  
- **Какие версии .NET совместимы?** .NET Framework 4.0+ и .NET 5/6/7.

## What is “convert geometry to WKT”?
Преобразование геометрии в WKT создает человекочитаемую строку, описывающую пространственные объекты. Этот формат широко поддерживается GIS‑инструментами, базами данных и веб‑сервисами, что делает его идеальным для обмена данными.

## Why use Aspose.GIS for this conversion?
- **Precision control** – Выберите, сколько десятичных знаков будет выводиться.  
- **Variant flexibility** – Соответствуйте точному диалекту WKT, требуемому вашей целевой системой.  
- **No external dependencies** – Чистая .NET‑библиотека, без нативных бинарных файлов.

## Prerequisites
Перед началом убедитесь, что у вас есть:

1. **Aspose.GIS for .NET** – Скачайте и установите его со [страницы загрузки](https://releases.aspose.com/gis/net/).  
2. **Development Environment** – Любая современная версия Visual Studio или VS Code с .NET SDK.  
3. **Basic C# knowledge** – Знание классов, объектов и платформы .NET.

## Import Namespaces
Сначала подключите необходимые пространства имён:

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

## Step 1: Create a Point Object
Создайте `Point`, который позже будет **преобразован в WKT**. Точка содержит широту, долготу и необязательное значение измерения (M):

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Step 2: Set Spatial Reference System (SRS)
Назначьте систему координат, чтобы вывод WKT знал, к какой системе привязаны координаты. Здесь используется общепринятая система WGS84:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Step 3: Specify WKT Variant
Выберите подходящий вариант WKT при **преобразовании геометрии в WKT**. Каждый вариант форматирует вывод немного по‑разному:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Step 4: Control Numeric Format (Set Numeric Format & Adjust Decimal Precision)
Точно настройте числовое представление координат. Класс `NumericFormat` позволяет **установить формат чисел** и **регулировать точность десятичных знаков** в соответствии с вашими потребностями:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## Common Issues & Tips
- **Missing M value** – Если измерение не требуется, опустите свойство `M`; вариант ISO автоматически его удалит.  
- **Unexpected precision** – Убедитесь, что используете правильный `NumericFormat`; `General` сохраняет полную двойную точность, а `Flat` округляет до указанного количества знаков.  
- **SRID not displayed** – Только вариант `ExtendedPostGis` добавляет префикс `SRID=` к выводу. Выбирайте этот вариант, если ваша целевая система ожидает SRID.

## Conclusion
Следуя этим шагам, вы теперь знаете, как **преобразовать геометрию в WKT**, выбрать правильный вариант и точно контролировать числовой вывод. Это даёт гибкость интеграции Aspose.GIS в любой GIS‑рабочий процесс, базу данных или веб‑сервис, который потребляет WKT.

## FAQ's
### Is Aspose.GIS compatible with all versions of .NET?
Yes, Aspose.GIS supports .NET Framework 4.0 and higher.  

### Can I use Aspose.GIS for commercial projects?
Yes, Aspose.GIS can be used for both personal and commercial projects.  

### Does Aspose.GIS provide support for other spatial data formats?
Yes, Aspose.GIS supports a wide range of spatial data formats, including ESRI Shapefile, GeoJSON, and KML.  

### Is there a free trial available for Aspose.GIS?
Yes, you can download a free trial version of Aspose.GIS from [here](https://releases.aspose.com/).  

### Where can I get help or support for Aspose.GIS?
You can post your queries or seek assistance from the Aspose.GIS community at the [forum](https://forum.aspose.com/c/gis/33).

## Frequently Asked Questions
**Q: How do I export a Geometry collection to a single WKT string?**  
A: Iterate over each geometry in the collection and concatenate their `AsText` results, optionally separating them with commas or newlines.

**Q: Can I change the SRID without altering the coordinates?**  
A: Yes, set the `SpatialReferenceSystem` property to the desired SRID; the coordinate values remain unchanged.

**Q: What happens if I use an unsupported WKT variant?**  
A: Aspose.GIS will throw an `ArgumentException`. Always validate the variant against `WktVariant` enum values.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}