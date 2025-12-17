---
date: 2025-12-17
description: Узнайте, как создавать мультиполигональную геометрию в ASP.NET с помощью
  Aspose.GIS для .NET. Пошаговое руководство, бесплатная пробная версия и информация
  о лицензировании.
linktitle: Create MultiPolygon Geometry
second_title: Aspose.GIS .NET API
title: Как создать мультиполигональную геометрию в asp.net с помощью Aspose.GIS
url: /ru/net/geometry-creation/create-multipolygon-geometry/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание геометрии MultiPolygon с помощью Aspose.GIS

## Введение
If you need to **create multipolygon geometry asp.net**, Aspose.GIS for .NET gives you a clean, type‑safe API that works on any .NET platform. In this tutorial we’ll walk through the whole process—from installing the library to building a MultiPolygon object that you can export to Shapefile, GeoJSON, or any other supported format. Whether you’re building a mapping web service or a desktop GIS tool, mastering this workflow will save you time and reduce bugs.

## Быстрые ответы
- **What can I build with this?** Любое GIS‑приложение, которому нужны сложные полигональные регионы, такие как карты землепользования или зоны доставки.  
- **Do I need a license?** Бесплатная пробная версия подходит для разработки; для продакшна требуется постоянная лицензия.  
- **Which .NET versions are supported?** Поддерживаемые версии .NET: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **How long does the code take to write?** Около 5‑10 минут для базового MultiPolygon.  
- **Can I export the result?** Да — используйте встроенные методы `Save` для записи в Shapefile, GeoJSON и т.д.

## Что такое геометрия MultiPolygon?
**MultiPolygon** — это набор отдельных полигонов, которые могут быть разрозненными или содержать отверстия. В терминологии GIS это представляет набор пространственных объектов, имеющих одинаковый атрибут, но геометрически раздельных — идеально подходит для представления стран, состоящих из островов, или участков с несколькими частями.

## Почему стоит использовать Aspose.GIS для .NET?
- **Full‑featured API** — отсутствие внешних нативных зависимостей, чистый управляемый код.  
- **Cross‑platform** — работает на Windows, Linux и macOS.  
- **Rich format support** — чтение/запись десятков векторных форматов из коробки.  
- **Performance‑optimized** — обрабатывает большие наборы данных с небольшими затратами памяти.

## Требования
Прежде чем начать, убедитесь, что у вас есть следующее:

1. **Visual Studio 2022** (или любая IDE для C#) с установленным .NET 6 SDK.  
2. **Aspose.GIS for .NET** пакет — скачайте его со [страницы загрузки](https://releases.aspose.com/gis/net/) и следуйте руководству по установке в документации.

## Импорт пространств имён
Добавьте необходимые директивы `using` в ваш проект, чтобы компилятор знал, где находятся типы GIS:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Шаг 1: Создание LinearRing
**LinearRing** — это замкнутый `LineString`, определяющий внешнюю или внутреннюю границу полигона. Здесь мы создаём два простых кольца:

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

> **Pro tip:** Первые и последние точки должны совпадать, чтобы замкнуть кольцо; Aspose.GIS автоматически замкнёт его, если вы опустите конечную точку, но явное указание избегает путаницы.

## Шаг 2: Создание полигонов
Каждый `Polygon` создаётся из `LinearRing`. При необходимости позже можно добавить внутренние кольца (отверстия).

```csharp
Polygon firstPolygon = new Polygon(firstRing);
Polygon secondPolygon = new Polygon(secondRing);
```

## Шаг 3: Создание MultiPolygon
Теперь мы объединяем два полигона в один объект `MultiPolygon` — это именно тот шаг, который позволяет **create multipolygon geometry asp.net**.

```csharp
MultiPolygon multiPolygon = new MultiPolygon();
multiPolygon.Add(firstPolygon);
multiPolygon.Add(secondPolygon);
```

Теперь у вас есть полностью функциональный `MultiPolygon`, которым вы можете манипулировать, выполнять запросы или сериализовать.

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|----------|---------|---------|
| **Ring not closed** | Отсутствует дублирование первой точки | Убедитесь, что первая и последняя точки одинаковы, либо явно вызовите `LinearRing.Close()`. |
| **Incorrect coordinate order** | Широта/долгота перепутаны | Aspose.GIS ожидает **X = longitude**, **Y = latitude**. Проверьте ваш источник данных. |
| **Exception on `Add`** | Добавление пустого (null) полигона | Убедитесь, что каждый экземпляр `Polygon` создан перед добавлением в `MultiPolygon`. |

## Заключение
Следуя этим шагам, вы научились **create multipolygon geometry asp.net** с помощью Aspose.GIS для .NET. Эта база позволяет создавать более сложные пространственные модели, выполнять пространственные запросы и экспортировать данные в любой поддерживаемый GIS‑формат. Далее изучайте методы, такие как `Contains`, `Intersects` или `Transform`, чтобы добавить аналитические возможности в ваше приложение.

## FAQ's
### Подходит ли Aspose.GIS для .NET новичкам?
Абсолютно! Aspose.GIS предоставляет обширную документацию и учебные материалы, помогающие разработчикам любого уровня начать работу.

### Можно ли попробовать Aspose.GIS перед покупкой?
Да, вы можете скачать бесплатную пробную версию [здесь](https://releases.aspose.com/), чтобы изучить её возможности перед покупкой.

### Где я могу найти поддержку Aspose.GIS?
Вы можете посетить форум Aspose.GIS [здесь](https://forum.aspose.com/c/gis/33), чтобы задать вопросы и получить помощь от сообщества.

### Есть ли временная лицензия для Aspose.GIS?
Да, вы можете получить временную лицензию [здесь](https://purchase.aspose.com/temporary-license/) для оценки.

### Можно ли купить Aspose.GIS напрямую?
Да, вы можете приобрести Aspose.GIS на сайте [здесь](https://purchase.aspose.com/buy).

## Часто задаваемые вопросы
**Q: Как сохранить MultiPolygon в файл?**  
A: Используйте класс `Feature`, чтобы обернуть геометрию, и вызовите `feature.Save("output.shp", Drivers.Shapefile);`.

**Q: Можно ли добавить внутренние кольца (отверстия) к полигону?**  
A: Да — создайте второй `LinearRing` и передайте его вторым аргументом в конструктор `Polygon`.

**Q: Можно ли преобразовать координаты в другую пространственную ссылку?**  
A: Конечно. Вызовите `multiPolygon.Transform(sourceCRS, targetCRS);`, где объекты CRS определяются через коды EPSG.

---

**Последнее обновление:** 2025-12-17  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}