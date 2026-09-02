---
date: 2026-08-24
description: Узнайте, как создавать curved line geometry и добавлять curves с помощью
  Aspose.GIS для .NET, обеспечивая точную обработку геопространственных данных.
keywords:
- create curved line
- how to add curves
- create compound curve
- circular arc geometry
lastmod: 2026-08-24
linktitle: Как добавить Curves – Compound Curve Geometry
og_description: Узнайте, как создавать curved line geometry с помощью Aspose.GIS для
  .NET. Этот учебник пошагово показывает, как добавлять curves и создавать compound
  curves за несколько минут.
og_image_alt: Screenshot of Aspose.GIS creating a compound curved line geometry in
  a .NET project
og_title: Как создать curved line geometry с Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to create curved line geometry and add curves using Aspose.GIS
    for .NET, enabling precise geospatial data processing.
  headline: How to create curved line geometry with Aspose.GIS
  type: TechArticle
- description: Learn how to create curved line geometry and add curves using Aspose.GIS
    for .NET, enabling precise geospatial data processing.
  name: How to create curved line geometry with Aspose.GIS
  steps:
  - name: define the output path
    text: First, specify where the resulting Shapefile will be saved. Replace the
      placeholder with a valid folder on your machine.
  - name: create a vector layer
    text: '`VectorLayer` represents a spatial layer that holds features and their
      geometries within a GIS dataset. The `using` block ensures the file is closed
      properly after writing.'
  - name: construct the compound curve feature
    text: The `CompoundCurve` class is Aspose.GIS's top‑level object for a geometry
      that consists of multiple connected curve parts. Here we instantiate an empty
      compound curve that will later receive individual components.
  - name: define component curves
    text: 'We prepare five pieces—two straight `LineString`s, two `CircularString`
      arcs, and a final `LineString`. `LineString` represents a simple straight line
      defined by an ordered list of points. `CircularString` is Aspose.GIS’s representation
      of a circular arc defined by three points (start, middle, end) '
  - name: add component curves to the compound curve
    text: Each component is appended in order, preserving continuity and orientation.
      The `Add` method automatically validates that the end point of one segment matches
      the start point of the next.
  - name: assign geometry to the feature
    text: Now the assembled `CompoundCurve` becomes the geometry of the feature we
      will store in the layer.
  - name: add the feature to the layer
    text: Finally, we write the feature into the Shapefile. When the `using` block
      ends, the file is closed and ready for use in any GIS application.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard,
      covering versions from 4.6 up to .NET 7.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. It reads and writes Shapefile, GeoJSON, KML, GML, and more
      than 30 additional formats.
    question: Does Aspose.GIS support reading and writing different geospatial file
      formats?
  - answer: Yes, the library can be used in desktop, web, and cloud services without
      any platform‑specific dependencies.
    question: Is Aspose.GIS suitable for both desktop and web applications?
  - answer: Yes, you can calculate distances, execute geometric operations, and run
      spatial queries directly on the geometries.
    question: Can I perform spatial analysis with Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) to ask
      questions and share ideas with other developers.
    question: Where can I get community help for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- GIS geometry
- Aspose.GIS
- .NET geospatial
- compound curve
title: Как создать curved line geometry с Aspose.GIS
url: /ru/net/geometry-creation/create-compound-curve-geometry/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать геометрию изогнутой линии с помощью Aspose.GIS

## Введение
В этом руководстве вы узнаете **как создать геометрию изогнутой линии** с использованием Aspose.GIS для .NET. Независимо от того, создаёте ли вы интерактивные карты, проводите пространственный анализ или генерируете GIS‑наборы данных, освоение возможности добавлять кривые позволяет моделировать реальные объекты — такие как извилистые дороги или извивающиеся реки — с высокой точностью. Это руководство проведёт вас через каждый шаг, от настройки проекта до экспорта переиспользуемой геометрии составной кривой.

