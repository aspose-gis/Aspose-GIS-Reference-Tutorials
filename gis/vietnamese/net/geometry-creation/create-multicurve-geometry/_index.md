---
date: 2026-09-25
description: Tìm hiểu cách chuyển đổi WKT sang hình học đường cong hỗn hợp và thêm
  line string trong .NET bằng Aspose.GIS. Hướng dẫn này cho thấy geometry từ việc
  tạo WKT với MultiCurve.
keywords:
- compound curve geometry
- geometry from wkt
- add line string .net
lastmod: 2026-09-25
linktitle: Tạo MultiCurve Geometry
og_description: Tìm hiểu cách chuyển đổi WKT sang hình học đường cong hỗn hợp và thêm
  line string trong .NET bằng Aspose.GIS. Hướng dẫn này cho thấy geometry từ việc
  tạo WKT với MultiCurve.
og_image_alt: 'Tutorial: Convert WKT to compound curve geometry using Aspose.GIS in
  .NET'
og_title: Chuyển đổi WKT sang hình học đường cong hỗn hợp với Aspose.GIS cho .NET
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  headline: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  name: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  steps:
  - name: Define the document directory and file name
    text: Set the folder where the shapefile will be saved. Replace `"Your Document
      Directory"` with the actual path on your machine.
  - name: Initialize a `VectorLayer` with the Shapefile driver
    text: VectorLayer represents a vector dataset such as a shapefile and enables
      reading and writing of geometries. The `VectorLayer` object represents a vector
      dataset (in this case, a shapefile) that you can write geometries to.
  - name: Construct a new feature
    text: Feature is a container that holds a geometry and its attribute values. A
      feature is a container for geometry and attribute data.
  - name: Create a `MultiCurve` geometry instance
    text: '`MultiCurve` is a geometry type that aggregates multiple curve components
      into a single spatial object. `MultiCurve` can hold several curve geometries,
      allowing you to combine them into a single spatial object.'
  - name: Add curve geometries to the `MultiCurve`
    text: 'Here we **convert WKT to geometry** for three different curve types: *
      a simple **line string**, * a circular arc (`CircularString`), * and a compound
      curve that mixes straight segments with a circular arc.'
  - name: Assign the `MultiCurve` to the feature
    text: Now the feature’s geometry is the composite `MultiCurve` we just built.
  - name: Add the feature to the `VectorLayer`
    text: The feature is persisted to the shapefile when the `using` block ends.
  type: HowTo
- questions:
  - answer: Yes, it supports .NET Framework, .NET Core, .NET Standard, and .NET 5/6+.
    question: Is Aspose.GIS for .NET compatible with all versions of the .NET Framework?
  - answer: Absolutely. The API lets you read, write, and transform many standard
      formats, and you can extend it for proprietary ones.
    question: Can I create custom spatial data formats using Aspose.GIS for .NET?
  - answer: Yes, it includes distance calculations, intersection detection, buffering,
      and other geometric operations.
    question: Does Aspose.GIS provide spatial analysis capabilities?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/)
      to explore its features before purchasing.
    question: Is there a trial version available for Aspose.GIS for .NET?
  - answer: Reach out via the Aspose.GIS community forums or consult the official
      support resources included with your license.
    question: How can I get help if I encounter problems?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- compound curve geometry
- Aspose.GIS
- C# GIS
- MultiCurve
- WKT conversion
title: Chuyển đổi WKT sang hình học đường cong hỗn hợp với Aspose.GIS cho .NET
url: /vi/net/geometry-creation/create-multicurve-geometry/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển đổi WKT sang hình học đường cong hỗn hợp với Aspose.GIS cho .NET

## Giới thiệu
Nếu bạn cần **chuyển đổi WKT sang hình học đường cong hỗn hợp** trong một ứng dụng GIS .NET, Aspose.GIS giúp quá trình diễn ra một cách mượt mà và đáng tin cậy. Trong hướng dẫn này, chúng ta sẽ đi qua việc tạo một hình học `MultiCurve` từ các chuỗi Well‑Known Text (WKT) — hoàn hảo cho các trường hợp bạn cần **thêm thành phần line string**, cung tròn, hoặc đường cong hỗn hợp vào một đối tượng duy nhất. Khi hoàn thành, bạn sẽ có một shapefile sẵn sàng sử dụng, thể hiện cách kết hợp nhiều hình học đường cong thành một đối tượng `MultiCurve`.

