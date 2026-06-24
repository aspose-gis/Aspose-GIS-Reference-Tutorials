---
date: 2026-05-31
description: Tìm hiểu cách giới hạn độ chính xác khi ghi đối tượng hình học với Aspose.GIS
  cho .NET, giảm kích thước GeoJSON và duy trì kiểm soát tọa độ.
keywords:
- how to limit precision
- reduce geojson size
- Aspose.GIS precision control
linktitle: Giới Hạn Độ Chính Xác Khi Ghi Đối Tượng Hình Học
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  headline: How to Limit Precision Writing Geometries with Aspose.GIS
  type: TechArticle
- description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  name: How to Limit Precision Writing Geometries with Aspose.GIS
  steps:
  - name: Define Precision Options
    text: The `GeoJsonOptions` class lets you specify how many fractional digits to
      keep for X/Y and Z coordinates. `PrecisionModel` defines how coordinate values
      are rounded or kept exact during writing.
  - name: Set Output Path
    text: Specify where the resulting GeoJSON file will be saved. `VectorLayer` is
      Aspose.GIS's container for a collection of features that share the same schema;
      it writes to the path you provide using the options set earlier.
  - name: Create and Populate Geometry
    text: Open a new `VectorLayer` with the options defined above, construct a `Point`
      geometry, and add it to the layer. `Point` represents a single coordinate (X,
      Y, optional Z) in a spatial reference system. It is the simplest geometry type
      and is used here to demonstrate precision rounding.
  - name: Read and Verify Precision
    text: Open the file you just created and print the coordinates. You should see
      the X/Y values rounded to three decimal places while the Z value remains exact.
      When you read the file back, Aspose.GIS parses the rounded values directly,
      so the in‑memory `Point` reflects the precision you defined during writ
  type: HowTo
- questions:
  - answer: Yes, it supports **50+** formats—including Shapefile, GeoJSON, KML, GML,
      and CSV—allowing seamless conversion between them.
    question: Is Aspose.GIS for .NET compatible with other GIS formats?
  - answer: Absolutely. A free trial is available from the download page, giving you
      full access to all features for evaluation.
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: Temporary evaluation licenses can be generated via the Aspose license
      portal; they are valid for 30 days.
    question: How do I obtain a temporary license for testing?
  - answer: The Aspose.GIS forum and Stack Overflow tag `aspose-gis` are great places
      to ask questions and find community solutions.
    question: Where can I get help if I run into issues?
  - answer: Yes, Aspose.GIS is designed to handle everything from quick prototypes
      to high‑throughput server workloads, processing multi‑gigabyte datasets with
      low memory overhead.
    question: Does the library work for both small scripts and enterprise‑scale applications?
  type: FAQPage
second_title: Aspise.GIS .NET API
title: Cách Giới Hạn Độ Chính Xác Khi Ghi Đối Tượng Hình Học với Aspose.GIS
url: /vi/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách giới hạn độ chính xác khi ghi hình học với Aspose.GIS

Nếu bạn đang tự hỏi **cách giới hạn độ chính xác** khi ghi hình học trong một ứng dụng .NET GIS, Aspose.GIS cho .NET cung cấp một cách đơn giản, hiệu suất cao để kiểm soát việc làm tròn tọa độ. Trong hướng dẫn này, chúng tôi sẽ đi qua toàn bộ quy trình — từ thiết lập môi trường đến xác minh rằng đầu ra tuân theo các quy tắc độ chính xác mà bạn định nghĩa.

## Câu trả lời nhanh
- **“Giới hạn độ chính xác” có nghĩa là gì?** Nó làm tròn các giá trị tọa độ tới một số chữ số thập phân đã định khi ghi tệp không gian.  
- **Định dạng nào được sử dụng trong ví dụ?** GeoJSON, nhưng cùng các tùy chọn áp dụng cho các định dạng được hỗ trợ khác.  
- **Tôi có cần giấy phép để thử không?** Bản dùng thử miễn phí hoạt động cho việc phát triển và thử nghiệm; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Tôi có thể kiểm soát độ chính xác của tọa độ Z riêng biệt không?** Có — sử dụng `ZPrecisionModel` để đặt giá trị chính xác hoặc đã làm tròn.

## Cách giới hạn độ chính xác khi ghi hình học

Tải trình ghi GeoJSON của bạn với một đối tượng `GeoJsonOptions` chỉ định độ chính xác X/Y và Z mong muốn, sau đó ghi hình học và đọc lại — toàn bộ quy trình này chỉ mất dưới mười dòng mã và đảm bảo mọi tọa độ được làm tròn chính xác theo định nghĩa của bạn.

Giới hạn độ chính xác là cần thiết khi bạn cần biểu diễn tọa độ nhất quán trên các công cụ GIS khác nhau, giảm kích thước tệp, hoặc tuân thủ các tiêu chuẩn trao đổi dữ liệu. Dưới đây chúng tôi sẽ định nghĩa các tùy chọn độ chính xác, ghi một hình học, và sau đó đọc lại để xác nhận việc làm tròn.

## Giới hạn độ chính xác là gì?

Giới hạn độ chính xác là quá trình làm tròn phần thập phân của các giá trị tọa độ tới một số chữ số cố định trước khi lưu hình học vào định dạng tệp. Điều này đảm bảo mọi người tiêu thụ tệp đều thấy cùng một giá trị số, giúp tránh những sai lệch nhỏ có thể gây lỗi topo.