## Быстрые ответы
- **Какова основная цель?** Создать геометрию составной кривой, объединяющую прямые линии и круговые дуги.  
- **Какая библиотека используется?** Aspose.GIS for .NET.  
- **Требования?** Visual Studio, установленный Aspose.GIS и проект C# с целевой платформой .NET 6 или новее.  
- **Типичное время реализации?** Около 10‑15 минут для работающего примера.  
- **Поддерживаемый формат вывода?** Shapefile (тот же код также записывает GeoJSON, KML и другие форматы).

## Что такое составная кривая?
Составная кривая — это единая геометрия, состоящая из нескольких соединённых компонентов кривой — прямых `LineString` и круговых дуг — объединённых в более сложную форму. Она идеальна, когда одна простая линия не может точно представить путь, например, шоссе с плавными изгибами или река, следящая за естественной дугой.

## Почему использовать Aspose.GIS для добавления кривых?
Aspose.GIS предоставляет **богатый API геометрии**, который нативно поддерживает линии, круговые строки и составные кривые, устраняя необходимость во внешних GIS‑библиотеках. Библиотека **кросс‑платформенная**, работает с .NET Framework 4.6+, .NET Core 2.0+, и .NET 5/6/7+. Она **обрабатывает наборы векторных данных до 500 страниц без загрузки всего файла в память**, обеспечивая быстрые и экономные по памяти операции. Экспорт прост: вы можете записывать напрямую в Shapefile, GeoJSON, KML, GML и более чем 30 других форматов.

## Почему это важно
Добавление кривых позволяет более точно моделировать реальные объекты, что улучшает визуальное качество отображения карт и повышает точность пространственного анализа, такого как поиск по близости или маршрутизация в сети. Освоение **как создать геометрию изогнутой линии** тем самым повышает достоверность любого .NET‑решения, основанного на GIS.

## Общие сценарии использования
- **Транспортные сети:** Моделировать шоссе, железные дороги или велосипедные дорожки с плавными изгибами.  
- **Гидрология:** Отображать русла рек, следящие за естественными дугами.  
- **Градостроительство:** Рисовать границы участков, включающие изогнутые участки.  
- **Пользовательские символы:** Создавать декоративные или схематические формы для легенд карт.