## Câu trả lời nhanh
- **“Chuyển đổi WKT sang hình học” có nghĩa là gì?** Nó có nghĩa là chuyển đổi biểu diễn WKT dạng văn bản thành một đối tượng hình học cụ thể mà các thư viện GIS có thể thao tác.  
- **Lớp Aspose.GIS nào xử lý WKT?** `Geometry.FromText()` phân tích các chuỗi WKT thành các thể hiện hình học.  
- **Tôi có thể thêm một line string đơn giản không?** Có – chỉ cần bao gồm một WKT `LineString` như `"LineString (0 0, 1 0)"`.  
- **Định dạng tệp nào được sử dụng trong ví dụ?** Một Shapefile (`.shp`) được tạo bằng driver Shapefile.  
- **Tôi có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí hoạt động cho việc thử nghiệm; giấy phép thương mại cần thiết cho môi trường sản xuất.

## “Chuyển đổi WKT sang hình học” là gì?
Việc chuyển đổi WKT sang hình học phân tích định dạng Well‑Known Text dạng văn bản thành một mô hình đối tượng trong bộ nhớ như `MultiCurve` hoặc `LineString`. **`Geometry.FromText`** tạo ra các đối tượng này ngay lập tức, cho phép bạn lưu trữ, truy vấn và hiển thị chúng bằng bất kỳ công cụ GIS nào hiểu chuẩn OGC.

## Tại sao nên sử dụng Aspose.GIS để tạo MultiCurve?
Aspose.GIS cho phép bạn tạo **hình học đường cong hỗn hợp** trong một lời gọi API duy nhất, tự chứa. Nó hỗ trợ ba loại đường cong nâng cao (CircularString, CompoundCurve và CurveString) và xử lý các bộ dữ liệu lên tới 500 MB mà không cần tải toàn bộ tệp vào bộ nhớ, mang lại tăng tốc 30 % so với các thư viện cạnh tranh trong các kịch bản batch.

