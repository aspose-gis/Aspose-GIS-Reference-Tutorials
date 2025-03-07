---
title: Подсчет геометрии в геометрии с помощью Aspose.GIS
linktitle: Подсчитайте геометрии в геометрии
second_title: API Aspose.GIS .NET
description: Узнайте, как подсчитывать геометрические фигуры с помощью Aspose.GIS для .NET. Пошаговое руководство с примерами кода для разработчиков.
weight: 23
url: /ru/net/geometry-creation/count-geometries-in-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Подсчет геометрии в геометрии с помощью Aspose.GIS

## Введение
Aspose.GIS for .NET — мощный инструмент для разработчиков, стремящихся включить геопространственные функции в свои .NET-приложения. Независимо от того, создаете ли вы картографическое программное обеспечение, службы определения местоположения или инструменты пространственного анализа, Aspose.GIS предоставляет полный набор функций для удовлетворения ваших потребностей. В этом уроке мы рассмотрим, как подсчитывать геометрии внутри геометрии с помощью Aspose.GIS для .NET.
## Предварительные условия
Прежде чем приступить к изучению этого руководства, убедитесь, что у вас есть следующие предварительные условия:
1. Visual Studio: убедитесь, что в вашей системе установлена Visual Studio.
2. Aspose.GIS for .NET: Загрузите и установите Aspose.GIS for .NET с сайта[страница загрузки](https://releases.aspose.com/gis/net/).
3. Базовые знания C#: ознакомьтесь с основами языка программирования C#.

## Импортировать пространства имен
Прежде чем приступить к написанию кода, вам необходимо импортировать необходимые пространства имен для доступа к функциям Aspose.GIS.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Шаг 2. Создайте точечную геометрию
```csharp
Point point = new Point(40.7128, -74.006);
```
 Здесь мы создаем`Point` геометрия с широтой 40,7128 и долготой -74,006.
## Шаг 3. Создайте геометрию LineString
```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```
 Этот шаг создает`LineString` геометрии и добавляет к ней две точки.
## Шаг 4: Создайте коллекцию геометрии
```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```
 Затем мы создаем`GeometryCollection` и добавьте к нему ранее созданную геометрию точек и линий.
## Шаг 5: Подсчитайте геометрии
```csharp
int geometriesCount = geometryCollection.Count;
```
 На этом этапе подсчитывается количество геометрий внутри`GeometryCollection`.
## Шаг 6: Отобразите счетчик
```csharp
Console.WriteLine(geometriesCount); // 2
```
 Наконец, мы распечатываем количество геометрий, которое в данном случае равно`2`.

## Заключение
В этом уроке мы научились подсчитывать геометрии внутри геометрии с помощью Aspose.GIS для .NET. Выполнив эти шаги, вы сможете легко включить геопространственные функции в свои приложения .NET.
## Часто задаваемые вопросы
### Подходит ли Aspose.GIS for .NET как для настольных, так и для веб-приложений?
Да, Aspose.GIS for .NET можно легко использовать как в настольных, так и в веб-приложениях.
### Могу ли я выполнять пространственные запросы с помощью Aspose.GIS for .NET?
Безусловно, Aspose.GIS for .NET обеспечивает надежную поддержку выполнения пространственных запросов к геометрии.
### Поддерживает ли Aspose.GIS for .NET различные форматы файлов ГИС?
Да, Aspose.GIS for .NET поддерживает широкий спектр форматов файлов ГИС, включая SHP, KML и GeoJSON.
### Доступна ли бесплатная пробная версия Aspose.GIS для .NET?
 Да, вы можете загрузить бесплатную пробную версию с сайта[Веб-сайт](https://releases.aspose.com/).
### Где я могу найти поддержку Aspose.GIS для .NET?
 Вы можете найти поддержку на[Форум Aspose.GIS](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
