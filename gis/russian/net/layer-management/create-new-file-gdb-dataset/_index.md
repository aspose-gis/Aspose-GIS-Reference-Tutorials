---
date: 2026-01-10
description: Изучите, как создавать наборы данных файловой геодatabase .NET с помощью
  Aspose.GIS для .NET. Пошаговое руководство для простого управления GIS‑данными.
linktitle: Create New File GDB Dataset
second_title: Aspose.GIS .NET API
title: Создать набор данных .NET File Geodatabase с Aspose.GIS
url: /ru/net/layer-management/create-new-file-gdb-dataset/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание набора данных File Geodatabase .NET с Aspose.GIS

## Introduction
В этом руководстве вы **создадите file geodatabase .NET** набор данных с нуля, используя Aspose.GIS для .NET. Независимо от того, разрабатываете ли вы настольный GIS‑инструмент, веб‑службу, хранящую пространственные данные, или просто нуждаетесь в надёжном способе программно генерировать File Geodatabases, это руководство проведёт вас через каждый шаг с понятными объяснениями и практическим контекстом.

## Quick Answers
- **Что покрывает это руководство?** Создание нового File Geodatabase, добавление двух слоёв и проверка набора данных с помощью Aspose.GIS для .NET.  
- **Сколько времени занимает?** Около 10‑15 минут для разработчика, знакомого с C#.  
- **Требования?** Среда разработки .NET, библиотека Aspose.GIS для .NET и путь к записываемой папке.  
- **Можно ли использовать это в .NET Core / .NET 6+?** Да — API полностью совместим с современными средами выполнения .NET.  
- **Нужна ли лицензия?** Для использования в продакшене требуется временная или постоянная лицензия Aspose.GIS.

## What is a File Geodatabase?
File Geodatabase (File GDB) — это хранилище данных на основе папки, которое содержит GIS‑классы объектов, растровые наборы данных и связанные метаданные. Оно обеспечивает быструю запись/чтение, поддерживает большие наборы данных и широко используется в экосистеме ArcGIS от Esri. С помощью Aspose.GIS вы можете создавать и управлять этими базами напрямую из кода .NET без какого‑либо внешнего GIS‑ПО.

## Why create file geodatabase .NET with Aspose.GIS?
- **Нет внешних зависимостей** — библиотека обрабатывает все детали формата файлов.  
- **Кросс‑платформенный** — работает на Windows, Linux и macOS в средах .NET.  
- **Богатая поддержка геометрии** — точки, линии, полигоны и многое другое.  
- **Полный контроль** — вы определяете схему, атрибуты и пространственную привязку.

## Prerequisites
Перед началом убедитесь, что у вас есть следующее:

- Aspose.GIS для .NET установлен. Вы можете скачать его со [страницы загрузки Aspose.GIS для .NET](https://releases.aspose.com/gis/net/).  
- Среда разработки, например Visual Studio 2022 (или любой IDE, поддерживающий .NET).  
- Записываемая папка на вашем компьютере, где будет создан новый GDB — замените `"Your Document Directory"` в коде на этот путь.  
- Базовое знакомство с C# и структурой проекта .NET.

## Import Namespaces
First, import the namespaces that give you access to Aspose.GIS classes:

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

## Step‑by‑Step Guide

### Step 1: Create a New File GDB Dataset
Следующий фрагмент кода создаёт пустой File Geodatabase. Это ядро **create file geodatabase .net**.

```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Output: 0
    // Continue with subsequent steps...
}
```

**Explanation:** `Dataset.Create` инициализирует GDB по указанному пути, используя драйвер `FileGdb`. На этом этапе набор данных не содержит слоёв, поэтому количество слоёв равно нулю.

### Step 2: Create and Populate `layer_1`
Теперь мы добавляем первый слой, который хранит целочисленные атрибуты и точечные геометрии.

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

### Step 3: Create and Populate `layer_2`
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

**Explanation:** Этот код создаёт **layer_2** и вставляет один объект, геометрия которого — `LineString`, соединяющий две точки.

### Step 4: Verify the Updated Layers Count
Наконец, подтвердите, что оба слоя были успешно добавлены.

```csharp
Console.WriteLine(dataset.LayersCount); // Output: 2
```

**Explanation:** Набор данных теперь сообщает о двух слоях, подтверждая, что процесс **create file geodatabase .net** завершён успешно.

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **`UnauthorizedAccessException`** при создании набора данных | Путь к папке только для чтения или у вас нет прав. | Выберите записываемый каталог или запустите Visual Studio от имени администратора. |
| **`ArgumentException` для драйвера** | Имя драйвера написано с ошибкой или версия библиотеки его не поддерживает. | Используйте `Drivers.FileGdb` точно как показано; убедитесь, что у вас последняя версия пакета Aspose.GIS. |
| **Элементы не отображаются в ArcGIS** | Отсутствует пространственная привязка или несовместимая геометрия. | Установите пространственную привязку для слоя, если требуется, и убедитесь, что геометрии корректны. |

## Frequently Asked Questions
### Q: Can I use Aspose.GIS for .NET with other GIS libraries?
Aspose.GIS для .NET — это автономный набор инструментов; однако вы можете интегрировать его с другими библиотеками .NET для расширения функциональности.

### Q: Is there a community forum for Aspose.GIS support?
Да, поддержку и обсуждения можно найти на [форуме Aspose.GIS](https://forum.aspose.com/c/gis/33).

### Q: How can I obtain a temporary license for Aspose.GIS?
Посетите страницу [Temporary License](https://purchase.aspose.com/temporary-license/) для получения информации о временной лицензии.

### Q: Are there additional examples and documentation available?
Изучите [документацию Aspose.GIS](https://reference.aspose.com/gis/net/) для получения дополнительных примеров и подробной информации.

### Q: Where can I purchase Aspose.GIS for .NET?
Купить Aspose.GIS для .NET можно на [странице покупки](https://purchase.aspose.com/buy).

## Conclusion
Вы успешно **создали file geodatabase .NET** наборы данных, добавили два различных слоя и проверили результат с помощью Aspose.GIS. Эта база позволяет строить более мощные GIS‑приложения — добавлять новые слои, определять сложные схемы или интегрировать с веб‑службами. Изучайте API Aspose.GIS дальше, чтобы работать с растровыми данными, пространственными запросами и продвинутыми операциями над геометрией.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.GIS for .NET 24.11 (or latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}