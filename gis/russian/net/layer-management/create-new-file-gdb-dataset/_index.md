---
date: 2026-06-30
description: Узнайте, как создавать наборы данных файловой геобазы .NET с использованием
  Aspose.GIS for .NET. Пошаговое руководство для простого управления GIS‑данными.
keywords:
- how to create gdb
- Aspose.GIS .NET tutorial
- file geodatabase dataset
linktitle: Создать новый набор данных File GDB
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create file geodatabase .NET datasets using Aspose.GIS
    for .NET. Step‑by‑step guide for effortless GIS data management.
  headline: How to Create GDB Dataset with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create file geodatabase .NET datasets using Aspose.GIS
    for .NET. Step‑by‑step guide for effortless GIS data management.
  name: How to Create GDB Dataset with Aspose.GIS for .NET
  steps:
  - name: Create a New File GDB Dataset
    text: The `Dataset.Create` method initializes an empty File Geodatabase at the
      supplied path using the `FileGdb` driver. At this point the dataset contains
      zero layers. **Explanation:** The `Dataset` class is Aspose.GIS's top‑level
      object that represents a single File Geodatabase in memory. After creation
  - name: Create and Populate `layer_1`
    text: 'Here we add a first layer that stores integer attributes and point geometries.
      **Explanation:** - `CreateLayer` creates a new feature class named **layer_1**.
      - An integer attribute called **value** is defined. - The loop adds ten features,
      each with a unique integer and a point at coordinates *(i, '
  - name: Create and Populate `layer_2`
    text: Next we add a second layer that demonstrates line geometry handling. **Explanation:**
      This creates **layer_2** and inserts a single feature whose geometry is a `LineString`
      connecting two points.
  - name: Verify the Updated Layers Count
    text: Finally, confirm that both layers were added successfully. **Explanation:**
      The dataset now reports two layers, confirming that the **how to create gdb**
      process completed as expected.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS is a standalone toolkit, but you can combine it with other
      .NET GIS libraries to extend functionality.
    question: Can I use Aspose.GIS for .NET with other GIS libraries?
  - answer: Absolutely – visit the [Aspose.GIS Forum](https://forum.aspose.com/c/gis/33)
      for discussions and assistance.
    question: Is there a community forum for Aspose.GIS support?
  - answer: Go to the [Temporary License](https://purchase.aspose.com/temporary-license/)
      page for details on short‑term licensing.
    question: How can I obtain a temporary license for Aspose.GIS?
  - answer: Explore the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for additional code samples and API references.
    question: Where can I find more examples and detailed documentation?
  - answer: You can buy a license on the official [purchase page](https://purchase.aspose.com/buy).
    question: How do I purchase a full Aspose.GIS for .NET license?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Как создать набор данных GDB с помощью Aspose.GIS for .NET
url: /ru/net/layer-management/create-new-file-gdb-dataset/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать набор данных GDB с помощью Aspose.GIS для .NET

## Введение
В этом руководстве вы **как создать gdb** наборы данных с нуля, используя Aspose.GIS для .NET. Независимо от того, разрабатываете ли вы настольный GIS‑инструмент, веб‑службу, хранящую пространственные данные, или вам просто нужен надёжный способ программно генерировать файловые геобазы данных, мы проведём вас через каждый шаг с понятными объяснениями и практическим контекстом.

## Быстрые ответы
- **Что охватывает это руководство?** Оно показывает, как создать новую File Geodatabase, добавить два слоя и проверить набор данных с помощью Aspose.GIS для .NET.  
- **Сколько это займет?** Около 10‑15 минут для разработчика, знакомого с C#.  
- **Какие предпосылки?** Среда разработки .NET, библиотека Aspose.GIS для .NET и путь к записываемой папке.  
- **Можно ли запускать на .NET 6+ или .NET Core?** Да — API полностью совместим с современными средами выполнения .NET.  
- **Требуется ли лицензия?** Для продакшн‑развёртываний нужна временная или постоянная лицензия Aspose.GIS.

## Что такое File Geodatabase?
File Geodatabase (File GDB) — это хранилище данных на основе папки, которое содержит классы объектов GIS, растровые наборы данных и связанные метаданные. Оно обеспечивает быструю запись/чтение, поддерживает наборы данных из сотен страниц и является родным форматом платформы ArcGIS от Esri. Также поддерживается версионное редактирование и возможность хранения больших растровых мозаик, что делает его подходящим для корпоративного управления пространственными данными.

## Почему создавать файловую геобазу в .NET с помощью Aspose.GIS?
Aspose.GIS устраняет внешние зависимости, работает кросс‑платформенно на Windows, Linux и macOS и поддерживает **50+** форматов ввода и вывода — включая shapefiles, GeoJSON, KML и растровые типы. Библиотека предоставляет полный контроль над схемой, атрибутами и пространственной привязкой, сохраняя точность геометрии до 0,001 м.

## Предпосылки
- Aspose.GIS для .NET установлен. Скачайте его со [страницы загрузки Aspose.GIS для .NET](https://releases.aspose.com/gis/net/).  
- Visual Studio 2022 (или любой IDE, поддерживающий .NET).  
- Записываемая папка на вашем компьютере — замените `"Your Document Directory"` в коде на этот путь.  
- Базовое знакомство с C# и структурой проекта .NET.

## Импорт пространств имён
Классы `Dataset`, `Layer` и геометрии находятся в пространстве имён `Aspose.Gis`.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Как создать набор данных gdb шаг за шагом?

Загрузите, создайте и проверьте File Geodatabase, используя всего несколько вызовов API. Процесс состоит из инициализации набора данных, добавления слоёв с атрибутами и геометрией, а затем проверки количества слоёв, чтобы убедиться, что всё сохранено корректно. Пример также демонстрирует, как установить пространственную привязку и правильно освободить набор данных, чтобы освободить системные ресурсы.

### Шаг 1: Создать новый набор данных File GDB
Метод `Dataset.Create` инициализирует пустую File Geodatabase по указанному пути с использованием драйвера `FileGdb`. На данный момент набор данных содержит ноль слоёв.

```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Output: 0
    // Continue with subsequent steps...
}
```

**Explanation:** Класс `Dataset` — это объект верхнего уровня Aspose.GIS, представляющий одну File Geodatabase в памяти. После создания вы можете добавлять классы объектов (слои) и напрямую работать с ними.

### Шаг 2: Создать и заполнить `layer_1`
Здесь мы добавляем первый слой, который хранит целочисленные атрибуты и точечные геометрии.

```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```

**Explanation:**  
- `CreateLayer` создаёт новый класс объектов с именем **layer_1**.  
- Определяется целочисленный атрибут **value**.  
- Цикл добавляет десять объектов, каждый с уникальным целым числом и точкой с координатами *(i, i)*.

### Шаг 3: Создать и заполнить `layer_2`
Далее мы добавляем второй слой, демонстрирующий работу с линейной геометрией.

```csharp
using (var layer = dataset.CreateLayer("layer_2"))
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

**Explanation:** Этот код создаёт **layer_2** и вставляет один объект, чья геометрия — `LineString`, соединяющая две точки.

### Шаг 4: Проверить обновлённое количество слоёв
Наконец, подтвердите, что оба слоя были успешно добавлены.

```csharp
Console.WriteLine(dataset.LayersCount); // Output: 2
```

**Explanation:** Теперь набор данных сообщает о двух слоях, подтверждая, что процесс **как создать gdb** завершён как ожидалось.

## Распространённые проблемы и решения
| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| **`UnauthorizedAccessException`** при создании набора данных | Путь к папке доступен только для чтения или у вас нет прав. | Выберите записываемый каталог или запустите Visual Studio от имени администратора. |
| **`ArgumentException` для драйвера** | Имя драйвера написано с ошибкой или версия библиотеки его не поддерживает. | Используйте `Drivers.FileGdb` точно как показано; убедитесь, что у вас последняя версия пакета Aspose.GIS. |
| **Объекты не отображаются в ArcGIS** | Отсутствует пространственная привязка или несовместимая геометрия. | Установите пространственную привязку для слоя, если требуется, и убедитесь, что геометрия валидна. |

## Часто задаваемые вопросы
**Q: Могу ли я использовать Aspose.GIS для .NET с другими GIS‑библиотеками?**  
A: Да, Aspose.GIS — это автономный набор инструментов, но вы можете комбинировать его с другими .NET GIS‑библиотеками для расширения функциональности.

**Q: Есть ли сообщество‑форум для поддержки Aspose.GIS?**  
A: Конечно — посетите [форум Aspose.GIS](https://forum.aspose.com/c/gis/33) для обсуждений и помощи.

**Q: Как получить временную лицензию для Aspose.GIS?**  
A: Перейдите на страницу [Temporary License](https://purchase.aspose.com/temporary-license/) для получения информации о краткосрочном лицензировании.

**Q: Где можно найти больше примеров и подробную документацию?**  
A: Изучите [документацию Aspose.GIS](https://reference.aspose.com/gis/net/) для дополнительных примеров кода и справки по API.

**Q: Как приобрести полную лицензию Aspose.GIS для .NET?**  
A: Вы можете купить лицензию на официальной [странице покупки](https://purchase.aspose.com/buy).

## Заключение
Теперь вы освоили **как создать gdb** наборы данных, добавили два различных слоя и проверили результат с помощью Aspose.GIS. Эта база позволяет вам расширять GIS‑приложения — добавлять новые слои, определять сложные схемы или интегрировать с веб‑службами. Погрузитесь глубже в API Aspose.GIS для работы с растровыми данными, пространственными запросами и продвинутыми операциями с геометрией.

---

**Last Updated:** 2026-06-30  
**Tested With:** Aspose.GIS for .NET 24.11 (or latest)  
**Author:** Aspose

## Связанные руководства

- [Создать векторный слой в File GDB – руководство Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Создать набор данных File GDB и установить допуски для слоя](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)
- [Как удалить слой из набора данных File GDB с помощью Aspose.GIS](/gis/net/layer-data-operations/remove-layers-from-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}