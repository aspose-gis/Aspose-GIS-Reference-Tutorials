---
date: 2026-01-13
description: Tìm hiểu cách chuyển đổi shapefile sang geojson bằng Aspose.GIS cho .NET.
  Hướng dẫn cũng đề cập đến việc sao chép thuộc tính giữa các lớp và tạo tệp geojson
  bằng C#.
linktitle: Extract Features to GeoJSON
second_title: Aspose.GIS .NET API
title: Cách chuyển đổi Shapefile sang GeoJSON bằng Aspose.GIS cho .NET
url: /vi/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển đổi Shapefile sang GeoJSON với Aspose.GIS cho .NET

## Giới thiệu
Trong hướng dẫn chi tiết, từng bước này, bạn sẽ học **cách chuyển đổi shapefile sang geojson** bằng thư viện mạnh mẽ Aspose.GIS cho .NET. Dù bạn đang xây dựng dịch vụ web bản đồ, chuẩn bị dữ liệu cho ứng dụng GIS di động, hay chỉ cần trao đổi dữ liệu giữa các định dạng, hướng dẫn này sẽ chỉ cho bạn cách thực hiện, lý do mỗi bước quan trọng, và cách tránh các lỗi thường gặp.

## Câu trả lời nhanh
- **Bài hướng dẫn này đề cập đến gì?** Chuyển đổi Shapefile sang tệp GeoJSON, sao chép thuộc tính giữa các lớp, và tạo ra đầu ra bằng C#.
- **Thư viện nào được yêu cầu?** Aspose.GIS cho .NET.
- **Có cần giấy phép không?** Cần một giấy phép tạm thời hoặc đầy đủ cho môi trường sản xuất; bản dùng thử miễn phí đủ cho việc đánh giá.
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 10‑15 phút cho một chuyển đổi cơ bản.
- **Có thể chạy trên .NET Core/.NET 6 không?** Có – mã hoạt động trên mọi phiên bản .NET được hỗ trợ.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có:

