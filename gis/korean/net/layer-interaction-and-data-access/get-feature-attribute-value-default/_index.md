---
title: 기능 속성 값 가져오기(기본값)
linktitle: 기능 속성 값 가져오기(기본값)
second_title: Aspose.GIS .NET API
description: .NET용 Aspose.GIS의 강력한 기능을 활용해 보세요! 이 단계별 가이드를 통해 지형지물 속성 값을 손쉽게 검색하고 조작하세요. 지금 평가판을 다운로드하세요!
weight: 14
url: /ko/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 기능 속성 값 가져오기(기본값)

## 소개
.NET용 Aspose.GIS의 세계에 오신 것을 환영합니다! 이 포괄적인 가이드에서는 Aspose.GIS의 강력한 기능을 사용하여 지형지물 속성 값을 검색하는 복잡한 과정을 자세히 살펴보겠습니다. 숙련된 개발자이든 이제 막 시작하는 개발자이든 이 튜토리얼은 단계별 연습을 제공하여 이 놀라운 도구의 잠재력을 최대한 활용할 수 있도록 보장합니다.
## 전제조건
이 코딩 모험을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하십시오.
- C# 및 .NET 프레임워크에 대한 실무 지식.
-  .NET용 Aspose.GIS가 설치되었습니다. 그렇지 않은 경우 다음에서 다운로드하십시오.[여기](https://releases.aspose.com/gis/net/).
- 원활하게 따라갈 수 있는 Visual Studio와 같은 코드 편집기.
## 네임스페이스 가져오기
C# 프로젝트에서 필요한 네임스페이스를 포함해야 합니다.
```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
이제 각 예를 따라하기 쉬운 일련의 단계로 나누어 보겠습니다.
## 기능 속성 값 가져오기(기본값)
### 1단계: 환경 설정
문서 디렉터리의 경로를 정의하는 것부터 시작하세요.
```csharp
string dataDir = "Your Document Directory";
```
### 2단계: GeoJson 레이어 생성
GeoJson 레이어를 생성하고 기본값으로 속성을 정의합니다.
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### 3단계: 기능 구성
정의된 속성을 사용하여 기능을 구성합니다.
```csharp
    Feature feature = layer.ConstructFeature();
```
### 4단계: 값 검색
다양한 시나리오로 속성 값을 검색합니다.
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // 값 == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // 값 == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // 값 == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## 기본값 설정
### 1단계: 다른 GeoJson 레이어 생성
다른 GeoJson 레이어와 이중 속성을 사용하여 프로세스를 반복합니다.
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### 2단계: 기능 구성(다시)
```csharp
    Feature feature = layer.ConstructFeature();
```
### 3단계: 값 검색 및 설정
기본값을 표시하는 속성 값을 검색하고 설정합니다.
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // 값 == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // 값 == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // 값 == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
축하해요! 피처 속성 값을 검색하고 조작하는 데 .NET용 Aspose.GIS의 강력한 기능을 성공적으로 활용했습니다.
## 결론
이 튜토리얼에서는 .NET용 Aspose.GIS를 사용하여 지형지물 속성 값을 검색하는 미묘한 차이를 살펴보았습니다. 직관적인 API와 강력한 기능을 갖춘 Aspose.GIS는 .NET 환경에서 GIS 개발 가능성의 세계를 열어줍니다.
## 자주 묻는 질문
### Aspose.GIS는 .NET Core와 호환됩니까?
예, Aspose.GIS는 .NET Core와 완벽하게 호환되어 크로스 플랫폼 지원을 제공합니다.
### 상업용 프로젝트에 Aspose.GIS를 사용할 수 있나요?
전적으로! Aspose.GIS에는 아무런 제한 없이 상업용 애플리케이션에서 사용할 수 있는 상업용 라이선스가 함께 제공됩니다.
### 추가 지원과 리소스는 어디에서 찾을 수 있나요?
 방문하다[Aspose.GIS 포럼](https://forum.aspose.com/c/gis/33) 지역사회 지원을 위해[선적 서류 비치](https://reference.aspose.com/gis/net/) 자세한 정보를 확인하세요.
### 무료 평가판이 제공되나요?
 예, 무료 평가판을 통해 Aspose.GIS를 탐색할 수 있습니다. 다운로드 해[여기](https://releases.aspose.com/).
### 테스트 목적으로 임시 라이센스를 얻으려면 어떻게 해야 합니까?
 임시 라이센스를 얻으려면 다음을 방문하세요.[여기](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
