---
title: 다각형 Shapefile을 라인스트링으로 변환
linktitle: 다각형 Shapefile을 라인스트링으로 변환
second_title: Aspose.GIS .NET API
description: .NET용 Aspose.GIS의 강력한 기능을 살펴보고 다각형 모양 파일을 라인스트링으로 쉽게 변환하세요. 지금 GIS 개발을 강화하세요!
type: docs
weight: 18
url: /ko/net/layer-management/convert-polygon-shapefile-to-linestring/
---
## 소개
.NET에서 GIS(지리 정보 시스템)로 작업하는 경우 Aspose.GIS는 작업을 단순화할 수 있는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.GIS를 사용하여 Polygon Shapefile을 Linestring으로 변환하는 과정을 안내합니다. 이는 경로 계획이나 네트워크 분석과 같은 다양한 애플리케이션을 위해 다각형 데이터에서 선형 특징을 추출해야 할 때 특히 유용할 수 있습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 사항이 준비되어 있는지 확인하세요.
-  Aspose.GIS 라이브러리: 다음에서 Aspose.GIS 라이브러리를 다운로드하고 설치합니다.[웹사이트](https://releases.aspose.com/gis/net/).
- Shapefile 데이터: 변환할 다각형 Shapefile을 준비합니다. 샘플 데이터가 없으면 샘플 데이터를 찾거나 직접 만들 수 있습니다.
- 개발 환경: 필요한 도구를 사용하여 .NET 개발 환경을 설정합니다.
## 네임스페이스 가져오기
C# 코드에서 필요한 클래스와 메서드에 액세스하려면 Aspose.GIS 네임스페이스를 가져와야 합니다. 코드 파일 시작 부분에 다음 네임스페이스를 추가합니다.
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## 1단계: 문서 디렉터리 설정
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
```
"Your Document Directory"를 Shapefile이 있는 디렉터리의 경로로 바꾸세요.
## 2단계: 소스 Shapefile 열기
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // 나머지 코드는 여기에 위치합니다.
}
```
이 단계에서는 읽을 수 있도록 소스 다각형 Shapefile을 엽니다.
## 3단계: 대상 유도선 셰이프파일 만들기
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // 나머지 코드는 여기에 위치합니다.
}
```
여기서는 변환된 데이터를 쓰기 위한 새로운 Linestring Shapefile을 생성합니다.
## 4단계: 소스 기능 반복
```csharp
foreach (Feature sourceFeature in source)
{
    // 나머지 코드는 여기에 위치합니다.
}
```
이 루프는 소스 다각형 Shapefile의 각 기능을 반복합니다.
## 5단계: 다각형을 유도선으로 변환하고 대상에 쓰기
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
이 단계에서는 각 다각형 기능이 라인스트링으로 변환되고 결과 라인스트링 기능이 대상 Shapefile에 기록됩니다.
## 결론
다음 단계를 수행하면 Aspose.GIS for .NET을 사용하여 Polygon Shapefile을 Linestring으로 쉽게 변환할 수 있습니다. 이 프로세스는 GIS 애플리케이션의 데이터 분석 및 시각화에 대한 새로운 가능성을 열어줍니다.

## 자주 묻는 질문
### Aspose.GIS는 모든 버전의 .NET과 호환됩니까?
예, Aspose.GIS는 다양한 버전의 .NET을 지원하여 개발 환경과의 호환성을 보장합니다.
### 상업용 프로젝트에 Aspose.GIS를 사용할 수 있나요?
 그래 넌 할수있어. Aspose.GIS를 상업용 프로젝트에 사용하려면 라이선스 구매를 고려하세요.[여기](https://purchase.aspose.com/buy).
### 사용 가능한 예제나 문서가 있나요?
 예, 다음에서 포괄적인 문서와 예제를 찾을 수 있습니다.[문서 페이지](https://reference.aspose.com/gis/net/).
### 평가판을 사용할 수 있나요?
 예, 다음 사이트를 방문하여 무료 평가판으로 Aspose.GIS를 탐색할 수 있습니다.[이 링크](https://releases.aspose.com/).
### 어디서 도움이나 지원을 구할 수 있나요?
 방문하다[Aspose.GIS 포럼](https://forum.aspose.com/c/gis/33) 지원이나 지원 관련 문의 사항이 있는 경우.