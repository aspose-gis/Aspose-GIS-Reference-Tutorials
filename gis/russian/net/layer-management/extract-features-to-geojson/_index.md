---
date: 2026-01-13
description: Узнайте, как преобразовать shapefile в geojson с помощью Aspose.GIS для
  .NET. Руководство также охватывает копирование атрибутов между слоями и генерацию
  geojson‑файла на C#.
linktitle: Extract Features to GeoJSON
second_title: Aspose.GIS .NET API
title: Как преобразовать Shapefile в GeoJSON с помощью Aspose.GIS для .NET
url: /ru/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Преобразование Shapefile в GeoJSON с помощью Aspose.GIS для .NET

## Введение
В этом полном пошаговом руководстве вы узнаете **как преобразовать shapefile в geojson** с помощью мощной библиотеки Aspose.GIS для .NET. Независимо от того, создаёте ли вы веб‑службу карт, готовите данные для мобильного GIS‑приложения или просто хотите обмениваться данными между форматами, это руководство покажет, что именно нужно сделать, почему каждый шаг важен и как избежать распространённых ошибок.

## Быстрые ответы
- **Что охватывает данное руководство?** Преобразование Shapefile в файл GeoJSON, копирование атрибутов между слоями и генерацию результата на C#.
- **Какая библиотека требуется?** Aspose.GIS для .NET.
- **Нужна ли лицензия?** Для продакшна требуется временная или полная лицензия; бесплатная trial‑версия подходит для оценки.
- **Сколько времени занимает реализация?** Около 10‑15 минут для базового преобразования.
- **Можно ли запускать на .NET Core/.NET 6?** Да — код работает на всех поддерживаемых версиях .NET.

## Предварительные требования
Прежде чем приступить, убедитесь, что у вас есть следующее:

- Aspose.GIS для .NET: Убедитесь, что библиотека установлена. Если нет, скачайте её со страницы [Aspose.GIS для .NET](https://releases.aspose.com/gis/net/).
- Данные Shapefile: Подготовьте Shapefile для ввода. При необходимости образцы данных можно найти в [документации Aspose.GIS](https://reference.aspose.com/gis/net/).
- Среда .NET: Настройте .NET‑окружение для выполнения предоставленного кода.
- Каталог документов: Укажите путь к вашему каталогу документов в фрагменте кода.

Теперь, когда всё готово, приступим к преобразованию shapefile в geojson!

## Что такое «convert shapefile to geojson»?
Преобразование Shapefile в GeoJSON означает чтение векторных объектов из классического формата ESRI Shapefile и запись их в современный, веб‑дружественный документ GeoJSON. GeoJSON широко используется в JavaScript‑библиотеках карт (Leaflet, Mapbox GL) и API, поэтому такое преобразование часто требуется в GIS‑разработке.

## Почему стоит использовать Aspose.GIS для этого преобразования?
Aspose.GIS абстрагирует низкоуровневые детали форматов файлов, позволяет легко копировать таблицы атрибутов и предоставляет чистый объектно‑ориентированный API, работающий на .NET Framework, .NET Core и .NET 5/6. Это даёт возможность сосредоточиться на бизнес‑логике, а не на разборе бинарных файлов.

## Подключение пространств имён
Сначала добавьте необходимые пространства имён в ваш код:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Эти пространства имён необходимы для работы с функциональностью Aspose.GIS.

## Как преобразовать Shapefile в GeoJSON
Ниже представлена полная последовательность действий, разбитая на чёткие шаги. Каждый шаг сопровождается коротким объяснением и точным блоком кода, который нужно скопировать в проект.

### Шаг 1: Открыть входной Shapefile
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```
Откройте входной Shapefile с помощью метода `VectorLayer.Open`. Это даст вам перечисляемую коллекцию объектов `Feature`.

### Шаг 2: Создать выходной GeoJSON
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```
Создайте выходной файл с помощью метода `VectorLayer.Create`, указав драйвер `Drivers.GeoJson`.

### Шаг 3: Копировать атрибуты между слоями
```csharp
outputLayer.CopyAttributes(inputLayer);
```
Эта единственная строка копирует схему атрибутов (имена полей, типы) из исходного Shapefile в новый слой GeoJSON — именно то, что описывает вторичное ключевое слово *copy attributes between layers*.

### Шаг 4: Обработать объекты
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```
Итерируйте каждый объект в Shapefile, чтобы при необходимости применить пользовательскую логику перед записью.

### Шаг 5: Фильтрация объектов по дате
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
В этом примере мы пропускаем записи, у которых поле `dob` (date of birth) отсутствует или дата раньше 1 янв 1982. При желании измените фильтр под свои требования к данным.

### Шаг 6: Создать новый объект (C# Generate GeoJSON File)
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Здесь мы формируем новый `Feature` для слоя GeoJSON, копируем геометрию и значения атрибутов и добавляем его в вывод. Это ядро *c# generate geojson file*.

Поздравляем! Вы успешно **преобразовали shapefile в geojson** и научились копировать атрибуты между слоями.

## Распространённые проблемы и решения
| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| Выходной файл пустой | `CopyAttributes` вызывается после закрытия выходного слоя | Убедитесь, что блок `using` для `outputLayer` остаётся открытым до добавления всех объектов. |
| Фильтр по дате удалил все записи | Неправильное имя поля или неожиданный формат даты | Проверьте имя атрибута (`dob`) и используйте `GetValue<string>`, если даты хранятся как строки. |
| Исключение лицензии | Запуск без действующей лицензии Aspose.GIS в продакшне | Примените временную или полную лицензию, как описано в документации Aspose. |

## Часто задаваемые вопросы
**В: Где можно найти дополнительную документацию?**  
О: Посетите [документацию Aspose.GIS](https://reference.aspose.com/gis/net/) для подробной информации.

**В: Как получить временную лицензию?**  
О: Временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/).

**В: Где получить поддержку?**  
О: Присоединяйтесь к [форуму Aspose.GIS](https://forum.aspose.com/c/gis/33) для общения с сообществом.

**В: Есть ли бесплатная trial‑версия?**  
О: Да, бесплатную trial‑версию можно скачать [здесь](https://releases.aspose.com/).

**В: Где можно приобрести Aspose.GIS для .NET?**  
О: Приобрести продукт можно [здесь](https://purchase.aspose.com/buy).

## Заключение
В этом руководстве мы рассмотрели полный процесс **convert shapefile to geojson** с помощью Aspose.GIS для .NET, продемонстрировали копирование атрибутов между слоями и показали чистый способ *c# generate geojson file*. Экспериментируйте с различными фильтрами, большими наборами данных или дополнительными преобразованиями геометрии, чтобы полностью раскрыть возможности библиотеки.

---

**Последнее обновление:** 2026-01-13  
**Тестировано с:** Aspose.GIS для .NET (последний стабильный релиз)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}