- Aspose.GIS cho .NET: Đảm bảo đã cài đặt thư viện. Nếu chưa, bạn có thể tải về từ [trang Aspose.GIS cho .NET](https://releases.aspose.com/gis/net/).
- Dữ liệu Shapefile: Có một Shapefile sẵn sàng để nhập. Nếu cần dữ liệu mẫu, bạn có thể tìm ở [tài liệu Aspose.GIS](https://reference.aspose.com/gis/net/).
- Môi trường .NET: Thiết lập môi trường .NET để chạy mã được cung cấp.
- Thư mục tài liệu: Định nghĩa đường dẫn tới thư mục tài liệu của bạn trong đoạn mã mẫu.

Bây giờ bạn đã có mọi thứ sẵn sàng, hãy bắt đầu chuyển đổi shapefile sang geojson!

## “convert shapefile to geojson” là gì?
Chuyển đổi Shapefile sang GeoJSON có nghĩa là đọc các đối tượng vector từ định dạng Shapefile cổ điển của ESRI và ghi chúng ra dưới dạng tài liệu GeoJSON hiện đại, thân thiện với web. GeoJSON được sử dụng rộng rãi trong các thư viện bản đồ JavaScript (Leaflet, Mapbox GL) và API, vì vậy việc chuyển đổi này là một nhiệm vụ thường gặp trong phát triển GIS.

## Tại sao lại dùng Aspose.GIS cho việc chuyển đổi này?
Aspose.GIS trừu tượng hoá các chi tiết mức thấp của định dạng tệp, cho phép bạn sao chép bảng thuộc tính một cách dễ dàng, và cung cấp một API hướng đối tượng sạch sẽ hoạt động trên .NET Framework, .NET Core và .NET 5/6. Điều này giúp bạn tập trung vào logic nghiệp vụ thay vì phải phân tích các tệp nhị phân.

## Nhập không gian tên
Đầu tiên, bao gồm các không gian tên cần thiết trong mã của bạn:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Các không gian tên này là cần thiết để làm việc với các chức năng của Aspose.GIS.

## Cách chuyển đổi Shapefile sang GeoJSON
Dưới đây là quy trình đầy đủ được chia thành các bước rõ ràng. Mỗi bước bao gồm một giải thích ngắn và đoạn mã chính xác bạn cần sao chép vào dự án.

### Bước 1: Mở Shapefile đầu vào
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```
Mở Shapefile đầu vào bằng phương thức `VectorLayer.Open`. Điều này sẽ cung cấp cho bạn một tập hợp có thể lặp lại các đối tượng `Feature`.

### Bước 2: Tạo GeoJSON đầu ra
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```
Tạo tệp đầu ra bằng phương thức `VectorLayer.Create`, chỉ định driver `Drivers.GeoJson`.

### Bước 3: Sao chép thuộc tính giữa các lớp
```csharp
outputLayer.CopyAttributes(inputLayer);
```
Dòng lệnh duy nhất này sao chép schema thuộc tính (tên trường, kiểu) từ Shapefile nguồn sang lớp GeoJSON mới — đúng như mô tả của từ khóa phụ *copy attributes between layers*.

### Bước 4: Xử lý các đối tượng
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```
Duyệt qua mỗi đối tượng trong Shapefile để bạn có thể áp dụng bất kỳ logic tùy chỉnh nào trước khi ghi ra.

### Bước 5: Lọc đối tượng theo ngày
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
Trong ví dụ này, chúng ta bỏ qua các bản ghi có trường `dob` (ngày sinh) bị thiếu hoặc sớm hơn 1 Jan 1982. Bạn có thể điều chỉnh bộ lọc để phù hợp với yêu cầu dữ liệu của mình.

### Bước 6: Tạo đối tượng mới (C# Generate GeoJSON File)
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Ở đây chúng ta xây dựng một `Feature` mới cho lớp GeoJSON, sao chép hình học và giá trị thuộc tính, và thêm nó vào đầu ra. Đây là phần cốt lõi của *c# generate geojson file*.

Chúc mừng! Bạn đã **chuyển đổi shapefile sang geojson** thành công và đồng thời học được cách sao chép thuộc tính giữa các lớp.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| Tệp đầu ra rỗng | `CopyAttributes` được gọi sau khi lớp đầu ra đã đóng | Đảm bảo khối `using` cho `outputLayer` vẫn mở cho đến khi tất cả các đối tượng đã được thêm. |
| Bộ lọc ngày loại bỏ toàn bộ bản ghi | Tên trường sai hoặc định dạng ngày không mong đợi | Kiểm tra lại tên thuộc tính (`dob`) và sử dụng `GetValue<string>` nếu ngày được lưu dưới dạng chuỗi. |
| Ngoại lệ giấy phép | Chạy mà không có giấy phép Aspose.GIS hợp lệ trong môi trường sản xuất | Áp dụng giấy phép tạm thời hoặc đầy đủ như mô tả trong tài liệu Aspose. |

## Câu hỏi thường gặp
**H: Tôi có thể tìm tài liệu thêm ở đâu?**  
Đ: Truy cập [tài liệu Aspose.GIS](https://reference.aspose.com/gis/net/) để biết thông tin chi tiết.

**H: Làm sao để lấy giấy phép tạm thời?**  
Đ: Bạn có thể nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

**H: Tôi có thể nhận hỗ trợ ở đâu?**  
Đ: Tham gia [diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33) để được cộng đồng hỗ trợ và thảo luận.

**H: Có bản dùng thử miễn phí không?**  
Đ: Có, bạn có thể tải bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

**H: Tôi có thể mua Aspose.GIS cho .NET ở đâu?**  
Đ: Bạn có thể mua sản phẩm [tại đây](https://purchase.aspose.com/buy).

## Kết luận
Trong hướng dẫn này, chúng ta đã khám phá quy trình đầy đủ để **convert shapefile to geojson** bằng Aspose.GIS cho .NET, trình bày cách sao chép thuộc tính giữa các lớp, và giới thiệu cách *c# generate geojson file* một cách sạch sẽ. Hãy thử nghiệm với các bộ lọc khác nhau, bộ dữ liệu lớn hơn, hoặc các phép biến đổi hình học bổ sung để khai thác tối đa khả năng của thư viện.

---

**Cập nhật lần cuối:** 2026-01-13  
**Đã kiểm tra với:** Aspose.GIS cho .NET (phiên bản ổn định mới nhất)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}