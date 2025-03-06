---
title: .NET용 Aspose.GIS를 사용하여 지형지물 라벨링 마스터하기
linktitle: 지도의 지형지물에 라벨 지정
second_title: Aspose.GIS .NET API
description: .NET용 Aspose.GIS를 탐색하고 지도의 지형지물 라벨링 기술을 마스터하세요. 지리공간 시각화를 쉽게 향상할 수 있습니다. #Aspose #GIS
weight: 11
url: /ko/net/map-rendering/label-features-on-map/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.GIS를 사용하여 지형지물 라벨링 마스터하기

## 소개
지리공간 데이터 시각화의 세계에서 지도의 지형지물에 라벨을 지정하는 것은 정보를 효과적으로 전달하는 데 중요한 역할을 합니다. .NET용 Aspose.GIS는 이를 원활하게 수행할 수 있는 강력한 툴킷을 제공합니다. 이 튜토리얼에서는 Aspose.GIS를 사용하여 지도의 지점에 라벨을 지정하는 다양한 방법을 살펴보고 정보 라벨로 지도 시각화를 향상시킵니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- C# 및 .NET 프레임워크에 대한 실무 지식.
-  .NET용 Aspose.GIS가 설치되었습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/gis/net/).
- 포인트 데이터가 포함된 GeoJSON 파일입니다. 샘플 파일이 없으면 테스트용 샘플 파일을 사용할 수 있습니다.
## 네임스페이스 가져오기
C# 코드에서 Aspose.GIS 작업에 필요한 네임스페이스를 가져와야 합니다.
```csharp
using System;
using System.Drawing;
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Labelings;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.GIS.Examples.CSharp;
using FontStyle = Aspose.Gis.Rendering.Labelings.FontStyle;
```
이제 단계별 가이드 형식으로 각 예를 여러 단계로 나누어 보겠습니다.
##  포인트 라벨링

### 1단계: 문서 디렉터리 경로를 설정합니다.
```csharp
string dataDir = "Your Document Directory";
```
### 2단계: 간단한 마커 기호를 사용하여 지도 만들기:
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. 벡터 레이어 추가 및 라벨링 적용
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. 지도를 SVG 파일로 렌더링
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## 점 레이블 지정 스타일

이전 예의 1단계와 2단계를 수행합니다.

### 1단계: 라벨링 스타일 사용자 정의:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// 나머지 단계는 동일하게 유지됩니다.
```
## 점 라벨링 배치

첫 번째 예의 1단계와 2단계를 따르세요.
### 2단계: 라벨 배치 사용자 정의:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        HorizontalOffset = 2,
        VerticalOffset = 2,
        Rotation = 10,
    }
};
// 나머지 단계는 동일하게 유지됩니다.
```
## 점 라벨링 기능 기반

첫 번째 예의 1단계와 2단계를 따르세요.

### 1단계: 기능 기반 라벨링 구현:
```csharp
var pointLabeling = new SimpleLabeling("name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        VerticalOffset = 4,
        HorizontalOffset = 4,
    },
    FeatureBasedConfiguration = (feature, labeling) =>
    {
        // 지형지물에서 인구를 검색합니다.
        var population = feature.GetValue<int>("population");
        // 글꼴 크기는 인구에 따라 계산됩니다.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // 라벨의 우선순위도 인구에 따라 결정됩니다.
        // 우선순위가 높을수록 출력 이미지에 레이블이 나타날 가능성이 높아집니다.
        labeling.Priority = population;
    }
};
// 나머지 단계는 동일하게 유지됩니다.
```
## 결론
축하해요! .NET용 Aspose.GIS를 사용하여 지형지물에 라벨을 지정하여 지도 시각화를 향상시키는 방법을 배웠습니다. 다양한 스타일과 배치를 실험하여 데이터에 맞는 매력적인 지도를 만드세요.
## 자주 묻는 질문
### 사용자 정의 글꼴을 사용하여 기능에 라벨을 붙일 수 있습니까?
예, 라벨링 구성에서 글꼴 스타일과 크기를 사용자 정의할 수 있습니다.
### Aspose.GIS는 다른 GIS 데이터 형식과 호환됩니까?
Aspose.GIS는 GeoJSON, Shapefile 등을 포함한 다양한 지리공간 형식을 지원합니다.
### 라벨링을 위한 대규모 데이터 세트를 어떻게 처리할 수 있나요?
Aspose.GIS는 성능에 최적화되어 있지만 데이터 속성을 기반으로 라벨의 우선순위를 지정하려면 기능 기반 구성을 사용하는 것이 좋습니다.
### 고급 라벨 배치 옵션을 사용할 수 있습니까?
예, 회전, 고정점, 오프셋과 같은 옵션을 사용하여 라벨 배치를 미세 조정할 수 있습니다.
### 일괄 프로세스에서 라벨 생성을 자동화할 수 있습니까?
물론 배치 라벨 생성을 위해 Aspose.GIS를 자동화된 워크플로우에 통합할 수 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
