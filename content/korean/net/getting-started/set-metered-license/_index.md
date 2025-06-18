---
"description": "GroupDocs.Viewer로 .NET 애플리케이션을 더욱 효율적으로 관리하여 원활한 문서 보기를 경험하세요. 문서 렌더링 기능을 프로젝트에 쉽게 통합할 수 있습니다."
"linktitle": "미터링 라이센스 설정"
"second_title": "GroupDocs.Viewer .NET API"
"title": "미터링 라이센스 설정"
"url": "/ko/net/getting-started/set-metered-license/"
"weight": 12
---

# 미터링 라이센스 설정

## 소개
.NET 개발 환경에서는 강력한 문서 보기 기능을 애플리케이션에 통합하는 것이 사용자 경험과 기능을 향상시키는 데 필수적입니다. GroupDocs.Viewer for .NET은 문서 보기 기능을 .NET 프로젝트에 원활하게 통합할 수 있는 강력한 솔루션을 제공합니다. PDF, Microsoft Office 문서 또는 다양한 이미지 형식 등 어떤 형식으로 작업하든 GroupDocs.Viewer는 애플리케이션 내에서 이러한 문서를 렌더링하고 표시하는 과정을 간소화합니다.

![GroupDocs.Viewer for .NET을 사용하여 미터링된 라이선스 설정](/viewer/getting-started/set-metered-license.png)

## 필수 조건
.NET용 GroupDocs.Viewer 구현에 들어가기 전에 다음 필수 구성 요소가 있는지 확인하세요.
### 1. .NET용 GroupDocs.Viewer 설치
시작하려면 GroupDocs.Viewer for .NET을 다운로드하여 설치해야 합니다. 다운로드 링크는 다음과 같습니다. [여기](https://releases.groupdocs.com/viewer/net/)제공된 설치 지침에 따라 개발 환경 내에서 라이브러리를 설정하세요.
### 2. 미터기 라이센스 획득
GroupDocs.Viewer for .NET을 사용하려면 계량형 라이선스를 구매해야 합니다. 이 라이선스를 사용하면 미리 정의된 할당량에 따라 API 사용량을 제어하고 모니터링할 수 있습니다. 계량형 라이선스를 설정하려면 다음 단계를 따르세요.

## 네임스페이스 가져오기
먼저, .NET용 GroupDocs.Viewer에서 제공하는 기능에 액세스하는 데 필요한 네임스페이스를 가져와야 합니다.
```csharp
using System;
```

이제 제공된 예제 코드를 여러 단계로 나누어 보겠습니다.
## 1단계: 공개 키와 개인 키 선언
공개 키와 개인 키를 저장할 변수를 선언합니다.
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
교체를 확인하세요 `"YOUR_PUBLIC_KEY"` 그리고 `"YOUR_PRIVATE_KEY"` 실제 열쇠로.
## 2단계: 미터링된 라이센스 설정
공개 키가 제공되었는지 확인하세요. 제공되지 않은 경우 사용자에게 키를 설정하라는 메시지를 표시합니다.
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://구매.그룹문서.com/faqs/라이센싱/미터드.");
    return;
}
```
## 3단계: 미터링된 객체 초기화 및 라이선스 설정
공개 키와 개인 키를 사용하여 Metered 객체를 초기화하고 Metered 라이선스를 설정합니다.
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## 4단계: 확인 메시지
라이선스가 성공적으로 설정되었음을 나타내는 확인 메시지를 표시합니다.
```csharp
Console.WriteLine("License set successfully.");
```

## 결론
결론적으로, GroupDocs.Viewer for .NET은 .NET 애플리케이션에 문서 보기 기능을 통합하는 포괄적인 솔루션을 제공합니다. 설명된 단계에 따라 간편하게 계량형 라이선스를 설정하고 프로젝트에서 GroupDocs.Viewer의 기능을 활용할 수 있습니다.
## 자주 묻는 질문
### 질문: .NET용 GroupDocs.Viewer에 대한 설명서는 어디에서 찾을 수 있나요?
문서를 찾을 수 있습니다 [여기](https://tutorials.groupdocs.com/viewer/net/).
### 질문: GroupDocs.Viewer for .NET에 대한 무료 평가판이 있나요?
네, 무료 체험판을 이용하실 수 있습니다. [여기](https://releases.groupdocs.com/).
### 질문: 테스트 목적으로 임시 라이센스를 얻으려면 어떻게 해야 합니까?
임시 면허를 취득할 수 있습니다 [여기](https://purchase.groupdocs.com/temporary-license/).
### 질문: GroupDocs.Viewer for .NET과 관련된 지원이나 질문은 어디에서 받을 수 있나요?
GroupDocs.Viewer 포럼에서 지원을 요청하고 질문을 할 수 있습니다. [여기](https://forum.groupdocs.com/c/viewer/9).
### 질문: GroupDocs.Viewer for .NET 라이선스는 어디에서 구매할 수 있나요?
라이센스를 구매할 수 있습니다 [여기](https://purchase.groupdocs.com/buy).