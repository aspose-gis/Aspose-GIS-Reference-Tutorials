---
date: 2025-12-31
description: Изучите Aspose.GIS для .NET и узнайте, как создать набор данных файлового
  GDB и задать допуски без усилий, следуя пошаговым инструкциям. Улучшите свои приложения
  на .NET.
linktitle: Set Tolerances for File GDB Layer
second_title: Aspose.GIS .NET API
title: Создать набор данных File GDB и задать допуски для слоя
url: /ru/net/layer-data-operations/set-tolerances-for-file-gdb-layer/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать набор данных File GDB и установить допуски для слоя

## Introduction
Если вам нужно **создать набор данных file GDB** и контролировать его точность, вы попали в нужное место. В этом руководстве мы пройдем весь процесс — начиная с настройки вашего проекта .NET, создания набора данных File Geodatabase (GDB), а затем применения допусков XY, Z и M к новому слою. К концу вы получите готовый набор данных, который будет плавно работать с инструментами ArcGIS и другими GIS‑приложениями.

## Quick Answers
- **Что означает «создать набор данных file GDB»?** Он создает новый контейнер File Geodatabase на диске, который может содержать несколько GIS‑слоев.  
- **Зачем устанавливать допуски?** Допуски определяют точность геометрических операций, предотвращая ошибки округления при пространственном анализе.  
- **Какой класс Aspose.GIS используется?** `Dataset.Create` вместе с `FileGdbOptions`.  
- **Нужна ли лицензия для разработки?** Временная лицензия достаточна для тестирования; полная лицензия требуется для продакшн.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is a File GDB Dataset?
File Geodatabase (GDB) — это хранилище данных на основе папки, которое содержит GIS‑слои, таблицы и связи. С помощью Aspose.GIS вы можете программно **создать набор данных file GDB** без необходимости установки ArcGIS, что делает его идеальным для автоматизированных конвейеров или пользовательских приложений.

## Why set tolerances for a layer?
Установка допусков гарантирует, что геометрические вычисления (например, пересечения, буферизация или привязка) учитывают необходимую точность. Это особенно важно при работе с данными высокого разрешения или при экспорте в другие GIS‑платформы, которые ожидают конкретные значения допусков.

## Prerequisites
Перед тем как перейти к коду, убедитесь, что у вас есть следующее:

- **Aspose.GIS for .NET Library** — Скачайте и установите библиотеку Aspose.GIS по [ссылке для загрузки](https://releases.aspose.com/gis/net/). Если вы ещё её не получили, можете подробнее изучить библиотеку в [документации](https://reference.aspose.com/gis/net/).
- **Среда разработки** — Visual Studio, Rider или любой IDE, поддерживающий разработку на .NET.
- **Действующая лицензия** — используйте временную лицензию для тестирования или полную лицензию для продакшн (см. ссылки в разделе FAQ).

Теперь, когда всё готово, импортируем необходимые пространства имён.

## Import Namespaces
В вашем .NET‑приложении включите следующие пространства имён, чтобы воспользоваться возможностями Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

С подключёнными пространствами имён мы можем приступить к построению набора данных.

## Step‑by‑Step Guide

### Step 1: Define Your Document Directory
Сначала укажите в коде папку, в которой будет создан File GDB:

```csharp
string dataDir = "Your Document Directory";
```

> **Совет:** Используйте `Path.Combine`, если нужно построить путь независимо от платформы.

### Step 2: Create a File GDB Dataset
Теперь мы действительно **создаём набор данных file GDB** на диске. Метод `Dataset.Create` принимает полный путь и тип драйвера (`Drivers.FileGdb`).

```csharp
var path = dataDir + "TolerancesForFileGdbLayer_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

> Блок `using` гарантирует, что набор данных будет корректно закрыт и сброшен на диск после завершения работы.

### Step 3: Set Tolerances using `FileGdbOptions`
Перед созданием слоя задайте необходимые допуски. `FileGdbOptions` позволяет указать допуски XY, Z и M.

```csharp
var options = new FileGdbOptions
{
    XYTolerance = 0.001,
    ZTolerance = 0.1,
    MTolerance = 0.1,
};
```

Эти значения типичны для инженерных данных высокой точности, но вы можете изменить их под требования вашего проекта.

### Step 4: Create a Layer with the Specified Tolerances
Наконец, создайте новый слой внутри набора данных, передав объект опций, который мы только что настроили.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options))
{
    // The layer is created with the provided tolerances, ready for use in ArcGIS features/tools.
}
```

Когда блок `using` завершается, слой сохраняется с заданными вами допусками.

## Common Issues & Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **Путь к набору данных не найден** | `dataDir` указывает на несуществующую папку. | Убедитесь, что директория существует, или создайте её с помощью `Directory.CreateDirectory(dataDir)`. |
| **Недопустимые значения допусков** | Допуски должны быть неотрицательными числами. | Используйте положительные значения; избегайте нуля, если только вы не хотите отсутствие допуска. |
| **Ошибка лицензии** | Пробная или временная лицензия истекла. | Примените новую временную лицензию или перейдите на полную. |

## Frequently Asked Questions

**В: Могу ли я использовать Aspose.GIS for .NET вместе с другими GIS‑библиотеками?**  
О: Да, Aspose.GIS поддерживает взаимодействие, позволяя интегрировать её с библиотеками, такими как NetTopologySuite или GDAL.

**В: Доступна ли пробная версия Aspose.GIS for .NET?**  
О: Конечно! Вы можете ознакомиться с функциями через [бесплатную пробную версию](https://releases.aspose.com/).

**В: Как получить поддержку по Aspose.GIS for .NET?**  
О: Посетите [форум Aspose.GIS](https://forum.aspose.com/c/gis/33), чтобы связаться с сообществом и получить помощь.

**В: Нужна ли временная лицензия для тестирования?**  
О: Да, вы можете получить [временную лицензию](https://purchase.aspose.com/temporary-license/) для тестирования и оценки.

**В: Где можно приобрести лицензию Aspose.GIS for .NET?**  
О: Вы можете купить лицензию на [странице покупки](https://purchase.aspose.com/buy).

## Conclusion
В этом руководстве мы рассмотрели, как **создать набор данных file GDB**, настроить геометрические допуски и сохранить готовый слой с помощью Aspose.GIS for .NET. Эти шаги дают вам точный контроль над пространственными данными, делая ваши GIS‑приложения более надёжными и совместимыми.

---  
**Последнее обновление:** 2025-12-31  
**Тестировано с:** Aspose.GIS for .NET 24.11 (последняя на момент написания)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}