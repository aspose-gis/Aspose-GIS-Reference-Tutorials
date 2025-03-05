---
title: 지오메트리가 동일한지 확인하세요.
linktitle: 지오메트리가 동일한지 확인하세요.
second_title: Aspose.GIS .NET API
description: 이 포괄적인 튜토리얼을 통해 .NET용 Aspose.GIS를 사용하여 .NET 애플리케이션에서 형상의 동일성을 확인하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/geometry-analysis/check-geometries-for-equality/
---
## 소개
.NET용 Aspose.GIS는 개발자가 .NET 애플리케이션에서 지리공간 데이터를 효율적으로 사용할 수 있게 해주는 강력한 라이브러리입니다. 매핑 애플리케이션, 공간 분석 도구를 구축하거나 지리공간 기능을 기존 소프트웨어에 통합하는 경우 Aspose.GIS는 작업을 완료하는 데 필요한 도구를 제공합니다.
## 전제조건
.NET용 Aspose.GIS를 사용하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### .NET 프레임워크가 설치됨
시스템에 .NET Framework가 설치되어 있는지 확인하십시오. 마이크로소프트 홈페이지에서 다운로드 받으실 수 있습니다.
### .NET 라이브러리용 Aspose.GIS
 다음에서 .NET용 Aspose.GIS 라이브러리를 다운로드하여 설치하세요.[다운로드 페이지](https://releases.aspose.com/gis/net/). 설명서에 제공된 설치 지침을 따르십시오.
### 개발 환경
.NET 개발을 위해 Visual Studio 등 선호하는 개발 환경을 설정하세요.

## 네임스페이스 가져오기
.NET 애플리케이션에서 Aspose.GIS 기능을 사용하는 데 필요한 네임스페이스를 가져옵니다.
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 1단계: 형상 정의
먼저 비교하려는 형상을 정의합니다. 이 예에는 두 개의 기하학이 있습니다.`geometry1` 그리고`geometry2`.
```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```
## 2단계: 형상이 동일한지 확인
 이제 다음을 사용하여 기하학이 공간적으로 동일한지 확인하십시오.`SpatiallyEquals` Aspose.GIS에서 제공하는 방법입니다.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // 진실
```
 이것은 인쇄됩니다`True` 이후 콘솔로`geometry1` 그리고`geometry2` 공간적으로 동일합니다.
## 3단계: 형상 수정
 다음으로 수정해보자`geometry2` 새로운 점을 추가함으로써.
```csharp
geometry2.AddPoint(3, 3);
```
## 4단계: 평등성 재확인
이제 수정 후 형상의 동등성을 다시 확인하십시오.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // 거짓
```
 이번에는 출력이`False` 에 대한 수정으로 인해 형상이 더 이상 공간적으로 동일하지 않기 때문입니다.`geometry2`.

## 결론
결론적으로 Aspose.GIS for .NET은 .NET 애플리케이션에서 지리공간 데이터 작업을 위한 강력한 도구를 제공합니다. 이 단계별 가이드를 따르면 Aspose.GIS 방법을 사용하여 형상의 동일성을 쉽게 확인할 수 있습니다.
## FAQ
### 다른 .NET 프레임워크와 함께 .NET용 Aspose.GIS를 사용할 수 있습니까?
예, .NET용 Aspose.GIS는 .NET Core 및 .NET Standard를 포함한 다양한 .NET 프레임워크와 호환됩니다.
### .NET용 Aspose.GIS에 대한 무료 평가판이 있습니까?
 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[릴리스 페이지](https://releases.aspose.com/).
### .NET용 Aspose.GIS에 대한 문서는 어디서 찾을 수 있나요?
 자세한 문서는 다음에서 찾을 수 있습니다.[Aspose.GIS 문서 페이지](https://reference.aspose.com/gis/net/).
### .NET용 Aspose.GIS에 대한 지원을 받으려면 어떻게 해야 합니까?
 Aspose.GIS 커뮤니티 포럼에서 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/gis/33).
### .NET용 Aspose.GIS의 임시 라이선스를 구입할 수 있나요?
 예, 다음 사이트에서 임시 라이센스를 구입할 수 있습니다.[구매 페이지](https://purchase.aspose.com/temporary-license/).