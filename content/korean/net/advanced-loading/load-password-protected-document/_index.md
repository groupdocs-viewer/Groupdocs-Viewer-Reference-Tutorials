---
title: 비밀번호로 보호된 문서 로드
linktitle: 비밀번호로 보호된 문서 로드
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 암호로 보호된 문서 보기를 .NET 응용 프로그램에 손쉽게 통합할 수 있습니다. 원활하게 진행하려면 단계별 튜토리얼을 따르세요.
type: docs
weight: 12
url: /ko/net/advanced-loading/load-password-protected-document/
---
## 소개
오늘날의 디지털 시대에 다양한 문서 형식을 원활하게 관리하고 보는 것은 많은 기업과 개인 모두에게 필수입니다. 다행히 .NET용 GroupDocs.Viewer는 .NET 개발자가 문서 보기 기능을 응용 프로그램에 쉽게 통합할 수 있는 포괄적인 솔루션을 제공합니다. 이 자습서에서는 GroupDocs.Viewer의 필수 기능 중 하나인 암호로 보호된 문서를 로드하는 방법을 자세히 살펴보겠습니다. 개발자가 쉽게 따라하고 프로젝트에 이 기능을 구현할 수 있도록 프로세스를 단계별로 분석하겠습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.
### 1. .NET용 GroupDocs.Viewer 설치
 개발 환경에 .NET용 GroupDocs.Viewer가 설치되어 있는지 확인하십시오. 다음에서 다운로드할 수 있습니다.[웹사이트](https://releases.groupdocs.com/viewer/net/).
### 2. 비밀번호로 보호된 문서 얻기
테스트 목적으로 비밀번호로 보호된 문서를 준비하세요. 이를 통해 로딩 프로세스를 효과적으로 시연할 수 있습니다.

## 네임스페이스 가져오기
튜토리얼을 진행하기 전에 필요한 네임스페이스를 프로젝트로 가져오겠습니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 1단계: 출력 디렉터리 정의
먼저 렌더링된 출력을 저장할 디렉터리를 지정합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
 바꾸다`"Your Document Directory"` 원하는 디렉토리의 경로로.
## 2단계: 페이지 파일 경로 형식 정의
다음으로, 렌더링된 각 페이지의 파일 경로 형식을 정의합니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 이 형식은 다음과 같은 파일 경로를 생성합니다.`"Your Document Directory/page_1.html"`, `"Your Document Directory/page_2.html"`, 등등.
## 3단계: 로드 옵션 구성
비밀번호를 포함하여 비밀번호로 보호된 문서에 대한 로드 옵션을 구성합니다.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    Password = "12345"
};
```
 바꾸다`"12345"` 문서의 실제 비밀번호로.
## 4단계: 뷰어 초기화
문서 및 로드 옵션을 사용하여 GroupDocs.Viewer를 초기화합니다.
```csharp
using (Viewer viewer = new Viewer("Path_to_your_document", loadOptions))
{
    // 보기 옵션에 대한 코드는 다음 단계에서 추가됩니다.
}
```
 바꾸다`"Path_to_your_document"` 비밀번호로 보호된 문서의 경로를 입력하세요.
## 5단계: HTML 보기 옵션 구성
포함된 리소스가 있는 문서를 렌더링하기 위한 HTML 보기 옵션을 구성합니다.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## 6단계: 문서 렌더링
구성된 뷰어 및 보기 옵션을 사용하여 문서를 렌더링합니다.
```csharp
viewer.View(options);
```
## 7단계: 성공 메시지 표시
사용자에게 문서가 성공적으로 렌더링되었음을 알립니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 암호로 보호된 문서를 로드하는 방법을 살펴보았습니다. 단계별 가이드에 따라 개발자는 이 기능을 .NET 애플리케이션에 원활하게 통합하여 사용자가 보호된 문서를 쉽게 볼 수 있도록 할 수 있습니다.
## FAQ
### GroupDocs.Viewer는 암호로 보호된 문서 외에 다른 문서 형식을 처리할 수 있습니까?
예, GroupDocs.Viewer는 PDF, DOCX, XLSX, PPTX 등을 포함한 광범위한 문서 형식을 지원합니다.
### GroupDocs.Viewer는 .NET Core와 호환되나요?
예, GroupDocs.Viewer는 .NET Framework 및 .NET Core 환경 모두와의 호환성을 제공합니다.
### 문서의 렌더링 옵션을 사용자 정의할 수 있나요?
전적으로! GroupDocs.Viewer는 개발자가 요구 사항에 따라 보기 환경을 사용자 정의할 수 있도록 다양한 렌더링 옵션을 제공합니다.
### GroupDocs.Viewer는 문서 주석을 지원합니까?
예, GroupDocs.Viewer는 문서 주석을 지원하므로 사용자는 문서에 설명, 강조 표시 및 기타 주석을 추가할 수 있습니다.
### GroupDocs.Viewer에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 GroupDocs.Viewer 무료 평가판을 얻을 수 있습니다.[웹사이트](https://releases.groupdocs.com/).