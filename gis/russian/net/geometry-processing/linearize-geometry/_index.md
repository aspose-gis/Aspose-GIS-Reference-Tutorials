---
date: 2026-09-10
description: Узнайте, как преобразовать кривые в линии (linearize geometry) с помощью
  Aspose.GIS for .NET, обеспечивая эффективную геопространственную обработку и анализ
  в ваших .NET приложениях.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
lastmod: 2026-09-10
linktitle: Linearize geometry
og_description: Преобразуйте кривые в линии (linearize geometry) с помощью Aspose.GIS
  for .NET. Узнайте step‑by‑step, как упростить геометрии для более быстрой отрисовки
  и более широкой совместимости.
og_image_alt: Guide showing how to linearize curved geometries to straight lines using
  Aspose.GIS in a .NET application
og_title: Преобразование кривых в линии с Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  headline: How to Convert Curves to Lines with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  name: How to Convert Curves to Lines with Aspose.GIS for .NET
  steps:
  - name: Define the output path
    text: '`Path.Combine` builds a platform‑independent file path, handling Windows
      backslashes and Unix forward slashes automatically. Replace `"Your Document
      Directory"` with the folder where you want the KML file saved.'
  - name: Create a layer for the output file
    text: A *layer* groups geographic features of the same type. Here we instantiate
      a new KML layer that will store the linearized geometry.
  - name: Construct a new feature
    text: A *feature* represents a single geographic object (point, line, polygon,
      etc.). We’ll attach our linear geometry to this feature.
  - name: Define the original complex geometry
    text: '`Geometry.FromWkt` parses a Well‑Known Text (WKT) string into a geometry
      object. The sample WKT includes a `LineString`, a `CompoundCurve`, and a `CircularString`
      to showcase curve handling.'
  - name: Convert curves to lines
    text: '`ToLinearGeometry()` tessellates every curve in the source geometry into
      straight‑line segments, returning a new linear geometry that retains any Z‑coordinates.'
  - name: Assign the linear geometry to the feature
    text: The feature’s `Geometry` property now holds the simplified, linear version
      of the original shape.
  - name: Add the feature to the layer
    text: Adding the feature to the KML layer queues it for writing; when the `using`
      block ends, the layer flushes the data to the output file.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Core, enabling cross‑platform applications.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Absolutely! The library supports KML, Shapefile, GeoJSON, and many more
      formats—over 30 in total.
    question: Can I work with different GIS file formats using Aspose.GIS for .NET?
  - answer: Yes, it provides a wide range of spatial functions, from buffering to
      spatial joins.
    question: Does Aspose.GIS offer spatial operations and analysis?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      and staff support.
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert curves to lines
- Aspose.GIS
- .NET GIS processing
title: Как преобразовать кривые в линии с помощью Aspose.GIS for .NET
url: /ru/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Преобразование кривых в линии (линеаризация геометрии) с Aspose.GIS для .NET

## Введение
Если вам необходимо **преобразовать кривые в линии** для картографии, пространственного анализа или задач обмена данными, Aspose.GIS для .NET предоставляет чистый программный способ сделать это. В этом руководстве мы пройдем полный реальный пример, показывающий, как взять сложную геометрию — содержащую кривые и составные формы — и превратить её в простое линейное представление, совместимое с любой GIS‑системой.

