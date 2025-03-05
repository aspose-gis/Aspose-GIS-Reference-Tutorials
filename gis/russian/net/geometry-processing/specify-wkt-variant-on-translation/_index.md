---
title: Укажите вариант WKT для перевода с помощью Aspose.GIS
linktitle: Укажите вариант WKT при переводе
second_title: API Aspose.GIS .NET
description: Узнайте, как указать варианты WKT в Aspose.GIS для .NET, чтобы эффективно управлять форматом и точностью представления пространственных данных.
type: docs
weight: 19
url: /ru/net/geometry-processing/specify-wkt-variant-on-translation/
---
## Введение
Aspose.GIS for .NET — это мощная библиотека, которая позволяет разработчикам легко работать с данными географической информационной системы (ГИС) в своих .NET-приложениях. Одной из важных функций, предоставляемых Aspose.GIS, является возможность указывать вариант хорошо известного текста (WKT) во время перевода, что позволяет пользователям контролировать формат и точность представления пространственных данных. В этом уроке мы рассмотрим, как шаг за шагом указывать варианты WKT, используя Aspose.GIS для .NET.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
1. Aspose.GIS for .NET: Загрузите и установите Aspose.GIS for .NET с сайта[страница загрузки](https://releases.aspose.com/gis/net/).
2. Среда разработки: убедитесь, что у вас настроена среда разработки .NET.
3. Базовые знания: Знакомство с языком программирования C# и .NET Framework.

## Импортировать пространства имен
Прежде чем использовать функциональность Aspose.GIS в своем коде, импортируйте необходимые пространства имен:
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
## Шаг 1. Создайте точечный объект
 Сначала создайте`Point` объект с широтой, долготой и дополнительными значениями меры (M):
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## Шаг 2. Установите пространственную систему отсчета (SRS).
Назначьте точечному объекту систему пространственной привязки (SRS). В этом примере мы используем пространственную систему координат WGS84:
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## Шаг 3. Укажите вариант WKT
 Теперь укажите вариант WKT для перевода. Aspose.GIS поддерживает различные варианты WKT, в том числе`Iso`, `SimpleFeatureAccessOutdated` , и`ExtendedPostGis`. Выберите подходящий вариант исходя из ваших требований:
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // ТОЧКА М (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // ТОЧКА (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```
## Шаг 4. Управляйте числовым форматом
Вы можете управлять числовым форматом координат в представлении WKT. Aspose.GIS предоставляет параметры для указания десятичной точности:
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // ТОЧКА М (23,5732 25,342099999999999 40,299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // ТОЧКА М (23,5732 25,3421 40,3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // ТОЧКА М (23,6 25,3 40,3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // ТОЧКА М (23,573 25,342 40,3)
```

## Заключение
В этом уроке мы узнали, как указывать варианты WKT при переводе с помощью Aspose.GIS для .NET. Следуя шагам, описанным выше, разработчики могут эффективно контролировать формат и точность представления пространственных данных в своих приложениях .NET, повышая гибкость и удобство использования географических информационных систем.
## Часто задаваемые вопросы
### Совместим ли Aspose.GIS со всеми версиями .NET?
Да, Aspose.GIS поддерживает .NET Framework 4.0 и выше.
### Могу ли я использовать Aspose.GIS для коммерческих проектов?
Да, Aspose.GIS можно использовать как для личных, так и для коммерческих проектов.
### Обеспечивает ли Aspose.GIS поддержку других форматов пространственных данных?
Да, Aspose.GIS поддерживает широкий спектр форматов пространственных данных, включая ESRI Shapefile, GeoJSON и KML.
### Доступна ли бесплатная пробная версия Aspose.GIS?
 Да, вы можете скачать бесплатную пробную версию Aspose.GIS с сайта[здесь](https://releases.aspose.com/).
### Где я могу получить помощь или поддержку по Aspose.GIS?
 Вы можете опубликовать свои вопросы или обратиться за помощью к сообществу Aspose.GIS на странице[Форум](https://forum.aspose.com/c/gis/33).