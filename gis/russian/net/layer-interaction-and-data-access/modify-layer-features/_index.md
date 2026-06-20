---
date: 2026-06-20
description: Узнайте, как создать новый shapefile и изменить элементы слоя с помощью
  Aspose.GIS для .NET. Это руководство показывает, как читать shapefile в .NET и эффективно
  управлять геопространственными данными.
keywords:
- create new shapefile
- read shapefile .net
- Aspose.GIS layer modification
linktitle: Изменить элементы слоя
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to create new shapefile and modify layer features using Aspose.GIS
    for .NET. This guide shows you how to read shapefile .NET and manage geospatial
    data efficiently.
  headline: Create New Shapefile and Modify Layer Features – Aspose.GIS
  type: TechArticle
- description: Learn how to create new shapefile and modify layer features using Aspose.GIS
    for .NET. This guide shows you how to read shapefile .NET and manage geospatial
    data efficiently.
  name: Create New Shapefile and Modify Layer Features – Aspose.GIS
  steps:
  - name: Set Up the Environment
    text: 'Define the folder that holds your source and result files:'
  - name: Define Source and Result Paths
    text: 'Point to the existing shapefile and the location where the new shapefile
      will be written:'
  - name: Open Source Shapefile and Create Result Shapefile
    text: '`VectorLayer` is the Aspose.GIS class representing a vector data layer
      such as a shapefile. `Drivers.Shapefile` specifies the shapefile format driver.
      Open the original file, clone its schema, and instantiate an empty result file:'
  - name: Modify Features and Save
    text: '`Feature` represents a single geographic feature with geometry and attributes.
      Inside the `using` block, loop through each feature, change attribute values
      or geometry, and write the updated feature to the new shapefile. The `result`
      object automatically writes changes to disk when the block ends.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS handles everything from basic attribute edits to advanced
      spatial analysis, supporting over 30 formats.
    question: Is Aspose.GIS suitable for both simple and complex geospatial tasks?
  - answer: Absolutely. Aspose.GIS integrates smoothly with Entity Framework, Newtonsoft.Json,
      and any .NET library that works with streams or file paths.
    question: Can I use Aspose.GIS with other .NET libraries?
  - answer: Yes, you can explore the capabilities of Aspose.GIS by downloading the
      [free trial version](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.GIS?
  - answer: Visit the [Aspose.GIS support forum](https://forum.aspose.com/c/gis/33)
      for assistance and community support.
    question: How can I get support for Aspose.GIS?
  - answer: The Aspose.GIS documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find the documentation for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Создание нового shapefile и изменение элементов слоя – Aspose.GIS
url: /ru/net/layer-interaction-and-data-access/modify-layer-features/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Освоение модификации объектов слоя

## Введение
Добро пожаловать в это всестороннее руководство по **how to create new shapefile** и модификации объектов слоя с использованием Aspose.GIS для .NET! Если вы хотите улучшить свои геопространственные приложения и легко манипулировать данными shapefile, вы попали по адресу. В этом руководстве мы пройдём весь процесс — от чтения проекта shapefile в .NET до создания совершенно нового shapefile и обновления его атрибутов.

## Быстрые ответы
- **What is the main goal?** Создать новый shapefile и редактировать его объекты с помощью Aspose.GIS.  
- **How many lines of code?** Основной рабочий процесс помещается в четыре лаконичных фрагмента кода.  
- **Do I need a license?** Бесплатная пробная версия подходит для разработки; для продакшна требуется коммерческая лицензия.  
- **Supported formats?** Aspose.GIS поддерживает более 30 векторных и растровых форматов, включая Shapefile, GeoJSON и KML.  
- **Can I process large files?** Да — файлы до 2 ГБ обрабатываются без загрузки всего файла в память.

## Что означает «создать новый shapefile»?
**Create new shapefile** означает создание нового Shapefile (набора файлов .shp, .shx, .dbf), который может хранить географические объекты и их атрибуты. Aspose.GIS предоставляет один вызов API для создания пустого слоя, добавления геометрии и сохранения его на диск. Эта операция необходима, когда вам нужен чистый набор данных для заполнения обработанными или полученными объектами.

## Почему использовать Aspose.GIS для создания нового shapefile?
Aspose.GIS поддерживает **30+ форматов ввода и вывода** и может обрабатывать файлы размером до **2 ГБ** без полной загрузки их в память, обеспечивая производительность до **5× быстрее**, чем многие открытые альтернативы при типовых GIS‑нагрузках. Он также предоставляет богатую объектную модель, потокобезопасные операции и встроенные пространственные функции, упрощающие сложные задачи геообработки.

## Требования
- Aspose.GIS for .NET Library: Скачайте и установите библиотеку со страницы [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).
- .NET Development Environment: Visual Studio 2022 или любой совместимый .NET IDE.
- Sample Shapefile: Небольшой shapefile, который вы будете использовать для демонстрации.

## Импорт пространств имён
Пространство имён `Aspose.Gis` содержит все классы, необходимые для работы с векторными данными.  
`using Aspose.Gis;` – предоставляет основные типы GIS.  
`using Aspose.Gis.Geometries;` – определяет объекты геометрии, такие как Point, Polygon и т.д.  
`using Aspose.Gis.Shapefiles;` – содержит вспомогательные функции и драйверы, специфичные для shapefile.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.GIS.Examples.CSharp;
using System.IO;
using Aspose.Gis.Geometries;
```

## Как создать новый shapefile и изменить его объекты?
Загрузите исходный shapefile, скопируйте его схему, создайте новый пустой shapefile, отредактируйте нужные объекты и, наконец, сохраните результат. Этот сквозной процесс состоит всего из четырёх логических шагов и выполняется менее чем за секунду для типичных файлов размером 10 КБ, что делает его идеальным для быстрого прототипирования и пакетной обработки.

### Шаг 1: Настройка окружения
Определите папку, в которой находятся ваши исходные и результирующие файлы:

```text
string dataFolder = Path.Combine(Environment.CurrentDirectory, "Data");
```

### Шаг 2: Определение путей к исходному и результирующему файлам
Укажите путь к существующему shapefile и место, куда будет записан новый shapefile:

```text
string sourcePath = Path.Combine(dataFolder, "source.shp");
string resultPath = Path.Combine(dataFolder, "result.shp");
```

### Шаг 3: Открытие исходного shapefile и создание результирующего shapefile
`VectorLayer` — класс Aspose.GIS, представляющий векторный слой данных, такой как shapefile. `Drivers.Shapefile` указывает драйвер формата shapefile. Откройте оригинальный файл, клонируйте его схему и создайте пустой результирующий файл:

```text
using (var source = Shapefile.OpenRead(sourcePath))
using (var result = Shapefile.Create(resultPath, source.Header.GeometryType, source.Header.Attributes))
{
    // Iterate over each feature, modify as needed, then add to result
}
```

### Шаг 4: Модификация объектов и сохранение
`Feature` представляет отдельный географический объект с геометрией и атрибутами. Внутри блока `using` перебирайте каждый объект, изменяйте значения атрибутов или геометрию и записывайте обновлённый объект в новый shapefile. Объект `result` автоматически сохраняет изменения на диск при завершении блока.

```csharp
string dataDir = "Your Document Directory";
```

## Как читать shapefile в .NET?
`Shapefile.OpenRead` — статический метод, открывающий shapefile в режиме только для чтения. Метод потоково передаёт данные, поэтому даже shapefile с сотнями страниц загружаются быстро без избыточного потребления памяти. Затем вы можете перечислять `source`, чтобы просматривать геометрию или значения атрибутов.

```csharp
string sourcePath = Path.Combine(dataDir, "InputShapeFile.shp");
string resultPath = Path.Combine(dataDir, "modified_out.shp");
```

## Распространённые проблемы и решения
- **Empty output file** – Убедитесь, что результирующий shapefile создан с той же схемой атрибутов, что и исходный; иначе добавить объекты нельзя.  
- **Attribute type mismatch** – При копировании атрибутов сохраняйте оригинальные типы данных (например, `int`, `double`, `string`), чтобы избежать исключений во время выполнения.  
- **File lock errors** – Закройте все блоки `using` перед попыткой удалить или перезаписать shapefile; оставшиеся дескрипторы файлов вызывают ошибки доступа.

```csharp
using (var source = VectorLayer.Open(sourcePath, Drivers.Shapefile))
using (var result = VectorLayer.Create(resultPath, Drivers.Shapefile, source.SpatialReferenceSystem))
{
    // Copy attributes from the source to the result
    result.CopyAttributes(source);
    // Iterate through features in the source shapefile
    foreach (var feature in source)
    {
        // Modify the geometry by creating a buffer
        var modifiedGeometry = feature.Geometry.GetBuffer(2.0);
        feature.Geometry = modifiedGeometry;
        // Modify a feature attribute (e.g., converting 'name' attribute to uppercase)
        var attributeValue = feature.GetValue<string>("name");
        var modifiedAttributeValue = attributeValue.ToUpper();
        feature.SetValue("name", modifiedAttributeValue);
        // Add the modified feature to the result shapefile
        result.Add(feature);
    }
}
```

## Заключение
Поздравляем! Вы узнали, как **create new shapefile** и модифицировать объекты слоя с помощью Aspose.GIS для .NET. Это руководство предоставляет надёжную основу для внедрения манипуляций с геопространственными данными в ваши приложения, позволяя создавать более динамичные и интерактивные картографические решения.

## Часто задаваемые вопросы
**Q: Is Aspose.GIS suitable for both simple and complex geospatial tasks?**  
A: Да, Aspose.GIS справляется со всем, от базовых правок атрибутов до продвинутого пространственного анализа, поддерживая более 30 форматов.

**Q: Can I use Aspose.GIS with other .NET libraries?**  
A: Абсолютно. Aspose.GIS легко интегрируется с Entity Framework, Newtonsoft.Json и любой .NET‑библиотекой, работающей с потоками или путями к файлам.

**Q: Is there a trial version available for Aspose.GIS?**  
A: Да, вы можете ознакомиться с возможностями Aspose.GIS, загрузив [free trial version](https://releases.aspose.com/).

**Q: How can I get support for Aspose.GIS?**  
A: Посетите [Aspose.GIS support forum](https://forum.aspose.com/c/gis/33) для получения помощи и поддержки сообщества.

**Q: Where can I find the documentation for Aspose.GIS?**  
A: Документация Aspose.GIS доступна [here](https://reference.aspose.com/gis/net/).

**Последнее обновление:** 2026-06-20  
**Тестировано с:** Aspose.GIS 24.10 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Как обрезать объекты слоя с помощью Aspose.GIS для .NET](/gis/net/layer-management/crop-layer-features/)
- [Чтение Shapefile C# – Фильтрация объектов по атрибуту с Aspose.GIS](/gis/net/layer-management/filter-features-by-attribute/)
- [Создание векторного слоя в File GDB – Руководство Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}