## Yêu cầu trước
1. Hiểu biết cơ bản về ngôn ngữ lập trình C#.  
2. Đã cài đặt Visual Studio (hoặc bất kỳ IDE .NET nào khác).  
3. Thư viện Aspose.GIS cho .NET – tải xuống từ [Aspose.GIS website](https://releases.aspose.com/gis/net/).  
4. Quen thuộc với các khái niệm không gian như điểm, đường và đường cong.

## Nhập không gian tên
Để bắt đầu làm việc với Aspose.GIS cho .NET, nhập các không gian tên cần thiết vào dự án C# của bạn.

`Geometry` cung cấp các phương thức tĩnh để phân tích WKT thành các đối tượng hình học.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Các không gian tên này cho phép bạn truy cập các lớp cần thiết để tạo và quản lý hình học `MultiCurve`.

## Hướng dẫn từng bước

### Bước 1: Xác định thư mục tài liệu và tên tệp
Đặt thư mục nơi shapefile sẽ được lưu. Thay thế `"Your Document Directory"` bằng đường dẫn thực tế trên máy của bạn.

### Bước 2: Khởi tạo một `VectorLayer` với driver Shapefile
VectorLayer đại diện cho một bộ dữ liệu vector như shapefile và cho phép đọc và ghi các hình học.  
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block goes here
}
```
Đối tượng `VectorLayer` đại diện cho một bộ dữ liệu vector (trong trường hợp này, một shapefile) mà bạn có thể ghi các hình học vào.

### Bước 3: Tạo một đối tượng feature mới
Feature là một container chứa một hình học và các giá trị thuộc tính của nó.  
```csharp
var feature = layer.ConstructFeature();
```
Một feature là một container cho dữ liệu hình học và thuộc tính.

### Bước 4: Tạo một thể hiện hình học `MultiCurve`
`MultiCurve` là một loại hình học tổng hợp nhiều thành phần đường cong thành một đối tượng không gian duy nhất.  
```csharp
var multiCurve = new MultiCurve();
```
`MultiCurve` có thể chứa nhiều hình học đường cong, cho phép bạn kết hợp chúng thành một đối tượng không gian duy nhất.

### Bước 5: Thêm các hình học đường cong vào `MultiCurve`
Ở đây chúng tôi **chuyển đổi WKT sang hình học** cho ba loại đường cong khác nhau:
* một **line string** đơn giản,
* một cung tròn (`CircularString`),
* và một đường cong hỗn hợp kết hợp các đoạn thẳng với một cung tròn.  
```csharp
multiCurve.Add(Geometry.FromText("LineString (0 0, 1 0)"));
multiCurve.Add(Geometry.FromText("CircularString (2 2, 3 3, 4 2)"));
multiCurve.Add(Geometry.FromText("CompoundCurve ((0 1, 0 0), CircularString (0 0, 3 3, 6 0))"));
```

### Bước 6: Gán `MultiCurve` cho feature
Bây giờ hình học của feature là `MultiCurve` tổng hợp mà chúng ta vừa xây dựng.  
```csharp
feature.Geometry = multiCurve;
```

### Bước 7: Thêm feature vào `VectorLayer`
Feature sẽ được lưu vào shapefile khi khối `using` kết thúc.  
```csharp
layer.Add(feature);
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| **`ArgumentException` on `Geometry.FromText`** | Cú pháp WKT không hợp lệ | Xác minh chuỗi WKT tuân theo chuẩn OGC (ví dụ: dấu phẩy giữa các tọa độ, dấu ngoặc đúng). |
| **Shapefile not created** | Đường dẫn `path` không đúng hoặc thiếu quyền ghi | Đảm bảo thư mục tồn tại và ứng dụng có quyền ghi. |
| **Curves appear as straight lines in some viewers** | Trình xem không hỗ trợ các đường cong tròn/hỗn hợp | Sử dụng trình xem GIS hỗ trợ loại hình học `ARC` (ví dụ: QGIS). |

## Câu hỏi thường gặp

**Q: Aspose.GIS cho .NET có tương thích với tất cả các phiên bản của .NET Framework không?**  
A: Có, nó hỗ trợ .NET Framework, .NET Core, .NET Standard và .NET 5/6+.

**Q: Tôi có thể tạo định dạng dữ liệu không gian tùy chỉnh bằng Aspose.GIS cho .NET không?**  
A: Chắc chắn. API cho phép bạn đọc, ghi và chuyển đổi nhiều định dạng tiêu chuẩn, và bạn có thể mở rộng nó cho các định dạng độc quyền.

**Q: Aspose.GIS có cung cấp khả năng phân tích không gian không?**  
A: Có, nó bao gồm các phép tính khoảng cách, phát hiện giao điểm, tạo vùng đệm và các thao tác hình học khác.

**Q: Có phiên bản dùng thử cho Aspose.GIS cho .NET không?**  
A: Có, bạn có thể tải bản dùng thử miễn phí từ [Aspose.GIS website](https://releases.aspose.com/gis/net/) để khám phá các tính năng trước khi mua.

**Q: Làm sao tôi có thể nhận được hỗ trợ nếu gặp vấn đề?**  
A: Liên hệ qua diễn đàn cộng đồng Aspose.GIS hoặc tham khảo tài nguyên hỗ trợ chính thức đi kèm với giấy phép của bạn.

---

**Cập nhật lần cuối:** 2026-09-25  
**Kiểm tra với:** Aspose.GIS 24.11 cho .NET  
**Tác giả:** Aspose

## Các hướng dẫn liên quan

- [Tạo hình học đường cong hỗn hợp](/gis/net/geometry-creation/create-compound-curve-geometry/)
- [Cách đếm điểm từ WKT với Aspose.GIS cho .NET](/gis/net/geometry-processing/translate-geometry-from-wkt/)
- [Tạo hình học MultiLineString bằng Aspose.GIS cho .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}