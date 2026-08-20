---
date: 2026-06-30
description: Узнайте, как добавить слой в набор данных File GDB с использованием Aspose.GIS
  и пространственной привязкой WGS84. Следуйте этому пошаговому руководству, чтобы
  добавить слой в .NET.
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: Добавить слой в набор данных File GDB
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Как добавить слой в набор данных File GDB с пространственной привязкой WGS84,
  используя Aspose.GIS
url: /ru/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# как добавить слой – spatial reference wgs84 с Aspose.GIS

## Введение
Готовы улучшить ваш GIS‑рабочий процесс с Aspose.GIS для .NET? В этом руководстве вы узнаете **как добавить слой** в набор данных File GDB, работая с **spatial reference WGS84** координатной системой. Мы пройдём каждый шаг, от подготовки папки с данными до проверки только что созданного слоя, чтобы вы могли уверенно и эффективно работать с географическими данными.

## Быстрые ответы
- **Какова основная используемая система координат?** spatial reference wgs84 (WGS 84)  
- **Какая библиотека предоставляет API?** Aspose.GIS for .NET  
- **Нужна ли лицензия для тестирования?** Да — доступна временная лицензия Aspose.  
- **Могу ли я добавить атрибуты к новому слою?** Абсолютно, вы можете определить любое количество атрибутов объектов.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## Что такое spatial reference wgs84?
Spatial reference wgs84 (World Geodetic System 1984) — самая широко используемая географическая система координат. Она определяет широту и долготу в градусах и служит CRS по умолчанию для многих GIS‑наборов данных, включая тот, который мы создадим в этом руководстве.

## Почему использовать Aspose.GIS для добавления слоя?
Загружайте ваши GIS‑данные без сторонних бинарных файлов и сохраняйте полный контроль над определением схемы. Aspose.GIS поддерживает **40+ spatial reference systems**, может обрабатывать файлы размером более **2 GB** без загрузки всего набора данных в память и работает на Windows, Linux и macOS. Это делает его надёжным кросс‑платформенным решением для корпоративной автоматизации GIS.

## Требования
- Библиотека Aspose.GIS для .NET: загрузите и установите библиотеку из [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Каталог документов: создайте отдельную папку на вашем компьютере для хранения GIS‑файлов.  
- Временная лицензия Aspose (опционально для оценки) — см. раздел FAQ ниже для ссылки загрузки.

## Импорт пространств имён
Добавьте необходимые директивы `using` в ваш C#‑проект, чтобы иметь доступ к классам Aspose.GIS:

*Блок кода здесь не требуется; просто добавьте следующие строки в начало вашего файла:*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## Шаг 1: Копировать каталог
**Определение якоря:** Набор данных File GDB — это основанная на папке геодatabase ESRI, которая хранит пространственные данные в наборе файлов.  
Сначала продублируйте папку, содержащую оригинальный набор данных GDB. Сохранение копии защищает исходные данные во время экспериментов.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Шаг 2: Открыть набор данных и проверить возможность создания
`Dataset` представляет собой коллекцию GIS‑слоёв, хранящихся в File GDB. Откройте только что скопированный набор данных и убедитесь, что он может создавать новые слои. Свойство `CanCreateLayers` должно возвращать **True**. **`CanCreateLayers` — булево свойство, указывающее, поддерживает ли набор данных создание новых слоёв.**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Шаг 3: Создать и заполнить новый слой с spatial reference wgs84
Теперь мы создаём слой с именем **data** и явно задаём его spatial reference как **Wgs84**. Мы также добавляем простой атрибут под названием **Name** и вставляем одну точечную особенность. **`CreateLayer` создаёт новый слой в наборе данных с указанным именем и spatial reference.** **`SpatialReference` представляет координатную систему, используемую слоем.** **`Feature` — отдельный географический объект (точка, линия или полигон), хранящийся в слое.**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Шаг 4: Открыть и проверить добавленный слой
Наконец, откройте только что созданный слой и проверьте его содержимое. Консоль покажет, что слой содержит одну особенность и что атрибут **Name** соответствует установленному значению. **`Layer.Open` открывает существующий слой для чтения или редактирования.** Это подтверждает, что слой был добавлен корректно и что spatial reference — WGS84.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## Как добавить слой в набор данных File GDB?
Загрузите набор данных, вызовите `CreateLayer` с нужным именем и spatial reference, определите схему атрибутов и затем вставьте объекты. Всё это можно выполнить несколькими вызовами методов Aspose.GIS, а API автоматически обрабатывает блокировку файлов и проверку схемы. Процесс гарантирует, что новый слой соответствует spatial reference набора данных, определения атрибутов сохраняются в схеме слоя, и данные могут быть доступны любому GIS‑программному обеспечению, поддерживающему File GDB.

## Распространённые проблемы и советы
- **Неправильный путь:** Убедитесь, что `dataDir` заканчивается разделителем пути (`/` или `\`), чтобы объединённые строки образовывали корректные пути к файлам.  
- **Ошибки лицензии:** Если вы видите предупреждения о лицензировании, примените временную лицензию из портала Aspose перед запуском кода.  
- **Несоответствие CRS:** При открытии слоя позже в другом GIS‑инструменте убедитесь, что инструмент распознаёт WGS 84 (EPSG:4326) как координатную систему.  
- **Большие наборы данных:** Для наборов данных более 1 GB рассмотрите возможность использования `Dataset.OpenReadOnly` для снижения потребления памяти.

## Часто задаваемые вопросы
### В: Могу ли я использовать Aspose.GIS для .NET с другими GIS‑библиотеками?
О: Да, Aspose.GIS работает независимо, но может быть комбинирован с библиотеками, такими как GDAL или NetTopologySuite, для расширенной обработки.

### В: Доступна ли временная лицензия для тестовых целей?
О: Да, вы можете получить временную лицензию по [ссылке](https://purchase.aspose.com/temporary-license/) для тестирования и оценки.

### В: Какие системы spatial reference поддерживает Aspose.GIS для .NET?
О: Aspose.GIS поддерживает более **40 EPSG кодов**, включая популярные системы, такие как WGS84 (EPSG:4326), Web Mercator (EPSG:3857) и NAD83 (EPSG:4269). Ознакомьтесь с полной документацией [здесь](https://reference.aspose.com/gis/net/).

### В: Могу ли я внести вклад в сообщество Aspose.GIS?
О: Конечно! Присоединяйтесь к обсуждениям и делитесь опытом на форуме [Aspose.GIS](https://forum.aspose.com/c/gis/33).

### В: Где я могу найти подробную документацию по Aspose.GIS для .NET?
О: Ознакомьтесь с полной документацией [здесь](https://reference.aspose.com/gis/net/) для получения подробной информации обо всех классах, методах и рекомендациях.

---

**Последнее обновление:** 2026-06-30  
**Тестировано с:** Aspose.GIS for .NET (latest stable version)  
**Автор:** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Связанные руководства

- [Создать набор данных File Geodatabase .NET с Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Создать векторный слой в File GDB – руководство Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Создать набор данных File GDB и установить допуски для слоя](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}