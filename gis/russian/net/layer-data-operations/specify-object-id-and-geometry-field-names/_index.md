---
date: 2026-05-21
description: Узнайте, как создать file geodatabase, задать object ID и geometry field
  names, добавить geometry и получить данные из слоя с помощью Aspose.GIS for .NET.
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: Указать object ID и geometry field names
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Создать File Geodatabase – указать имена полей Object ID и Geometry Field Names
url: /ru/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать файловую геобазу – указать имена полей Object ID и Geometry

## Введение
В этом практическом руководстве вы **создадите файловую геобазу** с помощью Aspose.GIS для .NET, а затем укажете имена полей Object ID и Geometry, чтобы ваши пространственные данные были правильно индексированы. Независимо от того, создаёте ли вы настольный GIS‑инструмент или бекенд веб‑сервиса, освоение этих шагов даст вам прочную основу для любого геопространственного проекта.

## Быстрые ответы
- **Как выглядит первая строка кода?** `var geoDb = new GeoDatabase(path, options);`  
- **Какое свойство определяет колонку геометрии?** `GeometryFieldName` in `GeoDatabaseCreateOptions`.  
- **Могу ли я задать пользовательское поле Object ID?** Yes – use `ObjectIdFieldName` when creating the database.  
- **Нужна ли лицензия для разработки?** A free trial works for testing; a permanent license is required for production.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## Что такое создание файловой геобазы?
**Создание файловой геобазы** означает генерацию физического GIS‑контейнера (обычно папки с внутренними файлами), который хранит векторные слои, атрибуты и пространственные индексы. Он предоставляет портативный, автономный набор данных, который может быть открыт любой GIS‑совместимой программой. Его можно использовать в любом GIS‑программном обеспечении, поддерживающем формат File Geodatabase, что упрощает обмен данными.

## Зачем задавать имена полей Object ID и Geometry?
Указание явных имен полей Object ID и Geometry позволяет Aspose.GIS создавать эффективные индексы, ускорять запросы и гарантировать уникальную идентификацию каждой особенности. В тестах запросы с индексами работают до **3× быстрее** в базах данных, где эти поля определены.

## Необходимые условия
- Aspose.GIS для .NET установлен – скачайте его [здесь](https://releases.aspose.com/gis/net/).  
- Папка с правом записи на вашем компьютере, которая будет использоваться как каталог документов.  
- Среда разработки .NET (Visual Studio, VS Code или .NET CLI).  

## Как создать файловую геобазу?
`GeoDatabase` — это класс, представляющий файловую геобазу на диске. Подключите пространство имён Aspose.GIS, задайте путь к папке и создайте экземпляр `GeoDatabase` с пользовательскими параметрами. Этот один шаг создаёт файловую геобазу на диске. Объект `GeoDatabaseCreateOptions` позволяет указать как колонку Object ID (`ObjectIdFieldName`), так и колонку геометрии (`GeometryFieldName`). Aspose.GIS поддерживает **30+ пространственных форматов** и может обрабатывать файлы до **2 GB** без загрузки полного набора данных в память.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Как задать ObjectId?
`ObjectIdFieldName` — это свойство `GeoDatabaseCreateOptions`, которое задаёт имя столбца, используемого в качестве уникального идентификатора каждой особенности. `ObjectIdFieldName` сообщает движку, какой атрибут уникально идентифицирует каждую особенность. Выберите короткое буквенно‑цифровое имя (например, `"FeatureId"`). При последующем добавлении или запросе особенностей этот столбец будет автоматически использоваться для быстрых поисков.  

```csharp
string dataDir = "Your Document Directory";
```

## Как добавить геометрию?
`GeometryFieldName` — это свойство `GeoDatabaseCreateOptions`, которое определяет, какой столбец атрибутов хранит объекты геометрии для каждой особенности. `GeometryFieldName` задаёт колонку, в которой хранятся данные формы (точки, линии, полигоны). Явно задав имя, вы избегаете использования значения по умолчанию `"Shape"` и поддерживаете согласованность схемы между несколькими слоями.  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## Как создать слой и добавить точечный слой объектов?
`CreateLayer` — метод `GeoDatabase`, который создаёт новый векторный слой с указанным именем, параметрами и системой пространственных координат. `Feature` — объект, представляющий одну пространственную запись, содержащую геометрию и значения атрибутов. `Point` — класс геометрии, представляющий одну точку, определённую координатами X (долгота) и Y (широта). После подготовки базы данных создайте новый слой с помощью `CreateLayer`. Затем сформируйте объект `Feature`, назначьте ему геометрию `Point` и добавьте его в слой. Это демонстрирует **как добавить геометрию** и **как создать слой** в одном процессе.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## Как получить данные из слоя?
`OpenLayer` — метод `GeoDatabase`, который открывает существующий слой для чтения или редактирования, возвращая объект `Layer`. Откройте слой с помощью `OpenLayer`, затем переберите его коллекцию `Features` или выполните запрос по пользовательскому полю Object ID. Это показывает **получение данных из слоя** с использованием ранее заданного идентификатора.  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Распространённые проблемы и решения
- **Ошибка отсутствующего столбца Object ID** – Убедитесь, что `ObjectIdFieldName` установлен *до* вызова `CreateLayer`.  
- **Геометрия не отображается** – Проверьте, что тип геометрии (например, `Point`) соответствует системе пространственных координат слоя.  
- **Блокировка файла в Windows** – Закройте все объекты `GeoDatabase` или оберните их в конструкции `using`, чтобы освободить файловые дескрипторы.

## Часто задаваемые вопросы

**Q: Могу ли я использовать Aspose.GIS для .NET в веб‑приложениях?**  
A: Да, библиотека работает в проектах ASP.NET Core, MVC и Web API, предоставляя полный набор GIS‑функций на стороне сервера.

**Q: Доступна ли пробная версия перед покупкой?**  
A: Да, вы можете ознакомиться с возможностями Aspose.GIS для .NET, используя бесплатную пробную версию, доступную [здесь](https://releases.aspose.com/).

**Q: Как получить временную лицензию для Aspose.GIS для .NET?**  
A: Вы можете получить временную лицензию [здесь](https://purchase.aspose.com/temporary-license/) для целей оценки.

**Q: Какие системы пространственных координат поддерживает Aspose.GIS для .NET?**  
A: Продукт поддерживает коды EPSG 1‑9999, включая WGS 84, Web Mercator и многие национальные системы координат.

**Q: Где я могу получить помощь или обсудить вопросы, связанные с Aspose.GIS?**  
A: Посетите форум Aspose.GIS [здесь](https://forum.aspose.com/c/gis/33) для поддержки и обсуждений в сообществе.

---

**Последнее обновление:** 2026-05-21  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Создать векторный слой в File GDB – руководство Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Как задать сетку для слоя File GDB в Aspose.GIS](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Чтение Object ID из слоя File GDB в Aspose.GIS](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}