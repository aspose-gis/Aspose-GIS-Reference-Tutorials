---
date: 2025-12-21
description: Aspose.GIS for .NET를 사용하여 기하학을 선형화하는 방법을 배우고, .NET 애플리케이션에서 효율적인 지리공간
  데이터 처리, 공간 분석 및 기하학 조작을 가능하게 합니다.
linktitle: Linearize a Geometry
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET를 사용하여 기하학을 선형화하는 방법
url: /ko/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 기하학 선형화

## 소개
매핑, 공간 분석 또는 데이터 교환 작업을 위해 **기하학을 선형화하는 방법**이 필요하다면, Aspose.GIS for .NET은 깔끔하고 프로그래밍 방식으로 이를 수행할 수 있는 방법을 제공합니다. 이 튜토리얼에서는 복잡한 기하학(곡선 및 복합 형태 포함)을 가져와 모든 GIS 시스템에서 작동하는 단순한 선형 표현으로 변환하는 전체 실전 예제를 단계별로 살펴보겠습니다.

## 빠른 답변
- **기하학을 선형화한다는 것은 무엇을 의미합니까?** 곡선 및 복합 형태를 직선 세그먼트로 변환하는 것입니다.  
- **왜 Aspose.GIS를 사용합니까?** 수십 가지 GIS 형식을 지원하며 외부 도구 없이도 기하학 변환을 처리합니다.  
- **전제 조건은?** .NET Framework 또는 .NET Core, Visual Studio, 그리고 Aspose.GIS 라이브러리.  
- **예제 실행에 걸리는 시간은?** 라이브러리를 설치한 후 5분 이내에 실행됩니다.  
- **다른 형식으로 저장할 수 있나요?** 예—KML 드라이버를 Shapefile, GeoJSON 등으로 교체하면 됩니다.

## 기하학 선형화란 무엇인가요?
기하학을 선형화한다는 것은 곡선이나 복합 형태를 일련의 직선 세그먼트(‘선형 기하학’)로 분해하는 것을 의미합니다. 이는 렌더링, 분석 및 선과 점만을 이해하는 도구와의 상호 운용성을 단순화합니다.

## 왜 기하학을 선형화해야 할까요?
- **성능:** 선형 기하학은 렌더링 및 쿼리가 더 빠릅니다.  
- **호환성:** 많은 GIS 플랫폼(예: 오래된 지도 서비스)은 선형 피처만 허용합니다.  
- **단순화:** 썸네일 생성, 빠른 미리보기, 또는 선형 입력을 요구하는 알고리즘에 데이터를 제공할 때 유용합니다.

## 전제 조건
코드에 들어가기 전에 다음이 준비되어 있는지 확인하십시오:

