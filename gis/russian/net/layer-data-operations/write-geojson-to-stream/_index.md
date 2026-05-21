---
date: 2026-05-21
description: Узнайте, как записать GeoJSON в поток, используя Aspose.GIS для .NET.
  Этот учебник по geojson .net демонстрирует пошаговое преобразование точек и генерацию
  кода GeoJSON на C#.
keywords:
- how to write geojson
- convert points geojson
- geojson tutorial .net
- generate geojson c#
linktitle: Записать GeoJSON в поток
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to write GeoJSON to stream using Aspose.GIS for .NET. This
    geojson tutorial .net shows step‑by‑step conversion of points and generation of
    GeoJSON C# code.
  headline: How to Write GeoJSON to Stream with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Как записать GeoJSON в поток с помощью Aspose.GIS для .NET
url: /ru/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Записать GeoJSON в поток

## Введение
В этом руководстве вы узнаете **как записать GeoJSON в поток** в приложении .NET с использованием Aspose.GIS. Мы пройдем каждый шаг, от настройки окружения до вывода корректного документа GeoJSON, чтобы вы могли бесшовно интегрировать геопространственные данные в свои сервисы.

## Быстрые ответы
- **Какой основной класс для вывода GeoJSON?** `VectorLayer` с `GeoJsonDriver`.
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для разработки; коммерческая лицензия требуется для продакшна.
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Можно ли преобразовать коллекцию точек в GeoJSON?** Да — используйте класс `Feature` и определите геометрию точки.
- **Поддерживается ли потоковая запись для больших наборов данных?** Абсолютно; `MemoryStream` позволяет записывать без промежуточных файлов.

## Что такое GeoJSON?
GeoJSON — это открытый стандартный формат для кодирования различных географических структур данных с использованием JSON. Он определяет объекты, такие как FeatureCollection, Feature и типы геометрий (Point, LineString, Polygon). Это легковесное, веб‑дружественное представление обеспечивает простой обмен и визуализацию пространственных данных на многих платформах и языках программирования.

## Почему использовать Aspose.GIS для генерации GeoJSON?
Aspose.GIS поддерживает более 30 пространственных форматов файлов и может обрабатывать файлы размером более 2 ГБ без загрузки всего документа в память. Его высокопроизводительный потоковый движок записывает GeoJSON непосредственно в потоки, снижая нагрузку ввода‑вывода. Это делает его идеальным для корпоративных геопространственных нагрузок, облачных сервисов и приложений в реальном времени.

## Предварительные требования
Прежде чем приступить к руководству, убедитесь, что у вас есть следующие предварительные требования:
1. Библиотека Aspose.GIS для .NET: Убедитесь, что библиотека Aspose.GIS для .NET установлена. Вы можете скачать её [здесь](https://releases.aspose.com/gis/net/).
2. Каталог документов: Создайте каталог документов в вашем проекте и запомните его путь.

Теперь давайте начнём руководство!

## Как записать GeoJSON в поток?
VectorLayer представляет векторный набор данных, который может быть сохранён в различных форматах, включая GeoJSON.  
GeoJsonDriver — драйвер, используемый Aspose.GIS для чтения и записи файлов GeoJSON.  
`layer.Save` записывает содержимое слоя в предоставленный поток, используя указанные параметры сохранения.  

Загрузите `VectorLayer` с `GeoJsonDriver`, добавьте объекты, содержащие точечную геометрию, а затем вызовите `layer.Save(stream, new GeoJsonSaveOptions())`. Это записывает полноценный, соответствующий стандартам документ GeoJSON непосредственно в предоставленный `MemoryStream` всего за несколько строк кода. Метод сериализует коллекцию объектов, автоматически обрабатывая атрибутные данные и преобразование геометрии, так что вы получаете готовый к использованию JSON‑payload без ручного формирования строк.

## Импорт пространств имён
Прежде всего, убедитесь, что включили необходимые пространства имён для доступа к функционалу Aspose.GIS в вашем коде:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Шаг 1: Настройка каталога документов
```csharp
string dataDir = "Your Document Directory";
```
Замените "Your Document Directory" фактическим путём к вашему каталогу документов.

## Шаг 2: Создание Memory Stream
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Шаг 3: Создание Vector Layer с драйвером GeoJSON
Класс `VectorLayer` представляет векторный набор данных, который может быть сохранён в различных форматах, включая GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Шаг 4: Определение атрибутов Feature
Определите схему атрибутов для ваших объектов (например, ID, Name).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Шаг 5: Создание и добавление объектов
Создайте объекты `Feature`, назначьте точечную геометрию, задайте значения атрибутов и добавьте их в слой.  
```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Шаг 6: Отображение вывода GeoJSON
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Поздравляем! Вы успешно записали GeoJSON в поток с помощью Aspose.GIS для .NET.

## Распространённые проблемы и решения
- **Поток вывода пуст:** Убедитесь, что вы сбрасываете позицию потока (`stream.Position = 0`) перед чтением.
- **Неправильный порядок координат:** GeoJSON ожидает порядок долгота‑широта; проверьте значения ваших точек.
- **Большие наборы данных:** Используйте `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` для поэтапной записи объектов.

## Часто задаваемые вопросы
### Могу ли я использовать Aspose.GIS для .NET в средах Windows и Linux?
Да, Aspose.GIS для .NET совместим как с Windows, так и с Linux.

### Доступна ли бесплатная пробная версия?
Конечно! Вы можете ознакомиться с бесплатной пробной версией [здесь](https://releases.aspose.com/).

### Где найти подробную документацию?
Посмотрите документацию [здесь](https://reference.aspose.com/gis/net/).

### Как получить временную лицензию?
Временные лицензии доступны [здесь](https://purchase.aspose.com/temporary-license/).

### Нужна помощь или есть дополнительные вопросы?
Посетите наш форум поддержки [здесь](https://forum.aspose.com/c/gis/33).

**Q: Могу ли я генерировать GeoJSON из коллекции точек широты/долготы?**  
A: Да — создайте `Feature` для каждой точки, назначьте геометрию `Point` и добавьте её в `VectorLayer`.  

**Q: Поддерживает ли Aspose.GIS запись сжатого GeoJSON (gzip)?**  
A: Вы можете обернуть `MemoryStream` в `GZipStream` перед сохранением, чтобы получить сжатый payload.  

**Q: Какой максимальный размер файла GeoJSON может обрабатывать Aspose.GIS?**  
A: Библиотека может потоково записывать файлы более 2 ГБ; использование памяти остаётся низким, поскольку данные записываются поэтапно.  

---

**Последнее обновление:** 2026-05-21  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Как прочитать GeoJSON из потока с Aspose.GIS для .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Как преобразовать GeoJSON в TopoJSON с Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Как преобразовать Shapefile в GeoJSON с помощью Aspose.GIS для .NET](/gis/net/layer-management/extract-features-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}