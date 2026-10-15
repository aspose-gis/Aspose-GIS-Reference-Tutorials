---
date: 2026-10-15
description: Узнайте, как создать geojson из координат и записать его в поток с помощью
  Aspose.GIS for .NET. Этот учебник показывает пошаговое преобразование точек и генерацию
  кода GeoJSON на C#.
keywords:
- create geojson from coordinates
- stream large geojson files
- write geojson to stream
- geojson tutorial c#
- compress geojson with gzip
lastmod: 2026-10-15
linktitle: Записать GeoJSON в поток
og_description: Узнайте, как создать geojson из координат и записать его в поток с
  помощью Aspose.GIS for .NET – пошаговое руководство для больших наборов данных.
og_image_alt: Screenshot of Aspose.GIS code generating GeoJSON stream in C#
og_title: Создать geojson из координат, записать в поток в .NET
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create geojson from coordinates and write it to a stream
    using Aspose.GIS for .NET. This tutorial shows step‑by‑step conversion of points
    and generation of GeoJSON C# code.
  headline: Create geojson from coordinates, write to a stream in .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET geospatial
- C# stream processing
- GIS data conversion
title: Создать geojson из координат, записать в поток в .NET
url: /ru/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать geojson из координат и записать в поток

## Введение
В этом руководстве вы узнаете **как создать geojson из координат** и записать его напрямую в поток с помощью Aspose.GIS для .NET. Мы пройдём настройку окружения, создание слоя, заполнение объектов и потоковую запись результата, чтобы вы могли внедрять геопространственные полезные нагрузки в API, облачные функции или сервисы без файлов, без временных файлов.

## Быстрые ответы
- **Какой класс записывает GeoJSON в поток?** `VectorLayer` вместе с `GeoJsonDriver`.
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для разработки; для продакшн‑использования требуется коммерческая лицензия.
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Можно ли преобразовать коллекцию точек в GeoJSON?** Да — создайте `Feature` для каждой точки и назначьте геометрию `Point`.
- **Подходит ли потоковая запись для больших наборов данных?** Абсолютно — `MemoryStream` позволяет записывать GeoJSON гигабайтного масштаба без загрузки всего файла в память.

## Что такое GeoJSON?
GeoJSON — открытый формат на основе JSON для кодирования географических объектов, таких как точки, линии и полигоны. Он состоит из `FeatureCollection`, который группирует отдельные объекты `Feature`, каждый из которых содержит геометрию и атрибутные данные. Благодаря своей лёгкости и веб‑дружелюбности, GeoJSON является де‑факто стандартом обмена пространственными данными между браузерами, GIS‑серверами и мобильными приложениями.

## Почему использовать Aspose.GIS для генерации geojson?
Aspose.GIS поддерживает **более 35 пространственных форматов** и может потоково записывать файлы размером более **2 ГБ**, удерживая потребление памяти ниже **50 МБ**. Его высокопроизводительный потоковый движок записывает GeoJSON напрямую в любой .NET `Stream`, устраняя необходимость во временных файлах и снижая задержку ввода‑вывода до **70 %** в типичных облачных сценариях.

## Требования
Перед началом убедитесь, что у вас есть:

