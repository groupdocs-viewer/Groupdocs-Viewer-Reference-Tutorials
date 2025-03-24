---
title: 아카이브를 단일 또는 다중 HTML 페이지로 렌더링
linktitle: 아카이브를 단일 또는 다중 HTML 페이지로 렌더링
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 아카이브를 HTML 페이지로 렌더링하는 방법을 알아보세요. 문서 보기 기능을 .NET 애플리케이션에 손쉽게 통합하세요.
weight: 12
url: /ko/net/rendering-archive-files/render-archives-html/
---
## 소개
.NET용 GroupDocs.Viewer는 개발자가 문서 보기 기능을 .NET 응용 프로그램에 쉽게 통합할 수 있게 해주는 강력한 문서 렌더링 라이브러리입니다. 아카이브를 단일 HTML 페이지로 렌더링해야 하는지 아니면 여러 HTML 페이지로 렌더링해야 하는지에 관계없이 이 튜토리얼은 프로세스를 단계별로 안내합니다.
## 전제조건
이 튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET용 GroupDocs.Viewer: 프로젝트에 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.groupdocs.com/viewer/net/).
2. 개발 환경: .NET 개발을 위한 작업 개발 환경을 설정합니다.
3. 문서 디렉터리: 문서가 저장되는 디렉터리를 준비합니다.
4. C#의 기본 이해: C# 프로그래밍 언어 기본 사항에 익숙해집니다.

## 네임스페이스 가져오기
C# 코드에서 필요한 네임스페이스를 가져와야 합니다.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

.NET용 GroupDocs.Viewer를 사용하여 아카이브를 단일 또는 여러 HTML 페이지로 렌더링하려면 다음 단계를 따르십시오.
## 1단계: 출력 디렉터리 설정
렌더링된 HTML 페이지를 저장할 디렉터리를 정의합니다.
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
.NET용 GroupDocs.Viewer를 사용하여 아카이브를 HTML 페이지로 렌더링하는 과정은 간단합니다. 이 자습서에 설명된 단계를 따르면 문서 보기 기능을 .NET 애플리케이션에 원활하게 통합할 수 있습니다.
## FAQ
### 아카이브 외에 다른 문서 형식을 렌더링할 수 있나요?
예, GroupDocs.Viewer는 PDF, DOCX, XLSX, PPTX 등을 포함한 광범위한 문서 형식을 지원합니다.
### GroupDocs.Viewer는 데스크톱과 웹 응용 프로그램 모두에 적합합니까?
물론, GroupDocs.Viewer는 데스크톱과 웹 응용 프로그램 모두에서 원활하게 활용될 수 있습니다.
### GroupDocs.Viewer는 뷰어 인터페이스에 대한 사용자 정의 옵션을 제공합니까?
예, 요구 사항에 따라 뷰어 인터페이스를 사용자 정의할 수 있습니다.
### GroupDocs.Viewer를 사용하여 문서를 비동기적으로 렌더링할 수 있나요?
예, GroupDocs.Viewer는 성능 향상을 위해 비동기 렌더링 기능을 제공합니다.
### GroupDocs.Viewer는 문서 주석을 지원합니까?
예, GroupDocs.Viewer를 사용하면 사용자가 문서 주석을 효율적으로 보고 관리할 수 있습니다.