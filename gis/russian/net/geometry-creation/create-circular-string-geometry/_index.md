---
date: 2026-02-15
description: Узнайте, как создать векторный слой и добавить геометрию типа CircularString
  с помощью Aspose.GIS для .NET — быстрый способ создания GIS‑приложений.
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: Создать векторный слой и круговую строку в Aspose.GIS для .NET
url: /ru/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание Vector Layer и Circular String Geometry с Aspose.GIS для .NET

## Введение
Если вы разрабатываете GIS‑приложение на платформе .NET, первым шагом часто является **создание vector layer** объектов, которые хранят ваши пространственные объекты. Aspose.GIS для .NET упрощает этот процесс и позволяет обогащать такие слои продвинутыми геометриями, например circular strings. В этом руководстве вы узнаете, как **создать vector layer**, **добавить circular string** геометрию и сохранить результат в виде Shapefile — всё с чистым, готовым к продакшену C# кодом.

## Быстрые ответы
- **Что означает “create vector layer”?** Он создает новый контейнер (слой), который может хранить пространственные объекты, такие как точки, линии или полигоны.  
- **Какой класс представляет circular string?** `CircularString` из `Aspose.Gis.Geometries`.  
- **Можно ли сохранить слой как Shapefile?** Да — используйте `Drivers.Shapefile` при создании слоя.  
- **Нужна ли лицензия для разработки?** Временная лицензия подходит для оценки; полная лицензия требуется для продакшена.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Что такое “create vector layer”?
Vector layer — это логическая группировка векторных объектов (точек, линий, полигонов), хранящихся в едином источнике данных. В Aspose.GIS вы создаёте слой, вызывая `VectorLayer.Create`, передавая путь к целевому файлу и нужный драйвер (например, Shapefile). После создания слоя вы можете добавлять объекты, назначать геометрии и выполнять пространственные операции.

## Зачем добавлять circular string?
Circular strings — это тип **linear geometry**, который аппроксимирует дуги последовательностью точек. Они полезны для представления изогнутых дорог, изгибов рек или любых объектов, где требуется плавная кривая без использования множества мелких отрезков.

## Требования
- **.NET Framework или .NET Core**, установленный на вашем компьютере.  
- **Aspose.GIS for .NET** библиотека — скачайте её с официального сайта **[здесь](https://releases.aspose.com/gis/net/)**.  
- IDE, например **Visual Studio** или **JetBrains Rider**.  
- Базовые знания программирования на **C#**.

## Импорт пространств имён
Add the required namespaces to your C# file:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Пошаговое руководство

### Шаг 1: Определите путь к выходному файлу
Укажите место, куда будет записан Shapefile.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

Замените `"Your Document Directory"` на фактический путь к папке в вашей системе.

### Шаг 2: **Create vector layer**
Откройте `VectorLayer`, используя метод `Create`. Это ядро операции **create vector layer**.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### Шаг 3: Создайте новый feature
Feature представляет одну пространственную запись внутри слоя.

```csharp
    var feature = layer.ConstructFeature();
```

### Шаг 4: Постройте геометрию circular string
Добавьте точки, определяющие изогнутую форму. Последовательность точек создаёт дугу, которая начинается и заканчивается в одной и той же точке, образуя закрытый circular string.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### Шаг 5: Присвойте геометрию и добавьте feature в слой
Свяжите геометрию с feature и сохраните её в слое.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

Когда блок `using` завершается, слой автоматически сохраняется в Shapefile на диске.

## Распространённые проблемы и решения
| Проблема | Решение |
|----------|---------|
| **Недопустимый путь к файлу** | Убедитесь, что каталог существует и у вас есть права на запись. |
| **CircularString отображается как прямая линия** | Проверьте, что точки добавлены в правильном порядке; первая и последняя точки должны совпадать для замкнутой формы. |
| **Исключение лицензии** | Примените временную лицензию во время разработки или приобретите полную лицензию для продакшн‑использования. |

## Часто задаваемые вопросы

### Совместим ли Aspose.GIS для .NET со всеми версиями .NET Framework?
Да, Aspose.GIS для .NET разработан для работы с широким диапазоном версий .NET, от Framework 4.5 до последних выпусков .NET 8.

### Могу ли я интегрировать Aspose.GIS для .NET с другими GIS‑библиотеками?
Абсолютно! Вы можете читать данные другими библиотеками, обрабатывать их с помощью Aspose.GIS, а затем записывать обратно, благодаря гибкому API.

### Поддерживает ли Aspose.GIS для .NET визуализацию пространственных данных?
Да, библиотека включает утилиты рендеринга, позволяющие генерировать карты и визуальные представления ваших геометрий.

### Есть ли сообщественный форум, где я могу получить помощь по Aspose.GIS для .NET?
Да, вы можете посетить форум Aspose.GIS **[здесь](https://forum.aspose.com/c/gis/33)**, чтобы задать вопросы и поделиться опытом.

### Можно ли получить временную лицензию для оценки Aspose.GIS для .NET?
Конечно! Временная оценочная лицензия доступна **[здесь](https://purchase.aspose.com/temporary-license/)**.

### Как добавить более сложные геометрии (например, MultiLineString) в тот же слой?
Создайте соответствующий объект геометрии (например, `MultiLineString`), заполните его отдельными объектами `LineString`, присвойте его `feature.Geometry` и добавьте feature так же, как мы делали с circular string.

## FAQ (Быстрый справочник)

**В:** Как программно **create vector layer**?  
**О:** Вызовите `VectorLayer.Create(path, Drivers.Shapefile)` (или другой драйвер) внутри блока `using`.

**В:** Какой метод добавляет точки в circular string?  
**О:** Используйте `circularString.AddPoint(x, y)` для каждой координаты.

**В:** Можно ли хранить несколько геометрий в одном слое?  
**О:** Да, создайте новый feature для каждой геометрии и добавьте его с помощью `layer.Add(feature)`.

**В:** Что делать, если Shapefile не создаётся?  
**О:** Убедитесь, что выходной каталог существует, у вас есть права на запись, и драйвер (`Drivers.Shapefile`) правильно указан.

**В:** Требуется ли лицензия для сборки оценки?  
**О:** Временная лицензия достаточна для разработки и тестирования; полная лицензия нужна для продакшн‑развёртываний.

## Заключение
Следуя этим шагам, вы теперь знаете, как **create vector layer** объекты и обогащать их геометрией **circular string** с помощью Aspose.GIS для .NET. Эта база позволяет создавать более продвинутые GIS‑решения — будь то картирование транспортных сетей, визуализация экологических данных или разработка пользовательских инструментов пространственного анализа.

---

**Последнее обновление:** 2026-02-15  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}