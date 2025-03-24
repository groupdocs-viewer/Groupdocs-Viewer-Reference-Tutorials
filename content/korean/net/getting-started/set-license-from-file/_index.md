---
title: 파일에서 라이센스 설정
linktitle: 파일에서 라이센스 설정
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 응용 프로그램에 손쉽게 통합하는 방법을 알아보세요. 라이센스를 설정하고, 문서를 보고, 뷰어 모양을 사용자 정의하세요.
weight: 10
url: /ko/net/getting-started/set-license-from-file/
---

# 파일에서 라이센스 설정

## 소개
.NET용 GroupDocs.Viewer는 .NET 개발자가 문서 보기 기능을 응용 프로그램에 원활하게 통합할 수 있게 해주는 강력한 문서 뷰어 API입니다. PDF, Microsoft Office 또는 이미지와 같은 다양한 형식의 문서를 표시해야 하는 경우 GroupDocs.Viewer는 광범위한 사용자 정의 옵션을 갖춘 안정적인 솔루션을 제공합니다.
## 전제조건
.NET용 GroupDocs.Viewer 구현을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### 1. .NET 프레임워크 설치
개발 컴퓨터에 .NET Framework가 설치되어 있는지 확인하세요. 마이크로소프트 공식 홈페이지에서 다운로드 받으실 수 있습니다.
### 2. .NET 패키지용 GroupDocs.Viewer
 다음에서 .NET용 GroupDocs.Viewer 패키지를 다운로드하고 설치합니다.[다운로드 링크](https://releases.groupdocs.com/viewer/net/).
### 3. 라이센스 파일
 다음에서 라이센스 파일을 얻습니다.[그룹문서](https://purchase.groupdocs.com/buy) 아무런 제한 없이 GroupDocs.Viewer for .NET을 활용합니다.
### 4. 임시 라이센스(선택)
 라이센스를 구입하기 전에 .NET용 GroupDocs.Viewer의 기능을 살펴보려면 다음 위치에서 임시 라이센스를 요청할 수 있습니다.[여기](https://purchase.groupdocs.com/temporary-license/).
### 5. C# 프로그래밍 언어에 대한 지식
이 튜토리얼에서 제공되는 예제를 따라하려면 C# 프로그래밍 언어에 대한 기본 지식이 필수적입니다.

## 네임스페이스 가져오기
C# 프로젝트에서 .NET용 GroupDocs.Viewer 기능을 활용하는 데 필요한 네임스페이스를 가져옵니다.

```csharp
using System;
using System.IO;
```

## 1단계: 라이센스 파일 존재 확인
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
                      "\nLearn more about licensing at https://buy.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request temporary license at https://buy.groupdocs.com/temporary-license.");
}
```
다음 단계를 수행하면 GroupDocs.Viewer를 사용하여 .NET 응용 프로그램의 파일에서 라이센스를 설정할 수 있습니다.

## 결론
결론적으로, .NET용 GroupDocs.Viewer는 문서 보기 기능을 .NET 응용 프로그램에 통합하기 위한 완벽한 솔루션을 제공합니다. 이 자습서에 설명된 단계를 따르면 파일에서 라이센스를 쉽게 설정하고 GroupDocs.Viewer의 잠재력을 최대한 활용할 수 있습니다.
## FAQ
### .NET용 GroupDocs.Viewer의 영구 라이센스를 얻으려면 어떻게 해야 합니까?
 다음에서 영구 라이센스를 구입할 수 있습니다.[그룹문서](https://purchase.groupdocs.com/buy) GroupDocs.Viewer를 제한 없이 사용할 수 있습니다.
### 평가 목적으로 임시 라이센스를 사용할 수 있습니까?
 예, 임시 라이센스를 요청할 수 있습니다.[여기](https://purchase.groupdocs.com/temporary-license/) 구매하기 전에 .NET용 GroupDocs.Viewer를 평가해 보세요.
### 문서 뷰어의 모양을 사용자 정의할 수 있나요?
예, .NET용 GroupDocs.Viewer는 요구 사항에 따라 뷰어를 맞춤화할 수 있는 광범위한 사용자 정의 옵션을 제공합니다.
### GroupDocs.Viewer는 다양한 문서 형식을 지원합니까?
예, GroupDocs.Viewer는 PDF, Microsoft Office, 이미지 등을 포함한 광범위한 문서 형식을 지원합니다.
### .NET용 GroupDocs.Viewer에 대한 지원은 어디서 찾을 수 있나요?
 다음에서 지원과 도움을 받으실 수 있습니다.[GroupDocs 뷰어 포럼](https://forum.groupdocs.com/c/viewer/9).