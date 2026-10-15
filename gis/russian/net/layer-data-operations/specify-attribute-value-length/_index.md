---
date: 2026-10-15
description: Создание ширины атрибутов shapefile с помощью Aspose.GIS for .NET – пошаговое
  руководство, показывающее, как задать ширину поля, определить длину атрибута и эффективно
  добавлять атрибуты.
keywords:
- create shapefile attribute width
- set field width shapefile
- Aspose.GIS attribute width
- vector layer example
- define attribute length
lastmod: 2026-10-15
linktitle: Как задать Field Width
og_description: Создание ширины атрибутов shapefile с помощью Aspose.GIS for .NET.
  Узнайте, как задать field width, определить attribute length и поддерживать согласованность
  ваших GIS‑данных.
og_image_alt: Guide showing how to create shapefile attribute width using Aspose.GIS
  for .NET
og_title: Создание ширины атрибутов shapefile с использованием Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create shapefile attribute width with Aspose.GIS for .NET – step‑by‑step
    guide showing how to set field width, define attribute length, and add attributes
    efficiently.
  headline: Create shapefile attribute width using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: You can acquire a temporary license [temporary license](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for peer‑to‑peer
      help and official responses.
    question: Where can I find community support for Aspose.GIS for .NET?
  - answer: Yes, explore the [free trial](https://releases.aspose.com/) to experience
      the full feature set without cost.
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Purchase your license [purchase a license](https://purchase.aspose.com/buy).
    question: How do I purchase a license for Aspose.GIS for .NET?
  - answer: Refer to the [documentation](https://reference.aspose.com/gis/net/) for
      comprehensive API details.
    question: Where can I access the documentation for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- shapefile
- Aspose.GIS
- .NET GIS
- attribute width
- vector layer
- author: Aspose
  dateModified: '2026-10-15'
  description: Create shapefile attribute width with Aspose.GIS for .NET – step‑by‑step
    guide showing how to set field width, define attribute length, and add attributes
    efficiently.
  headline: Create shapefile attribute width using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: You can acquire a temporary license [temporary license](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for peer‑to‑peer
      help and official responses.
    question: Where can I find community support for Aspose.GIS for .NET?
  - answer: Yes, explore the [free trial](https://releases.aspose.com/) to experience
      the full feature set without cost.
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Purchase your license [purchase a license](https://purchase.aspose.com/buy).
    question: How do I purchase a license for Aspose.GIS for .NET?
  - answer: Refer to the [documentation](https://reference.aspose.com/gis/net/) for
      comprehensive API details.
    question: Where can I access the documentation for Aspose.GIS for .NET?
  type: FAQPage
title: Создание ширины атрибутов shapefile с использованием Aspose.GIS for .NET
url: /ru/net/layer-data-operations/specify-attribute-value-length/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание ширины атрибута shapefile с использованием Aspose.GIS для .NET

В этом примере с векторным слоем вы узнаете, как **создать ширину атрибута shapefile** при генерации Shapefile с помощью Aspose.GIS для .NET. Управление длиной атрибута важно для целостности данных, особенно при обмене файлами с другими GIS‑инструментами, которые ожидают столбец DBF фиксированного размера.

## Быстрые ответы
- **Какова основная цель данного руководства?** Показать, как задать ширину поля для атрибута в shapefile с использованием Aspose.GIS для .NET.  
- **Какой класс определяет ширину поля?** `FeatureAttribute.Width`.  
- **Нужна ли лицензия для выполнения кода?** Временная лицензия подходит для оценки; полная лицензия требуется для продакшн.  
- **Какой формат файла используется в примере?** ESRI Shapefile (`.shp`).  
- **Можно ли изменить ширину после создания слоя?** Нет — ширина должна быть определена до добавления объектов.

## Что такое ширина поля и почему это важно?
Ширина поля — это максимальное количество символов, которое строковый столбец может хранить в компоненте DBF Shapefile. Правильная настройка предотвращает бесшумное усечение, гарантирует, что другие GIS‑приложения читают данные точно так, как вы их ввели, и делает размер файла предсказуемым — каждый дополнительный символ добавляет один байт на запись.

Ширина поля (также называемая длиной атрибута) — это максимальное количество символов, которое строковое поле может хранить в компоненте DBF Shapefile. Установка правильной ширины предотвращает бесшумное усечение, гарантирует, что другие GIS‑приложения читают данные точно так, как вы их ввели, и делает размер файла предсказуемым — каждый дополнительный символ добавляет один байт на запись.

## Зачем использовать пример векторного слоя с заданной шириной?
Задание ширины заранее устраняет выделение по умолчанию в 255 символов, что может добавить до 255 × количествоЗаписей байт. Для набора данных из 10 000 записей это дополнительное пространство составит примерно **2,5 МБ** — заметный накладной расход для крупных проектов. Точная ширина также обеспечивает совместимость со старыми GIS‑инструментами, требующими строгих схем DBF.

Точная ширина также обеспечивает совместимость со старыми GIS‑инструментами, требующими строгих схем DBF. Для набора данных из 10 000 записей выделение по умолчанию в 255 символов добавит примерно 2,5 МБ лишних данных, тогда как поле в 50 символов экономит около 2 МБ.

## Как задать ширину поля для атрибута?
Загрузите или создайте `VectorLayer`, указывающий на целевой файл `.shp`, объявите строковый атрибут с именем **wide** и `Width = 120`, затем добавьте объект, значение которого соблюдает ограничение в 120 символов. Aspose.GIS автоматически усечёт любую более длинную строку до заданной ширины, сохраняя согласованность данных без выброса исключений.

### Импорт пространств имён
`FeatureAttribute`, `VectorLayer` и связанные типы принадлежат библиотеке Aspose.GIS. Импортируйте их в начале вашего файла:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Создание VectorLayer
Класс `VectorLayer` представляет векторный источник данных (например, Shapefile). Это контейнер, который хранит объекты и их атрибуты.

```csharp
string dataDir = "Your Document Directory";
using (VectorLayer layer = VectorLayer.Create(dataDir + "SpecifyAttributeValueLength_out.shp", Drivers.Shapefile))
{
    // Your code for the next steps will go here.
}
```

### Добавление атрибута с определённой длиной
Объект `FeatureAttribute` описывает столбец в таблице атрибутов; установка `Width = 120` указывает записывающему Shapefile выделять ровно 120 байт для каждой записи этого поля.

```csharp
FeatureAttribute attribute = new FeatureAttribute("wide", AttributeDataType.String);
attribute.Width = 120;
layer.Attributes.Add(attribute);
```

> **Полезный совет:** Свойство `Width` применяется только к строковым атрибутам. Для числовых, датовых или логических полей `Width` игнорируется, поскольку их размер фиксирован типом данных.

### Создание и добавление объекта
Класс `Feature` инкапсулирует геометрию и значения атрибутов; после установки атрибута вызов `layer.Add(feature)` записывает запись в Shapefile.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("wide", "this string can be up to 120 characters long now.");
layer.Add(feature);
```

Если попытаться присвоить более длинную строку, Aspose.GIS усечёт её до заданной ширины, сохраняя целостность данных.

## Распространённые подводные камни и устранение неполадок
- **Забыли установить `Width` перед добавлением атрибута?** Ширина по умолчанию — 255 символов; изменение позже не влияет на уже созданные поля. Всегда задавайте ширину сначала.  
- **Используете тип данных, отличный от строки?** `Width` игнорируется для числовых или датовых полей; убедитесь, что `AttributeDataType` атрибута установлен в `String`.  
- **Ошибка «Поле не найдено»?** Имена атрибутов чувствительны к регистру. Убедитесь, что имя, использованное в `SetValue`, точно совпадает с именем, определённым в схеме.  
- **Неожиданный рост размера файла?** Большие ширины увеличивают размер `.dbf` линейно. Для 10 000 записей увеличение ширины с 50 до 120 добавит примерно 700 KB.

## Часто задаваемые вопросы
**Q: Как я могу получить временную лицензию для Aspose.GIS для .NET?**  
A: Вы можете получить временную лицензию [temporary license](https://purchase.aspose.com/temporary-license/).

**Q: Где я могу найти поддержку сообщества для Aspose.GIS для .NET?**  
A: Посетите [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) для помощи от коллег и официальных ответов.

**Q: Доступна ли бесплатная пробная версия Aspose.GIS для .NET?**  
A: Да, изучите [free trial](https://releases.aspose.com/) чтобы испытать полный набор функций без оплаты.

**Q: Как приобрести лицензию для Aspose.GIS для .NET?**  
A: Приобретите лицензию по ссылке [purchase a license](https://purchase.aspose.com/buy).

**Q: Где я могу получить доступ к документации Aspose.GIS для .NET?**  
A: Обратитесь к [documentation](https://reference.aspose.com/gis/net/) для подробных сведений об API.

**Q: Можно ли изменить ширину поля после создания слоя?**  
A: Нет. Ширина поля должна быть определена до добавления атрибута; для её изменения необходимо пересоздать слой с новой схемой.

**Q: Влияет ли установка большей ширины на размер файла?**  
A: Shapefile хранит строковые поля фиксированной длины, поэтому увеличение ширины напрямую увеличивает размер файла `.dbf` пропорционально количеству записей.

## Заключение
Этот пример векторного слоя продемонстрировал, как **создать ширину атрибута shapefile** для атрибута в Shapefile с использованием Aspose.GIS для .NET, и показал, как эффективно добавить атрибут с конкретной длиной. Управляя шириной атрибутов, вы избегаете усечения данных, поддерживаете оптимальный размер файлов и обеспечиваете беспрепятственную совместимость с другими GIS‑платформами. Экспериментируйте с различными ширинами, изучайте [documentation](https://reference.aspose.com/gis/net/), и раскрывайте весь потенциал геопространственной разработки с Aspose.GIS.

---

**Последнее обновление:** 2026-10-15  
**Тестировано с:** Aspose.GIS 24.11 for .NET  
**Автор:** Aspose  
Скачайте последнюю версию Aspose.GIS для .NET по [download link](https://releases.aspose.com/gis/net/).

## Связанные руководства

- [Получить атрибуты слоя – Получить информацию об атрибутах слоя с помощью Aspose.GIS для .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Как получить значение атрибута (по умолчанию) с Aspose.GIS для .NET](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [Создание векторного слоя в File GDB – Руководство Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}