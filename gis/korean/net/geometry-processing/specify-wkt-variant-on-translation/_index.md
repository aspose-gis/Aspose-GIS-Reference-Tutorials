---
title: Aspose.GIS를 사용하여 번역 시 WKT 변형 지정
linktitle: 번역 시 WKT 변형 지정
second_title: Aspose.GIS .NET API
description: 공간 데이터 표현 형식과 정밀도를 효과적으로 제어하기 위해 .NET용 Aspose.GIS에서 WKT 변형을 지정하는 방법을 알아보세요.
type: docs
weight: 19
url: /ko/net/geometry-processing/specify-wkt-variant-on-translation/
---
## 소개
.NET용 Aspose.GIS는 개발자가 .NET 애플리케이션에서 GIS(지리 정보 시스템) 데이터를 쉽게 사용할 수 있도록 하는 강력한 라이브러리입니다. Aspose.GIS가 제공하는 필수 기능 중 하나는 번역 중에 WKT(Well-Known Text) 변형을 지정하여 사용자가 공간 데이터 표현의 형식과 정밀도를 제어할 수 있도록 하는 기능입니다. 이 튜토리얼에서는 .NET용 Aspose.GIS를 사용하여 WKT 변형을 단계별로 지정하는 방법을 살펴보겠습니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. .NET용 Aspose.GIS: 다음 사이트에서 .NET용 Aspose.GIS를 다운로드하여 설치하세요.[다운로드 페이지](https://releases.aspose.com/gis/net/).
2. 개발 환경: .NET 개발 환경이 설정되어 있는지 확인하세요.
3. 기본 지식: C# 프로그래밍 언어 및 .NET 프레임워크에 대한 지식.

## 네임스페이스 가져오기
코드에서 Aspose.GIS 기능을 사용하기 전에 필요한 네임스페이스를 가져옵니다.
```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```
## 1단계: 점 개체 만들기
 먼저`Point` 위도, 경도 및 선택적 측정값(M) 값이 있는 객체:
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## 2단계: 공간 참조 시스템(SRS) 설정
SRS(공간 참조 시스템)를 포인트 개체에 할당합니다. 이 예에서는 WGS84 공간 참조 시스템을 사용합니다.
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## 3단계: WKT 변형 지정
 이제 번역을 위해 WKT 변형을 지정합니다. Aspose.GIS는 다음을 포함하여 다양한 WKT 변형을 지원합니다.`Iso`, `SimpleFeatureAccessOutdated` , 그리고`ExtendedPostGis`. 요구 사항에 따라 적절한 변형을 선택하십시오.
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // 포인트M(23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // 포인트 (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM(23.5732, 25.3421, 40.3)
```
## 4단계: 숫자 형식 제어
WKT 표현에서 좌표의 숫자 형식을 제어할 수 있습니다. Aspose.GIS는 소수 정밀도를 지정하는 옵션을 제공합니다.
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // 포인트 M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // 포인트M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // 포인트 M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // 포인트M (23.573 25.342 40.3)
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.GIS를 사용하여 번역 시 WKT 변형을 지정하는 방법을 배웠습니다. 위에 설명된 단계를 따르면 개발자는 .NET 애플리케이션에서 공간 데이터 표현의 형식과 정밀도를 효과적으로 제어하여 지리 정보 시스템의 유연성과 유용성을 향상시킬 수 있습니다.
## FAQ
### Aspose.GIS는 모든 버전의 .NET과 호환됩니까?
예, Aspose.GIS는 .NET Framework 4.0 이상을 지원합니다.
### 상업용 프로젝트에 Aspose.GIS를 사용할 수 있나요?
예, Aspose.GIS는 개인 및 상업 프로젝트 모두에 사용할 수 있습니다.
### Aspose.GIS는 다른 공간 데이터 형식을 지원합니까?
예, Aspose.GIS는 ESRI Shapefile, GeoJSON 및 KML을 포함한 광범위한 공간 데이터 형식을 지원합니다.
### Aspose.GIS에 대한 무료 평가판이 있습니까?
 예, 다음에서 Aspose.GIS 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Aspose.GIS에 대한 도움이나 지원은 어디서 받을 수 있나요?
 질문을 게시하거나 Aspose.GIS 커뮤니티에서 도움을 구할 수 있습니다.[법정](https://forum.aspose.com/c/gis/33).