---
date: 2026-01-05
description: Aspose.GIS for .NET을 사용하여 C#에서 shapefile을 읽는 방법을 배우고, 모든 피처 속성 값을 가져오며,
  속성을 효율적으로 덤프하는 방법을 알아보세요.
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: Shapefile 읽기 C# – 모든 피처 속성 값 가져오기
url: /ko/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 모든 피처 속성 값 가져오기

## Introduction
Aspose.GIS for .NET와 함께하는 지리공간 개발의 세계에 오신 것을 환영합니다! 이 튜토리얼에서는 **C#으로 shapefile을 읽는 방법**을 배우고 피처마다 모든 속성 값을 가져오는 방법을 알아봅니다. 매핑 앱을 만들든 배치로 공간 데이터를 처리하든, 속성 추출을 마스터하는 것은 필수입니다. 이제 코드를 직접 확인해 보세요.

## Quick Answers
- **이 코드는 무엇을 하나요?** Shapefile을 열고 각 피처에서 모든, 일부 또는 덤프된 속성 값을 읽습니다.  
- **필요한 라이브러리는?** Aspose.GIS for .NET (.NET Framework 및 .NET Core와 호환).  
- **라이선스가 필요합니까?** 테스트용 임시 라이선스는 동작하지만, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **다른 포맷을 읽을 수 있나요?** 예 – 동일한 API가 GeoJSON, KML 등 다양한 포맷을 지원합니다.  
- **속성을 덤프하려면?** `feature.GetValuesDump()`를 사용하여 유연한 객체 배열을 얻습니다.

## What is “read shapefile C#”?
C#에서 Shapefile을 읽는다는 것은 GIS 라이브러리를 사용해 .shp 파일을 열고, 벡터 피처들을 순회하면서 동반되는 .dbf 파일에 저장된 속성 데이터를 접근하는 것을 의미합니다. Aspose.GIS는 저수준 파일 처리를 추상화하여 필요한 속성 값에 집중할 수 있게 해줍니다.

## Why use Aspose.GIS to read attributes?
- **간단한 API** – `GetValues` 및 `GetValuesDump`와 같은 직관적인 메서드.  
- **크로스‑플랫폼** – .NET Core와 함께 Windows, Linux, macOS에서 동작합니다.  
- **다양한 포맷 지원** – 추가 플러그인 없이 Shapefile, GeoJSON, GML 등을 처리합니다.  
- **성능 최적화** – 대용량 데이터셋을 빠르게 순회합니다.

## Prerequisites
이 흥미진진한 여정을 시작하기 전에 다음 사전 조건을 확인하세요:
- Aspose.GIS for .NET: [Aspose.GIS for .NET 다운로드 페이지](https://releases.aspose.com/gis/net/)에서 라이브러리를 다운로드하고 설치합니다.
- Development Environment: Visual Studio와 같은 .NET 개발 환경을 설정합니다.
- Shapefile: 예시 Shapefile(예: "InputShapeFile.shp")을 문서 디렉터리에 준비합니다.

## Import Namespaces
C# 코드에서 Aspose.GIS 기능을 활용하려면 필요한 네임스페이스를 먼저 가져옵니다:
```csharp
using System;
using Aspose.Gis;
```

## Step 1: Set the Document Directory
```csharp
string dataDir = "Your Document Directory";
```
"Your Document Directory"를 Shapefile이 위치한 실제 경로로 교체합니다.

## Step 2: Open the VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
이 단계에서는 Aspose.GIS를 사용해 Shapefile을 열고 파일 경로와 포맷(이 경우 Shapefile)을 지정합니다.

## Step 3: Retrieve All Feature Attribute Values
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
이 스니펫은 고정 크기 배열에 로드하여 **모든 피처의 속성을 읽는 방법**을 보여줍니다.

## Step 4: Retrieve Several Feature Attribute Values
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
필드의 일부만 필요할 때 **특정 속성 값을 읽는 방법**을 시연합니다.

## Step 5: Retrieve Attribute Values as Objects Dump
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
마지막 단계에서는 `GetValuesDump()`를 사용해 **속성을 덤프하는 방법**을 보여줍니다. 이 메서드는 검사하거나 직렬화할 수 있는 유연한 컬렉션을 반환합니다.

## Common Issues and Solutions
- **배열 크기 불일치** – `GetValues`에 전달하는 배열이 기대하는 속성 수와 일치하는지 확인하세요; 그렇지 않으면 `null` 항목이 발생합니다.  
- **파일을 찾을 수 없음** – `dataDir`이 올바른 폴더를 가리키고 있는지, Shapefile 이름이 정확히 입력되었는지 확인합니다.  
- **라이선스 예외** – 라이선스 오류가 발생하면 API 메서드를 호출하기 전에 임시 또는 정식 라이선스를 적용하십시오.

## Frequently Asked Questions
### Aspose.GIS가 .NET Core와 호환되나요?
예, Aspose.GIS는 .NET Core와 완전히 호환되어 크로스‑플랫폼 애플리케이션을 구축할 수 있습니다.

### Aspose.GIS를 사용해 다양한 GIS 파일 포맷을 다룰 수 있나요?
물론입니다! Aspose.GIS는 Shapefile, GeoJSON 등을 포함한 다양한 포맷을 지원합니다.

### Aspose.GIS 지원을 위한 커뮤니티 포럼이 있나요?
예, [지원 포럼](https://forum.aspose.com/c/gis/33)에서 도움을 받고 Aspose.GIS 커뮤니티와 교류할 수 있습니다.

### Aspose.GIS의 임시 라이선스를 어떻게 얻나요?
테스트용 임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

### Aspose.GIS에 대한 자세한 문서는 어디서 찾을 수 있나요?
포괄적인 문서는 [여기](https://reference.aspose.com/gis/net/)에서 확인할 수 있습니다.

### 각 피처에서 “Name” 속성만 가져오려면 어떻게 하나요?
`GetValues`에 크기가 1인 배열을 사용하고 “Name” 필드의 인덱스를 전달하거나, `feature["Name"]`를 직접 호출합니다.

### `GetValues`와 `GetValuesDump`의 차이점은 무엇인가요?
`GetValues`는 사전 할당된 배열에 원시 값을 채우고, `GetValuesDump`는 스키마를 미리 알 필요 없이 열거할 수 있는 객체 배열을 반환합니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**마지막 업데이트:** 2026-01-05  
**테스트 환경:** Aspose.GIS for .NET (최신 릴리스)  
**작성자:** Aspose  

---