---
date: 2025-12-11
description: Aspose.GIS for .NET을 사용하여 좌표를 DMS(도·분·초)로 변환하는 방법을 배워보세요. C# 예제, C#으로
  위도와 경도 변환, 단계별 가이드를 포함합니다.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET을 사용하여 좌표를 DMS로 변환
url: /ko/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS를 사용하여 좌표를 DMS로 변환하기

## 소개
이 튜토리얼에서는 강력한 Aspose.GIS .NET 라이브러리를 사용하여 **좌표를 DMS**(도, 분, 초) 형식으로 **변환하는 방법**을 알아봅니다. 매핑 애플리케이션을 위한 위도·경도 변환, 사람이 읽을 수 있는 위치 문자열 생성, 혹은 다양한 좌표 형식을 탐색하고자 할 때, 이 가이드는 명확한 설명과 바로 실행 가능한 C# 코드를 통해 모든 단계를 안내합니다.

## 빠른 답변
- **“좌표를 DMS로 변환한다”는 무슨 의미인가요?** 숫자 형태의 위도·경도 값을 전통적인 도·분·초 표기법으로 바꾸는 것입니다.  
- **변환을 담당하는 라이브러리는 무엇인가요?** Aspose.GIS for .NET이 `GeoConvert` 클래스를 제공하며, 내장된 형식 지원을 포함합니다.  
- **체험판을 사용하려면 라이선스가 필요한가요?** 무료 체험판을 사용할 수 있으며, 실제 운영 환경에서는 상용 라이선스가 필요합니다.  
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 4.5+, .NET Core 3.1+, 그리고 .NET 5/6+를 지원합니다.  
- **다른 형식에도 같은 코드를 사용할 수 있나요?** 예, `PointFormats` 열거형 값을 `DecimalDegrees`, `GeoRef` 등으로 바꾸기만 하면 됩니다.  

## 좌표를 DMS로 변환한다는 의미는?
좌표를 DMS로 변환하면 소수점 형태의 위도·경도 값을 `25°30'00"N 45°30'00"E`와 같은 형식으로 재작성합니다. 이 표기는 지도 제작, 항법, GIS 데이터 교환 등에서 널리 사용됩니다.

## Aspose.GIS를 좌표 변환에 사용하는 이유
- **All‑in‑one API** – 외부 라이브러리나 복잡한 수학 연산이 필요 없으며, Aspose.GIS가 파싱과 포맷팅을 내부에서 처리합니다.  
- **높은 정확도** – 음수 값 및 반구 표시와 같은 경계 상황을 정밀하게 처리합니다.  
- **크로스‑플랫폼** – Windows, Linux, macOS .NET 런타임에서 동일하게 동작합니다.  
- **확장성** – DMS, 십진법 도, 도‑십진‑분, GeoRef 등 다양한 형식 간에 손쉽게 전환할 수 있습니다.

## 사전 요구 사항
시작하기 전에 다음을 확인하세요:

1. **C# 기본 지식** – 변수, 메서드 호출, 콘솔 출력 등에 익숙해야 합니다.  
2. **Aspose.GIS 설치** – 최신 패키지를 [Aspose.GIS 웹사이트](https://releases.aspose.com/gis/net/)에서 다운로드합니다.  

## 네임스페이스 가져오기
GIS 작업에 필요한 네임스페이스를 먼저 가져옵니다:

```csharp
using System;
using Aspose.Gis;
```

## 단계별 가이드

### 단계 1: 변환 프로세스 시작
데모가 시작되었음을 알리는 친절한 메시지를 출력합니다.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### 단계 2: 십진법 도(Decimal Degrees) 변환  
최종 목표가 DMS이지만, 원본 십진법 표현을 먼저 보여줍니다.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### 단계 3: 도‑십진‑분(Degree Decimal Minutes) 변환  
이 형식(`DD°MM.m'`)은 *convert lat long degree minutes*와 같은 중간 단계에서 흔히 사용됩니다.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### 단계 4: 도‑분‑초(Degree Minutes Seconds, DMS) 변환  
튜토리얼의 핵심—**좌표를 DMS로 변환**합니다.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### 단계 5: GeoRef 변환  
완전성을 위해 원격 감지 워크플로우에 유용한 `GeoRef` 형식도 시연합니다.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## 일반적인 문제와 해결 방법
- **반구 문자 오류** – 북/동은 양수, 남/서를 음수로 전달해야 합니다; API가 자동으로 올바른 접미사를 추가합니다.  
- **출력이 비어 있음** – `Aspose.Gis` 어셈블리가 올바르게 참조되었는지, 프로젝트가 지원되는 .NET 버전을 대상으로 하는지 확인하세요.  
- **라이선스를 찾을 수 없음** – 라이선스 파일을 애플리케이션 루트에 두거나 `License license = new License(); license.SetLicense("Aspose.GIS.lic");`와 같이 프로그래밍적으로 설정합니다.

## 자주 묻는 질문

**Q: Aspose.GIS가 다른 프로그래밍 언어와 호환되나요?**  
A: Aspose.GIS는 주로 .NET 개발자를 대상으로 하지만, Java 버전도 제공됩니다.

**Q: 구매 전에 Aspose.GIS를 체험해볼 수 있나요?**  
A: 예, [웹사이트](https://releases.aspose.com/)에서 무료 체험판을 이용할 수 있습니다.

**Q: Aspose.GIS 지원을 어떻게 받을 수 있나요?**  
A: Aspose.GIS 커뮤니티 포럼([여기](https://forum.aspose.com/c/gis/33))에서 도움을 받을 수 있습니다.

**Q: 임시 라이선스를 발급받을 수 있나요?**  
A: 예, [임시 라이선스 페이지](https://purchase.aspose.com/temporary-license/)에서 발급받을 수 있습니다.

**Q: Aspose.GIS를 어디서 구매하나요?**  
A: [구매 페이지](https://purchase.aspose.com/buy)에서 구매할 수 있습니다.

## 결론
이 단계들을 따라 하면 Aspose.GIS for .NET을 사용해 **좌표를 DMS** 및 기타 일반 GIS 형식으로 변환하는 방법을 알게 됩니다. 이 기능을 활용하면 매핑 애플리케이션, 보고서, 혹은 모든 공간 데이터 워크플로우에 사람이 읽기 쉬운 위치 문자열을 손쉽게 통합할 수 있습니다. 다양한 위도·경도 값을 실험해 보고 `GeoConvert` 클래스가 제공하는 다른 형식도 탐색해 보세요.

---

**마지막 업데이트:** 2025-12-11  
**테스트 환경:** Aspose.GIS 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}