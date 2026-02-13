---
date: 2026-02-13
description: Học cách chuyển đổi tọa độ sang DMS với Aspose.GIS cho .NET. Hướng dẫn
  C# chi tiết này chỉ ra cách chuyển đổi vĩ độ, kinh độ và độ thập phân sang DMS và
  nhiều hơn nữa.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Cách chuyển đổi tọa độ sang DMS với Aspose.GIS cho .NET
url: /vi/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Chuyển Đổi Tọa Độ Sang DMS với Aspose.GIS

## Introduction
Trong hướng dẫn này, bạn sẽ học **cách chuyển đổi tọa độ** sang DMS (độ, phút, giây) bằng thư viện mạnh mẽ Aspose.GIS cho .NET. Dù bạn cần **c# convert lat long**, tạo chuỗi vị trí dễ đọc cho con người, hoặc chỉ đơn giản khám phá các định dạng tọa độ khác nhau, hướng dẫn này sẽ dẫn bạn qua từng bước với giải thích rõ ràng và mã C# sẵn sàng chạy.

## Quick Answers
- **Ý nghĩa của “convert coordinates to DMS” là gì?** Nó chuyển đổi các giá trị vĩ độ/kinh độ số sang ký hiệu truyền thống độ‑phút‑giây.  
- **Thư viện nào thực hiện việc chuyển đổi?** Aspose.GIS cho .NET cung cấp lớp `GeoConvert` với hỗ trợ định dạng tích hợp.  
- **Có cần giấy phép để thử không?** Có bản dùng thử miễn phí; giấy phép thương mại cần thiết cho việc sử dụng trong môi trường sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, và .NET 5/6+.  
- **Có thể dùng cùng một đoạn mã cho các định dạng khác không?** Có — chỉ cần thay đổi giá trị enum `PointFormats` (ví dụ: `DecimalDegrees`, `GeoRef`).  

## How to Convert Coordinates to DMS
Trước khi đi vào mã, hãy làm rõ lý do DMS vẫn còn giá trị. Các nhà bản đồ, phi công và nhiều nhà cung cấp dữ liệu GIS dựa vào DMS vì nó thân thiện với con người và phù hợp với các bản đồ truyền thống. Aspose.GIS loại bỏ nhu cầu tính toán thủ công, cho phép bạn tập trung vào logic ứng dụng.

## What is coordinate conversion to DMS?
Việc chuyển đổi tọa độ sang DMS chuyển các giá trị vĩ độ và kinh độ thập phân thành định dạng như `25°30'00"N 45°30'00"E`. Định dạng này được sử dụng rộng rãi trong bản đồ học, điều hướng và trao đổi dữ liệu GIS.

## Why use Aspose.GIS for coordinate conversion?
- **API tất cả trong một** – Không cần thư viện bên ngoài hay phép tính phức tạp; Aspose.GIS xử lý việc phân tích và định dạng nội bộ.  
- **Độ chính xác cao** – Xử lý chính xác các trường hợp đặc biệt như giá trị âm và ký hiệu bán cầu.  
- **Đa nền tảng** – Hoạt động giống nhau trên Windows, Linux và macOS với runtime .NET.  
- **Mở rộng** – Dễ dàng chuyển đổi giữa DMS, độ thập phân, độ‑phút thập phân, và định dạng GeoRef.  

## Prerequisites
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

1. **Kiến thức cơ bản về C#** – Quen thuộc với biến, gọi phương thức và xuất ra console.  
2. **Aspose.GIS đã được cài đặt** – Tải gói mới nhất từ [trang web Aspose.GIS](https://releases.aspose.com/gis/net/).  

## Import Namespaces
First, import the namespaces required for GIS operations:

```csharp
using System;
using Aspose.Gis;
```

## Step‑by‑step guide

### Step 1: Start the conversion process
Chúng ta in ra một thông báo thân thiện để bạn biết bản demo đã bắt đầu.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Step 2: Convert to Decimal Degrees  
Mặc dù mục tiêu cuối cùng là DMS, chúng ta bắt đầu bằng cách hiển thị biểu diễn thập phân gốc. Điều này cũng minh họa đường **decimal degrees to dms** mà bạn sẽ theo sau.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Step 3: Convert to Degree Decimal Minutes  
Định dạng này (`DD°MM.m'`) là bước trung gian phổ biến khi bạn cần *convert lat long degree minutes*.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Step 4: Convert to Degree Minutes Seconds (DMS)  
Đây là phần cốt lõi của hướng dẫn—**convert coordinates to DMS**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Step 5: Convert to GeoRef  
Để đầy đủ, chúng ta cũng trình diễn định dạng `GeoRef`, hữu ích trong quy trình xử lý ảnh viễn thám.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Common Issues and Solutions
- **Ký tự bán cầu không đúng** – Đảm bảo bạn truyền giá trị dương cho bắc/đông và âm cho nam/tây; API sẽ tự động thêm hậu tố đúng.  
- **Kết quả đầu ra trống không mong muốn** – Kiểm tra rằng assembly `Aspose.Gis` được tham chiếu đúng và dự án nhắm tới phiên bản .NET được hỗ trợ.  
- **Không tìm thấy giấy phép** – Đặt file giấy phép của bạn ở thư mục gốc của ứng dụng hoặc thiết lập nó bằng mã: `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.  

## Frequently Asked Questions

**Q: Aspose.GIS có tương thích với các ngôn ngữ lập trình khác không?**  
A: Aspose.GIS chủ yếu hướng tới các nhà phát triển .NET, nhưng cũng có phiên bản Java.

**Q: Tôi có thể dùng thử Aspose.GIS trước khi mua không?**  
A: Có, bạn có thể truy cập bản dùng thử miễn phí của Aspose.GIS từ [trang web](https://releases.aspose.com/).

**Q: Làm sao tôi có thể nhận hỗ trợ cho Aspose.GIS?**  
A: Bạn có thể tìm trợ giúp tại diễn đàn cộng đồng Aspose.GIS [tại đây](https://forum.aspose.com/c/gis/33).

**Q: Có giấy phép tạm thời cho Aspose.GIS không?**  
A: Có, bạn có thể lấy giấy phép tạm thời từ [trang giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể mua Aspose.GIS ở đâu?**  
A: Bạn có thể mua Aspose.GIS từ [trang mua hàng](https://purchase.aspose.com/buy).

## Conclusion
Bằng cách thực hiện các bước trên, bạn đã biết cách **convert coordinates to DMS** và các định dạng GIS phổ biến khác bằng Aspose.GIS cho .NET. Khả năng này cho phép bạn tích hợp liền mạch các chuỗi vị trí dễ đọc vào ứng dụng bản đồ, báo cáo, hoặc bất kỳ quy trình dữ liệu không gian nào. Hãy thoải mái thử nghiệm với các giá trị vĩ độ/kinh độ khác nhau và khám phá các định dạng khác mà lớp `GeoConvert` cung cấp.

---

**Cập nhật lần cuối:** 2026-02-13  
**Kiểm thử với:** Aspose.GIS 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}