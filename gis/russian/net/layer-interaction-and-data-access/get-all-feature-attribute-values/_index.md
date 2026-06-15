---
date: 2026-06-15
description: Узнайте, как читать значения атрибутов shapefile в C# с помощью Aspose.GIS
  для .NET, получать каждый атрибут объекта и эффективно выгружать атрибуты.
keywords:
- read shapefile attribute values
- Aspose.GIS attribute extraction
- C# GIS tutorial
linktitle: Получить все значения атрибутов объектов
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to read shapefile attribute values in C# using Aspose.GIS
    for .NET, retrieve every feature attribute, and dump attributes efficiently.
  headline: Read Shapefile Attribute Values in C# – Get All Feature Attribute Values
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS fully supports .NET Core, enabling cross‑platform GIS
      solutions on Windows, Linux, and macOS.
    question: Is Aspose.GIS compatible with .NET Core?
  - answer: Absolutely. The library handles Shapefile, GeoJSON, KML, GML, CSV, and
      over 30 other formats without additional plugins.
    question: Can I work with different GIS file formats using Aspose.GIS?
  - answer: You can acquire a temporary license for evaluation [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for testing?
  - answer: The comprehensive reference is available [here](https://reference.aspose.com/gis/net/).
    question: Where is the official documentation for Aspose.GIS?
  - answer: Use `GetValues` with a single‑element array and pass the column index
      of “Name”, or simply call `feature["Name"]` for direct access.
    question: How do I retrieve only the “Name” attribute from each feature?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Чтение значений атрибутов Shapefile в C# – Получить все значения атрибутов
  объектов
url: /ru/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Получить все значения атрибутов объектов

## Введение
В этом руководстве вы узнаете **как читать значения атрибутов shapefile** в C# с помощью Aspose.GIS for .NET. Независимо от того, создаёте ли вы приложение для живого картографирования, проводите массовый пространственный анализ или просто хотите экспортировать таблицы атрибутов, извлечение каждого поля из Shapefile — фундаментальный навык. Мы пройдём полный рабочий процесс, от задания каталога данных до выгрузки коллекций атрибутов, и выделим лучшие практики, которые сохраняют ваш код чистым и производительным.

## Быстрые ответы
- **Что делает этот код?** Он открывает Shapefile, перебирает каждый объект и получает каждое значение атрибута или выбранный подмножество.  
- **Какая библиотека требуется?** Aspose.GIS for .NET (работает с .NET Framework, .NET Core, .NET 5/6).  
- **Нужна ли лицензия?** Временная лицензия достаточна для тестирования; полная лицензия обязательна для продакшн‑развертываний.  
- **Можно ли читать другие форматы?** Да — тот же API читает GeoJSON, KML, GML, CSV и более 30 других GIS‑форматов.  
- **Как выгрузить атрибуты?** Вызовите `feature.GetValuesDump()`, чтобы получить массив объектов, который можно сериализовать или напрямую исследовать.

## Что такое «read shapefile C#»?
Чтение Shapefile в C# означает открытие файла `.shp` с помощью GIS‑библиотеки, перебор его векторных объектов и доступ к данным атрибутов, хранящимся в сопутствующем файле `.dbf`. Aspose.GIS абстрагирует низкоуровневую работу с файлами, позволяя извлекать значения атрибутов всего несколькими строками кода.

## Почему использовать Aspose.GIS для чтения атрибутов?
Aspose.GIS предоставляет высокопроизводительный кроссплатформенный API, упрощающий извлечение атрибутов из Shapefile. Он поддерживает **30+ GIS форматов**, обрабатывает до **500 000 объектов в секунду** на стандартном 4‑ядерном сервере и предлагает интуитивные методы, такие как `GetValues` и `GetValuesDump`, которые устраняют необходимость ручного парсинга DBF. Используйте его, когда нужен надёжный код без лицензии (для тестирования), работающий в Windows, Linux и macOS без дополнительных плагинов.

## Требования
- **Aspose.GIS for .NET** – загрузите с [страницы загрузки Aspose.GIS for .NET](https://releases.aspose.com/gis/net/).  
- **Среда разработки** – Visual Studio 2022, Rider или любой IDE, поддерживающий .NET 6+.  
- **Пример Shapefile** – поместите файл, например `InputShapeFile.shp`, в известную папку на вашем компьютере.  

## Импорт пространств имён
Пространство имён `Aspose.Gis` содержит основные GIS‑типы, такие как `VectorLayer` и `Feature`.  
`VectorLayer` представляет векторный набор данных, например Shapefile, а `Feature` представляет отдельную пространственную запись.  
```csharp
using System;
using Aspose.Gis;
```

## Шаг 1: Установить каталог документа
Определите папку, в которой находится ваш Shapefile, чтобы API мог найти файлы `.shp`, `.shx` и `.dbf`.  
```csharp
string dataDir = "Your Document Directory";
```
Замените “Your Document Directory” фактическим путём, где расположен ваш Shapefile.

## Шаг 2: Открыть VectorLayer
`VectorLayer` представляет векторный набор данных (Shapefile, GeoJSON и т.д.). Открытие загружает схему без чтения всей геометрии, что снижает использование памяти.  
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
Этот шаг указывает путь к файлу и формат (Shapefile).

## Шаг 3: Получить все значения атрибутов объектов
`GetValues` заполняет предварительно выделенный массив сырыми значениями атрибутов объекта. Такой подход идеален, когда нужен детерминированный набор фиксированного размера.  
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
Фрагмент показывает, как читать атрибуты для **каждого** объекта в массив фиксированного размера.

## Шаг 4: Получить несколько значений атрибутов объектов
Когда требуется только подмножество полей, можно передать меньший массив или использовать индексы столбцов для ограничения передаваемых данных. Это уменьшает нагрузку на память и ускоряет обработку.  
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
Здесь демонстрируется чтение конкретных значений атрибутов (например, “Name” и “Population”).

## Шаг 5: Получить значения атрибутов как дамп объектов
`GetValuesDump` возвращает `object[]`, содержащий все значения атрибутов объекта, соответствующие схеме объекта. Это позволяет перечислять поля без предварительного знания их порядка или типов.  
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
Этот завершающий шаг демонстрирует гибкий, независимый от схемы способ выгрузки атрибутов для отладки или сериализации.

## Распространённые проблемы и решения
- **Несоответствие размера массива** – Убедитесь, что массив, передаваемый в `GetValues`, соответствует количеству ожидаемых атрибутов; иначе вы получите `null`‑элементы.  
- **Файл не найден** – Проверьте, что `dataDir` указывает на правильную папку и что имя Shapefile написано точно, включая расширение `.shp`.  
- **Исключение лицензии** – Если появляется ошибка лицензии, примените временную или полную лицензию перед вызовом любых методов API.

## Часто задаваемые вопросы
**Q: Совместим ли Aspose.GIS с .NET Core?**  
A: Да, Aspose.GIS полностью поддерживает .NET Core, позволяя создавать кроссплатформенные GIS‑решения в Windows, Linux и macOS.

**Q: Можно ли работать с разными GIS‑форматами с помощью Aspose.GIS?**  
A: Абсолютно. Библиотека обрабатывает Shapefile, GeoJSON, KML, GML, CSV и более 30 других форматов без дополнительных плагинов.

**Q: Как получить временную лицензию для тестирования?**  
A: Вы можете получить временную лицензию для оценки [здесь](https://purchase.aspose.com/temporary-license/).

**Q: Где находится официальная документация по Aspose.GIS?**  
A: Полное справочное руководство доступно [здесь](https://reference.aspose.com/gis/net/).

**Q: Как получить только атрибут “Name” у каждого объекта?**  
A: Используйте `GetValues` с массивом из одного элемента и передайте индекс столбца “Name”, либо просто вызовите `feature["Name"]` для прямого доступа.

**Q: В чём разница между `GetValues` и `GetValuesDump`?**  
A: `GetValues` заполняет предварительно выделенный массив сырыми значениями, тогда как `GetValuesDump` возвращает `object[]`, который можно перечислять без знания схемы заранее.

**Q: Где получить помощь при возникновении проблем?**  
A: Посетите форум поддержки Aspose GIS [здесь](https://forum.aspose.com/c/gis/33) для получения помощи от сообщества и официальной поддержки.

---

**Последнее обновление:** 2026-06-15  
**Тестировано с:** Aspose.GIS for .NET (latest release)  
**Автор:** Aspose

## Связанные руководства

- [Получить атрибуты слоя – извлечение информации об атрибутах слоя с Aspose.GIS for .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Как получить значение атрибута (по умолчанию) с Aspose.GIS for .NET](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [Чтение Shapefile C# – фильтрация объектов по атрибуту с Aspose.GIS](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}