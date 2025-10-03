---
"description": "GroupDocs.Viewer for .NET을 사용하여 아카이브를 HTML 페이지로 렌더링하는 방법을 알아보세요. 문서 보기 기능을 .NET 애플리케이션에 손쉽게 통합할 수 있습니다."
"linktitle": "아카이브를 단일 또는 여러 HTML 페이지로 렌더링"
"second_title": "GroupDocs.Viewer .NET API"
"title": "아카이브를 단일 또는 여러 HTML 페이지로 렌더링"
"url": "/ko/net/rendering-archive-files/render-archives-html/"
"weight": 12
type: docs
---
# 아카이브를 단일 또는 여러 HTML 페이지로 렌더링

## 소개
GroupDocs.Viewer for .NET은 개발자가 문서 보기 기능을 .NET 애플리케이션에 손쉽게 통합할 수 있도록 지원하는 강력한 문서 렌더링 라이브러리입니다. 아카이브를 단일 또는 여러 HTML 페이지로 렌더링해야 하는 경우, 이 튜토리얼을 통해 단계별로 프로세스를 안내해 드립니다.
## 필수 조건
이 튜토리얼을 시작하기 전에 다음 필수 조건이 충족되었는지 확인하세요.
1. .NET용 GroupDocs.Viewer: 프로젝트에 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다. [여기](https://releases.groupdocs.com/viewer/net/).
2. 개발 환경: .NET 개발을 위한 작업 개발 환경을 설정합니다.
3. 문서 디렉토리: 문서를 저장할 디렉토리를 준비하세요.
4. C#에 대한 기본 이해: C# 프로그래밍 언어의 기본 사항을 익혀보세요.

## 네임스페이스 가져오기
C# 코드에서 필요한 네임스페이스를 가져오세요.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

GroupDocs.Viewer for .NET을 사용하여 아카이브를 단일 또는 여러 HTML 페이지로 렌더링하려면 다음 단계를 따르세요.
## 1단계: 출력 디렉토리 설정
렌더링된 HTML 페이지를 저장할 디렉토리를 정의합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2단계: 파일 경로 형식 정의
HTML 페이지의 파일 경로 형식을 지정합니다. 단일 페이지 렌더링의 경우:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
다중 페이지 렌더링의 경우:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## 3단계: 단일 페이지 HTML로 렌더링
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## 4단계: 여러 페이지 HTML로 렌더링
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; // 페이지당 항목 설정
    viewer.View(options);
}
```
## 5단계: 출력 확인
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
GroupDocs.Viewer for .NET을 사용하여 아카이브를 HTML 페이지로 렌더링하는 것은 간단한 과정입니다. 이 튜토리얼에 설명된 단계를 따르면 문서 보기 기능을 .NET 애플리케이션에 원활하게 통합할 수 있습니다.
## 자주 묻는 질문
### 보관 파일 외에 다른 문서 형식도 렌더링할 수 있나요?
네, GroupDocs.Viewer는 PDF, DOCX, XLSX, PPTX 등 다양한 문서 형식을 지원합니다.
### GroupDocs.Viewer는 데스크톱과 웹 애플리케이션 모두에 적합합니까?
물론입니다. GroupDocs.Viewer는 데스크톱과 웹 애플리케이션 모두에서 원활하게 활용할 수 있습니다.
### GroupDocs.Viewer는 뷰어 인터페이스에 대한 사용자 정의 옵션을 제공합니까?
네, 귀하의 요구 사항에 맞게 뷰어 인터페이스를 사용자 지정할 수 있습니다.
### GroupDocs.Viewer를 사용하여 문서를 비동기적으로 렌더링할 수 있나요?
네, GroupDocs.Viewer는 향상된 성능을 위해 비동기 렌더링 기능을 제공합니다.
### GroupDocs.Viewer는 문서 주석을 지원합니까?
네, GroupDocs.Viewer를 사용하면 사용자가 문서 주석을 효율적으로 보고 관리할 수 있습니다.