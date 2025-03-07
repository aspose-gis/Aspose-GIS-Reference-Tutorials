---
title: 형상에 다른 항목이 포함되어 있는지 확인
linktitle: 형상에 다른 항목이 포함되어 있는지 확인
second_title: Aspose.GIS .NET API
description: .NET 애플리케이션에 원활한 지리공간 데이터 통합을 위한 강력한 라이브러리인 Aspose.GIS for .NET을 살펴보세요.
weight: 14
url: /ko/net/geometry-analysis/check-geometry-contains-another/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 형상에 다른 항목이 포함되어 있는지 확인

## 소개
.NET용 Aspose.GIS는 개발자가 .NET 애플리케이션 내에서 지리공간 데이터를 원활하게 사용할 수 있게 해주는 강력한 라이브러리입니다. 매핑 애플리케이션을 구축하든, 지리공간 분석을 수행하든, 위치 기반 기능을 소프트웨어에 통합하든 Aspose.GIS는 직관적인 API와 강력한 기능을 제공하여 프로세스를 단순화합니다.
## 전제조건
.NET용 Aspose.GIS를 사용하기 전에 다음 전제 조건이 있는지 확인하세요.
### 1. .NET 개발 환경 설정
컴퓨터에 작동하는 .NET 개발 환경이 설정되어 있는지 확인하세요. 여기에는 .NET SDK를 올바르게 설치하고 구성하는 것이 포함됩니다.
### 2. Aspose.GIS 설치
 릴리스 페이지에서 라이브러리를 다운로드하여 .NET용 Aspose.GIS를 설치하세요.[여기](https://releases.aspose.com/gis/net/) . 설명서에 제공된 설치 지침을 따르십시오.[여기](https://reference.aspose.com/gis/net/)Aspose.GIS를 프로젝트에 통합합니다.
### 3. C#의 기본 이해
.NET용 Aspose.GIS는 주로 C#과 함께 사용되므로 C# 프로그래밍 언어에 익숙해지세요.

## 네임스페이스 가져오기
C# 프로젝트에서 Aspose.GIS 기능을 활용하는 데 필요한 네임스페이스를 가져옵니다.
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 1단계: 형상 개체 정의
먼저 Aspose.GIS 클래스를 사용하여 지오메트리 개체를 정의합니다.
```csharp
var geometry1 = new Polygon();
geometry1.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 4),
    new Point(4, 4),
    new Point(4, 0),
    new Point(0, 0),
});
geometry1.AddInteriorRing(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 3),
    new Point(3, 3),
    new Point(3, 1),
    new Point(1, 1),
}));
var geometry2 = new Point(2, 2);
```
## 2단계: 공간 격리 확인
다음으로, 하나의 도형에 다른 도형이 포함되어 있는지 확인하세요.
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); // 거짓
```
## 3단계: 다른 형상 정의
다른 기하학 객체를 정의하십시오:
```csharp
var geometry3 = new Point(0.5, 0.5);
```
## 4단계: 공간 격리 다시 확인
새로 정의된 기하학이 첫 번째 기하학 내에 포함되어 있는지 확인하십시오.
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); // 진실
```
## 5단계: 동등한 기능
 이해 했어`a.SpatiallyContains(b)` 는 다음과 같습니다`b.Within(a)`:
```csharp
Console.WriteLine(geometry3.Within(geometry1)); // 진실
```

## 결론
결론적으로 Aspose.GIS for .NET은 .NET 애플리케이션에서 지리공간 데이터를 처리하기 위한 강력한 도구를 제공합니다. 이 가이드를 따르고 제공된 예제를 활용하면 공간 포함 검사를 효율적으로 수행하고 프로젝트 내에서 다른 지리공간 기능을 활용할 수 있습니다.
## FAQ
### Q1: Aspose.GIS는 .NET Core와 호환됩니까?
A: 예, Aspose.GIS는 .NET Core를 완벽하게 지원하므로 다양한 플랫폼에서 지리공간 애플리케이션을 개발할 수 있습니다.
### Q2: Aspose.GIS를 사용하여 지리공간 분석을 수행할 수 있습니까?
A: 물론 Aspose.GIS는 공간 쿼리, 거리 계산, 기하학 조작 등 지리공간 분석을 위한 다양한 기능을 제공합니다.
### Q3: Aspose.GIS에 대한 업데이트는 얼마나 자주 출시됩니까?
A: Aspose.GIS는 성능을 개선하고, 새로운 기능을 추가하고, 보고된 문제를 해결하기 위해 정기적으로 업데이트를 출시합니다. 릴리스 페이지를 방문하여 최신 소식을 받아보실 수 있습니다.
### Q4: Aspose.GIS 사용자를 위한 커뮤니티 포럼이 있습니까?
A: 예, Aspose.GIS 커뮤니티 포럼에 가입할 수 있습니다.[여기](https://forum.aspose.com/c/gis/33) 다른 사용자와 소통하고, 질문하고, 경험을 공유하세요.
### Q5: 구매하기 전에 Aspose.GIS를 사용해 볼 수 있나요?
 A: 물론 무료 평가판을 다운로드하여 Aspose.GIS를 탐색할 수 있습니다.[여기](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
