---
date: 2025-12-11
description: Tìm hiểu cách chuyển đổi tọa độ sang DMS bằng Aspose.GIS cho .NET. Bao
  gồm các ví dụ C#, chuyển đổi vĩ độ‑kinh độ bằng C#, và hướng dẫn từng bước.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Chuyển đổi tọa độ sang DMS với Aspose.GIS cho .NET
url: /vi/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển Đổi Tọa Độ Sang DMS với Aspose.GIS

## Giới thiệu
Trong hướng dẫn này, bạn sẽ khám phá cách **chuyển đổi tọa độ sang DMS** (độ, phút, giây) bằng thư viện mạnh mẽ Aspose.GIS cho .NET. Dù bạn cần **c# convert latitude longitude** cho các ứng dụng bản đồ, tạo chuỗi vị trí dễ đọc cho con người, hay chỉ đơn giản là khám phá các định dạng tọa độ khác nhau, hướng dẫn này sẽ dẫn bạn qua từng bước với giải thích rõ ràng và mã C# sẵn sàng chạy.

## Trả Lời Nhanh
- **“chuyển đổi tọa độ sang DMS” có nghĩa là gì?** Nó biến các giá trị vĩ độ/kinh độ số thành ký hiệu truyền thống độ‑phút‑giây.  
- **Thư viện nào thực hiện việc chuyển đổi?** Aspose.GIS cho .NET cung cấp lớp `GeoConvert` với hỗ trợ định dạng tích hợp.  
- **Tôi có cần giấy phép để thử không?** Có bản dùng thử miễn phí; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, và .NET 5/6+.  
- **Tôi có thể dùng cùng một đoạn mã cho các định dạng khác không?** Có — chỉ cần thay đổi giá trị enum `PointFormats` (ví dụ: `DecimalDegrees`, `GeoRef`).  

## Chuyển đổi tọa độ sang DMS là gì?
Việc chuyển đổi tọa độ sang DMS ghi lại các giá trị vĩ độ và kinh độ thập phân thành định dạng như `25°30'00"N 45°30'00"E`. Định dạng này được sử dụng rộng rãi trong bản đồ học, hàng hải và trao đổi dữ liệu GIS.

## Tại sao nên dùng Aspose.GIS cho việc chuyển đổi tọa độ?
- **API toàn diện** – Không cần thư viện bên ngoài hay phép tính phức tạp; Aspose.GIS tự xử lý việc phân tích và định dạng.  
- **Độ chính xác cao** – Xử lý chính xác các trường hợp biên như giá trị âm và ký hiệu bán cầu.  
- **Đa nền tảng** – Hoạt động giống nhau trên Windows, Linux và macOS .NET runtimes.  
- **Mở rộng** – Dễ dàng chuyển đổi giữa DMS, độ thập phân, độ‑phút thập phân, và định dạng GeoRef.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

1. **Kiến thức cơ bản về C#** – Quen thuộc với biến, gọi phương thức và xuất ra console.  
2. **Aspose.GIS đã được cài đặt** – Tải gói mới nhất từ [trang web Aspose.GIS](https://releases.aspose.com/gis/net/).  

## Nhập Không Gian Tên
Đầu tiên, nhập các không gian tên cần thiết cho các thao tác GIS:

```csharp
using System;
using Aspose.Gis;
```

## Hướng dẫn từng bước

### Bước 1: Bắt đầu quá trình chuyển đổi
Chúng ta in ra một thông báo thân thiện để bạn biết bản demo đã bắt đầu.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Bước 2: Chuyển sang Độ Thập Phân  
Mặc dù mục tiêu cuối cùng là DMS, chúng ta bắt đầu bằng cách hiển thị biểu diễn thập phân gốc.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Bước 3: Chuyển sang Độ Phút Thập Phân  
Định dạng này (`DD°MM.m'`) là bước trung gian phổ biến khi bạn cần *convert lat long degree minutes*.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Bước 4: Chuyển sang Độ Phút Giây (DMS)  
Đây là phần cốt lõi của hướng dẫn—**chuyển đổi tọa độ sang DMS**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Bước 5: Chuyển sang GeoRef  
Để đầy đủ, chúng ta cũng trình diễn định dạng `GeoRef`, hữu ích trong quy trình xử lý ảnh viễn thám.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Các Vấn Đề Thường Gặp và Giải Pháp
- **Ký tự bán cầu không đúng** – Đảm bảo bạn truyền giá trị dương cho bắc/đông và âm cho nam/tây; API sẽ tự động thêm hậu tố đúng.  
- **Kết quả trống không mong muốn** – Kiểm tra rằng assembly `Aspose.Gis` đã được tham chiếu đúng và dự án nhắm tới phiên bản .NET được hỗ trợ.  
- **Không tìm thấy giấy phép** – Đặt file giấy phép vào thư mục gốc của ứng dụng hoặc thiết lập bằng mã: `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.

## Câu Hỏi Thường Gặp

**Q: Aspose.GIS có tương thích với các ngôn ngữ lập trình khác không?**  
A: Aspose.GIS chủ yếu hướng tới các nhà phát triển .NET, nhưng cũng có phiên bản Java.

**Q: Tôi có thể thử Aspose.GIS trước khi mua không?**  
A: Có, bạn có thể truy cập bản dùng thử miễn phí của Aspose.GIS từ [website](https://releases.aspose.com/).

**Q: Làm sao tôi có thể nhận hỗ trợ cho Aspose.GIS?**  
A: Bạn có thể tìm trợ giúp tại diễn đàn cộng đồng Aspose.GIS [tại đây](https://forum.aspose.com/c/gis/33).

**Q: Có giấy phép tạm thời cho Aspose.GIS không?**  
A: Có, giấy phép tạm thời có thể được lấy từ [trang giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể mua Aspose.GIS ở đâu?**  
A: Bạn có thể mua Aspose.GIS từ [trang mua hàng](https://purchase.aspose.com/buy).

## Kết luận
Sau khi thực hiện các bước trên, bạn đã biết cách **chuyển đổi tọa độ sang DMS** và các định dạng GIS phổ biến khác bằng Aspose.GIS cho .NET. Khả năng này cho phép bạn tích hợp các chuỗi vị trí dễ đọc vào các ứng dụng bản đồ, báo cáo, hoặc bất kỳ quy trình dữ liệu không gian nào. Hãy thoải mái thử nghiệm với các giá trị vĩ độ/kinh độ khác nhau và khám phá các định dạng khác mà lớp `GeoConvert` cung cấp.

---

**Cập nhật lần cuối:** 2025-12-11  
**Đã kiểm tra với:** Aspose.GIS 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}