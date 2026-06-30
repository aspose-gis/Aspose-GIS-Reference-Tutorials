---
date: 2026-06-30
description: Узнайте, как создать векторный слой в File Geodatabase с помощью Aspose.GIS
  для .NET. Управляйте геопространственными данными с пространственной привязкой WGS84
  и параметрами file gdb.
keywords:
- create vector layer
- add line feature
- manage geospatial data
- feature count example
- file gdb compression
linktitle: Создать File GDB с одним слоем
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  headline: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  type: TechArticle
- description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  name: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  steps:
  - name: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
    text: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
  - name: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
    text: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
  type: HowTo
- questions:
  - answer: It means adding a new vector dataset (points, lines, or polygons) to a
      geodatabase file.
    question: What does “create vector layer” mean?
  - answer: Aspose.GIS for .NET provides full support for File GDB creation and editing.
    question: Which library should I use?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `SpatialReferenceSystem.Wgs84` for the common WGS84 datum.
    question: Can I set the spatial reference?
  - answer: Less than 30 lines to create the GDB, add a line feature, and read back
      the feature count.
    question: How many lines of code?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Создание векторного слоя в File GDB – учебник Aspose.GIS .NET
url: /ru/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать векторный слой в файловой GDB

## Введение
Если вам нужно **create vector layer** внутри файловой геодатабазы (GDB) и эффективно управлять геопространственными данными, Aspose.GIS for .NET предоставляет чистый, code‑first подход. В этом пошаговом руководстве мы покажем, как записать линейный объект, настроить параметры файловой GDB и работать с пространственной привязкой WGS84 — всё это в нескольких строках C#. К концу вы сможете подсчитать объекты в слое и интегрировать полученную GDB в любой .NET рабочий процесс картографии или анализа.

## Быстрые ответы
- **Что означает “create vector layer”?** Это добавление нового векторного набора данных (точек, линий или полигонов) в файл геодатабазы.  
- **Какую библиотеку следует использовать?** Aspose.GIS for .NET предоставляет полную поддержку создания и редактирования File GDB.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; коммерческая лицензия требуется для продакшна.  
- **Можно ли задать пространственную привязку?** Да — используйте `SpatialReferenceSystem.Wgs84` для общепринятой системы WGS84.  
- **Сколько строк кода?** Менее 30 строк для создания GDB, добавления линейного объекта и чтения количества объектов.

## Что такое операция “create vector layer”?
Создание векторного слоя определяет новую таблицу в геодатабазе, которая хранит геометрические объекты (точки, линии, полигоны) и их атрибуты. Каждая строка представляет объект, а столбец геометрии содержит его форму. В Aspose.GIS вы создаёте его, создавая экземпляр `FeatureClass` внутри `FileGdbDataSource` и указывая тип геометрии.

## Почему использовать Aspose.GIS для создания векторного слоя?
Aspose.GIS устраняет внешние зависимости и поддерживает **50+** форматов GIS, делая его универсальным решением для .NET разработчиков.  
Он предоставляет встроенное сжатие файловой GDB (до 70 % уменьшения для типичных векторных данных), пространственное индексирование и полную поддержку WGS84 «из коробки». Библиотека работает на .NET Framework 4.6+, .NET Core 2.0+, и .NET 5/6, поэтому вы можете нацеливаться на любую современную Windows‑ или кроссплатформенную среду без дополнительных нативных библиотек.

## Предварительные требования
1. **Aspose.GIS for .NET** – скачайте его со страницы [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).  
2. **A .NET development environment** – Visual Studio, Rider или `dotnet` CLI.  
3. **A folder** где будет создана файловая GDB (мы назовём её *Your Document Directory*).

## Импорт пространств имён
Операторы `using` импортируют необходимые типы в область видимости.  

Пространство имён `Document` предоставляет основные GIS‑объекты, а `System.IO` работает с путями к файлам.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```

## Шаг 1: Настройте ваш каталог документов
Замените `"Your Document Directory"` абсолютным путём, где вы хотите разместить файловую GDB.  
Создание каталога заранее предотвращает ошибку «File not found», которая часто встречается у новых пользователей.

```csharp
string dataDir = "Your Document Directory";
```

## Шаг 2: Создайте файловую геодатабазу с одним слоем
FileGdbOptions — класс, позволяющий настроить сжатие, пространственное индексирование и другие параметры файловой геодатабазы.  
Этот фрагмент **creates a vector layer** с помощью `FileGdbOptions`, записывает простой линейный объект и сохраняет его в файловой GDB, использующей **spatial reference WGS84**.

```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```

## Шаг 3: Откройте файловую геодатабазу и получите информацию о слое
`FileGdbDataSource` — точка входа для создания и открытия файловых геодатабаз.  
`FeatureClass` представляет векторный слой внутри геодатабазы и предоставляет доступ к его объектам.  
Здесь мы **count features in the layer** открывая набор данных и выводя количество объектов — в данном случае `1`.

```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```

## Как проверить, что слой был создан корректно?
Откройте геодатабазу с помощью `FileGdbDataSource.Open` и запросите `FeatureClass`. Свойство `Count` возвращает общее количество объектов, подтверждая, что линия была сохранена. Этот быстрый шаг проверки помогает обнаружить проблемы на раннем этапе, особенно при автоматизации массовых импортов.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|----------|----------|
| **`File not found`** | Неправильная переменная `path` | Убедитесь, что `dataDir` указывает на существующий каталог и что `path` объединяется с именем файла, например, `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | Используется тип геометрии, не поддерживаемый в File GDB | Используйте `Point`, `LineString` или `Polygon` для базовых слоёв. |
| **`License not set`** | Запуск без действующей лицензии в продакшене | Зарегистрируйте лицензию с помощью `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Часто задаваемые вопросы
### Могу ли я использовать Aspose.GIS for .NET в своих существующих .NET проектах?
Да, Aspose.GIS for .NET может быть бесшовно интегрирован в ваши существующие .NET проекты.

### Доступна ли пробная версия Aspose.GIS for .NET?
Да, вы можете ознакомиться с возможностями Aspose.GIS for .NET, скачав [бесплатную пробную версию](https://releases.aspose.com/).

### Где я могу найти подробную документацию по Aspose.GIS for .NET?
Обратитесь к [документации](https://reference.aspose.com/gis/net/) для получения полной информации о Aspose.GIS for .NET.

### Как я могу получить поддержку по Aspose.GIS for .NET?
Посетите [форум Aspose.GIS](https://forum.aspose.com/c/gis/33) для получения поддержки от сообщества и помощи.

### Доступны ли временные лицензии для Aspose.GIS for .NET?
Да, вы можете получить [временную лицензию](https://purchase.aspose.com/temporary-license/) для Aspose.GIS for .NET.

---

**Последнее обновление:** 2026-06-30  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Создать набор данных файловой геодатабазы .NET с Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Создать векторный слой и задать систему пространственной привязки слоя](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Как удалить слой из набора данных файловой GDB с Aspose.GIS](/gis/net/layer-data-operations/remove-layers-from-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}