1. **Aspose.GIS for .NET** – [Aspose.GIS 웹사이트](https://releases.aspose.com/gis/net/)에서 다운로드하십시오.  
2. **.NET Framework**(또는 .NET Core)가 개발 머신에 설치되어 있어야 합니다.  
3. **Visual Studio**(또는 C# 호환 IDE)에서 샘플을 작성하고 실행할 수 있어야 합니다.

## 네임스페이스 가져오기
Aspose.GIS 기능을 사용하려면 필요한 네임스페이스를 가져오세요.

### 단계 1: Aspose.GIS 핵심 네임스페이스 가져오기
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### 단계 2: 대상 형식에 대한 드라이버 가져오기
이 예제에서는 결과를 KML 파일로 저장합니다:
```csharp
using Aspose.GIS.Kml;
```

## 기하학 선형화 방법 – 단계별 가이드
아래는 각 코드 라인을 자세히 살펴보며 **기하학을 선형화하는 방법**과 각 단계가 중요한 이유를 설명합니다.

### 단계 1: 출력 경로 정의
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
`"Your Document Directory"`를 KML 파일을 저장하려는 폴더 경로로 교체하십시오.

### 단계 2: 출력 파일용 레이어 생성
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
*레이어*는 지리적 피처를 담는 컨테이너입니다. 여기서는 선형화된 기하학을 담을 새로운 KML 레이어를 생성합니다.

### 단계 3: 새 피처 구성
```csharp
var feature = layer.ConstructFeature();
```
*피처*는 단일 지리 객체(점, 선, 폴리곤 등)를 나타냅니다. 이 피처에 선형 기하학을 연결합니다.

### 단계 4: 원본 복합 기하학 정의
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Well‑Known Text(WKT) 문자열에서 기하학을 생성합니다. 이 예제에는 `LineString`, `CompoundCurve`, `CircularString`이 포함되어 있어 선형화 시연에 적합합니다.

### 단계 5: 기하학 선형화
```csharp
var linear = geometry.ToLinearGeometry();
```
`ToLinearGeometry()` 메서드는 모든 곡선을 직선 세그먼트로 변환하여 원본 기하학의 *선형* 버전을 생성합니다.

### 단계 6: 선형 기하학을 피처에 할당
```csharp
feature.Geometry = linear;
```
이제 피처는 단순화된 선형 기하학을 보유합니다.

### 단계 7: 피처를 레이어에 추가
```csharp
layer.Add(feature);
```
마지막으로 피처를 KML 레이어에 추가합니다. `using` 블록이 종료될 때 선형 기하학이 출력 파일에 기록됩니다.

## 일반적인 함정 및 팁
- **경로 구분자:** 크로스 플랫폼 경로 구성을 위해 `Path.Combine`을 사용하십시오.  
- **대형 기하학:** 매우 복잡한 형태를 선형화하면 많은 정점이 생성될 수 있습니다. 점이 적게 필요하면 선형화 후 `Simplify()` 사용을 고려하십시오.  
- **드라이버 선택:** 다른 출력 형식이 필요하면 `Drivers.Kml`을 `Drivers.Shapefile`, `Drivers.GeoJson` 등으로 교체하고 파일 확장자를 적절히 조정하십시오.

## 결론
이 튜토리얼에서는 Aspose.GIS for .NET을 사용하여 **기하학을 선형화하는 방법**을 환경 설정부터 선형화된 결과를 KML 파일에 쓰는 과정까지 다루었습니다. 이제 이 워크플로를 매핑 애플리케이션, 데이터 처리 파이프라인 또는 단순화된 기하학이 필요한 모든 GIS 관련 프로젝트에 통합할 수 있습니다.

## FAQ
### Q: Aspose.GIS for .NET이 .NET Core와 호환되나요?
예, Aspose.GIS for .NET은 .NET Core와 호환되어 크로스 플랫폼 애플리케이션을 구축할 수 있습니다.

### Q: Aspose.GIS for .NET을 사용해 다양한 GIS 파일 형식을 다룰 수 있나요?
물론입니다! Aspose.GIS는 KML, Shapefile, GeoJSON 등을 포함한 다양한 GIS 파일 형식을 지원합니다.

### Q: Aspose.GIS가 공간 연산 및 분석을 지원하나요?
예, Aspose.GIS는 복잡한 지리공간 작업을 처리하기 위한 다양한 공간 연산 및 분석 기능을 제공합니다.

### Q: Aspose.GIS for .NET의 무료 체험판이 있나요?
예, [Aspose 웹사이트](https://releases.aspose.com/)에서 무료 체험판을 다운로드할 수 있습니다.

### Q: Aspose.GIS에 대한 도움과 지원은 어디서 찾을 수 있나요?
[Aspose.GIS 포럼](https://forum.aspose.com/c/gis/33)에서 커뮤니티와 Aspose 지원팀의 도움을 받을 수 있습니다.

## 자주 묻는 질문 (추가)

**Q: 3D(Z) 좌표를 포함한 기하학을 선형화할 수 있나요?**  
A: 예, `ToLinearGeometry()`는 2D 및 3D 기하학 모두에서 작동하며, Z 값은 결과 선 세그먼트에 보존됩니다.

**Q: 선형화가 출력 파일 크기에 어떤 영향을 줍니까?**  
A: 곡선을 많은 짧은 선 세그먼트로 변환하면 파일 크기가 증가할 수 있습니다. 파일 크기가 문제라면 선형화 후 `Simplify()`를 사용하십시오.

**Q: 선형화 시 세그먼트 길이를 제어할 수 있나요?**  
A: 기본 방법은 내부 허용오차를 사용합니다. 사용자 지정 세그먼트를 원한다면 `ToLinearGeometry()`를 호출하기 전에 곡선을 수동으로 테셀레이션할 수 있습니다.

---

**마지막 업데이트:** 2025-12-21  
**테스트 환경:** Aspose.GIS 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}