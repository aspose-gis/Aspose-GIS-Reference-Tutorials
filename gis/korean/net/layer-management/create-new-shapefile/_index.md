---
date: 2026-01-13
description: Aspose.GIS for .NET를 사용하여 새로운 shapefile을 만드는 방법을 배웁니다. 이 단계별 가이드는 벡터
  레이어를 정의하고, 날짜 속성을 추가하며, 공간 데이터를 관리하는 방법을 보여줍니다.
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: 새 셰이프파일 만들기
url: /ko/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 새 Shapefile 만들기

## 소개
.NET으로 지리 정보 시스템(GIS) 개발에 뛰어들고 있다면 Aspose.GIS가 최고의 솔루션입니다. 이 강력한 라이브러리는 개발자가 공간 데이터를 원활하게 다룰 수 있게 해주며, 이번 튜토리얼에서는 Aspose.GIS for .NET을 사용해 **새 shapefile 만들기** 방법을 단계별로 안내합니다. 벡터 레이어를 정의하고 날짜 속성을 추가하는 것이 견고한 GIS 프로젝트에 왜 중요한지 확인해 보세요.

## 빠른 답변
- **이 튜토리얼은 무엇을 가르치나요?** 새 shapefile을 만들고, 벡터 레이어를 정의하며, 속성(날짜 필드 포함)을 추가하는 방법.  
- **필요한 라이브러리는?** Aspose.GIS for .NET.  
- **라이선스가 필요합니까?** 학습용으로는 무료 체험판으로 충분하지만, 실제 서비스에서는 상용 라이선스가 필요합니다.  
- **어떤 IDE를 사용해야 하나요?** Visual Studio(최근 버전이면 모두 가능).  
- **구현 시간은 얼마나 걸리나요?** 기본 예제는 약 10‑15분 정도 소요됩니다.

## 사전 요구 사항
튜토리얼을 시작하기 전에 다음 요구 사항을 충족했는지 확인하세요:
- C# 프로그래밍 언어에 대한 기본 이해.
- 머신에 Visual Studio가 설치되어 있음.
- Aspose.GIS for .NET 라이브러리. [여기](https://releases.aspose.com/gis/net/)에서 다운로드할 수 있습니다.

## 네임스페이스 가져오기
Aspose.GIS 기능을 활용하려면 필요한 네임스페이스를 가져옵니다:

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
Visual Studio에서 새 C# 프로젝트를 만들고 Aspose.GIS 라이브러리를 포함합니다.

## 2단계: 문서 디렉터리 정의
```csharp
string dataDir = "Your Document Directory";
```
*Your Document Directory*를 새 shapefile을 저장하려는 실제 경로로 교체하세요.

## 3단계: VectorLayer 만들기
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
이 코드 조각은 **벡터 레이어를 정의**하고 세 개의 속성을 선언합니다: 텍스트 필드(`name`), 정수 필드(`age`), 날짜‑시간 필드(`dob`). 날짜 속성을 추가하는 것은 시간 기반 GIS 분석에 필수적입니다.

## 4단계: 피처 추가
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
두 개의 포인트를 생성하고 각 속성을 개별적으로 설정한 뒤 레이어에 피처를 추가합니다.

### 사례 2: 모든 속성에 새 값 일괄 설정
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
이 방법은 객체 배열을 사용해 한 번에 모든 속성 값을 채워 넣습니다—속성이 많을 때 유용합니다.

## 왜 중요한가
프로그램matically shapefile을 생성하면 데이터 파이프라인을 자동화하고, 테스트 데이터 세트를 만들며, GIS 출력을 웹 서비스에 직접 통합할 수 있습니다. Aspose.GIS로 **shapefile 만들기**를 마스터하면 피처 기하, 속성 스키마, 파일 형식 준수 등을 완벽히 제어할 수 있습니다.

## 흔히 발생하는 실수와 팁
- **경로 구분자:** 문자열 연결 대신 `Path.Combine`을 사용해 크로스‑플랫폼 호환성을 확보하세요.  
- **속성 순서:** `SetValues`에 전달하는 값의 순서는 속성을 추가한 순서와 일치해야 합니다.  
- **날짜 처리:** GIS 데이터를 여러 시간대에서 공유할 경우 항상 `DateTimeKind.Utc`를 사용하세요.

## 결론
축하합니다! Aspose.GIS for .NET을 사용해 새 shapefile을 성공적으로 만들었습니다. 이번 튜토리얼에서는 프로젝트 설정, 벡터 레이어 정의, 피처 추가(날짜 속성 포함)까지 기본 과정을 다루었습니다. 더 깊이 탐구하고 싶다면 [문서](https://reference.aspose.com/gis/net/)를 참고해 고급 기능과 활용법을 확인하세요.

## 자주 묻는 질문
### Q: Aspose.GIS를 다른 프로그래밍 언어와 함께 사용할 수 있나요?
Aspose.GIS는 주로 .NET을 지원하지만 Java 버전도 제공됩니다.  

### Q: 무료 체험판을 이용할 수 있나요?
네, 무료 체험판은 [여기](https://releases.aspose.com/)에서 이용할 수 있습니다.  

### Q: Aspose.GIS 지원을 어디서 받을 수 있나요?
커뮤니티 지원 및 토론은 [Aspose.GIS 포럼](https://forum.aspose.com/c/gis/33)에서 확인하세요.  

### Q: 임시 라이선스는 어떻게 얻나요?
임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.  

### Q: Aspose.GIS for .NET을 어디서 구매하나요?
라이브러리는 [여기](https://purchase.aspose.com/buy)에서 구매할 수 있습니다.

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}