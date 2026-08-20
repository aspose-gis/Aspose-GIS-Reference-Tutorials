---
date: 2026-07-05
description: Tìm hiểu cách chuyển đổi shapefile sang geojson bằng Aspose.GIS cho .NET.
  Hướng dẫn cũng bao gồm việc sao chép thuộc tính giữa các lớp và tạo tệp geojson
  bằng c#.
keywords:
- convert shapefile to geojson
- export shapefile as geojson
- aspose gis conversion
- read shapefile c#
- write geojson c#
linktitle: Trích xuất tính năng sang GeoJSON
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  headline: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  name: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  steps:
  - name: Open Input Shapefile
    text: The `VectorLayer.Open` method reads a Shapefile and returns an enumerable
      collection of `Feature` objects that you can iterate over.
  - name: Create Output GeoJSON
    text: '`VectorLayer.Create` with the `Drivers.GeoJson` driver creates an empty
      GeoJSON file ready to receive features.'
  - name: Copy Attributes Between Layers
    text: '`CopyAttributes` copies the attribute schema (field names and data types)
      from the source Shapefile to the new GeoJSON layer in a single call.'
  - name: Process Features
    text: Iterate through each feature in the Shapefile so you can apply any custom
      logic before writing it out.
  - name: Filter Features by Date
    text: In this example we skip records whose `dob` (date of birth) field is missing
      or earlier than 1 Jan 1982. Adjust the filter to match your own data requirements.
  - name: Construct a New Feature (C# Generate GeoJSON File)
    text: A `Feature` represents a single spatial element containing geometry and
      attribute data. Here we build a new `Feature` for the GeoJSON layer, copy the
      geometry and attribute values, and add it to the output. This is the core of
      *c# generate geojson file*. Congratulations! You’ve successfully **conver
  type: HowTo
- questions:
  - answer: Visit the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for in‑depth information.
    question: Where can I find more documentation?
  - answer: You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I seek support?
  - answer: Yes, you can find the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can buy the product [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Chuyển đổi Shapefile sang GeoJSON với Aspose.GIS cho .NET
url: /vi/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển đổi Shapefile sang GeoJSON với Aspose.GIS cho .NET

## Giới thiệu
Trong hướng dẫn chi tiết, từng bước này, bạn sẽ học **cách chuyển đổi shapefile sang geojson** bằng thư viện mạnh mẽ Aspose.GIS cho .NET. Cho dù bạn đang xây dựng dịch vụ web bản đồ, chuẩn bị dữ liệu cho ứng dụng GIS di động, hoặc chỉ cần trao đổi dữ liệu giữa các định dạng, hướng dẫn này sẽ cho bạn biết chính xác những gì cần làm, lý do mỗi bước quan trọng, và cách tránh các lỗi phổ biến.

## Câu trả lời nhanh
- **Mục tiêu của hướng dẫn này là gì?** Chuyển đổi Shapefile sang tệp GeoJSON, sao chép thuộc tính giữa các lớp, và tạo ra kết quả bằng C#.
- **Thư viện nào được yêu cầu?** Aspose.GIS cho .NET.
- **Tôi có cần giấy phép không?** Cần một giấy phép tạm thời hoặc đầy đủ cho môi trường sản xuất; bản dùng thử miễn phí có thể dùng để đánh giá.
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 10‑15 phút cho một chuyển đổi cơ bản.
- **Tôi có thể chạy trên .NET Core/.NET 6 không?** Có – mã hoạt động trên tất cả các phiên bản .NET được hỗ trợ.

## Chuyển đổi shapefile sang geojson là gì?
Chuyển đổi một Shapefile sang GeoJSON có nghĩa là đọc các đối tượng vector từ định dạng Shapefile cổ điển của ESRI và ghi chúng ra dưới dạng tài liệu GeoJSON hiện đại, thân thiện với web. Việc chuyển đổi này cho phép bạn đưa dữ liệu GIS trực tiếp vào các thư viện bản đồ JavaScript như Leaflet hoặc Mapbox GL, và đơn giản hoá việc trao đổi dữ liệu giữa các công cụ GIS trên máy tính để bàn và các API web.

## Tại sao nên sử dụng Aspose.GIS cho việc chuyển đổi này?
Aspose.GIS trừu tượng hoá việc phân tích nhị phân cấp thấp, hỗ trợ hơn 50 định dạng nhập và xuất, và có thể xử lý các bộ dữ liệu hàng trăm trang mà không cần tải toàn bộ tệp vào bộ nhớ. Thư viện còn cung cấp một API hướng đối tượng sạch sẽ, hoạt động trên .NET Framework, .NET Core và .NET 5/6, giúp bạn tập trung vào logic nghiệp vụ thay vì các chi tiết định dạng.

## Yêu cầu trước
- Aspose.GIS cho .NET: Đảm bảo bạn đã cài đặt thư viện. Nếu chưa, bạn có thể tải xuống từ [trang Aspose.GIS cho .NET](https://releases.aspose.com/gis/net/).
- Dữ liệu Shapefile: Có một Shapefile sẵn sàng để nhập. Nếu cần dữ liệu mẫu, bạn có thể tìm trong [tài liệu Aspose.GIS](https://reference.aspose.com/gis/net/).
- Môi trường .NET: Thiết lập môi trường .NET để chạy mã được cung cấp.
- Thư mục tài liệu: Xác định đường dẫn tới thư mục tài liệu của bạn trong đoạn mã.

Bây giờ bạn đã có mọi thứ sẵn sàng, hãy bắt đầu chuyển đổi shapefile sang geojson!

## Cách chuyển đổi Shapefile sang GeoJSON
Tải Shapefile nguồn, tạo lớp GeoJSON đích, sao chép schema thuộc tính, lọc bản ghi, và ghi kết quả—tất cả trong một vài bước ngắn gọn. Quy trình hoàn chỉnh vừa vặn trong một khối `using` duy nhất, đảm bảo tài nguyên được giải phóng tự động.

### Bước 1: Mở Shapefile đầu vào
Phương thức `VectorLayer.Open` đọc một Shapefile và trả về một tập hợp có thể lặp lại các đối tượng `Feature` mà bạn có thể duyệt.

```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```

### Bước 2: Tạo GeoJSON đầu ra
`VectorLayer.Create` với driver `Drivers.GeoJson` tạo một tệp GeoJSON trống sẵn sàng nhận các đối tượng.

```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```

### Bước 3: Sao chép thuộc tính giữa các lớp
`CopyAttributes` sao chép schema thuộc tính (tên trường và kiểu dữ liệu) từ Shapefile nguồn sang lớp GeoJSON mới trong một lần gọi.

```csharp
outputLayer.CopyAttributes(inputLayer);
```

### Bước 4: Xử lý các đối tượng
Duyệt qua từng đối tượng trong Shapefile để bạn có thể áp dụng bất kỳ logic tùy chỉnh nào trước khi ghi ra.

```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```

### Bước 5: Lọc đối tượng theo ngày
Trong ví dụ này chúng tôi bỏ qua các bản ghi có trường `dob` (ngày sinh) bị thiếu hoặc sớm hơn 1 Jan 1982. Điều chỉnh bộ lọc để phù hợp với yêu cầu dữ liệu của bạn.

```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```

### Bước 6: Tạo một Đối tượng Mới (C# Tạo tệp GeoJSON)
`Feature` đại diện cho một phần tử không gian duy nhất chứa dữ liệu hình học và thuộc tính.  
Ở đây chúng tôi tạo một `Feature` mới cho lớp GeoJSON, sao chép hình học và giá trị thuộc tính, và thêm nó vào đầu ra. Đây là phần cốt lõi của *c# generate geojson file*.

```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```

Chúc mừng! Bạn đã thành công **chuyển đổi shapefile sang geojson** và học được cách **sao chép thuộc tính giữa các lớp** trong quá trình thực hiện.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| Tệp đầu ra rỗng | `CopyAttributes` được gọi sau khi lớp đầu ra đã đóng | Đảm bảo khối `using` cho `outputLayer` vẫn mở cho đến khi tất cả các đối tượng được thêm. |
| Bộ lọc ngày loại bỏ tất cả bản ghi | Tên trường sai hoặc định dạng ngày không mong đợi | Kiểm tra lại tên thuộc tính (`dob`) và sử dụng `GetValue<string>` nếu ngày được lưu dưới dạng chuỗi. |
| Lỗi giấy phép | Chạy mà không có giấy phép Aspose.GIS hợp lệ trong môi trường sản xuất | Áp dụng giấy phép tạm thời hoặc đầy đủ như mô tả trong tài liệu Aspose. |

## Câu hỏi thường gặp
**Q: Tôi có thể tìm thêm tài liệu ở đâu?**  
**A:** Truy cập [tài liệu Aspose.GIS](https://reference.aspose.com/gis/net/) để có thông tin chi tiết.

**Q: Làm sao tôi có thể nhận giấy phép tạm thời?**  
**A:** Bạn có thể nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể tìm hỗ trợ ở đâu?**  
**A:** Tham gia [diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33) để nhận hỗ trợ cộng đồng và thảo luận.

**Q: Có bản dùng thử miễn phí không?**  
**A:** Có, bạn có thể tìm bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

**Q: Tôi có thể mua Aspose.GIS cho .NET ở đâu?**  
**A:** Bạn có thể mua sản phẩm [tại đây](https://purchase.aspose.com/buy).

## Kết luận
Trong hướng dẫn này, chúng tôi đã khám phá quy trình đầy đủ để **chuyển đổi shapefile sang geojson** bằng Aspose.GIS cho .NET, trình bày cách **sao chép thuộc tính giữa các lớp**, và giới thiệu một cách sạch sẽ để *c# generate geojson file*. Hãy thử nghiệm với các bộ lọc khác nhau, bộ dữ liệu lớn hơn, hoặc các phép biến đổi hình học bổ sung để tận dụng tối đa khả năng của thư viện.

---

**Cập nhật lần cuối:** 2026-07-05  
**Đã kiểm tra với:** Aspose.GIS for .NET (latest stable release)  
**Tác giả:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Các hướng dẫn liên quan

- [Cách chuyển đổi GeoJSON sang File GDB bằng Aspose.GIS cho .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Cách đọc GeoJSON từ luồng với Aspose.GIS cho .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Cách chuyển đổi GeoJSON sang TopoJSON với Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}