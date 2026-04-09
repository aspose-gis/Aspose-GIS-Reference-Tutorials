---
date: 2026-04-09
description: Aspose.GIS for .NET를 사용하여 곡선을 선(기하학 선형화)으로 변환하는 방법을 배우고, .NET 애플리케이션에서
  효율적인 지리공간 처리 및 분석을 구현하세요.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
linktitle: 기하학을 선형화
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET를 사용하여 곡선을 선으로 변환하는 방법
url: /ko/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET를 사용하여 곡선을 선으로 변환 (기하학 선형화)

## 소개
지도 작성, 공간 분석 또는 데이터 교환 작업을 위해 **곡선을 선으로 변환**해야 한다면, Aspose.GIS for .NET은 이를 깔끔하고 프로그래밍 방식으로 수행할 수 있는 방법을 제공합니다. 이 튜토리얼에서는 복잡한 기하학(곡선 및 복합 형태 포함)을 가져와 모든 GIS 시스템에서 작동하는 단순한 선형 표현으로 변환하는 완전한 실제 예제를 단계별로 살펴봅니다.

## 빠른 답변
- **“곡선을 선으로 변환”이 의미하는 바는 무엇인가요?** 곡선 형태의 기하학을 직선 세그먼트로 변환합니다.  
- **왜 Aspose.GIS를 선택해야 하나요?** 이 라이브러리는 수십 가지 GIS 형식을 지원하며 외부 도구 없이도 기하학 변환을 처리합니다.  
- **사전에 무엇이 필요하나요?** .NET Framework 또는 .NET Core, Visual Studio(또는 any C# IDE), 그리고 Aspose.GIS NuGet 패키지.  
- **샘플 실행 시간은 얼마나 걸리나요?** 라이브러리를 설치하면 5분 미만입니다.  
- **다른 형식으로 내보낼 수 있나요?** 물론입니다—KML 드라이버를 Shapefile, GeoJSON 등으로 교체하면 됩니다.

## 곡선을 선으로 변환한다는 의미는 무엇인가요?
곡선을 선으로 변환하는 작업(일명 **기하학 선형화**)은 곡선이거나 복합 형태인 모든 도형을 일련의 직선 세그먼트, 즉 “선형 기하학”으로 분해합니다. 이러한 단순화는 렌더링 속도를 높이고, 오래된 GIS 서비스와의 호환성을 향상시키며, 공간 알고리즘의 복잡성을 감소시킵니다.

## 왜 곡선을 선으로 변환해야 할까요?
- **성능:** 선형 기하학은 렌더링 및 쿼리가 훨씬 빠릅니다.  
- **호환성:** 많은 GIS 플랫폼(특히 레거시 서비스)은 선형 피처만 허용합니다.  
- **단순화:** 썸네일, 빠른 미리보기 또는 선형 입력을 요구하는 알고리즘에 데이터를 제공할 때 이상적입니다.

## 전제 조건
코드에 들어가기 전에 다음이 준비되어 있는지 확인하십시오:

1. **Aspose.GIS for .NET** – [Aspose.GIS 웹사이트](https://releases.aspose.com/gis/net/)에서 다운로드하세요.  
2. **.NET Framework**(또는 .NET Core) – 개발 머신에 설치되어 있어야 합니다.  
3. **Visual Studio**(또는 C# 호환 IDE) – 샘플을 작성하고 실행하기 위해 필요합니다.

## 네임스페이스 가져오기
Aspose.GIS 기능을 사용하려면 필요한 네임스페이스를 가져오세요.

### 단계 1: 핵심 Aspose.GIS 네임스페이스
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### 단계 2: 대상 형식용 드라이버
이 예제에서는 결과를 KML 파일에 기록합니다:
```csharp
using Aspose.GIS.Kml;
```

## 단계별 가이드: 곡선을 선으로 변환
아래는 각 코드 라인을 자세히 살펴보며 **곡선을 선으로 변환하는 방법**과 각 단계가 중요한 이유를 설명합니다.

### 단계 1: 출력 경로 정의
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
`"Your Document Directory"`를 KML 파일을 저장하고 싶은 폴더 경로로 교체하세요. 크로스‑플랫폼 호환성을 위해 `Path.Combine` 사용을 권장합니다.

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
Well‑Known Text(WKT) 문자열에서 기하학을 생성합니다. 이 예제는 `LineString`, `CompoundCurve`, `CircularString`을 포함하고 있어 **곡선을 선으로 변환**을 시연하기에 적합합니다.

### 단계 5: 곡선을 선으로 변환
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

## 일반적인 함정 및 전문가 팁
- **경로 구분자:** Windows와 Linux 간 문제를 방지하려면 `Path.Combine`을 사용하세요.  
- **매우 큰 기하학:** 복잡한 형태를 선형화하면 수천 개의 정점이 생성될 수 있으므로, 선형화 후 `Simplify()`를 호출해 점 수를 줄이는 것을 고려하세요.  
- **드라이버 선택:** 다른 출력 형식이 필요하면 `Drivers.Kml`을 `Drivers.Shapefile`, `Drivers.GeoJson` 등으로 교체하고 파일 확장자를 적절히 변경하세요.  
- **Z값 보존:** `ToLinearGeometry()`는 3‑D(Z) 좌표를 유지하므로 고도 데이터를 잃지 않습니다.

## 자주 묻는 질문 (FAQ)

**Q: Aspose.GIS for .NET은 .NET Core와 호환되나요?**  
A: 네, Aspose.GIS는 .NET Core와 함께 작동하여 크로스‑플랫폼 애플리케이션을 지원합니다.

**Q: Aspose.GIS for .NET을 사용해 다양한 GIS 파일 형식을 다룰 수 있나요?**  
A: 물론입니다! 이 라이브러리는 KML, Shapefile, GeoJSON 등 많은 형식을 지원합니다.

**Q: Aspose.GIS가 공간 연산 및 분석을 제공하나요?**  
A: 네, 버퍼링부터 공간 조인까지 다양한 공간 기능을 제공합니다.

**Q: 무료 체험판을 이용할 수 있나요?**  
A: 네, [Aspose 웹사이트](https://releases.aspose.com/)에서 무료 체험판을 다운로드할 수 있습니다.

**Q: 문제가 발생하면 어디서 도움을 받을 수 있나요?**  
A: 커뮤니티 및 직원 지원을 위해 [Aspose.GIS 포럼](https://forum.aspose.com/c/gis/33)을 방문하세요.

### 추가 일반 질문

**Q: 3D(Z) 좌표를 포함한 기하학도 선형화할 수 있나요?**  
A: 네, `ToLinearGeometry()`는 2D와 3D 기하학 모두에서 작동하며 Z값을 보존합니다.

**Q: 선형화가 파일 크기에 어떤 영향을 미치나요?**  
A: 곡선을 많은 짧은 선 세그먼트로 변환하면 파일 크기가 증가할 수 있습니다. 크기가 문제라면 선형화 후 `Simplify()`를 사용하세요.

**Q: 곡선을 선으로 변환할 때 세그먼트 길이를 제어할 수 있나요?**  
A: 기본 방법은 내부 허용오차를 사용합니다. 사용자 정의 세그먼트를 원한다면 `ToLinearGeometry()` 호출 전에 곡선을 수동으로 테셀레이션할 수 있습니다.

## 결론
이 튜토리얼에서는 Aspose.GIS for .NET을 사용해 **곡선을 선으로 변환**(기하학 선형화)하는 방법을 환경 설정부터 선형화된 결과를 KML 파일에 기록하는 단계까지 다루었습니다. 이제 이 워크플로를 지도 애플리케이션, 데이터 처리 파이프라인, 또는 단순화된 기하학이 필요한 모든 GIS 관련 프로젝트에 통합할 수 있습니다.

---

**마지막 업데이트:** 2026-04-09  
**테스트 환경:** Aspose.GIS 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}