---
date: 2026-07-24
description: Узнайте, как без усилий конвертировать Shapefile в GeoJSON в .NET с помощью
  Aspose.GIS и обеспечить бесшовную совместимость геопространственных данных при чтении
  Shapefile на C#.
keywords:
- convert shapefile to geojson
- read shapefile c#
- c# shapefile to geojson
- export geojson c#
- convert shapefile to json
lastmod: 2026-07-24
linktitle: Конвертировать Shapefile в GeoJSON
og_description: Быстро конвертируйте shapefile в geojson с помощью Aspose.GIS для
  .NET. Узнайте пошаговый код C#, необходимые условия и устранение неполадок за менее
  чем 10 минут.
og_image_alt: 'Developer guide: Convert Shapefile to GeoJSON in C# with Aspose.GIS'
og_title: Конвертировать Shapefile в GeoJSON – Быстрое руководство C# (50‑60 символов)
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Learn how to effortlessly convert Shapefile to GeoJSON in .NET using
    Aspose.GIS and achieve seamless geospatial data interoperability while reading
    Shapefile in C#.
  headline: Convert Shapefile to GeoJSON
  type: TechArticle
- questions:
  - answer: Yes. Place the conversion code inside a `foreach` loop that iterates over
      each `.shp` file in a directory, calling `VectorLayer.Convert` for every file.
    question: Can I convert multiple Shapefiles to GeoJSON in one go using Aspose.GIS
      for .NET?
  - answer: It supports .NET Framework 4.5 and higher, as well as .NET Core 3.1+ and
      .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with all versions of .NET Framework?
  - answer: Absolutely. The library handles formats such as GeoTIFF, KML, GML, CSV,
      and many more—over 60 in total.
    question: Does Aspose.GIS for .NET provide support for other geospatial formats
      apart from Shapefile and GeoJSON?
  - answer: Yes. The API offers overloads and properties to set target coordinate
      systems, filter attributes, and modify feature geometry during conversion.
    question: Can I customize the conversion process, such as specifying a coordinate
      system or attribute mappings?
  - answer: Yes, you can download a free trial from the [Aspose website](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert shapefile
- Aspose.GIS
- C# geospatial processing
- geojson export
title: Конвертировать Shapefile в GeoJSON
url: /ru/net/geo-data-conversion/convert-shapefile-to-geojson/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Конвертировать Shapefile в GeoJSON

## Введение
В современных географических информационных системах (GIS) **геопространственная совместимость данных** является ключом к раскрытию мощных пространственных анализов. Одной из самых распространённых задач конвертации является **конвертировать shapefile в geojson**, позволяя лёгкий обмен данными с веб‑картами, мобильными приложениями и облачными сервисами. В этом руководстве вы увидите, как **читать shapefile в C#** и экспортировать его как GeoJSON с помощью библиотеки Aspose.GIS для .NET, чтобы вы могли интегрировать конвертацию напрямую в свои приложения.

## Краткие ответы
- **Какая библиотека обрабатывает конвертацию?** Aspose.GIS for .NET  
- **Сколько времени занимает реализация?** Обычно менее 10 минут для одного файла  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; для продакшн требуется лицензия  
- **Поддерживаемые версии .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Можно ли конвертировать несколько файлов?** Да — просто выполните цикл по вызову `VectorLayer.Convert`  

## Что такое «конвертировать shapefile в geojson»?
Конвертация Shapefile (три файла `.shp`, `.shx`, `.dbf`) в GeoJSON преобразует данные в единый формат на основе JSON, который легко читать, редактировать и отображать в браузерах. GeoJSON особенно подходит для JavaScript‑библиотек карт, таких как Leaflet или Mapbox.

## Почему использовать Aspose.GIS для .NET для конвертации форматов GIS‑данных?
Aspose.GIS предоставляет всестороннее, полностью управляемое решение, поддерживающее более 60 векторных и растровых форматов, устраняющее внешние зависимости и обеспечивающее высокоскоростную конвертацию даже для больших наборов данных, что делает его идеальным для корпоративных и облачных сред, где надёжность и производительность критически важны.

- **All‑in‑one API** – Поддерживает **60+** геопространственных векторных и растровых форматов, включая KML, GML, CSV, GeoTIFF и др.  
- **Zero‑dependency conversion** – Не требуется GDAL, Proj4 или нативные бинарные файлы; всё работает на чистом управляемом коде.  
- **High performance** – Обрабатывает файлы размером до **500 MB** менее чем за **5 секунд** на типичной серверной VM и может выполнять пакетные задания без избыточного использования памяти.  
- **Rich customization** – Вы можете указать целевые системы координат, фильтровать атрибуты и преобразовывать геометрии «на лету».

## Требования
1. **Aspose.GIS for .NET установлен** – Следуйте инструкциям в официальной [документации Aspose.GIS для .NET](https://reference.aspose.com/gis/net/) чтобы добавить пакет NuGet в ваш проект.  
2. **Исходный Shapefile** – Получите его из портала открытых данных, государственного агентства или создайте в QGIS/ArcGIS.  
3. **Базовые знания C#** – Фрагменты кода используют синтаксис C# и соглашения .NET.  

## Импорт пространств имён
Пространства имён `Aspose.GIS` предоставляют классы, необходимые для чтения и записи векторных данных.

Пространство имён `Aspose.GIS.Geometries` содержит типы геометрий, а `Aspose.GIS.VectorLayers` содержит класс `VectorLayer`, который выполняет конвертацию форматов. Пространство имён `Aspose.GIS.VectorLayers` содержит класс `VectorLayer`, используемый для конвертации форматов.

## Как конвертировать shapefile в GeoJSON на C#?
Метод `VectorLayer.Open` загружает векторный набор данных из файла в объект `VectorLayer`.  
`VectorLayer.Convert` — статический метод, который преобразует исходный векторный файл напрямую в целевой формат, например GeoJSON.

Загрузите исходный Shapefile с помощью `VectorLayer.Open`, затем вызовите статический метод `VectorLayer.Convert`, чтобы записать файл GeoJSON одной строкой. Этот подход читает исходный файл, при необходимости пере‑проецирует его и сразу записывает результат на диск, устраняя необходимость в промежуточных объектах.

### Шаг 1: Определите пути ввода и вывода
Укажите папку, содержащую ваш Shapefile, и место назначения для файла GeoJSON. Настройте путь в соответствии с вашей средой.

Используйте `Path.Combine(dataDir, "InputShapeFile.shp")` для построения кроссплатформенного пути и `Path.Combine(outputDir, "output.geojson")` для файла результата.

> **Совет:** Держите три компонента Shapefile (`.shp`, `.shx`, `.dbf`) в одной папке; `VectorLayer.Open` автоматически находит связанные файлы.

### Шаг 2: Выполните конвертацию
Вызовите `VectorLayer.Convert(inputPath, outputPath, OutputFormat.GeoJSON)`. Эта единственная строка читает Shapefile, преобразует его и записывает корректный GeoJSON FeatureCollection.

После выполнения `output.geojson` будет содержать полностью соответствующий спецификации GeoJSON документ, который можно загрузить в любой веб‑картографический просмотрщик, GIS‑сервер или аналитический конвейер.

## Почему это важно
Конвертация shapefile в GeoJSON обеспечивает бесшовную интеграцию с современными веб‑картографическими библиотеками, уменьшает размер файлов и упрощает обмен данными между платформами, позволяя разработчикам создавать отзывчивые GIS‑приложения без работы с устаревшими форматами и повышая общую эффективность рабочего процесса для команд, работающих с пространственными данными.

- **Interoperability:** Конвертация в GeoJSON позволяет делиться данными с широким спектром веб‑GIS‑инструментов без беспокойства о проприетарных форматах.  
- **Performance:** Aspose.GIS обрабатывает конвертацию в памяти, что быстрее, чем вызов внешних утилит командной строки.  
- **Scalability:** Тот же подход можно обернуть в цикл или фоновой сервис для пакетной конвертации в рамках конвейеров данных.

## Распространённые проблемы и решения
| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| **Файл не найден** | Неправильный `dataDir` или отсутствует файл `.shp` | Проверьте путь и убедитесь, что все три компонента Shapefile (`.shp`, `.shx`, `.dbf`) присутствуют. |
| **Несоответствие системы координат** | Исходный Shapefile использует проекцию, не распознаваемую получателем | Используйте `VectorLayer.Open(...).CoordinateSystem` для репроекции перед конвертацией. |
| **Большие файлы вызывают нагрузку на память** | Весь набор данных загружается в память | Обрабатывайте объекты по частям или используйте `VectorLayer.Stream` для потоковой конвертации. |

## Часто задаваемые вопросы

**В: Можно ли конвертировать несколько Shapefile в GeoJSON за один проход, используя Aspose.GIS для .NET?**  
Да. Поместите код конвертации внутрь цикла `foreach`, который перебирает каждый файл `.shp` в каталоге, вызывая `VectorLayer.Convert` для каждого файла.

**В: Совместим ли Aspose.GIS для .NET со всеми версиями .NET Framework?**  
Он поддерживает .NET Framework 4.5 и выше, а также .NET Core 3.1+ и .NET 5/6/7.

**В: Предоставляет ли Aspose.GIS для .NET поддержку других геопространственных форматов, помимо Shapefile и GeoJSON?**  
Безусловно. Библиотека работает с форматами, такими как GeoTIFF, KML, GML, CSV и многими другими — более 60 в общей сложности.

**В: Могу ли я настроить процесс конвертации, например указать систему координат или сопоставление атрибутов?**  
Да. API предоставляет перегрузки и свойства для установки целевых систем координат, фильтрации атрибутов и изменения геометрии объектов во время конвертации.

**В: Доступна ли пробная версия Aspose.GIS для .NET?**  
Да, вы можете скачать бесплатную пробную версию с [веб‑сайта Aspose](https://releases.aspose.com/).

## Заключение
Следуя этим шагам, вы теперь знаете, **как эффективно конвертировать shapefile в geojson** с помощью **Aspose.GIS для .NET**. Эта возможность открывает бесшовную **геопространственную совместимость данных**, позволяя интегрировать пространственные данные в современные веб‑карты, API и аналитические конвейеры. Исследуйте более широкие возможности **конвертации форматов GIS‑данных** в Aspose.GIS для работы с KML, GML, растровыми форматами и другими по мере развития ваших проектов.

---

**Последнее обновление:** 2026-07-24  
**Тестировано с:** Aspose.GIS for .NET 24.11  
**Автор:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

```csharp
string dataDir = "Your Document Directory";
string shapefilePath = dataDir + "InputShapeFile.shp";
string jsonPath = dataDir + "output_out.json";
```

```csharp
VectorLayer.Convert(shapefilePath, Drivers.Shapefile, jsonPath, Drivers.GeoJson);
```

## Связанные руководства

- [Как читать GeoJSON из потока с помощью Aspose.GIS для .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Как конвертировать GeoJSON в TopoJSON с помощью Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Чтение Shapefile C# – Фильтрация объектов по атрибуту с Aspose.GIS](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}