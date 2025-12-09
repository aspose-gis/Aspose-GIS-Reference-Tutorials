---
date: 2025-12-06
description: Узнайте, как преобразовать GeoJSON в TopoJSON с группировкой, установить
  атрибут имени объекта и сгруппировать объекты GeoJSON с помощью Aspose.GIS для .NET.
linktitle: How to Convert GeoJSON to TopoJSON with Grouping using Aspose.GIS
second_title: Aspose.GIS .NET API
title: Как конвертировать GeoJSON в TopoJSON с группировкой с помощью Aspose.GIS
url: /ru/net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как преобразовать GeoJSON в TopoJSON с группировкой с помощью Aspose.GIS

## Введение

В этом пошаговом руководстве вы узнаете **как преобразовать GeoJSON**‑файлы в TopoJSON, группируя объекты на основе выбранного атрибута. Использование Aspose.GIS .NET API делает преобразование быстрым, надёжным и полностью управляемым из вашего кода на C#. Независимо от того, создаёте ли вы сервис конвертации GeoJSON на ASP.NET или настольный GIS‑инструмент, это руководство покажет, что именно нужно сделать.

## Быстрые ответы
- **Какая библиотека обрабатывает преобразование?** Aspose.GIS for .NET  
- **Сколько времени занимает реализация?** Обычно 5‑10 минут для базовой настройки  
- **Нужна ли лицензия для продакшн?** Да, требуется коммерческая лицензия (доступна бесплатная пробная версия)  
- **Можно ли группировать объекты по любому атрибуту?** Да – установите `ObjectNameAttribute` в поле, по которому хотите группировать  
- **Поддерживается ли .NET Core?** Абсолютно – API работает с .NET Core, .NET 5/6 и классическим .NET Framework  

## Что такое GeoJSON и TopoJSON?

GeoJSON — это широко используемый формат JSON для кодирования географических объектов, таких как точки, линии и полигоны. TopoJSON расширяет GeoJSON, хранит топологию (общие отрезки линий), что уменьшает размер файлов и повышает производительность отрисовки сложных карт. Преобразование между ними часто требуется, когда нужны компактные данные карты для веб‑визуализаций.

## Зачем группировать объекты GeoJSON?

Группировка (`group geojson features`) позволяет организовать связанные геометрии под одним именованным объектом в результирующем TopoJSON. Это особенно полезно, когда:
- Вы хотите создать отдельные слои для разных административных регионов.  
- Ваша клиентская библиотека карт ожидает именованные объекты для стилизации или взаимодействия.  
- Нужно уменьшить дублирование, разделяя границы между соседними объектами.

## Предварительные требования

Перед началом убедитесь, что у вас есть следующее:

1. **Aspose.GIS for .NET** – скачайте и установите с официального сайта [здесь](https://releases.aspose.com/gis/net/).  
2. **Среда разработки** – Visual Studio, Visual Studio Code или любой IDE, поддерживающий C#.  
3. **Пример файла GeoJSON** – файл, содержащий объекты, которые вы хотите конвертировать.  

## Импорт пространств имён

Сначала подключите необходимые пространства имён в вашем проекте:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```

## Пошаговое руководство

### Шаг 1: Определите пути к файлам

Укажите, где находится исходный GeoJSON и куда следует записать TopoJSON:

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

> **Pro tip:** Используйте `Path.Combine` для кросс‑платформенного построения путей, если вы целитесь в .NET Core.

### Шаг 2: Настройте параметры конвертации (установите атрибут имени объекта)

Создайте экземпляр `ConversionOptions` и укажите Aspose.GIS, как группировать объекты:

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // Specify the attribute in GeoJSON layer by which we are going to group into objects
        ObjectNameAttribute = "group",
        // Specify the default object name for features with unknown attribute values
        DefaultObjectName = "unnamed",
    }
};
```

Замените `"group"` на фактическое имя свойства в вашем GeoJSON, которое вы хотите использовать для **geojson feature grouping**. Параметр `DefaultObjectName` гарантирует, что каждый объект попадёт в объект TopoJSON, даже если атрибут отсутствует.

### Шаг 3: Выполните преобразование (конвертировать GeoJSON в TopoJSON)

Запустите конвертацию одним вызовом API:

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

После выполнения `convertedSampleWithGrouping_out.topojson` будет содержать представление TopoJSON с объектами, сгруппированными согласно указанному атрибуту.

## Распространённые проблемы и их устранение

| Симптом | Вероятная причина | Решение |
|---------|-------------------|---------|
| **Все объекты попадают в “unnamed”** | `ObjectNameAttribute` не соответствует ни одному свойству в GeoJSON | Проверьте точное имя свойства (чувствительно к регистру) и обновите параметр |
| **Файл вывода пустой** | Неправильный путь к файлу или отсутствие прав на чтение | Используйте абсолютные пути или убедитесь, что приложение имеет доступ к файловой системе |
| **Преобразование бросает `NotSupportedException`** | Попытка конвертировать GeoJSON с неподдерживаемыми типами геометрий (например, GeometryCollection) | Упростите исходные данные или обновите до последней версии Aspose.GIS |

## Часто задаваемые вопросы

**В: Можно ли группировать объекты по нескольким атрибутам?**  
**О:** Да, вы можете конкатенировать несколько полей в один виртуальный атрибут или выполнить несколько проходов конвертации с разными значениями `ObjectNameAttribute`.

**В: Совместим ли Aspose.GIS с ASP.NET Core?**  
**О:** Абсолютно – библиотека работает с ASP.NET Core, .NET 5, .NET 6 и классическим .NET Framework.

**В: Можно ли конвертировать другие географические форматы, кроме GeoJSON?**  
**О:** Да, Aspose.GIS поддерживает Shapefile, KML, GML, CSV и многие другие форматы как для импорта, так и для экспорта.

**В: Предлагает ли Aspose.GIS бесплатную пробную версию?**  
**О:** Да, вы можете получить бесплатную пробную версию Aspose.GIS [здесь](https://releases.aspose.com/).

**В: Где можно получить поддержку по Aspose.GIS?**  
**О:** Вы можете получить поддержку на форуме сообщества Aspose.GIS [здесь](https://forum.aspose.com/c/gis/33).

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2025-12-06  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

---