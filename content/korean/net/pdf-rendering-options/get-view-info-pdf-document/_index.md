---
title: PDF 문서에 대한 정보 보기
linktitle: PDF 문서에 대한 정보 보기
second_title: GroupDocs.Viewer .NET API
description: 이 포괄적인 튜토리얼에서 .NET용 GroupDocs.Viewer를 사용하여 PDF 문서에서 보기 정보를 추출하는 방법을 알아보세요.
weight: 16
url: /ko/net/pdf-rendering-options/get-view-info-pdf-document/
---
## 소개
.NET용 GroupDocs.Viewer는 .NET 응용 프로그램 내에서 문서 보기를 간소화하도록 설계된 강력한 도구입니다. PDF, Word 문서, Excel 스프레드시트 또는 PowerPoint 프레젠테이션을 처리하는 경우 이 라이브러리는 다양한 파일 형식의 렌더링 및 상호 작용 프로세스를 단순화합니다. 이 자습서에서는 특히 PDF 문서에서 보기 정보를 추출하기 위해 GroupDocs.Viewer의 기능을 활용하는 데 중점을 둘 것입니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
1.  .NET용 GroupDocs.Viewer 설치: GroupDocs.Viewer 라이브러리를 다운로드하여 설치했는지 확인하세요. 에서 얻으실 수 있습니다.[다운로드 링크](https://releases.groupdocs.com/viewer/net/).   
2. C#에 대한 기본 지식: 제공된 코드 예제를 이해하고 구현하려면 C# 프로그래밍 언어에 대한 지식이 필수적입니다.
3. PDF 문서에 액세스: 보기 정보를 추출하는 데 사용할 PDF 문서를 준비하십시오.

## 네임스페이스 가져오기
C# 프로젝트에서 GroupDocs.Viewer 기능을 활용하는 데 필요한 네임스페이스를 가져옵니다.

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```


이제 .NET용 GroupDocs.Viewer를 사용하여 PDF 문서에서 보기 정보를 검색하는 프로세스를 분석해 보겠습니다.
## 1단계: 뷰어 개체 초기화
뷰어 개체를 생성하고 PDF 문서의 경로를 매개변수로 제공합니다.
```csharp
using (Viewer viewer = new Viewer("path/to/your/sample.pdf"))
{
```
## 2단계: ViewInfoOptions 정의
보기 정보를 검색하려면 HTML 보기와 같은 보기 옵션을 지정하십시오.
```csharp
	ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
## 3단계: 보기 정보 가져오기
GetViewInfo 메서드를 호출하여 PDF 문서에서 보기 정보를 추출합니다.
```csharp
	PdfViewInfo info = viewer.GetViewInfo(options) as PdfViewInfo;
```
## 4단계: 출력 보기 정보
문서 유형, 페이지 수, 인쇄 권한 등 추출된 보기 정보를 표시합니다.
```csharp
	Console.WriteLine("Document type is: " + info.FileType);
	Console.WriteLine("Pages count: " + info.Pages.Count);
	Console.WriteLine("Printing allowed: " + info.PrintingAllowed);
}
```

## 결론
이 자습서에서는 .NET용 GroupDocs.Viewer를 활용하여 PDF 문서에서 보기 정보를 추출하는 방법을 살펴보았습니다. 제공된 단계를 따르면 이 기능을 .NET 애플리케이션에 원활하게 통합하여 문서 관리 및 보기 기능을 향상시킬 수 있습니다.
## FAQ
### GroupDocs.Viewer는 PDF 이외의 다른 파일 형식과 호환됩니까?
예, GroupDocs.Viewer는 Word, Excel, PowerPoint 등을 포함한 광범위한 문서 형식을 지원합니다.
### 내 애플리케이션 요구 사항에 따라 보기 옵션을 사용자 정의할 수 있습니까?
물론, GroupDocs.Viewer는 특정 요구 사항에 따라 보기 환경을 맞춤화할 수 있는 다양한 옵션을 제공합니다.
### GroupDocs.Viewer는 데스크톱과 웹 응용 프로그램 모두에 적합합니까?
예, GroupDocs.Viewer는 다목적이며 데스크톱 및 웹 기반 .NET 응용 프로그램 모두에 원활하게 통합될 수 있습니다.
### 구현 중에 문제가 발생하면 GroupDocs.Viewer에서 지원을 제공합니까?
물론, GroupDocs.Viewer 커뮤니티 포럼에서 도움을 구하거나 전문 지원 서비스에 액세스하여 문제를 신속하게 해결할 수 있습니다.
### 구매하기 전에 GroupDocs.Viewer를 사용해 볼 수 있나요?
 예, 다음에서 제공되는 무료 평가판에 액세스하여 GroupDocs.Viewer의 기능을 탐색할 수 있습니다.[웹사이트](https://purchase.groupdocs.com/buy).