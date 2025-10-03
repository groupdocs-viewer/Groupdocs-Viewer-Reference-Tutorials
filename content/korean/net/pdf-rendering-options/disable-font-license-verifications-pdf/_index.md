---
"description": "GroupDocs.Viewer for .NET을 사용하여 .NET 환경에서 원활한 문서 보기 기능을 활용하세요. 최소한의 종속성으로 문서 렌더링을 쉽게 통합하고 사용자 지정할 수 있습니다."
"linktitle": "PDF에서 글꼴 라이선스 확인 비활성화"
"second_title": "GroupDocs.Viewer .NET API"
"title": "PDF에서 글꼴 라이선스 확인 비활성화"
"url": "/ko/net/pdf-rendering-options/disable-font-license-verifications-pdf/"
"weight": 12
type: docs
---
# PDF에서 글꼴 라이선스 확인 비활성화

## 소개
.NET 개발 분야에서 문서 관리 및 조작은 많은 애플리케이션에서 매우 중요한 요소입니다. PDF, Word 문서 또는 기타 파일 형식을 보든, 이러한 작업을 효율적으로 처리할 수 있는 강력한 도구가 필수적입니다. 바로 이 부분에서 GroupDocs.Viewer for .NET이 중요한 역할을 합니다. 이 강력한 라이브러리는 개발자에게 문서 보기 기능을 .NET 애플리케이션에 완벽하게 통합할 수 있는 기능을 제공합니다.

![GroupDocs.Viewer .NET을 사용하여 PDF에서 글꼴 라이선스 확인 비활성화](/viewer/pdf-rendering-options/disable-font-license-verifications-in-pdf.png)

## 필수 조건
.NET에서 GroupDocs.Viewer를 사용하기 전에 꼭 갖춰야 할 몇 가지 전제 조건이 있습니다.
### 1. Visual Studio 설치
가장 중요한 것은 시스템에 Visual Studio가 설치되어 있는지 확인하는 것입니다. 아직 설치되어 있지 않다면 Microsoft 웹사이트에서 다운로드할 수 있습니다.
### 2. .NET용 GroupDocs.Viewer 다운로드
로 향하세요 [다운로드 링크](https://releases.groupdocs.com/viewer/net/) .NET용 GroupDocs.Viewer의 최신 버전을 다운로드하세요. 제공된 설치 지침에 따라 개발 환경에 설치하세요.
### 3. 임시 면허 취득
개발 및 테스트 중에 GroupDocs.Viewer for .NET의 모든 기능을 활용하려면 임시 라이선스를 구매하는 것이 좋습니다. 라이선스는 다음에서 요청할 수 있습니다. [여기](https://purchase.groupdocs.com/temporary-license/).

## 네임스페이스 가져오기
필수 조건을 모두 완료하면 프로젝트에서 GroupDocs.Viewer for .NET을 활용할 준비가 된 것입니다. 먼저 필요한 네임스페이스를 코드베이스로 가져오세요.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

더 명확하게 이해하도록 제공된 예를 여러 단계로 나누어 보겠습니다.
## 1단계: 출력 디렉토리 정의
렌더링된 문서 페이지를 저장할 디렉토리를 정의하는 것부터 시작합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2단계: 페이지 파일 경로 형식 정의
문서의 개별 페이지에 대한 파일 경로 형식을 설정합니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
## 3단계: 뷰어 객체 초기화
보려는 문서의 경로를 전달하여 Viewer 클래스의 인스턴스를 만듭니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.OXPS_EMBEDDED_FONT))
```
## 4단계: HTML 보기 옵션 구성
문서를 HTML로 보기 위한 옵션을 정의하고, 내장된 리소스(예: 이미지)에 대한 형식을 지정합니다.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## 5단계: 글꼴 라이선스 확인 비활성화
원활한 렌더링을 위해 글꼴 라이선스 검증을 비활성화하는 옵션을 활성화하세요.
```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
## 6단계: 문서 보기
구성된 옵션을 전달하여 Viewer 개체의 View 메서드를 호출합니다.
```csharp
viewer.View(options);
```
## 7단계: 출력 디렉토리 표시
렌더링된 문서 페이지가 저장된 위치를 사용자에게 알려줍니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
GroupDocs.Viewer for .NET은 개발자에게 문서 보기 기능을 .NET 애플리케이션에 손쉽게 통합할 수 있는 포괄적인 솔루션을 제공합니다. 이 튜토리얼에 설명된 단계를 따르면 이 강력한 라이브러리를 효과적으로 활용하여 문서 관리 워크플로를 개선할 수 있습니다.
## 자주 묻는 질문
### GroupDocs.Viewer for .NET은 여러 문서 형식을 처리할 수 있나요?
네, GroupDocs.Viewer는 PDF, Microsoft Word, Excel, PowerPoint 등 다양한 문서 형식을 지원합니다.
### GroupDocs.Viewer for .NET은 웹 애플리케이션에 적합합니까?
물론입니다. GroupDocs.Viewer는 .NET 기술을 사용하여 개발된 데스크톱 및 웹 애플리케이션에 완벽하게 통합될 수 있습니다.
### GroupDocs.Viewer에 추가 종속성이 필요합니까?
아니요, .NET용 GroupDocs.Viewer는 종속성이 최소화되어 기존 프로젝트에 쉽게 통합할 수 있습니다.
### 렌더링된 문서의 모양을 사용자 정의할 수 있나요?
네, GroupDocs.Viewer는 사용자의 특정 요구 사항에 맞게 렌더링된 문서의 모양과 동작을 사용자 정의할 수 있는 다양한 옵션을 제공합니다.
### GroupDocs.Viewer for .NET에 대한 기술 지원을 받을 수 있나요?
예, 전담 지원팀을 통해 도움과 안내를 받을 수 있습니다. [법정](https://forum.groupdocs.com/c/viewer/9).