---
date: 2026-03-29
description: Узнайте, как создавать геометрию мультиполигона и добавлять полигоны
  в мультиполигон с помощью Aspose.GIS для .NET. Пошаговое руководство с бесплатной
  пробной версией.
linktitle: Create MultiPolygon Geometry
second_title: Aspose.GIS .NET API
title: Как создать геометрию MultiPolygon с помощью Aspose.GIS
url: /ru/net/geometry-creation/create-multipolygon-geometry/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать геометрию MultiPolygon с помощью Aspose.GIS

## Введение
Если вы ищете **как создать multipolygon** формы в среде .NET, вы попали в нужное место. Aspose.GIS для .NET предоставляет чистый, объектно‑ориентированный API для построения сложных геопространственных объектов, а этот учебник проведёт вас через каждый шаг — от установки библиотеки до объединения отдельных полигонов в один MultiPolygon. К концу вы сможете уверенно **добавлять полигоны в multipolygon** структуры.

## Быстрые ответы
- **What is a MultiPolygon?** Геометрия, которая группирует два или более объектов Polygon в одну коллекцию.  
- **Why use Aspose.GIS?** Он поддерживает множество форматов GIS, работает на .NET Framework и .NET Core и не требует внешних нативных библиотек.  
- **How long does the example take?** Около 5 минут на набор и запуск.  
- **Do I need a license?** Бесплатная пробная версия подходит для разработки; для продакшна требуется коммерческая лицензия.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Что такое геометрия MultiPolygon?
MultiPolygon — это составная геометрия, содержащая несколько объектов Polygon, каждый из которых может иметь свои внутренние кольца (отверстия). Такая структура идеальна для представления разрозненных земельных участков, островов или любого набора отдельных областей, имеющих общую характеристику.

## Зачем добавлять полигоны в MultiPolygon?
Добавление полигонов в MultiPolygon позволяет рассматривать несколько независимых фигур как единый объект. Это упрощает пространственные запросы, визуализацию и обмен данными, поскольку вы можете хранить, передавать и манипулировать всей коллекцией одним объектом, а не обрабатывать каждый полигон отдельно.

## Требования
Прежде чем погрузиться в код, убедитесь, что у вас есть следующее:

- **Aspose.GIS for .NET** установлен (см. шаги ниже).  
- Среда разработки .NET (Visual Studio, VS Code или любая другая IDE по вашему выбору).  
- Базовое знакомство с синтаксисом C#.

### Установка Aspose.GIS для .NET
1. Скачайте Aspose.GIS: перейдите на [download page](https://releases.aspose.com/gis/net/) и выберите подходящую версию для вашей среды разработки.  
2. Установите Aspose.GIS: следуйте инструкциям по установке, приведённым в документации, чтобы установить Aspose.GIS для .NET на ваш компьютер.

## Импорт пространств имён
Чтобы начать работу с Aspose.GIS в вашем проекте .NET, импортируйте необходимые пространства имён:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Шаг 1: Создание линейных колец
Сначала нам нужно создать объекты **LinearRing** для каждого полигона. LinearRing — это замкнутая линейная строка, определяющая внешнюю границу (и при необходимости внутренние отверстия) полигона.

```csharp
LinearRing firstRing = new LinearRing();
firstRing.AddPoint(8.5, -2.5);
firstRing.AddPoint(-8.5, 2.5);
firstRing.AddPoint(8.5, -2.5);
LinearRing secondRing = new LinearRing();
secondRing.AddPoint(7.6, -3.6);
secondRing.AddPoint(-9.6, 1.5);
secondRing.AddPoint(7.6, -3.6);
```

## Шаг 2: Создание полигонов
Затем мы преобразуем каждый LinearRing в объект **Polygon**. Эти полигоны позже будут добавлены в MultiPolygon.

```csharp
Polygon firstPolygon = new Polygon(firstRing);
Polygon secondPolygon = new Polygon(secondRing);
```

## Шаг 3: Создание MultiPolygon
Теперь объединим полигоны в одну геометрию **MultiPolygon**. Здесь мы **добавляем полигоны в multipolygon**.

```csharp
MultiPolygon multiPolygon = new MultiPolygon();
multiPolygon.Add(firstPolygon);
multiPolygon.Add(secondPolygon);
```

Поздравляем! Вы успешно создали геометрию MultiPolygon с помощью Aspose.GIS для .NET.

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|-------|-------|-----|
| **Точки не замыкают кольцо** | Первый и последний пункты различаются. | Убедитесь, что первая и последняя координаты одинаковы; Aspose.GIS автоматически замыкает кольцо, но явное замыкание избегает путаницы. |
| **Неправильный порядок координат (X, Y vs. Lon, Lat)** | Смешивание долготы и широты. | Следуйте порядку (X, Y), используемому в Aspose.GIS; X = долгота, Y = широта. |
| **Библиотека не найдена во время выполнения** | Отсутствует ссылка NuGet или DLL. | Проверьте, что пакет Aspose.GIS указан в файле проекта и DLL скопирована в выходную папку. |

## Часто задаваемые вопросы

**Q: Подходит ли Aspose.GIS для .NET начинающим?**  
A: Абсолютно! Aspose.GIS предоставляет обширную документацию и учебные материалы, помогающие разработчикам любого уровня начать работу.

**Q: Могу ли я попробовать Aspose.GIS перед покупкой?**  
A: Да, вы можете скачать бесплатную пробную версию [здесь](https://releases.aspose.com/), чтобы изучить её возможности перед покупкой.

**Q: Где я могу найти поддержку Aspose.GIS?**  
A: Вы можете посетить форум Aspose.GIS [здесь](https://forum.aspose.com/c/gis/33), чтобы задать вопросы и получить помощь от сообщества.

**Q: Есть ли временная лицензия для Aspose.GIS?**  
A: Да, вы можете получить временную лицензию [здесь](https://purchase.aspose.com/temporary-license/) для оценки.

**Q: Можно ли купить Aspose.GIS напрямую?**  
A: Да, вы можете приобрести Aspose.GIS на сайте [здесь](https://purchase.aspose.com/buy).

---

**Последнее обновление:** 2026-03-29  
**Тестировано с:** Aspose.GIS 24.12 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}