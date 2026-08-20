---
date: 2026-07-05
description: Узнайте, как конвертировать shapefile в geojson с использованием Aspose.GIS
  for .NET. Руководство также охватывает копирование атрибутов между слоями и генерацию
  geojson‑файла на c#.
keywords:
- convert shapefile to geojson
- export shapefile as geojson
- aspose gis conversion
- read shapefile c#
- write geojson c#
linktitle: Извлечь объекты в GeoJSON
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  headline: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  name: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  steps:
  - name: Open Input Shapefile
    text: The `VectorLayer.Open` method reads a Shapefile and returns an enumerable
      collection of `Feature` objects that you can iterate over.
  - name: Create Output GeoJSON
    text: '`VectorLayer.Create` with the `Drivers.GeoJson` driver creates an empty
      GeoJSON file ready to receive features.'
  - name: Copy Attributes Between Layers
    text: '`CopyAttributes` copies the attribute schema (field names and data types)
      from the source Shapefile to the new GeoJSON layer in a single call.'
  - name: Process Features
    text: Iterate through each feature in the Shapefile so you can apply any custom
      logic before writing it out.
  - name: Filter Features by Date
    text: In this example we skip records whose `dob` (date of birth) field is missing
      or earlier than 1 Jan 1982. Adjust the filter to match your own data requirements.
  - name: Construct a New Feature (C# Generate GeoJSON File)
    text: A `Feature` represents a single spatial element containing geometry and
      attribute data. Here we build a new `Feature` for the GeoJSON layer, copy the
      geometry and attribute values, and add it to the output. This is the core of
      *c# generate geojson file*. Congratulations! You’ve successfully **conver
  type: HowTo
- questions:
  - answer: Visit the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for in‑depth information.
    question: Where can I find more documentation?
  - answer: You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I seek support?
  - answer: Yes, you can find the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can buy the product [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Конвертировать Shapefile в GeoJSON с помощью Aspose.GIS for .NET
url: /ru/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Конвертировать Shapefile в GeoJSON с помощью Aspose.GIS для .NET

## Введение
В этом всестороннем пошаговом руководстве вы узнаете **как конвертировать shapefile в geojson** с помощью мощной библиотеки Aspose.GIS для .NET. Независимо от того, создаёте ли вы веб‑службу картирования, подготавливаете данные для мобильного GIS‑приложения или просто нужно обменяться данными между форматами, это руководство покажет, что именно делать, почему каждый шаг важен и как избежать распространённых ошибок.

## Быстрые ответы
- **Что охватывает данное руководство?** Конвертация Shapefile в файл GeoJSON, копирование атрибутов между слоями и генерация результата с помощью C#.
- **Какая библиотека требуется?** Aspose.GIS для .NET.
- **Нужна ли лицензия?** Для продакшна требуется временная или полная лицензия; бесплатная пробная версия подходит для оценки.
- **Сколько времени занимает реализация?** Около 10‑15 минут для базовой конвертации.
- **Можно ли запускать на .NET Core/.NET 6?** Да — код работает на всех поддерживаемых версиях .NET.

## Что такое конвертация shapefile в geojson?
Конвертация Shapefile в GeoJSON означает чтение векторных объектов из классического формата ESRI Shapefile и запись их в современный, веб‑дружелюбный документ GeoJSON. Такое преобразование позволяет напрямую передавать GIS‑данные в JavaScript‑библиотеки картирования, такие как Leaflet или Mapbox GL, и упрощает обмен данными между настольными GIS‑инструментами и веб‑API.

## Почему стоит использовать Aspose.GIS для этой конвертации?
Aspose.GIS абстрагирует низкоуровневый бинарный парсинг, поддерживает более 50 форматов ввода и вывода и может обрабатывать наборы данных в сотни страниц без загрузки всего файла в память. Библиотека также предоставляет чистый объектно‑ориентированный API, работающий на .NET Framework, .NET Core и .NET 5/6, так что вы тратите время на бизнес‑логику, а не на нюансы форматов.

## Предварительные требования
Прежде чем приступить, убедитесь, что у вас есть следующее:

- Aspose.GIS для .NET: Убедитесь, что библиотека установлена. Если нет, скачайте её со [страницы Aspose.GIS для .NET](https://releases.aspose.com/gis/net/).
- Данные Shapefile: Подготовьте Shapefile для ввода. При необходимости образцы данных можно найти в [документации Aspose.GIS](https://reference.aspose.com/gis/net/).
- Среда .NET: Настройте .NET‑окружение для выполнения предоставленного кода.
- Каталог документов: Укажите путь к вашему каталогу документов в фрагменте кода.

Теперь, когда всё готово, приступим к конвертации shapefile в geojson!

## Как конвертировать Shapefile в GeoJSON
Загрузите исходный Shapefile, создайте целевой слой GeoJSON, скопируйте схему атрибутов, отфильтруйте записи и запишите результаты — всё в нескольких лаконичных шагах. Полный рабочий процесс удобно помещается в один блок `using`, обеспечивая автоматическое освобождение ресурсов.

### Шаг 1: Открыть входной Shapefile
Метод `VectorLayer.Open` читает Shapefile и возвращает перечисляемую коллекцию объектов `Feature`, по которой можно итерировать.

```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```

### Шаг 2: Создать выходной GeoJSON
`VectorLayer.Create` с драйвером `Drivers.GeoJson` создаёт пустой файл GeoJSON, готовый принимать объекты.

```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```

### Шаг 3: Скопировать атрибуты между слоями
`CopyAttributes` копирует схему атрибутов (имена полей и типы данных) из исходного Shapefile в новый слой GeoJSON одним вызовом.

```csharp
outputLayer.CopyAttributes(inputLayer);
```

### Шаг 4: Обработать объекты
Итерируйте каждый объект в Shapefile, чтобы применить любую пользовательскую логику перед записью.

```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```

### Шаг 5: Фильтрация объектов по дате
В этом примере мы пропускаем записи, у которых поле `dob` (дата рождения) отсутствует или раньше 1 янв 1982 г. Настройте фильтр под свои требования к данным.

```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```

### Шаг 6: Создать новый объект (C# Generate GeoJSON File)
`Feature` представляет один пространственный элемент, содержащий геометрию и атрибутные данные.  
Здесь мы создаём новый `Feature` для слоя GeoJSON, копируем геометрию и значения атрибутов и добавляем его в вывод. Это ядро *c# generate geojson file*.

```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```

Поздравляем! Вы успешно **конвертировали shapefile в geojson** и узнали, как **копировать атрибуты между слоями** в процессе.

## Распространённые проблемы и решения
| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| Выходной файл пустой | `CopyAttributes` вызван после закрытия выходного слоя | Убедитесь, что блок `using` для `outputLayer` остаётся открытым до добавления всех объектов. |
| Фильтр даты удалил все записи | Неправильное имя поля или неожиданный формат даты | Проверьте имя атрибута (`dob`) и используйте `GetValue<string>`, если даты хранятся как строки. |
| Исключение лицензии | Запуск без действующей лицензии Aspose.GIS в продакшне | Примените временную или полную лицензию, как описано в документации Aspose. |

## Часто задаваемые вопросы
**В: Где можно найти дополнительную документацию?**  
О: Посетите [документацию Aspose.GIS](https://reference.aspose.com/gis/net/) для подробной информации.

**В: Как получить временную лицензию?**  
О: Временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/).

**В: Где можно получить поддержку?**  
О: Присоединяйтесь к [форуму Aspose.GIS](https://forum.aspose.com/c/gis/33) для общения с сообществом и обсуждения вопросов.

**В: Есть ли бесплатная пробная версия?**  
О: Да, бесплатную пробную версию можно найти [здесь](https://releases.aspose.com/).

**В: Где можно приобрести Aspose.GIS для .NET?**  
О: Приобрести продукт можно [здесь](https://purchase.aspose.com/buy).

## Заключение
В этом руководстве мы рассмотрели полный процесс **конвертации shapefile в geojson** с помощью Aspose.GIS для .NET, продемонстрировали, как **копировать атрибуты между слоями**, и показали чистый способ *c# generate geojson file*. Экспериментируйте с различными фильтрами, большими наборами данных или дополнительными преобразованиями геометрии, чтобы полностью раскрыть возможности библиотеки.

---

**Последнее обновление:** 2026-07-05  
**Тестировано с:** Aspose.GIS для .NET (последний стабильный релиз)  
**Автор:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Похожие руководства

- [Как конвертировать GeoJSON в File GDB с помощью Aspose.GIS для .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Как читать GeoJSON из потока с Aspose.GIS для .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Как конвертировать GeoJSON в TopoJSON с помощью Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}