## Требования
- Visual Studio (любая современная версия).  
- Aspose.GIS for .NET, загруженный со [страницы загрузки](https://releases.aspose.com/gis/net/).  
- Проект C# с целевой платформой .NET 6 (или любой поддерживаемой версии).

## Импорт пространств имён
Директивы `using` импортируют необходимые типы Aspose.GIS в область видимости.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Пошаговое руководство по созданию геометрии составной кривой

### Шаг 1: определить путь вывода
Сначала укажите, где будет сохранён полученный Shapefile. Замените заполнитель действительной папкой на вашем компьютере.

```csharp
string path = "Your Document Directory" + "CreateCompoundCurve_out.shp";
```

### Шаг 2: создать векторный слой
`VectorLayer` представляет пространственный слой, содержащий объекты и их геометрии в GIS‑наборе данных. Блок `using` гарантирует корректное закрытие файла после записи.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block for creating the compound curve geometry will be inserted here.
}
```

### Шаг 3: построить объект составной кривой
Класс `CompoundCurve` — это объект верхнего уровня Aspose.GIS для геометрии, состоящей из нескольких соединённых частей кривой. Здесь мы создаём пустую составную кривую, которая позже получит отдельные компоненты.

```csharp
var feature = layer.ConstructFeature();
var compoundCurve = new CompoundCurve();
```

### Шаг 4: определить компоненты кривой
Мы готовим пять частей — два прямых `LineString`, две дуги `CircularString` и финальный `LineString`. `LineString` представляет простую прямую линию, определённую упорядоченным списком точек. `CircularString` — это представление Aspose.GIS круговой дуги, определяемой тремя точками (начало, середина, конец), лежащими на одной окружности.

```csharp
var bottom = (ILineString)Geometry.FromText("LineString (0 0, 3 0)");
var firstArc = (ICircularString)Geometry.FromText("CircularString (3 0, 4 1, 3 2)");
var middle = (ILineString)Geometry.FromText("LineString (3 2, 1 2)");
var secondArc = (ICircularString)Geometry.FromText("CircularString (1 2, 0 3, 1 4)");
var top = (ILineString)Geometry.FromText("LineString (1 4, 4 4)");
```

### Шаг 5: добавить компоненты к составной кривой
Каждый компонент добавляется последовательно, сохраняя непрерывность и ориентацию. Метод `Add` автоматически проверяет, что конечная точка одного сегмента совпадает с начальной точкой следующего.

```csharp
compoundCurve.AddCurve(bottom);
compoundCurve.AddCurve(firstArc);
compoundCurve.AddCurve(middle);
compoundCurve.AddCurve(secondArc);
compoundCurve.AddCurve(top);
```

### Шаг 6: назначить геометрию объекту
Теперь собранный `CompoundCurve` становится геометрией объекта, который мы сохраним в слое.

```csharp
feature.Geometry = compoundCurve;
```

### Шаг 7: добавить объект в слой
Наконец, мы записываем объект в Shapefile. Когда блок `using` завершается, файл закрывается и готов к использованию в любом GIS‑приложении.

```csharp
layer.Add(feature);
```

## Распространённые проблемы и советы
- **Порядок координат:** Aspose.GIS ожидает координаты в порядке `X Y` (долгота, широта). Смена порядка приводит к инверсии геометрии.  
- **Синтаксис CircularString:** Средняя точка должна лежать на требуемой дуге; иначе кривая превращается в прямую линию.  
- **Перезапись файла:** `VectorLayer.Create` перезаписывает существующий Shapefile без предупреждения — используйте уникальное имя файла во время разработки.  
- **Производительность:** Для больших наборов данных лучше пакетно добавлять объекты, а не вставлять их по одному внутри блока `using`.  
- **Совет:** Повторно используйте один экземпляр `CompoundCurve` при создании множества похожих объектов; вызовите `compoundCurve.Clear()` перед повторным заполнением, чтобы уменьшить количество выделений.

## Часто задаваемые вопросы

**Q: Могу ли я использовать Aspose.GIS для .NET с другими .NET‑фреймворками?**  
A: Да, Aspose.GIS работает с .NET Framework, .NET Core и .NET Standard, охватывая версии от 4.6 до .NET 7.

**Q: Поддерживает ли Aspose.GIS чтение и запись различных геопространственных форматов файлов?**  
A: Абсолютно. Он читает и записывает Shapefile, GeoJSON, KML, GML и более 30 дополнительных форматов.

**Q: Подходит ли Aspose.GIS как для настольных, так и для веб‑приложений?**  
A: Да, библиотека может использоваться в настольных, веб‑ и облачных сервисах без каких‑либо зависимостей от платформы.

**Q: Могу ли я выполнять пространственный анализ с помощью Aspose.GIS для .NET?**  
A: Да, вы можете вычислять расстояния, выполнять геометрические операции и запускать пространственные запросы непосредственно над геометриями.

**Q: Где я могу получить помощь от сообщества по Aspose.GIS?**  
A: Посетите [форум Aspose.GIS](https://forum.aspose.com/c/gis/33), чтобы задавать вопросы и делиться идеями с другими разработчиками.

**Последнее обновление:** 2026-08-24  
**Тестировано с:** Aspose.GIS for .NET (latest stable release)  
**Автор:** Aspose

## Связанные руководства

- [Создать векторный слой и круговую строку в Aspose.GIS для .NET](/gis/net/geometry-creation/create-circular-string-geometry/)
- [Создать векторный слой и полигон с кривой в Aspose.GIS](/gis/net/geometry-creation/create-curve-polygon-geometry/)
- [Преобразовать WKT в геометрию: MultiCurve с Aspose.GIS .NET](/gis/net/geometry-creation/create-multicurve-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}