## Tại sao nên sử dụng Aspose.GIS để kiểm soát độ chính xác?

Aspose.GIS hỗ trợ **hơn 50** định dạng nhập và xuất — bao gồm GeoJSON, Shapefile, KML và GML — và có thể xử lý **hàng trăm nghìn tính năng** mà không cần tải toàn bộ bộ dữ liệu vào bộ nhớ. Các mô hình độ chính xác tích hợp cho phép bạn làm tròn tọa độ trong một lần gọi, loại bỏ nhu cầu viết script xử lý hậu kỳ thủ công.

## Yêu cầu trước

### 1. Tải xuống và Cài đặt
Tải gói Aspose.GIS cho .NET mới nhất từ trang chính thức: [download link](https://releases.aspose.com/gis/net/). Thực hiện theo hướng dẫn cài đặt để thêm gói NuGet vào dự án của bạn.

### 2. Nhập không gian tên
Thêm các không gian tên cần thiết để bạn có thể truy cập các lớp GIS và tiện ích trợ giúp.

## Hướng dẫn từng bước

### Bước 1: Xác định tùy chọn độ chính xác
Lớp `GeoJsonOptions` cho phép bạn chỉ định số chữ số thập phân cần giữ cho tọa độ X/Y và Z.

`PrecisionModel` xác định cách các giá trị tọa độ được làm tròn hoặc giữ nguyên trong quá trình ghi.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Bước 2: Đặt đường dẫn đầu ra
Xác định nơi tệp GeoJSON kết quả sẽ được lưu.

`VectorLayer` là container của Aspose.GIS cho một tập hợp các tính năng có cùng schema; nó ghi vào đường dẫn bạn cung cấp bằng các tùy chọn đã thiết lập trước.  

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### Bước 3: Tạo và Điền dữ liệu hình học
Mở một `VectorLayer` mới với các tùy chọn đã định nghĩa ở trên, tạo một hình học `Point`, và thêm nó vào lớp.

`Point` đại diện cho một tọa độ duy nhất (X, Y, tùy chọn Z) trong hệ tham chiếu không gian. Đây là loại hình học đơn giản nhất và được sử dụng ở đây để minh họa việc làm tròn độ chính xác.  

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### Bước 4: Đọc và Xác minh độ chính xác
Mở tệp bạn vừa tạo và in ra các tọa độ. Bạn sẽ thấy các giá trị X/Y đã được làm tròn tới ba chữ số thập phân trong khi giá trị Z vẫn giữ nguyên.

Khi bạn đọc lại tệp, Aspose.GIS sẽ phân tích trực tiếp các giá trị đã làm tròn, vì vậy `Point` trong bộ nhớ phản ánh độ chính xác bạn đã định nghĩa khi ghi.  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

## Các vấn đề thường gặp & Mẹo

- **Lỗi đường dẫn:** Đảm bảo thư mục trong `path` tồn tại hoặc sử dụng `Path.Combine` với `Environment.CurrentDirectory` để tạo một đường dẫn an toàn.  
- **Độ chính xác không được áp dụng:** Kiểm tra rằng bạn đã truyền đối tượng `GeoJsonOptions` khi tạo lớp; nếu không, độ chính xác mặc định (double đầy đủ) sẽ được sử dụng.  
- **Bộ dữ liệu lớn:** Đối với các thao tác bulk, cân nhắc tái sử dụng một thể hiện `VectorLayer` duy nhất và thêm tính năng theo batch để cải thiện hiệu suất.

## Câu hỏi thường gặp

**Q: Aspose.GIS cho .NET có tương thích với các định dạng GIS khác không?**  
A: Có, nó hỗ trợ **hơn 50** định dạng — bao gồm Shapefile, GeoJSON, KML, GML và CSV — cho phép chuyển đổi liền mạch giữa chúng.

**Q: Tôi có thể thử Aspose.GIS cho .NET trước khi mua không?**  
A: Chắc chắn. Một bản dùng thử miễn phí có sẵn trên trang tải xuống, cung cấp quyền truy cập đầy đủ vào tất cả các tính năng để đánh giá.

**Q: Làm thế nào để tôi có được giấy phép tạm thời để thử nghiệm?**  
A: Giấy phép đánh giá tạm thời có thể được tạo qua cổng giấy phép Aspose; chúng có hiệu lực trong 30 ngày.

**Q: Tôi có thể nhận được hỗ trợ ở đâu nếu gặp vấn đề?**  
A: Diễn đàn Aspose.GIS và thẻ Stack Overflow `aspose-gis` là những nơi tuyệt vời để đặt câu hỏi và tìm giải pháp cộng đồng.

**Q: Thư viện có hoạt động cho cả script nhỏ và ứng dụng quy mô doanh nghiệp không?**  
A: Có, Aspose.GIS được thiết kế để xử lý mọi thứ từ prototype nhanh đến khối lượng công việc máy chủ cao, xử lý các bộ dữ liệu đa gigabyte với mức tiêu thụ bộ nhớ thấp.

---

**Cập nhật lần cuối:** 2026-05-31  
**Được kiểm tra với:** Aspose.GIS 24.11 cho .NET  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Tạo lớp Vector, Giới hạn độ chính xác với Aspose.GIS cho .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Cách chuyển đổi GeoJSON – Aspose.GIS cho .NET](/gis/net/geo-data-conversion/)
- [Cách kiểm tra hình học với Aspose.GIS cho .NET](/gis/net/geometry-analysis/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

{{< /blocks/products/pf/main-wrap-class >}}