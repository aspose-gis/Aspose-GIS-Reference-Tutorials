---
title: 스트림에 GeoJSON 작성
linktitle: 스트림에 GeoJSON 작성
second_title: Aspose.GIS .NET API
description: .NET용 Aspose.GIS의 강력한 기능을 살펴보세요! 손쉽게 스트리밍하려면 GeoJSON을 작성하세요. 원활한 지리공간 통합을 위해 지금 다운로드하세요.
weight: 25
url: /ko/net/layer-data-operations/write-geojson-to-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 스트림에 GeoJSON 작성

## 소개
Aspose.GIS를 사용하여 .NET 애플리케이션에서 GeoJSON의 강력한 기능을 활용하고 싶으십니까? 글쎄, 당신은 바로 이곳에 있어요! 이 단계별 가이드는 .NET용 Aspose.GIS의 강력한 기능을 활용하여 GeoJSON을 스트림에 작성하는 과정을 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. .NET 라이브러리용 Aspose.GIS: .NET 라이브러리용 Aspose.GIS가 설치되어 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/gis/net/).
2. 문서 디렉터리: 프로젝트에 문서 디렉터리를 설정하고 해당 경로를 기록해 둡니다.
이제 튜토리얼을 시작하겠습니다!
## 네임스페이스 가져오기
먼저, 코드에서 Aspose.GIS 기능에 액세스하는 데 필요한 네임스페이스를 포함해야 합니다.
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```
## 1단계: 문서 디렉터리 설정
```csharp
string dataDir = "Your Document Directory";
```
"Your Document Directory"를 문서 디렉터리의 실제 경로로 바꾸십시오.
## 2단계: 메모리 스트림 생성
```csharp
using (var memoryStream = new MemoryStream())
{
    // 다음 단계에 대한 코드는 여기에 있습니다.
}
```
## 3단계: GeoJSON 드라이버를 사용하여 벡터 레이어 생성
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // 다음 단계에 대한 코드는 여기에 있습니다.
}
```
## 4단계: 지형지물 속성 정의
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```
## 5단계: 기능 구성 및 추가
```csharp
// 첫 번째 기능
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// 두 번째 기능
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```
## 6단계: GeoJSON 출력 표시
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```
축하해요! .NET용 Aspose.GIS를 사용하여 스트림에 GeoJSON을 성공적으로 작성했습니다.
## 결론
이 튜토리얼에서는 Aspose.GIS for .NET을 프로젝트에 통합하는 기본 단계, 특히 GeoJSON을 스트림에 작성하는 데 중점을 두는 단계를 다루었습니다. 이러한 간단하면서도 강력한 단계를 통해 애플리케이션의 지리공간 기능을 향상시킬 수 있습니다.
## 자주 묻는 질문
### Windows 및 Linux 환경 모두에서 .NET용 Aspose.GIS를 사용할 수 있습니까?
예, .NET용 Aspose.GIS는 Windows 및 Linux 시스템과 모두 호환됩니다.
### 무료 평가판이 제공되나요?
 전적으로! 무료 평가판을 탐색할 수 있습니다.[여기](https://releases.aspose.com/).
### 자세한 문서는 어디서 찾을 수 있나요?
 문서를 확인하세요[여기](https://reference.aspose.com/gis/net/).
### 임시 라이센스는 어떻게 얻을 수 있나요?
 임시 라이센스를 사용할 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).
### 도움이 필요하거나 더 궁금한 점이 있으신가요?
 지원 포럼을 방문하세요[여기](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
