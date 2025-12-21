---
date: 2025-12-21
description: Aspose.GIS for .NET를 사용하여 벡터 레이어를 생성하고, 선형화 허용오차를 설정하며, 레이어에 피처를 추가하는
  방법을 배웁니다. 이 단계별 가이드를 따라 GeoJSON 파일을 내보내세요.
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET를 사용하여 벡터 레이어 생성 및 선형화 허용오차 설정
url: /ko/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET을 사용하여 벡터 레이어 생성 및 선형화 허용오차 설정

## 소개
**벡터 레이어** 파일을 생성하고, 곡선 정밀도를 제어하며, 결과를 GeoJSON 문서로 내보내야 할 때 Aspose.GIS for .NET을 사용하면 간단합니다. 이 튜토리얼에서는 GeoJSON 옵션을 구성하고, 선형화 허용오차를 설정하며, **레이어에 피처 추가**하는 방법을 배우게 됩니다—코드는 깔끔하고 프로덕션 준비가 된 상태를 유지합니다.

## 빠른 답변
- **“벡터 레이어 생성”은 무엇을 의미하나요?** 새로운 GIS 벡터 데이터셋(예: GeoJSON 파일)을 생성하여 기하와 속성을 저장할 수 있게 합니다.  
- **허용오차는 어떻게 설정하나요?** `GeoJsonOptions`의 `LinearizationTolerance` 속성을 사용합니다.  
- **GeoJSON 파일을 내보낼 수 있나요?** 예—`Drivers.GeoJson` 드라이버를 사용해 `VectorLayer`를 생성하면 됩니다.  
- **라이선스가 필요하나요?** 유효한 Aspose.GIS 라이선스를 적용하면 모든 기능이 해제됩니다; 평가용 임시 라이선스도 사용할 수 있습니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “벡터 레이어 생성”이란?
벡터 레이어를 생성한다는 것은 점, 선, 폴리곤과 같은 기하 피처를 저장할 수 있는 새로운 GIS 컨테이너(예: GeoJSON 파일)를 초기화하는 것을 의미합니다. 이 레이어는 이후에 구성하는 모든 기하와 연결하는 모든 속성의 대상이 됩니다.

## 왜 GeoJSON 옵션을 구성해야 하나요?
특히 **선형화 허용오차**와 같은 GeoJSON 옵션을 구성하면 곡선 기하(예: `CircularString`)를 원본 곡선에 충분히 근접하도록 근사시킬 수 있어, 애플리케이션의 정확도 요구사항을 충족합니다. 이 단계는 이후 **GeoJSON 파일 내보내기** 시 웹 지도나 공간 분석에 사용될 때 매우 중요합니다.

## 사전 준비 사항
시작하기 전에 다음을 확인하세요:

1. **Visual Studio**가 설치되어 있음(최근 버전 중 하나).  
2. **Aspose.GIS 라이선스**(또는 임시 평가 키).  
3. **Aspose.GIS for .NET** 라이브러리를 다운로드하여 프로젝트에 참조함.  
4. **C#**에 대한 기본적인 이해.

## 네임스페이스 가져오기
컴파일러가 GIS 클래스를 찾을 수 있도록 필요한 네임스페이스를 먼저 가져옵니다:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 단계별 가이드

### 단계 1: GeoJSON 옵션 구성 (허용오차 설정 방법)
`GeoJsonOptions` 객체를 생성하고, 선형화된 기하가 원본 곡선에 얼마나 근접해야 하는지 Aspose.GIS에 알려줍니다.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### 단계 2: 출력 경로 정의 (GeoJSON 내보내기 방법)
결과 파일이 저장될 위치를 지정합니다. 자리표시자를 실제 폴더 경로로 교체하세요.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### 단계 3: **구성된 옵션으로 벡터 레이어 생성**
이제 `VectorLayer.Create` 메서드를 사용해 **벡터 레이어 생성**을 수행합니다. `using` 블록은 리소스가 적절히 해제되도록 보장합니다.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### 단계 4: 기하 구성 (예: 원형 문자열)
샘플 기하인 `CircularString`을 구축합니다. 필요에 따라 유효한 WKT로 교체할 수 있습니다.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### 단계 5: **레이어에 피처 추가** 및 저장
마지막으로 피처를 생성하고, 기하를 할당한 뒤 레이어에 추가합니다. 이것이 **레이어에 피처 추가** 작업의 핵심입니다.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

`using` 블록이 종료되면 레이어가 `path`에 정의된 파일에 자동으로 기록되어 바로 사용할 수 있는 GeoJSON 파일이 생성됩니다.

## 일반적인 문제 및 팁
- **경로 오류** – 디렉터리가 존재하고 쓰기 권한이 있는지 확인하세요.  
- **허용오차가 너무 낮음** – `LinearizationTolerance`를 매우 작은 값으로 설정하면 파일 크기가 급격히 증가할 수 있습니다. 정확도 요구에 맞게 조정하세요.  
- **라이선스 오류** – 라이선스 경고가 표시되면 Aspose.GIS 호출 전에 라이선스 파일이 올바르게 로드되었는지 확인하세요.

## 자주 묻는 질문

**Q: Aspose.GIS for .NET이 다른 .NET 프레임워크와 호환되나요?**  
A: 예, .NET Framework, .NET Core, .NET 5/6/7 모두에서 작동합니다.

**Q: 상업 프로젝트에서도 Aspose.GIS를 사용할 수 있나요?**  
A: 물론입니다. 상업용 라이선스를 적용하면 모든 평가 제한이 해제됩니다.

**Q: GeoJSON 외에 다른 GIS 포맷도 지원하나요?**  
A: 예, Shapefile, KML, GML 등 다양한 포맷을 지원합니다.

**Q: 체험판 버전을 제공하나요?**  
A: Aspose 웹사이트에서 무료 체험판을 다운로드할 수 있습니다.

**Q: 지원은 어디서 받을 수 있나요?**  
A: Aspose 포럼이나 리소스 섹션에 있는 지원 링크를 이용하세요.

## 결론
이 단계들을 따라 하면 **벡터 레이어 생성**, 선형화 허용오차 구성, 그리고 **레이어에 피처 추가**를 통해 원활한 **GeoJSON 파일 내보내기**를 수행할 수 있습니다. 추가적인 기하 유형과 속성 처리를 탐색하여 .NET GIS 프로젝트에서 Aspose.GIS를 최대한 활용해 보세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**마지막 업데이트:** 2025-12-21  
**테스트 환경:** Aspose.GIS 24.11 for .NET  
**작성자:** Aspose  

---