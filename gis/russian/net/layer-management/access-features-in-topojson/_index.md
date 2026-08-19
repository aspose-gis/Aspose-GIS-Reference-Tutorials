---
date: 2026-06-25
description: Узнайте, как получить доступ к объектам TopoJSON в .NET с использованием
  Aspose.GIS для .NET — пошаговое руководство, требования и быстрые ответы.
keywords:
- access topojson features .net
- aspose gis .net
- topojson .net tutorial
linktitle: Доступ к объектам в TopoJSON
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to access TopoJSON features .NET using Aspose.GIS for .NET
    – step‑by‑step guide, prerequisites, and quick answers.
  headline: How to Access TopoJSON Features .NET with Aspose.GIS
  type: TechArticle
- questions:
  - answer: Visit the [Aspose.GIS for .NET documentation](https://reference.aspose.com/gis/net/).
    question: Where can I find more documentation?
  - answer: Download the library [here](https://releases.aspose.com/gis/net/).
    question: How can I download Aspose.GIS for .NET?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for assistance.
    question: Where can I get support for Aspose.GIS?
  - answer: Yes, you can access a free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Purchase a license [here](https://purchase.aspose.com/buy).
    question: How do I purchase a license?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Как получить доступ к объектам TopoJSON в .NET с помощью Aspose.GIS
url: /ru/net/layer-management/access-features-in-topojson/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Разблокировка функций TopoJSON с помощью Aspose.GIS для .NET

## Введение
В этом руководстве вы **будете получать доступ к функциям TopoJSON в .NET** с помощью библиотеки Aspose.GIS для .NET. Aspose.GIS позволяет читать, выполнять запросы и манипулировать широким спектром геопространственных форматов без сторонних зависимостей. К концу урока вы сможете загрузить файл TopoJSON, перечислить его функции и работать с их геометрией — всё в чистом коде C#.

## Быстрые ответы
- **Что мне нужно?** .NET 6+ (или .NET Framework 4.6.1+) и Aspose.GIS для .NET.  
- **Сколько строк кода?** Примерно 10 строк для загрузки и перебора функций.  
- **Можно ли использовать его на Linux/macOS?** Да — библиотека кросс‑платформенная.  
- **Требуется ли лицензия?** Бесплатная пробная версия подходит для разработки; для продакшена нужна коммерческая лицензия.  
- **Где найти пример данных?** Официальная документация предоставляет готовый пример TopoJSON.  

## Что такое TopoJSON?
TopoJSON — это расширение GeoJSON, которое кодирует топологию для уменьшения размера файлов и устранения избыточности. Храня общие линейные сегменты только один раз, он значительно сокращает количество дублирующихся координатных данных, делая файлы меньше и быстрее передаваемыми. Этот формат особенно полезен для масштабных карт, где многие функции делят границы, улучшая как эффективность хранения, так и производительность рендеринга.

## Почему стоит использовать Aspose.GIS для .NET для доступа к функциям TopoJSON?
Aspose.GIS поддерживает **30+ векторных и растровых форматов** и может обрабатывать файлы до **2 ГБ**, не загружая весь документ в память. API предоставляет строго типизированные объекты, запросы в стиле LINQ и развертывание без зависимостей, обеспечивая высокую производительность в серверных сценариях. Кроме того, встроенная обработка топологии упрощает работу с TopoJSON, позволяя разработчикам сосредоточиться на бизнес‑логике, а не на низкоуровневом парсинге.

## Предварительные требования
- Знание C# и .NET.  
- Библиотека Aspose.GIS для .NET установлена. Вы можете скачать её [здесь](https://releases.aspose.com/gis/net/).  
- Пример файла TopoJSON для тестирования. Вы можете найти его в [документации](https://reference.aspose.com/gis/net/).

## Импорт пространств имён
Начните с импорта необходимых пространств имён в ваш код C#:
```csharp
using Aspose.Gis;
using System;
using System.Text;
```

## Как получить доступ к функциям TopoJSON в .NET?
`TopoJsonDataSource` — класс, представляющий файл TopoJSON как источник данных, позволяющий выборочно читать его содержимое. Загрузите файл TopoJSON с помощью `new TopoJsonDataSource("file.topojson")` и вызовите `GetFeatureCollection()` — это вернёт коллекцию, которую можно перебрать для чтения свойств и геометрии каждой функции. Операция читает только необходимые части файла, поддерживая низкое потребление памяти даже для многомегабайтных наборов данных.

### Шаг 1: Настройте ваш проект
Начните с создания нового проекта C# и добавления Aspose.GIS для .NET в качестве ссылки. Убедитесь, что ваш проект нацелен на .NET 6 (или совместимую платформу) и что пакет NuGet `Aspose.GIS` установлен.

### Шаг 2: Загрузите данные TopoJSON
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
string sampleTopoJsonPath = dataDir + "sample.topojson";
StringBuilder builder = new StringBuilder();
// Open the TopoJSON file
using (VectorLayer layer = VectorLayer.Open(sampleTopoJsonPath, Drivers.TopoJson))
{
    // Iterate through each feature in the layer
    foreach (Feature feature in layer)
    {
        // get id property
        int id = feature.GetValue<int>("id");
        // get name of the object that contains this feature
        string objectName = feature.GetValue<string>("topojson_object_name");
        // get name attribute property, located inside 'properties' object
        string name = feature.GetValue<string>("name");
        // get geometry of the feature.
        string geometry = feature.Geometry.AsText();
        // Build the output string
        builder.AppendFormat("Feature with ID {0}:\n", id);
        builder.AppendFormat("Object Name = {0}\n", objectName);
        builder.AppendFormat("Name        = {0}\n", name);
        builder.AppendFormat("Geometry    = {0}\n", geometry);
    }
}
// Display the output
Console.WriteLine("Output:");
Console.WriteLine(builder.ToString());
```

## Распространённые проблемы и решения
- **Ошибка «Файл не найден»** – Проверьте правильность пути и наличие прав чтения у файла.  
- **Неподдерживаемый тип геометрии** – В текущей версии Aspose.GIS поддерживает Point, LineString, Polygon, MultiPolygon и т.д.; пользовательские расширения могут потребовать преобразования в поддерживаемый тип.  
- **Производительность при работе с большими файлами** – Используйте `TopoJsonDataSource.LoadPartial()` для чтения только необходимых подмножеств функций.

## Часто задаваемые вопросы

**Q: Где я могу найти более подробную документацию?**  
A: Посетите [документацию Aspose.GIS для .NET](https://reference.aspose.com/gis/net/).

**Q: Как я могу скачать Aspose.GIS для .NET?**  
A: Скачайте библиотеку [здесь](https://releases.aspose.com/gis/net/).

**Q: Где я могу получить поддержку Aspose.GIS?**  
A: Присоединяйтесь к [форуму Aspose.GIS](https://forum.aspose.com/c/gis/33) для получения помощи.

**Q: Доступна ли бесплатная пробная версия?**  
A: Да, вы можете получить бесплатную пробную версию [здесь](https://releases.aspose.com/).

**Q: Как приобрести лицензию?**  
A: Приобретите лицензию [здесь](https://purchase.aspose.com/buy).

## Заключение
Поздравляем! Вы успешно получили доступ к функциям TopoJSON в .NET с помощью Aspose.GIS для .NET. Это руководство охватило основные шаги — настройку проекта, загрузку файла TopoJSON и перебор его коллекции функций. Изучайте API дальше, чтобы выполнять пространственные запросы, преобразовывать геометрии и экспортировать в другие форматы.

---

**Last Updated:** 2026-06-25  
**Tested With:** Aspose.GIS 23.10 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Как конвертировать GeoJSON в TopoJSON с помощью Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Получить атрибуты слоя – извлечение информации об атрибутах слоя с помощью Aspose.GIS для .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Как обрезать функции слоя с помощью Aspose.GIS для .NET](/gis/net/layer-management/crop-layer-features/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}