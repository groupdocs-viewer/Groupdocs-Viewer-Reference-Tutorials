---
title: 측정 라이센스 설정
linktitle: 측정 라이센스 설정
second_title: GroupDocs.Viewer .NET API
description: 원활한 문서 보기를 위해 GroupDocs.Viewer를 사용하여 .NET 응용 프로그램을 강화하세요. 문서 렌더링 기능을 프로젝트에 쉽게 통합하세요.
weight: 12
url: /ko/net/getting-started/set-metered-license/
---

# 측정 라이센스 설정

## 소개
.NET 개발 세계에서 강력한 문서 보기 기능을 애플리케이션에 통합하는 것은 사용자 경험과 기능을 향상시키는 데 필수적입니다. .NET용 GroupDocs.Viewer는 문서 보기 기능을 .NET 프로젝트에 원활하게 통합하기 위한 강력한 솔루션을 제공합니다. PDF, Microsoft Office 문서 또는 다양한 이미지 형식으로 작업하는 경우 GroupDocs.Viewer는 응용 프로그램 내에서 이러한 문서를 렌더링하고 표시하는 프로세스를 단순화합니다.
## 전제조건
.NET용 GroupDocs.Viewer 구현을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### 1. .NET용 GroupDocs.Viewer 설치
 시작하려면 .NET용 GroupDocs.Viewer를 다운로드하여 설치해야 합니다. 다운로드 링크를 찾을 수 있습니다[여기](https://releases.groupdocs.com/viewer/net/). 개발 환경 내에서 라이브러리를 설정하려면 제공된 설치 지침을 따르십시오.
### 2. 계량 라이센스 획득
.NET용 GroupDocs.Viewer를 활용하려면 유료 라이센스를 얻어야 합니다. 이 라이선스를 사용하면 사전 정의된 할당량에 따라 API 사용량을 제어하고 모니터링할 수 있습니다. 측정 라이선스를 설정하려면 아래 단계를 따르세요.

## 네임스페이스 가져오기
먼저 .NET용 GroupDocs.Viewer에서 제공하는 기능에 액세스하려면 필요한 네임스페이스를 가져와야 합니다.
```csharp
using System;
```

이제 제공된 예제 코드를 여러 단계로 나누어 보겠습니다.
## 1단계: 공개 및 개인 키 선언
공개 키와 개인 키를 저장할 변수를 선언합니다.
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
 반드시 교체하세요`"YOUR_PUBLIC_KEY"` 그리고`"YOUR_PRIVATE_KEY"` 실제 키로.
## 2단계: 측정 라이센스 설정
공개키가 제공되었는지 확인하세요. 그렇지 않은 경우 사용자에게 키를 설정하라는 메시지를 표시합니다.
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://buy.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## 3단계: 측정된 개체 초기화 및 라이센스 설정
측정 대상 객체를 초기화하고 공개 및 개인 키를 사용하여 측정 라이선스를 설정합니다.
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## 4단계: 확인 메시지
라이센스가 성공적으로 설정되었음을 나타내는 확인 메시지를 표시합니다.
```csharp
Console.WriteLine("License set successfully.");
```

## 결론
결론적으로 .NET용 GroupDocs.Viewer는 문서 보기 기능을 .NET 응용 프로그램에 통합하기 위한 포괄적인 솔루션을 제공합니다. 간략하게 설명된 단계를 따르면 계량형 라이센스를 쉽게 설정하고 프로젝트 내에서 GroupDocs.Viewer의 기능을 활용할 수 있습니다.
## FAQ
### 질문: .NET용 GroupDocs.Viewer에 대한 설명서는 어디에서 찾을 수 있습니까?
 문서를 찾을 수 있습니다[여기](https://tutorials.groupdocs.com/viewer/net/).
### 질문: .NET용 GroupDocs.Viewer에 대한 무료 평가판이 있습니까?
 예, 무료 평가판에 액세스할 수 있습니다[여기](https://releases.groupdocs.com/).
### Q: 테스트 목적으로 임시 라이센스를 얻으려면 어떻게 해야 합니까?
 임시면허 취득 가능[여기](https://purchase.groupdocs.com/temporary-license/).
### 질문: .NET용 GroupDocs.Viewer와 관련된 지원을 받거나 질문을 할 수 있는 곳은 어디입니까?
 GroupDocs.Viewer 포럼에서 지원을 요청하고 질문할 수 있습니다.[여기](https://forum.groupdocs.com/c/viewer/9).
### 질문: .NET용 GroupDocs.Viewer 라이센스는 어디에서 구입할 수 있습니까?
 라이센스를 구매하실 수 있습니다[여기](https://purchase.groupdocs.com/buy).