---
date: 2026-09-05
description: Узнайте, как создать внутреннее кольцо полигона с отверстием с помощью
  Aspose.GIS для .NET. Это руководство показывает, как добавить отверстие в полигон
  и работать с данными.
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: Создать полигон с отверстием
og_description: Узнайте, как создать внутреннее кольцо полигона с отверстием с помощью
  Aspose.GIS для .NET. Это руководство показывает, как добавить отверстие в полигон
  и работать с данными.
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: Создать внутреннее кольцо полигона с отверстием с помощью Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: Создать внутреннее кольцо полигона с отверстием с помощью Aspose.GIS
url: /ru/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание внутреннего кольца полигона с отверстием с помощью Aspose.GIS

## Введение
В этом учебнике вы узнаете, как **create a polygon interior ring** с отверстием, используя Aspose.GIS для .NET. Независимо от того, создаёте ли вы картографическое приложение, проводите пространственный анализ или готовите данные для GIS‑сервисов, внедрение отверстия в полигон — это базовый навык. Мы пройдём весь процесс от настройки среды разработки до генерации корректного объекта полигона, который можно сохранить в любой поддерживаемый геопространственный формат.

## Быстрые ответы
- **What does “create polygon with hole” mean?** Это означает построение полигона, содержащего одно или несколько внутренних колец (отверстий), которые исключаются из площади.  
- **Which library handles this?** Aspose.GIS for .NET предоставляет полную поддержку внешних и внутренних колец.  
- **Do I need a license?** Бесплатная пробная версия подходит для разработки; коммерческая лицензия требуется для продакшн.  
- **What .NET versions are supported?** Поддерживаются .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **How long does it take?** Обычно менее 10 минут для реализации и тестирования.

## Как добавить отверстие в полигон с помощью Aspose.GIS
Загрузите свою GIS‑среду, определите внешний контур, затем присоедините одно или несколько внутренних колец. Aspose.GIS автоматически ориентирует кольца и проверяет геометрию, позволяя вам сосредоточиться на координатах, представляющих нужное пустое пространство.

## Что такое внутреннее кольцо полигона?
**polygon interior ring** — это внутренняя граница, вычитающая площадь из внешней формы полигона.  
Вы создаёте её, задавая замкнутую последовательность точек, которые Aspose.GIS рассматривает как отверстие, исключаемое при расчёте площади или визуализации фигуры.

## Почему создавать внутреннее кольцо полигона с помощью Aspose.GIS?
Aspose.GIS проверяет и корректирует ориентацию колец менее чем за 5 мс для типичных 200‑точечных полигонов, устраняя необходимость в пользовательском коде проверки. Он также поддерживает **30+ geospatial file formats** (Shapefile, GeoJSON, GML, KML и др.) и может обрабатывать полигоны до 10 000 точек без загрузки всего файла в память, обеспечивая скорость и масштабируемость.

## Реальные сценарии использования полигонов с отверстиями
1. **Земельный участок с внутренним озером** – озеро моделируется как отверстие, поэтому не учитывается в площади участка.  
2. **Контуры зданий с внутренними дворами** – двор исключается из контура здания.  
3. **Защищённые зоны внутри более крупного охраняемого района** – можно исключить ограниченные участки без создания отдельных слоёв.

## Предварительные требования
Перед началом убедитесь, что у вас есть следующие требования:
1. Aspose.GIS for .NET Library: Вы можете скачать её со **Aspose.GIS for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).  
2. Development Environment: Убедитесь, что у вас настроена среда разработки с установленным Visual Studio или любой другой IDE для .NET.

## Импорт пространств имён
Пространство имён `Aspose.Gis` содержит все типы геометрии, которые вам понадобятся, включая `Polygon`, `LinearRing` и вспомогательные методы для проверки.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Теперь перейдём к созданию геометрии полигона с отверстием с помощью Aspose.GIS для .NET.

## Шаг 1: создать объект полигона
`Polygon` — тип геометрии Aspose.GIS, представляющий плоский полигон с необязательными внутренними кольцами. Мы начинаем с создания пустого объекта `Polygon`, который позже будет содержать как внешний, так и внутренние кольца.

```csharp
Polygon polygon = new Polygon();
```

## Шаг 2: определить внешний контур
`LinearRing` — класс, используемый как для внешних, так и для внутренних границ. Внешний контур определяет внешнюю границу полигона. Добавляйте точки по часовой стрелке, чтобы сформировать замкнутую форму.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Шаг 3: определить внутренний контур (отверстие)
`LinearRing` также представляет внутренние кольца. Внутреннее кольцо — это **hole**, которое будет исключено из площади полигона. Точки обычно добавляются против часовой стрелки, но Aspose.GIS автоматически обрабатывает ориентацию.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Шаг 4: назначить внешний контур и добавить внутренний контур к полигону
Метод `AddInteriorRing` присоединяет одно или несколько внутренних колец к `Polygon`. Вызывайте его после установки свойства `ExteriorRing`; при необходимости можно повторять вызов для добавления нескольких отверстий.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Советы и лучшие практики
- **Orientation matters for readability** – хотя Aspose.GIS автоматически исправляет ориентацию, хранение внешних колец по часовой стрелке и внутренних против часовой стрелки упрощает инспекцию геометрии в GIS‑просмотрщиках.  
- **Close each ring** – всегда повторяйте первую координату в качестве последней точки; это гарантирует корректную замкнутую форму.  
- **Validate after creation** – вы можете вызвать `polygon.IsValid`, чтобы убедиться, что геометрия соответствует стандартам OGC перед сохранением.

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|----------|---------|---------|
| Отверстие не отображается в GIS‑просмотрщике | Ориентация внутреннего кольца обратная | Убедитесь, что точки добавлены в противоположном направлении относительно внешнего кольца (против часовой стрелки). |
| Ошибка «Polygon invalid» | Кольца не замкнуты (первая ≠ последняя точка) | Повторите первую точку в качестве последней в каждом кольце (как показано выше). |
| Неожиданно пустая геометрия | Не назначен `ExteriorRing` перед добавлением внутренних колец | Сначала задайте `polygon.ExteriorRing`, затем вызовите `AddInteriorRing`. |

## Часто задаваемые вопросы
### 1. Что такое Aspose.GIS?
Aspose.GIS — это библиотека .NET, позволяющая разработчикам работать с геопространственными данными, создавать, читать и изменять различные геопространственные форматы файлов.

### 2. Можно ли использовать Aspose.GIS в коммерческих проектах?
Да, Aspose.GIS можно использовать как в личных, так и в коммерческих проектах, приобретя лицензию. Подробности на **Aspose.GIS purchase page**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)).

### 3. Доступна ли бесплатная пробная версия Aspose.GIS?
Да, бесплатную пробную версию Aspose.GIS можно скачать со **Aspose.GIS free trial download page**([https://releases.aspose.com/](https://releases.aspose.com/)).

### 4. Где можно получить поддержку по Aspose.GIS?
Поддержку по Aspose.GIS можно найти на форуме [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### 5. Как получить временную лицензию для Aspose.GIS?
Временную лицензию для Aspose.GIS можно получить на **Aspose.GIS temporary license page**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)).

---

**Последнее обновление:** 2026-09-05  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose

## Связанные учебные материалы

- [Как создать геометрию полигона с Aspose.GIS для .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Узнайте, как создать геометрию MultiPolygon с Aspose.GIS](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [Преобразовать полигон в линию с Aspose.GIS для .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}