---
"description": "GroupDocs.Viewer for .NET을 애플리케이션에 손쉽게 통합하는 방법을 알아보세요. 라이선스를 설정하고, 문서를 보고, 뷰어 디자인을 사용자 지정할 수 있습니다."
"linktitle": "파일에서 라이센스 설정"
"second_title": "GroupDocs.Viewer .NET API"
"title": "파일에서 라이센스 설정"
"url": "/ko/net/getting-started/set-license-from-file/"
"weight": 10
type: docs
---
# 파일에서 라이센스 설정

## 소개
GroupDocs.Viewer for .NET은 .NET 개발자가 문서 보기 기능을 애플리케이션에 원활하게 통합할 수 있도록 지원하는 강력한 문서 뷰어 API입니다. PDF, Microsoft Office 또는 이미지 등 다양한 형식의 문서를 표시해야 하는 경우, GroupDocs.Viewer는 광범위한 사용자 지정 옵션을 갖춘 안정적인 솔루션을 제공합니다.

![GroupDocs.Viewer for .NET을 사용하여 파일에서 라이선스 설정](/viewer/getting-started/set-license-from-file.png)

## 필수 조건
.NET용 GroupDocs.Viewer 구현에 들어가기 전에 다음 필수 구성 요소가 있는지 확인하세요.
### 1. .NET Framework 설치됨
개발용 컴퓨터에 .NET Framework가 설치되어 있는지 확인하세요. Microsoft 공식 웹사이트에서 다운로드할 수 있습니다.
### 2. .NET 패키지용 GroupDocs.Viewer
.NET 패키지용 GroupDocs.Viewer를 다운로드하여 설치하세요. [다운로드 링크](https://releases.groupdocs.com/viewer/net/).
### 3. 라이센스 파일
라이센스 파일을 획득하세요 [그룹닥스](https://purchase.groupdocs.com/buy) 아무런 제한 없이 GroupDocs.Viewer for .NET을 활용하세요.
### 4. 임시 면허(선택 사항)
라이선스를 구매하기 전에 .NET용 GroupDocs.Viewer의 기능을 살펴보려면 다음에서 임시 라이선스를 요청할 수 있습니다. [여기](https://purchase.groupdocs.com/temporary-license/).
### 5. C# 프로그래밍 언어에 대한 지식
이 튜토리얼에서 제공하는 예제를 따라가려면 C# 프로그래밍 언어에 대한 기본 지식이 필수적입니다.

## 네임스페이스 가져오기
C# 프로젝트에서 .NET 기능을 위해 GroupDocs.Viewer를 활용하는 데 필요한 네임스페이스를 가져옵니다.

```csharp
using System;
using System.IO;
```

## 1단계: 라이선스 파일 존재 여부 확인
```csharp
if (File.Exists(Utils.LicensePath))
{
```
## 2단계: 파일에서 라이선스 설정
```csharp
    License license = new License();
    license.SetLicense(Utils.LicensePath);
    Console.WriteLine("License set successfully.");
}
```
## 3단계: 누락된 라이센스 파일 처리
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://구매.그룹문서.com/faqs/licensing. " +
                      "\nLearn how to request temporary license at https://구매.그룹문서.com/임시-라이센스.");
}
```
이러한 단계를 따르면 GroupDocs.Viewer를 사용하여 .NET 애플리케이션의 파일에서 라이선스를 설정할 수 있습니다.

## 결론
결론적으로, GroupDocs.Viewer for .NET은 문서 보기 기능을 .NET 애플리케이션에 통합하는 완벽한 솔루션을 제공합니다. 이 튜토리얼에 설명된 단계를 따르면 파일에서 라이선스를 쉽게 설정하고 GroupDocs.Viewer의 모든 기능을 활용할 수 있습니다.
## 자주 묻는 질문
### GroupDocs.Viewer for .NET에 대한 영구 라이선스를 어떻게 얻을 수 있나요?
영구 라이센스를 구매할 수 있습니다. [그룹닥스](https://purchase.groupdocs.com/buy) 아무런 제한 없이 GroupDocs.Viewer를 사용하세요.
### 평가 목적으로 임시 라이센스를 받을 수 있나요?
네, 임시 면허를 요청할 수 있습니다. [여기](https://purchase.groupdocs.com/temporary-license/) 구매하기 전에 GroupDocs.Viewer for .NET을 평가해 보세요.
### 문서 뷰어의 모양을 사용자 정의할 수 있나요?
네, GroupDocs.Viewer for .NET은 사용자의 요구 사항에 맞게 뷰어를 맞춤 설정할 수 있는 광범위한 사용자 정의 옵션을 제공합니다.
### GroupDocs.Viewer는 여러 문서 형식을 지원합니까?
네, GroupDocs.Viewer는 PDF, Microsoft Office, 이미지 등 다양한 문서 형식을 지원합니다.
### .NET용 GroupDocs.Viewer에 대한 지원은 어디에서 찾을 수 있나요?
지원 및 도움말은 다음에서 찾을 수 있습니다. [GroupDocs 뷰어 포럼](https://forum.groupdocs.com/c/viewer/9).