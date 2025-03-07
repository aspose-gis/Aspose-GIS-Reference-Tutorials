---
title: Создайте многоугольник с геометрией отверстий с помощью Aspose.GIS
linktitle: Создайте многоугольник с геометрией отверстий
second_title: API Aspose.GIS .NET
description: Узнайте, как создать многоугольник с геометрией отверстий с помощью Aspose.GIS для .NET. Пошаговое руководство с примерами кода.
weight: 13
url: /ru/net/geometry-creation/create-polygon-with-hole-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создайте многоугольник с геометрией отверстий с помощью Aspose.GIS

## Введение
В этом уроке мы рассмотрим процесс создания многоугольника с геометрией отверстия с помощью Aspose.GIS для .NET. Aspose.GIS — это мощная библиотека, которая позволяет разработчикам работать с геопространственными данными в своих .NET-приложениях. 
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
1. Библиотека Aspose.GIS для .NET: ее можно загрузить с сайта[здесь](https://releases.aspose.com/gis/net/).
2. Среда разработки: убедитесь, что у вас настроена среда разработки с установленной Visual Studio или любой другой .NET IDE.
## Импортировать пространства имен
Во-первых, вам необходимо импортировать необходимые пространства имен для работы с функциями Aspose.GIS. Вот как это сделать:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Теперь приступим к созданию многоугольника с геометрией отверстия с помощью Aspose.GIS for .NET.
## Шаг 1: Создайте полигональный объект
```csharp
Polygon polygon = new Polygon();
```
## Шаг 2. Определите внешнее кольцо
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## Шаг 3: Определите внутреннее кольцо (отверстие)
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## Шаг 4. Назначьте внешнее кольцо и добавьте внутреннее кольцо к многоугольнику.
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## Заключение
Поздравляем! Вы успешно научились создавать многоугольник с геометрией отверстия с помощью Aspose.GIS for .NET. Эти знания будут полезны для различных геопространственных приложений, где такая геометрия важна.
## Часто задаваемые вопросы
### 1. Что такое Aspose.GIS?
Aspose.GIS — это библиотека .NET, которая позволяет разработчикам работать с геопространственными данными, позволяя им создавать, читать и манипулировать различными форматами геопространственных файлов.
### 2. Могу ли я использовать Aspose.GIS для коммерческих проектов?
 Да, вы можете использовать Aspose.GIS как для личных, так и для коммерческих проектов, купив лицензию. Посещать[здесь](https://purchase.aspose.com/buy) Больше подробностей.
### 3. Существует ли бесплатная пробная версия Aspose.GIS?
 Да, вы можете воспользоваться бесплатной пробной версией Aspose.GIS на сайте[здесь](https://releases.aspose.com/).
### 4. Где я могу найти поддержку Aspose.GIS?
 Вы можете найти поддержку Aspose.GIS на сайте[Форум Aspose.GIS](https://forum.aspose.com/c/gis/33).
### 5. Как я могу получить временную лицензию на Aspose.GIS?
 Вы можете получить временную лицензию на Aspose.GIS на сайте[здесь](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
