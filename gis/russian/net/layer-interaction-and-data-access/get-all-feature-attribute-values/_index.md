---
date: 2026-01-05
description: Изучите, как читать shapefile в C# с помощью Aspose.GIS для .NET, получать
  все значения атрибутов объектов и эффективно выводить атрибуты.
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: Чтение Shapefile в C# – Получить все значения атрибутов объектов
url: /ru/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Получить все значения атрибутов объектов

## Введение
Добро пожаловать в мир геопространственной разработки с Aspose.GIS for .NET! В этом руководстве вы узнаете **how to read shapefile C#** и получите каждое значение атрибута из его объектов. Независимо от того, создаёте ли вы приложение картографирования или обрабатываете пространственные данные пакетно, освоение извлечения атрибутов необходимо. Давайте погрузимся и посмотрим код в действии.

## Быстрые ответы
- **Что делает этот код?** Он открывает Shapefile и читает все, некоторые или выгруженные значения атрибутов каждого объекта.  
- **Какая библиотека требуется?** Aspose.GIS for .NET (compatible with .NET Framework and .NET Core).  
- **Нужна ли лицензия?** A temporary license works for testing; a full license is required for production.  
- **Можно ли читать другие форматы?** Yes – the same API supports GeoJSON, KML, and many more.  
- **Как выгрузить атрибуты?** Use `feature.GetValuesDump()` to obtain a flexible object array.

## Что такое “read shapefile C#”?
Чтение Shapefile в C# означает открытие файла .shp с помощью GIS‑библиотеки, итерацию по его векторным объектам и доступ к данным атрибутов, хранящимся в сопутствующем файле .dbf. Aspose.GIS абстрагирует низкоуровневую работу с файлами, позволяя сосредоточиться на нужных вам значениях атрибутов.

## Почему использовать Aspose.GIS для чтения атрибутов?
- **Simple API** – Простой API – интуитивные методы, такие как `GetValues` и `GetValuesDump`.  
- **Cross‑platform** – Кросс‑платформенный – работает на Windows, Linux и macOS с .NET Core.  
- **Rich format support** – Широкая поддержка форматов – работа с Shapefile, GeoJSON, GML и другими без дополнительных плагинов.  
- **Performance‑optimized** – Оптимизированная производительность – быстрая итерация по большим наборам данных.

## Предварительные требования
Перед тем как отправиться в это захватывающее путешествие, убедитесь, что у вас есть следующие требования:
- Aspose.GIS for .NET: загрузите и установите библиотеку со страницы [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).
- Среда разработки: настройте .NET‑среду разработки, например Visual Studio.
- Shapefile: подготовьте пример Shapefile (например, "InputShapeFile.shp") в каталоге вашего документа.

## Импорт пространств имён
В вашем C# коде начните с импорта необходимых пространств имён, чтобы использовать возможности Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

## Шаг 1: Установить каталог документов
```csharp
string dataDir = "Your Document Directory";
```
Замените "Your Document Directory" на фактический путь, где находится ваш Shapefile.

## Шаг 2: Открыть VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
На этом этапе открывается Shapefile с помощью Aspose.GIS, указывая путь к файлу и формат (в данном случае Shapefile).

## Шаг 3: Получить все значения атрибутов объектов
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
Фрагмент кода показывает **how to read attributes** для каждого объекта, загружая их в массив фиксированного размера.

## Шаг 4: Получить несколько значений атрибутов объектов
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
Здесь демонстрируется **how to read specific attribute values**, когда вам нужен только подмножество полей.

## Шаг 5: Получить значения атрибутов как выгрузку объектов
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
Этот последний шаг демонстрирует **how to dump attributes** с помощью `GetValuesDump()`, который возвращает гибкую коллекцию, которую можно просмотреть или сериализовать.

## Распространённые проблемы и решения
- **Несоответствие размера массива** – Убедитесь, что массив, передаваемый в `GetValues`, соответствует количеству ожидаемых атрибутов; иначе вы получите `null` элементы.  
- **Файл не найден** – Проверьте, что `dataDir` указывает на правильную папку и имя Shapefile написано точно.  
- **Исключение лицензии** – Если появляется ошибка лицензирования, примените временную или полную лицензию перед вызовом любых методов API.

## Часто задаваемые вопросы
### Совместим ли Aspose.GIS с .NET Core?
Да, Aspose.GIS полностью совместим с .NET Core, позволяя создавать кросс‑платформенные приложения.

### Можно ли работать с разными GIS‑форматами файлов, используя Aspose.GIS?
Абсолютно! Aspose.GIS поддерживает различные форматы, включая Shapefile, GeoJSON и многие другие.

### Есть ли форум сообщества для поддержки Aspose.GIS?
Да, вы можете получить помощь и пообщаться с сообществом Aspose.GIS на [support forum](https://forum.aspose.com/c/gis/33).

### Как получить временную лицензию для Aspose.GIS?
Вы можете получить временную лицензию для тестирования [здесь](https://purchase.aspose.com/temporary-license/).

### Где найти подробную документацию по Aspose.GIS?
Подробная документация доступна [здесь](https://reference.aspose.com/gis/net/).

### Как получить только атрибут “Name” из каждого объекта?
Используйте `GetValues` с массивом размером в один элемент и передайте индекс поля “Name”, либо вызовите `feature["Name"]` напрямую.

### В чём разница между `GetValues` и `GetValuesDump`?
`GetValues` заполняет предварительно выделенный массив сырыми значениями, тогда как `GetValuesDump` возвращает массив объектов, который можно перечислять без предварительного знания схемы.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Последнее обновление:** 2026-01-05  
**Тестировано с:** Aspose.GIS for .NET (latest release)  
**Автор:** Aspose  

---