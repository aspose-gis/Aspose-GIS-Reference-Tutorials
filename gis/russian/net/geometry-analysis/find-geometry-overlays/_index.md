---
title: Освоение наложений геометрии с помощью Aspose.GIS for .NET
linktitle: Найдите наложения геометрии
second_title: API Aspose.GIS .NET
description: Узнайте, как выполнять операции наложения геометрических фигур с помощью Aspose.GIS для .NET. Освойте операции пересечения, объединения, разности и симметричной разности.
type: docs
weight: 16
url: /ru/net/geometry-analysis/find-geometry-overlays/
---
## Введение
В сфере географических информационных систем (ГИС) операции наложения имеют основополагающее значение для пространственного анализа. Они позволяют сравнивать и комбинировать различные наборы пространственных данных для получения ценной информации. Aspose.GIS for .NET предоставляет надежные функциональные возможности для эффективного выполнения геометрических наложений. В этом уроке мы углубимся в различные операции наложения, такие как пересечение, объединение, разница и симметричная разница, с использованием Aspose.GIS для .NET.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
### 1. Среда разработки .NET.
Убедитесь, что на вашем компьютере установлена среда разработки .NET. Вы можете загрузить и установить .NET SDK с веб-сайта .NET.
### 2. Aspose.GIS для библиотеки .NET
 Загрузите и установите библиотеку Aspose.GIS for .NET с сайта[Веб-сайт](https://releases.aspose.com/gis/net/).
## Импортировать пространства имен
Прежде чем вы сможете начать использовать Aspose.GIS for .NET, вам необходимо импортировать необходимые пространства имен в ваш проект.
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Шаг 1. Создайте полигональные объекты
Сначала мы определим два полигональных объекта, представляющих пространственные области.
```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```
## Шаг 2. Выполните операцию пересечения
Далее давайте найдем пересечение двух многоугольников.
```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Полигон
```
## Шаг 3. Распечатайте точки пересечения
Мы напечатаем точки пересечения многоугольника.
```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```
## Шаг 4. Выполните операцию объединения
Теперь давайте найдем объединение двух многоугольников.
```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Полигон
```
## Шаг 5: Распечатайте очки Union Points
Выведите точки объединенного многоугольника.
```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```
## Шаг 6: Выполните операцию разницы
Далее давайте найдем разницу между двумя многоугольниками.
```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Полигон
```
## Шаг 7: Распечатайте точки различий
Выведите точки разностного многоугольника.
```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```
## Шаг 8. Выполните операцию симметричной разности
Наконец, давайте найдем разницу симметрии между двумя многоугольниками.
```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // Мультиполигон
```
## Шаг 9: Распечатайте симметричные разностные многоугольники
Выведите точки каждого многоугольника в симметричной разности.
```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```
## Заключение
Освоение наложений геометрии имеет решающее значение для пространственного анализа, и Aspose.GIS for .NET предоставляет полный набор инструментов для эффективного выполнения этих операций. Следуя этому руководству, вы узнали, как использовать Aspose.GIS для .NET для выполнения операций пересечения, объединения, разности и симметричной разности геометрических фигур.
## Часто задаваемые вопросы
### Вопрос: Могу ли я использовать Aspose.GIS for .NET в своих коммерческих проектах?
Да, Aspose.GIS for .NET можно использовать как в коммерческих, так и в некоммерческих проектах.
### Вопрос: Доступна ли пробная версия Aspose.GIS для .NET?
 Да, вы можете скачать бесплатную пробную версию с сайта[здесь](https://releases.aspose.com/).
### Вопрос: Как я могу получить поддержку Aspose.GIS для .NET?
 Вы можете получить поддержку на форуме сообщества Aspose.GIS.[здесь](https://forum.aspose.com/c/gis/33).
### Вопрос: Существуют ли временные лицензии для Aspose.GIS for .NET?
 Да, временные лицензии доступны для тестирования и оценки. Вы можете получить их от[здесь](https://purchase.aspose.com/temporary-license/).
### Вопрос: Могу ли я купить Aspose.GIS для .NET напрямую?
 Да, вы можете приобрести Aspose.GIS для .NET на веб-сайте.[здесь](https://purchase.aspose.com/buy).