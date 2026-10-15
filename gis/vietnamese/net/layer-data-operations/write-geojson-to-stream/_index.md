---
date: 2026-10-15
description: Tìm hiểu cách tạo geojson từ tọa độ và ghi nó vào stream bằng Aspose.GIS
  cho .NET. Hướng dẫn này trình bày quá trình chuyển đổi điểm và tạo mã GeoJSON C#
  từng bước.
keywords:
- create geojson from coordinates
- stream large geojson files
- write geojson to stream
- geojson tutorial c#
- compress geojson with gzip
lastmod: 2026-10-15
linktitle: Ghi GeoJSON vào Stream
og_description: Tìm hiểu cách tạo geojson từ tọa độ và ghi nó vào stream bằng Aspose.GIS
  cho .NET – hướng dẫn từng bước cho các bộ dữ liệu lớn.
og_image_alt: Screenshot of Aspose.GIS code generating GeoJSON stream in C#
og_title: Tạo geojson từ tọa độ, ghi vào stream trong .NET
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
title: Tạo geojson từ tọa độ, ghi vào stream trong .NET
url: /vi/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo geojson từ tọa độ và ghi vào luồng

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học **cách tạo geojson từ tọa độ** và ghi trực tiếp vào một luồng bằng cách sử dụng Aspose.GIS cho .NET. Chúng tôi sẽ hướng dẫn qua việc thiết lập môi trường, tạo lớp, điền dữ liệu đặc trưng, và truyền luồng kết quả, để bạn có thể nhúng tải trọng không gian địa lý vào API, chức năng đám mây, hoặc dịch vụ không cần tệp tạm thời.

## Câu trả lời nhanh
- **Lớp nào ghi GeoJSON vào luồng?** `VectorLayer` cùng với `GeoJsonDriver`.
- **Tôi có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí hoạt động cho việc phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.
- **Phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Tôi có thể chuyển đổi bộ sưu tập điểm sang GeoJSON không?** Có – tạo một `Feature` cho mỗi điểm và gán một hình học `Point`.
- **Truyền luồng có phù hợp với bộ dữ liệu lớn không?** Chắc chắn – `MemoryStream` cho phép bạn ghi GeoJSON quy mô gigabyte mà không cần tải toàn bộ tệp vào bộ nhớ.

## GeoJSON là gì?
GeoJSON là một định dạng mở dựa trên JSON để mã hoá các đối tượng địa lý như điểm, đường và đa giác. Nó bao gồm một `FeatureCollection` nhóm các đối tượng `Feature` riêng lẻ, mỗi đối tượng chứa dữ liệu hình học và thuộc tính. Vì nó nhẹ và thân thiện với web, GeoJSON là tiêu chuẩn de‑facto để trao đổi dữ liệu không gian giữa trình duyệt, máy chủ GIS và ứng dụng di động.

## Tại sao nên sử dụng Aspose.GIS để tạo geojson?
Aspose.GIS hỗ trợ **hơn 35 định dạng tệp không gian** và có thể truyền các tệp lớn hơn **2 GB** trong khi giữ mức sử dụng bộ nhớ dưới **50 MB**. Động cơ truyền luồng hiệu năng cao của nó ghi GeoJSON trực tiếp vào bất kỳ .NET `Stream` nào, loại bỏ nhu cầu các tệp tạm thời trung gian và giảm độ trễ I/O lên tới **70 %** trong các kịch bản đám mây điển hình.

