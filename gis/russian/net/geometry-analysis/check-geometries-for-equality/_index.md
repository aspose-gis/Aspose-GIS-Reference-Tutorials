---
title: Проверка геометрии на равенство
linktitle: Проверка геометрии на равенство
second_title: API Aspose.GIS .NET
description: Из этого подробного руководства вы узнаете, как использовать Aspose.GIS for .NET для проверки равенства геометрии в ваших .NET-приложениях.
weight: 10
url: /ru/net/geometry-analysis/check-geometries-for-equality/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Проверка геометрии на равенство

## Введение
Aspose.GIS for .NET — это мощная библиотека, которая позволяет разработчикам эффективно работать с геопространственными данными в своих .NET-приложениях. Независимо от того, создаете ли вы картографические приложения, инструменты пространственного анализа или интегрируете геопространственные функции в существующее программное обеспечение, Aspose.GIS предоставляет инструменты, необходимые для выполнения работы.
## Предварительные условия
Прежде чем приступить к использованию Aspose.GIS for .NET, убедитесь, что у вас есть следующие предварительные условия:
### Установленная платформа .NET Framework
Убедитесь, что в вашей системе установлена .NET Framework. Вы можете скачать его с сайта Microsoft.
### Aspose.GIS для библиотеки .NET
 Загрузите и установите библиотеку Aspose.GIS for .NET с сайта[страница загрузки](https://releases.aspose.com/gis/net/). Следуйте инструкциям по установке, приведенным в документации.
### Среда разработки
Настройте предпочтительную среду разработки, например Visual Studio, для разработки .NET.

## Импортировать пространства имен
В вашем .NET-приложении импортируйте необходимые пространства имен для использования функций Aspose.GIS:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Шаг 1: Определите геометрию
Сначала определите геометрии, которые вы хотите сравнить. В этом примере у нас есть две геометрии:`geometry1` и`geometry2`.
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
## Шаг 2. Проверьте геометрии на равенство
 Теперь проверьте, равны ли геометрии в пространстве, используя`SpatiallyEquals` метод, предоставленный Aspose.GIS.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // Истинный
```
 Это будет напечатано`True` на консоль с тех пор`geometry1` и`geometry2` пространственно равны.
## Шаг 3: Измените геометрию
 Далее, давайте изменим`geometry2` добавив новую точку.
```csharp
geometry2.AddPoint(3, 3);
```
## Шаг 4. Еще раз проверьте равенство
Теперь еще раз проверьте равенство геометрий после модификации.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // ЛОЖЬ
```
 На этот раз вывод будет`False` поскольку геометрии больше не являются пространственно равными из-за модификации, внесенной в`geometry2`.

## Заключение
В заключение, Aspose.GIS for .NET предоставляет мощные инструменты для работы с геопространственными данными в приложениях .NET. Следуя этому пошаговому руководству, вы сможете легко проверить геометрию на равенство с помощью методов Aspose.GIS.
## Часто задаваемые вопросы
### Могу ли я использовать Aspose.GIS for .NET с другими платформами .NET?
Да, Aspose.GIS for .NET совместим с различными платформами .NET, включая .NET Core и .NET Standard.
### Доступна ли бесплатная пробная версия Aspose.GIS для .NET?
 Да, вы можете загрузить бесплатную пробную версию с сайта[страница релизов](https://releases.aspose.com/).
### Где я могу найти документацию по Aspose.GIS для .NET?
 Подробную документацию вы можете найти на[Страница документации Aspose.GIS](https://reference.aspose.com/gis/net/).
### Как я могу получить поддержку Aspose.GIS для .NET?
 Вы можете получить поддержку на форуме сообщества Aspose.GIS.[здесь](https://forum.aspose.com/c/gis/33).
### Могу ли я приобрести временную лицензию на Aspose.GIS для .NET?
 Да, вы можете приобрести временную лицензию на сайте[страница покупки](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
