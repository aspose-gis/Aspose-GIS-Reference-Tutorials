---
date: 2026-01-10
description: Узнайте, как создать векторный слой в файловой геобазе данных с помощью
  Aspose.GIS для .NET. Управляйте геопространственными данными с пространственной
  привязкой WGS84 и параметрами файловой GDB.
linktitle: Create File GDB with Single Layer
second_title: Aspose.GIS .NET API
title: Создание векторного слоя в файловой базе GDB – учебник Aspose.GIS .NET
url: /ru/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание векторного слоя в File GDB

## Введение
Если вам нужно **создать векторный слой** внутри файловой геодatabase (GDB) и эффективно управлять геопространственными данными, Aspose.GIS for .NET предоставляет чистый, code‑first подход. В этом пошаговом руководстве мы покажем, как записать линейный объект, настроить параметры File GDB и работать с пространственной привязкой WGS84 — всё в нескольких строках C#. К концу вы сможете подсчитать объекты в слое и интегрировать полученный GDB в любой .NET‑workflow по картографированию или анализу.

## Быстрые ответы
- **Что означает «создать векторный слой»?** Это добавление нового векторного набора данных (точки, линии или полигоны) в файл геодatabase.  
- **Какую библиотеку использовать?** Aspose.GIS for .NET полностью поддерживает создание и редактирование File GDB.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; для продакшна требуется коммерческая лицензия.  
- **Можно ли задать пространственную привязку?** Да — используйте `SpatialReferenceSystem.Wgs84` для общепринятой системы WGS84.  
- **Сколько строк кода?** Менее 30 строк для создания GDB, добавления линейного объекта и чтения количества объектов.

## Что такое операция «создать векторный слой»?
Создание векторного слоя означает определение новой таблицы внутри геодatabase, которая хранит геометрические объекты (точки, линии, полигоны) вместе с их атрибутами. Эта операция является основой любой GIS‑приложения, которому необходимо **управлять геопространственными данными**.

## Почему стоит использовать Aspose.GIS для создания векторного слоя?
- **Никаких внешних зависимостей** — API работает сразу же на .NET Framework, .NET Core и .NET 5/6.  
- **Полная поддержка File GDB** — вы можете настроить `FileGdbOptions` для управления сжатием, пространственным индексированием и др.  
- **Встроенная работа с пространственными привязками** — просто передайте `SpatialReferenceSystem.Wgs84`, чтобы работать в глобальной системе координат.  
- **Простой API** — записывайте линейный объект, добавляйте его в слой и получайте количество объектов всего несколькими вызовами методов.

## Предварительные требования
Прежде чем начать, убедитесь, что у вас есть:

1. **Aspose.GIS for .NET** — скачайте её со [страницы загрузки Aspose.GIS for .NET](https://releases.aspose.com/gis/net/).  
2. **Среда разработки .NET** — Visual Studio, Rider или `dotnet` CLI.  
3. **Папка**, в которой будет создан File GDB (мы назовём её *Your Document Directory*).

## Импорт пространств имён
Добавьте необходимые `using`‑директивы в начало вашего C#‑файла:

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

## Шаг 1: Настройка каталога документа
```csharp
string dataDir = "Your Document Directory";
```
Замените `"Your Document Directory"` на абсолютный путь к папке, где вы хотите разместить File GDB.

## Шаг 2: Создание файловой геодatabase с одним слоем
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
Этот фрагмент **создаёт векторный слой** с помощью `FileGdbOptions`, записывает простой линейный объект и сохраняет его в File GDB, использующем **пространственную привязку WGS84**.

## Шаг 3: Открытие файловой геодatabase и получение информации о слое
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```
Здесь мы **подсчитываем объекты слоя**, открывая набор данных и выводя количество объектов — в данном случае `1`.

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|----------|----------|----------|
| **`File not found`** | Неправильная переменная `path` | Убедитесь, что `dataDir` указывает на существующую папку, а `path` формируется, например, `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | Используется тип геометрии, не поддерживаемый в File GDB | Оставайтесь в пределах `Point`, `LineString` или `Polygon` для базовых слоёв. |
| **`License not set`** | Запуск без действующей лицензии в продакшне | Зарегистрируйте лицензию: `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Часто задаваемые вопросы
### Могу ли я использовать Aspose.GIS for .NET в существующих проектах .NET?
Да, Aspose.GIS for .NET легко интегрируется в ваши текущие .NET‑проекты.

### Доступна ли пробная версия Aspose.GIS for .NET?
Да, вы можете изучить возможности Aspose.GIS for .NET, скачав [бесплатную пробную версию](https://releases.aspose.com/).

### Где найти подробную документацию по Aspose.GIS for .NET?
Обратитесь к [документации](https://reference.aspose.com/gis/net/) для получения полной информации о Aspose.GIS for .NET.

### Как получить поддержку по Aspose.GIS for .NET?
Посетите [форум Aspose.GIS](https://forum.aspose.com/c/gis/33) для получения помощи от сообщества.

### Есть ли временные лицензии для Aspose.GIS for .NET?
Да, вы можете оформить [временную лицензию](https://purchase.aspose.com/temporary-license/) для Aspose.GIS for .NET.

---

**Последнее обновление:** 2026-01-10  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}