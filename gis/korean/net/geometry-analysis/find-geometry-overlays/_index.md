---
title: .NET용 Aspose.GIS를 사용하여 형상 오버레이 마스터링
linktitle: 기하학 오버레이 찾기
second_title: Aspose.GIS .NET API
description: .NET용 Aspose.GIS를 사용하여 기하학적 오버레이 작업을 수행하는 방법을 알아보세요. 마스터 교차, 합집합, 차이 및 대칭 차이 연산.
type: docs
weight: 16
url: /ko/net/geometry-analysis/find-geometry-overlays/
---
## 소개
GIS(지리정보시스템) 영역에서 오버레이 작업은 공간 분석의 기본입니다. 이를 통해 다양한 공간 데이터 세트를 비교하고 결합하여 귀중한 통찰력을 얻을 수 있습니다. .NET용 Aspose.GIS는 기하학적 오버레이를 효율적으로 수행하기 위한 강력한 기능을 제공합니다. 이 튜토리얼에서는 Aspose.GIS for .NET을 사용하여 Intersection, Union, Difference 및 Symmetric Difference와 같은 다양한 오버레이 작업을 살펴보겠습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
### 1. .NET 개발 환경
컴퓨터에 .NET 개발 환경이 설정되어 있는지 확인하세요. .NET 웹사이트에서 .NET SDK를 다운로드하여 설치할 수 있습니다.
### 2. .NET 라이브러리용 Aspose.GIS
 다음에서 Aspose.GIS for .NET 라이브러리를 다운로드하여 설치하세요.[웹사이트](https://releases.aspose.com/gis/net/).
## 네임스페이스 가져오기
.NET용 Aspose.GIS 사용을 시작하기 전에 필요한 네임스페이스를 프로젝트로 가져와야 합니다.
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 1단계: 다각형 개체 만들기
먼저 공간 영역을 나타내는 두 개의 다각형 객체를 정의합니다.
```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```
## 2단계: 교차로 작업 수행
다음으로 두 다각형의 교차점을 찾아보겠습니다.
```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // 다각형
```
## 3단계: 교차점 인쇄
교차점 다각형의 점을 인쇄하겠습니다.
```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```
## 4단계: 연합 운영 수행
이제 두 다각형의 합집합을 찾아보겠습니다.
```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // 다각형
```
## 5단계: 유니온 포인트 인쇄
결합 다각형의 점을 인쇄합니다.
```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```
## 6단계: 차이 연산 수행
다음으로 두 다각형의 차이점을 찾아보겠습니다.
```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // 다각형
```
## 7단계: 차이점 인쇄
차이 다각형의 점을 인쇄합니다.
```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```
## 8단계: 대칭 차분 연산 수행
마지막으로 두 다각형의 대칭적 차이를 찾아보겠습니다.
```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // 다중 다각형
```
## 9단계: 대칭 차이 다각형 인쇄
대칭 차이로 각 다각형의 점을 인쇄합니다.
```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```
## 결론
지오메트리 오버레이를 마스터하는 것은 공간 분석에 매우 중요하며 .NET용 Aspose.GIS는 이러한 작업을 효율적으로 수행할 수 있는 포괄적인 도구 세트를 제공합니다. 이 튜토리얼을 따라 .NET용 Aspose.GIS를 활용하여 기하학적 모양에 대한 교차, 합집합, 차이 및 대칭 차이 작업을 수행하는 방법을 배웠습니다.
## FAQ
### Q: 상업용 프로젝트에서 .NET용 Aspose.GIS를 사용할 수 있습니까?
예, .NET용 Aspose.GIS는 상업용 및 비상업적 프로젝트 모두에서 사용할 수 있습니다.
### Q: .NET용 Aspose.GIS에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: .NET용 Aspose.GIS에 대한 지원을 어떻게 받을 수 있나요?
 Aspose.GIS 커뮤니티 포럼에서 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/gis/33).
### Q: .NET용 Aspose.GIS에 사용할 수 있는 임시 라이선스가 있습니까?
 예, 테스트 및 평가 목적으로 임시 라이선스를 사용할 수 있습니다. 당신은 그것을 얻을 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).
### Q: .NET용 Aspose.GIS를 직접 구입할 수 있나요?
 예, 웹사이트에서 .NET용 Aspose.GIS를 구입할 수 있습니다[여기](https://purchase.aspose.com/buy).