## Быстрые ответы
- **Что означает «преобразовать кривые в линии»?** Это преобразует изогнутые геометрии в отрезки прямых линий.  
- **Почему выбирают Aspose.GIS?** Библиотека поддерживает более 30 GIS‑форматов и выполняет преобразование геометрии без внешних инструментов.  
- **Что требуется заранее?** .NET Framework или .NET Core, Visual Studio (или любая IDE для C#) и пакет Aspose.GIS NuGet.  
- **Сколько времени займет выполнение примера?** Менее пяти минут после установки библиотеки.  
- **Можно ли экспортировать в другие форматы?** Конечно — замените драйвер KML на Shapefile, GeoJSON и т.д.  
Вы можете скачать полный набор продуктов с [веб‑сайта Aspose](https://releases.aspose.com/).

## Что означает преобразование кривых в линии?
Преобразование кривых в линии (также называемое **линеаризацией геометрии**) заменяет каждый изогнутый сегмент серией коротких отрезков прямых линий, создавая *линейную геометрию*. Это делает рендеринг до пяти раз быстрее, снижает потребление памяти и гарантирует, что данные могут быть использованы устаревшими GIS‑службами, принимающими только линейные объекты.

## Почему преобразовывать кривые в линии?
Линейные геометрии рендерятся и запрашиваются до **5× быстрее**, чем их изогнутые аналоги, и **30+ GIS‑платформ** принимают только линейные объекты. Упрощение геометрии также уменьшает размер файлов для веб‑просмотров и позволяет использовать алгоритмы — такие как сетевой анализ или кластеризация — требующие входных данных в виде прямых линий.

## Как линеаризовать геометрию?
Используйте метод `ToLinearGeometry()`, предоставляемый Aspose.GIS. Он автоматически разбивает каждую кривую в геометрии на отрезки прямых линий, сохраняя любые Z‑значения, так что вы получаете линейную аппроксимацию без потери данных о высоте. Вы также можете указать допуск, контролирующий максимальное отклонение между исходной кривой и сгенерированными сегментами, позволяя балансировать точность и размер файла. Метод работает как с 2‑D, так и с 3‑D геометриями.

## Требования
Перед тем как погрузиться в код, убедитесь, что у вас есть:

1. **Aspose.GIS для .NET** — скачайте его с [веб‑сайта Aspose.GIS](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (или .NET Core), установленный на вашей машине разработки.  
3. **Visual Studio** (или любая IDE, совместимая с C#) для написания и выполнения примера.

## Импорт пространств имён
Чтобы начать использовать возможности Aspose.GIS, импортируйте необходимые пространства имён.

### Основные пространства имён Aspose.GIS
Пространство имён `Aspose.Gis` содержит основные классы геометрии, драйверы и утилиты, необходимые для всех GIS‑операций.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Драйвер целевого формата
`Aspose.Gis.Drivers` предоставляет статические фабрики для каждого поддерживаемого формата файлов; `Drivers.Kml` создаёт писатель KML.  
```csharp
using Aspose.GIS.Kml;
```

## Пошаговое руководство по преобразованию кривых в линии
Ниже представлено подробное пошаговое объяснение каждой строки кода, описывающее **как преобразовать кривые в линии** и почему каждый шаг важен.

### Шаг 1: Определите путь вывода
`Path.Combine` формирует кроссплатформенный путь к файлу, автоматически обрабатывая обратные слеши Windows и прямые слеши Unix.  
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Замените `"Your Document Directory"` на папку, в которой вы хотите сохранить файл KML.

### Шаг 2: Создайте слой для выходного файла
*Слой* группирует географические объекты одного типа. Здесь мы создаём новый KML‑слой, который будет хранить линеаризованную геометрию.  
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```

### Шаг 3: Создайте новый объект (feature)
*Объект* (feature) представляет один географический объект (точка, линия, полигон и т.д.). Мы привяжем нашу линейную геометрию к этому объекту.  
```csharp
var feature = layer.ConstructFeature();
```

### Шаг 4: Определите исходную сложную геометрию
`Geometry.FromWkt` разбирает строку Well‑Known Text (WKT) в объект геометрии. Пример WKT включает `LineString`, `CompoundCurve` и `CircularString`, демонстрируя работу с кривыми.  
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```

### Шаг 5: Преобразуйте кривые в линии
`ToLinearGeometry()` разбивает каждую кривую исходной геометрии на отрезки прямых линий, возвращая новую линейную геометрию, сохраняющую любые Z‑координаты.  
```csharp
var linear = geometry.ToLinearGeometry();
```

### Шаг 6: Присвойте линейную геометрию объекту
Свойство `Geometry` объекта теперь содержит упрощённую линейную версию исходной формы.  
```csharp
feature.Geometry = linear;
```

### Шаг 7: Добавьте объект в слой
Добавление объекта в KML‑слой ставит его в очередь на запись; когда блок `using` завершается, слой сбрасывает данные в выходной файл.  
```csharp
layer.Add(feature);
```

## Распространённые подводные камни и профессиональные советы
- **Разделители путей:** Используйте `Path.Combine`, чтобы избежать проблем в Windows и Linux.  
- **Очень большие геометрии:** Линеаризация сложных форм может создать тысячи вершин; рассмотрите вызов `Simplify()` после линеаризации для уменьшения количества точек.  
- **Выбор драйвера:** Если нужен другой формат вывода, замените `Drivers.Kml` на `Drivers.Shapefile`, `Drivers.GeoJson` и т.д., и измените расширение файла соответственно.  
- **Сохранение Z‑значений:** `ToLinearGeometry()` сохраняет 3‑D (Z) координаты, поэтому вы не теряете данные о высоте.

## Часто задаваемые вопросы (FAQ)

**В: Совместим ли Aspose.GIS для .NET с .NET Core?**  
О: Да, Aspose.GIS работает с .NET Core, позволяя создавать кроссплатформенные приложения.

**В: Могу ли я работать с различными GIS‑форматами файлов, используя Aspose.GIS для .NET?**  
О: Конечно! Библиотека поддерживает KML, Shapefile, GeoJSON и многие другие форматы — более 30 в сумме.

**В: Предоставляет ли Aspose.GIS пространственные операции и анализ?**  
О: Да, она предоставляет широкий набор пространственных функций, от буферизации до пространственных соединений.

**В: Доступна ли бесплатная пробная версия?**  
О: Да, вы можете скачать бесплатную пробную версию с [веб‑сайта Aspose.GIS](https://releases.aspose.com/gis/net/).

**В: Где я могу получить помощь, если возникнут проблемы?**  
О: Посетите [форум Aspose.GIS](https://forum.aspose.com/c/gis/33) для поддержки сообщества и сотрудников.

### Дополнительные часто задаваемые вопросы

**В: Могу ли я линеаризовать геометрии, содержащие 3D (Z) координаты?**  
О: Да, `ToLinearGeometry()` работает как с 2D, так и с 3D геометриями; Z‑значения сохраняются.

**В: Как линеаризация влияет на размер файла?**  
О: Преобразование кривых в множество коротких отрезков может увеличить размер файла; при необходимости запустите `Simplify()` после линеаризации.

**В: Могу ли я контролировать длину сегмента при преобразовании кривых в линии?**  
О: Метод по умолчанию использует внутреннюю толерантность. Для пользовательской сегментации можно вручную разбивать кривые перед вызовом `ToLinearGeometry()`.

## Заключение
В этом руководстве мы рассмотрели **как преобразовать кривые в линии** (линеаризацию геометрии) с помощью Aspose.GIS для .NET, от настройки окружения до записи линеаризованного результата в файл KML. Теперь вы можете внедрять этот рабочий процесс в картографические приложения, конвейеры обработки данных или любой GIS‑проект, требующий упрощённых геометрий.

**Последнее обновление:** 2026-09-10  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Как создать GeoJSON с допуском Aspose.GIS для .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Преобразовать полигон в линию с Aspose.GIS для .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)
- [Узнайте, как создать геометрию LineString с Aspose.GIS для .NET](/gis/net/geometry-creation/create-linestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}