1. **Aspose.GIS для .NET** установлен. Скачайте пакет **Aspose.GIS для .NET** [здесь](https://releases.aspose.com/gis/net/).
2. Папка, в которую ваш проект может записывать файлы, если это понадобится.
3. Среда выполнения .NET 5+ или .NET Core 3.1+.

Теперь давайте перейдём к реализации.

## Как создать geojson из координат и записать в поток?
`VectorLayer` представляет набор векторных данных в памяти, который можно сохранить в различных форматах.  
`GeoJsonDriver` — драйвер, позволяющий читать и записывать файлы GeoJSON.  

Загрузите `VectorLayer` с помощью `GeoJsonDriver`, добавьте объекты `Feature` с геометрией `Point` и вызовите `layer.Save(stream, new GeoJsonSaveOptions())`. Этот один вызов сериализует всю коллекцию объектов в соответствующий стандарту документ GeoJSON, находящийся в переданном `MemoryStream`. Процесс автоматически обрабатывает сопоставление атрибутов и преобразование координат, так что вы получаете готовый JSON‑payload без ручного построения строк.

### Определения
**VectorLayer** — основной объект Aspose.GIS, представляющий изменяемый векторный набор данных в памяти.  
**GeoJsonDriver** — драйвер, отвечающий за чтение и запись файлов GeoJSON.  

## Импорт пространств имён
Сначала убедитесь, что включили необходимые пространства имён для доступа к функционалу Aspose.GIS в вашем коде:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Шаг 1: настройка каталога документов
Создайте путь к папке, где Aspose.GIS может хранить вспомогательные файлы при необходимости.  
```csharp
string dataDir = "Your Document Directory";
```
Замените «Your Document Directory» на фактический путь к вашему каталогу документов.

## Шаг 2: создание MemoryStream
`MemoryStream` предоставляет буфер в памяти, который можно отправлять напрямую по HTTP или сохранять в облачное хранилище.  
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Шаг 3: создание векторного слоя с драйвером GeoJSON
Класс `VectorLayer` представляет векторный набор данных, который можно сохранять в различных форматах, включая GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Шаг 4: определение атрибутов объектов
Определите схему атрибутов для ваших объектов (например, ID, Name).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Шаг 5: создание и добавление объектов
Создайте объекты `Feature`, назначьте им геометрию точки, задайте значения атрибутов и добавьте их в слой.  
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

## Шаг 6: отображение вывода GeoJSON
После сохранения сбросьте позицию потока и прочитайте строку JSON для проверки или передачи.  
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Поздравляем! Вы успешно создали geojson из координат и записали его в поток с помощью Aspose.GIS для .NET.

## Распространённые проблемы и решения
- **Поток вывода пустой:** Убедитесь, что вы сбросили позицию потока (`stream.Position = 0`) перед чтением.
- **Неправильный порядок координат:** GeoJSON ожидает порядок долгота‑широта; проверьте значения точек.
- **Большие наборы данных:** Используйте `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` для поэтапной записи объектов и снижения потребления памяти.

## Часто задаваемые вопросы

**В: Можно ли использовать Aspose.GIS для .NET как в Windows, так и в Linux?**  
О: Да, Aspose.GIS для .NET работает на Windows, Linux и macOS с полной поддержкой .NET Core.

**В: Доступна ли бесплатная пробная версия?**  
О: Абсолютно! Вы можете изучить **страницу загрузки бесплатной пробной версии** [здесь](https://releases.aspose.com/).

**В: Где найти подробную документацию?**  
О: См. **документацию Aspose.GIS .NET** [здесь](https://reference.aspose.com/gis/net/).

**В: Как получить временную лицензию?**  
О: Временные лицензии доступны на **странице временных лицензий** [здесь](https://purchase.aspose.com/temporary-license/).

**В: Нужна помощь или есть дополнительные вопросы?**  
О: Посетите наш **форум поддержки GIS** [здесь](https://forum.aspose.com/c/gis/33).

**В: Можно ли генерировать GeoJSON из коллекции точек широта/долгота?**  
О: Да — создайте `Feature` для каждой точки, назначьте геометрию `Point` и добавьте её в `VectorLayer`.

**В: Поддерживает ли Aspose.GIS запись сжатого GeoJSON (gzip)?**  
О: Вы можете обернуть `MemoryStream` в `GZipStream` перед сохранением, чтобы получить сжатый payload.

**В: Каков максимальный размер файла GeoJSON, который может обработать Aspose.GIS?**  
О: Библиотека способна потоково записывать файлы более 2 ГБ; потребление памяти остаётся низким, так как данные записываются по частям.

---

**Последнее обновление:** 2026-10-15  
**Тестировано с:** Aspose.GIS 24.11 для .NET  
**Автор:** Aspose  

## Связанные руководства

- [How to Read GeoJSON from Stream with Aspose.GIS for .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [How to Convert GeoJSON to TopoJSON with Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [How to Convert Shapefile to GeoJSON using Aspose.GIS for .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}