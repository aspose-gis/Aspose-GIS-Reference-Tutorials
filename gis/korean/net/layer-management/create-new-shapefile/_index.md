---
title: 새 셰이프파일 생성
linktitle: 새 셰이프파일 생성
second_title: Aspose.GIS .NET API
description: .NET용 Aspose.GIS를 사용하여 새 모양 파일을 만드는 방법을 알아보세요. 단계별 가이드를 따라 공간 데이터 조작의 힘을 활용해 보세요.
weight: 12
url: /ko/net/layer-management/create-new-shapefile/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 새 셰이프파일 생성

## 소개
.NET을 사용하여 지리 정보 시스템(GIS) 개발을 탐구하고 있다면 Aspose.GIS가 적합한 솔루션입니다. 이 강력한 라이브러리는 개발자가 공간 데이터를 원활하게 사용할 수 있도록 지원하며, 이 튜토리얼에서는 .NET용 Aspose.GIS를 사용하여 새로운 쉐이프파일을 생성하는 과정을 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- C# 프로그래밍 언어에 대한 기본 이해.
- 컴퓨터에 Visual Studio가 설치되어 있습니다.
-  .NET 라이브러리용 Aspose.GIS. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/gis/net/).
## 네임스페이스 가져오기
Aspose.GIS의 기능을 활용하려면 필요한 네임스페이스를 가져오는 것부터 시작하세요.
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## 1단계: 프로젝트 설정
Visual Studio에서 새 C# 프로젝트를 만드는 것으로 시작하고 Aspose.GIS 라이브러리를 포함합니다.
## 2단계: 문서 디렉터리 정의
```csharp
string dataDir = "Your Document Directory";
```
"Your Document Directory"를 새 모양 파일을 저장하려는 실제 경로로 바꾸십시오.
## 3단계: VectorLayer 생성
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //기능을 추가하기 전에 속성을 추가하세요
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
이 코드 세그먼트는 벡터 레이어를 설정하고 피처의 속성을 정의합니다.
## 4단계: 기능 추가
### 사례 1: 개별적으로 값 설정
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
### 사례 2: 모든 속성에 대한 새 값 설정
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## 결론
 축하해요! .NET용 Aspose.GIS를 사용하여 새 모양 파일을 성공적으로 만들었습니다. 이 튜토리얼에서는 프로젝트 설정, 속성 정의 및 기능 추가의 기본 사항을 다루었습니다. 더 자세히 알아보려면 다음을 참조하세요.[선적 서류 비치](https://reference.aspose.com/gis/net/) 고급 기능 및 기능을 확인하세요.
## 자주 묻는 질문
### Q: Aspose.GIS를 다른 프로그래밍 언어와 함께 사용할 수 있나요?
Aspose.GIS는 주로 .NET을 지원하지만 Java에서도 사용할 수 있는 버전이 있습니다.
### Q: 무료 평가판이 제공됩니까?
 예, 무료 평가판에 액세스할 수 있습니다[여기](https://releases.aspose.com/).
### Q: Aspose.GIS에 대한 지원은 어디서 찾을 수 있나요?
 방문하다[Aspose.GIS 포럼](https://forum.aspose.com/c/gis/33) 커뮤니티 지원 및 토론을 위해.
### Q: 임시 라이센스는 어떻게 얻을 수 있나요?
 임시 면허증을 받으세요[여기](https://purchase.aspose.com/temporary-license/).
### Q: .NET용 Aspose.GIS를 어디서 구입할 수 있나요?
 도서관을 구매하시면 됩니다[여기](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