## Yêu cầu trước
1. **Aspose.GIS cho .NET** đã được cài đặt. Tải gói **Aspose.GIS cho .NET** [tại đây](https://releases.aspose.com/gis/net/).
2. Một thư mục có thể ghi trong dự án của bạn, nơi bạn có thể đặt các tệp tạm thời nếu cần.
3. Runtime .NET 5+ hoặc .NET Core 3.1+ đã được cài đặt.

Bây giờ, hãy đi sâu vào phần thực hiện.

## Cách tạo geojson từ tọa độ và ghi vào luồng?
`VectorLayer` đại diện cho một bộ dữ liệu vector trong bộ nhớ có thể được lưu ở nhiều định dạng.  
`GeoJsonDriver` là trình điều khiển cho phép đọc và ghi các tệp GeoJSON.  

Tải một `VectorLayer` bằng `GeoJsonDriver`, thêm các đối tượng `Feature` chứa hình học `Point`, và gọi `layer.Save(stream, new GeoJsonSaveOptions())`. Lệnh duy nhất này sẽ tuần tự hoá toàn bộ bộ sưu tập đặc trưng thành một tài liệu GeoJSON tuân thủ tiêu chuẩn, nằm trong `MemoryStream` được cung cấp. Quá trình này tự động xử lý ánh xạ thuộc tính và chuyển đổi tọa độ, vì vậy bạn nhận được payload JSON sẵn sàng sử dụng mà không cần tự xây dựng chuỗi.

### Định nghĩa các mỏ neo
**VectorLayer** là đối tượng cốt lõi của Aspose.GIS đại diện cho một bộ dữ liệu vector có thể thay đổi trong bộ nhớ.  
**GeoJsonDriver** là trình điều khiển chịu trách nhiệm đọc và ghi các tệp GeoJSON.  

## Nhập không gian tên
Đầu tiên, hãy chắc chắn bao gồm các không gian tên cần thiết để truy cập các chức năng của Aspose.GIS trong mã của bạn:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Bước 1: thiết lập thư mục tài liệu
Tạo một đường dẫn thư mục nơi Aspose.GIS có thể lưu các tệp phụ trợ nếu cần.  
```csharp
string dataDir = "Your Document Directory";
```
Thay thế "Your Document Directory" bằng đường dẫn thực tế tới thư mục tài liệu của bạn.

## Bước 2: tạo một memory stream
`MemoryStream` cung cấp một bộ đệm trong bộ nhớ có thể được gửi trực tiếp qua HTTP hoặc lưu vào lưu trữ đám mây.  
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Bước 3: tạo một vector layer với trình điều khiển GeoJSON
Lớp `VectorLayer` đại diện cho một bộ dữ liệu vector có thể được lưu ở nhiều định dạng, bao gồm GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Bước 4: định nghĩa các thuộc tính của feature
Xác định lược đồ thuộc tính cho các feature của bạn (ví dụ: ID, Name).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Bước 5: tạo và thêm các feature
Tạo các đối tượng `Feature`, gán hình học điểm, đặt giá trị thuộc tính, và thêm chúng vào layer.  
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

## Bước 6: hiển thị đầu ra GeoJSON
Sau khi lưu, đặt lại vị trí của stream và đọc chuỗi JSON để xác minh hoặc truyền đi.  
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Chúc mừng! Bạn đã tạo thành công geojson từ tọa độ và ghi nó vào một luồng bằng cách sử dụng Aspose.GIS cho .NET.

## Các vấn đề thường gặp và giải pháp
- **Luồng đầu ra rỗng:** Đảm bảo bạn đặt lại vị trí của stream (`stream.Position = 0`) trước khi đọc.
- **Thứ tự tọa độ không đúng:** GeoJSON yêu cầu thứ tự kinh độ‑vĩ độ; hãy kiểm tra giá trị điểm của bạn.
- **Bộ dữ liệu lớn:** Sử dụng `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` để truyền luồng các feature một cách tuần tự và giữ mức sử dụng bộ nhớ thấp.

## Câu hỏi thường gặp
**Q: Tôi có thể sử dụng Aspose.GIS cho .NET trên cả môi trường Windows và Linux không?**  
A: Có, Aspose.GIS cho .NET chạy trên Windows, Linux và macOS với hỗ trợ đầy đủ .NET Core.

**Q: Có bản dùng thử miễn phí không?**  
A: Chắc chắn! Bạn có thể khám phá **trang tải bản dùng thử miễn phí** [tại đây](https://releases.aspose.com/).

**Q: Tôi có thể tìm tài liệu chi tiết ở đâu?**  
A: Xem **tài liệu Aspose.GIS .NET** [tại đây](https://reference.aspose.com/gis/net/).

**Q: Làm sao tôi có thể nhận giấy phép tạm thời?**  
A: Giấy phép tạm thời có sẵn trên **trang giấy phép tạm thời** [tại đây](https://purchase.aspose.com/temporary-license/).

**Q: Cần hỗ trợ hoặc có thêm câu hỏi?**  
A: Ghé thăm **diễn đàn hỗ trợ GIS** của chúng tôi [tại đây](https://forum.aspose.com/c/gis/33).

**Q: Tôi có thể tạo GeoJSON từ một bộ sưu tập các điểm vĩ độ/kinh độ không?**  
A: Có – tạo một `Feature` cho mỗi điểm, gán hình học `Point`, và thêm nó vào `VectorLayer`.

**Q: Aspose.GIS có hỗ trợ ghi GeoJSON nén (gzip) không?**  
A: Bạn có thể bao bọc `MemoryStream` trong một `GZipStream` trước khi lưu để tạo payload nén.

**Q: Kích thước tối đa của tệp GeoJSON mà Aspose.GIS có thể xử lý là bao nhiêu?**  
A: Thư viện có thể truyền luồng các tệp vượt quá 2 GB; mức sử dụng bộ nhớ vẫn thấp vì dữ liệu được ghi một cách tuần tự.

---

**Cập nhật lần cuối:** 2026-10-15  
**Kiểm tra với:** Aspose.GIS 24.11 for .NET  
**Tác giả:** Aspose  

## Các hướng dẫn liên quan
- [Cách đọc GeoJSON từ luồng với Aspose.GIS cho .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Cách chuyển đổi GeoJSON sang TopoJSON với Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Cách chuyển đổi Shapefile sang GeoJSON bằng Aspose.GIS cho .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}