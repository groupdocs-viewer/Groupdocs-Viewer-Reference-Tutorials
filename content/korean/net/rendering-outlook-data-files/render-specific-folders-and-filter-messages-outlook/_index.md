---
"description": "GroupDocs.Viewer for .NET을 사용하여 Outlook에서 특정 폴더를 렌더링하고 메시지를 필터링하는 방법을 알아보세요. .NET 애플리케이션에서 문서 관리를 간소화하세요."
"linktitle": "특정 폴더 렌더링 및 필터 메시지(Outlook)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "특정 폴더 렌더링 및 필터 메시지(Outlook)"
"url": "/ko/net/rendering-outlook-data-files/render-specific-folders-and-filter-messages-outlook/"
"weight": 11
type: docs
---
# 특정 폴더 렌더링 및 필터 메시지(Outlook)

## 소개
.NET 개발 환경에서는 문서를 효율적으로 관리하고 표시하는 것이 매우 중요합니다. GroupDocs.Viewer for .NET은 다양한 문서 형식을 원활하게 렌더링하는 강력한 기능을 제공하여 이러한 작업을 간소화합니다. 이 튜토리얼에서는 GroupDocs.Viewer for .NET을 사용하여 Outlook에서 특정 폴더를 렌더링하고 메시지를 필터링하는 방법을 자세히 살펴보겠습니다.
## 필수 조건
튜토리얼을 시작하기 전에 다음 사항이 있는지 확인하세요.
1. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET이 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다. [웹사이트](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: 컴퓨터에 .NET Framework가 설치되어 있어야 합니다.
3. C#에 대한 기본적인 이해: 튜토리얼을 따라가려면 C# 프로그래밍 언어에 대한 지식이 필요합니다.

## 네임스페이스 가져오기
먼저, 필요한 네임스페이스를 C# 코드로 가져오겠습니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 1단계: 출력 디렉토리 정의
```csharp
string outputDirectory = "Your Document Directory";
```
바꾸다 `"Your Document Directory"` 렌더링된 문서를 저장할 디렉토리 경로를 입력합니다.
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
이 줄은 렌더링된 각 페이지의 파일 경로 형식을 정의합니다. 이 예에서는 다음과 같은 이름의 HTML 파일을 생성합니다. `page_1.html`, `page_2.html`, 등등.
## 3단계: 뷰어 객체 초기화
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
여기서 우리는 초기화합니다 `Viewer` 샘플 Outlook 폴더의 경로가 있는 개체입니다.
## 4단계: HTML 보기 옵션 정의
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.OutlookOptions.Folder = "Входящие";
```
우리는 인스턴스를 생성합니다 `HtmlViewOptions` 포함된 리소스의 형식을 지정합니다. 또한 Outlook 폴더가 다음과 같이 렌더링되도록 설정합니다. `"Входящие"` (들어오는).
## 5단계: 문서 렌더링
```csharp
viewer.View(options);
```
이 줄은 지정된 옵션으로 렌더링 프로세스를 트리거합니다.
## 6단계: 성공 메시지 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
렌더링이 끝나면 렌더링 프로세스가 성공적으로 완료되었음을 나타내는 메시지가 표시되고 사용자를 출력 디렉토리로 안내합니다.

## 결론
이 튜토리얼에서는 GroupDocs.Viewer for .NET을 사용하여 Outlook에서 특정 폴더를 렌더링하고 메시지를 필터링하는 방법을 살펴보았습니다. 위에 설명된 단계를 따르면 .NET 애플리케이션에서 문서를 효율적으로 관리하고 표시할 수 있습니다.
## 자주 묻는 질문
### GroupDocs.Viewer for .NET을 사용하여 Outlook 메시지 이외의 문서를 렌더링할 수 있나요?
네, GroupDocs.Viewer for .NET은 PDF, DOCX, XLSX 등 다양한 문서 형식을 지원합니다.
### GroupDocs.Viewer for .NET은 .NET Core와 호환됩니까?
네, GroupDocs.Viewer for .NET은 .NET Framework와 .NET Core 모두와 호환됩니다.
### 렌더링 출력 형식을 사용자 정의할 수 있나요?
물론입니다. GroupDocs.Viewer for .NET은 HTML, 이미지, PDF 형식을 비롯하여 렌더링 출력을 사용자 정의할 수 있는 다양한 옵션을 제공합니다.
### GroupDocs.Viewer for .NET의 평가판이 있나요?
네, 무료 평가판을 다운로드할 수 있습니다. [웹사이트](https://releases.groupdocs.com/).
### GroupDocs.Viewer for .NET에 대한 도움이나 지원은 어디에서 받을 수 있나요?
방문할 수 있습니다 [GroupDocs.Viewer 포럼](https://forum.groupdocs.com/c/viewer/9) 도움이나 질문이 있으시면 언제든지 문의해 주세요.