---
title: N 연속 페이지 렌더링
linktitle: N 연속 페이지 렌더링
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 응용 프로그램에 통합하여 N개의 연속 페이지로 문서를 손쉽게 렌더링하는 방법을 알아보세요.
weight: 16
url: /ko/net/rendering-options/render-n-consecutive-pages/
---

# N 연속 페이지 렌더링

## 소개
.NET 개발 영역에서 문서 보기 기능을 애플리케이션에 통합하면 사용자 경험과 기능이 크게 향상될 수 있습니다. 원활한 문서 렌더링을 용이하게 하는 도구 중 하나는 .NET용 GroupDocs.Viewer입니다. 이 강력한 라이브러리를 통해 개발자는 애플리케이션 내에서 다양한 문서 형식을 쉽게 표시할 수 있습니다.
## 전제조건
.NET용 GroupDocs.Viewer 구현을 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. .NET 개발 환경: 컴퓨터에 작동하는 .NET 개발 환경이 설정되어 있는지 확인하세요.
  
2.  .NET용 GroupDocs.Viewer: 제공된 파일에서 .NET용 GroupDocs.Viewer를 다운로드하고 설치합니다.[다운로드 링크](https://releases.groupdocs.com/viewer/net/).
3. 문서 파일: .NET용 GroupDocs.Viewer를 사용하여 렌더링하려는 문서 파일을 준비합니다.
#
## 네임스페이스 가져오기
.NET용 GroupDocs.Viewer를 프로젝트에 통합하려면 필요한 네임스페이스를 가져와야 합니다. 이 단계는 코드베이스 내에서 라이브러리 기능에 액세스하는 데 중요합니다.
## 1단계: GroupDocs.Viewer 네임스페이스 가져오기
```csharp
using System;
using System.IO;
using System.Linq;
using GroupDocs.Viewer.Options;
```
## 2단계: System.IO 네임스페이스 가져오기
```csharp
using System.IO;
```

이제 전제 조건을 설정하고 필수 네임스페이스를 가져왔으므로 .NET용 GroupDocs.Viewer를 사용하여 문서에서 지정된 수의 연속 페이지를 렌더링하는 방법을 살펴보겠습니다.
## 1단계: 출력 디렉터리 정의
```csharp
string outputDirectory = "Your Document Directory";
```
렌더링된 페이지를 저장할 디렉터리를 지정합니다.
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
렌더링된 페이지의 파일 경로 형식을 설정합니다. 이 예에서 페이지는 "page_1.html", "page_2.html" 등과 같은 이름의 HTML 파일로 저장됩니다.
## 3단계: 페이지 범위 정의
```csharp
int[] range = Enumerable.Range(1, 3).ToArray();
```
렌더링하려는 연속 페이지의 범위를 지정합니다. 이 경우 페이지 1~3을 렌더링합니다.
## 4단계: 문서 페이지 렌더링
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options, range);
}
```
 인스턴스를 생성합니다.`Viewer` 클래스, 문서 파일의 경로를 매개변수로 전달합니다. 그런 다음 HTML 보기 옵션을 구성하고`View` 메서드, 렌더링할 페이지 범위를 지정합니다.
## 5단계: 렌더링된 출력 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
마지막으로 문서가 성공적으로 렌더링되었음을 나타내는 성공 메시지를 표시하고 렌더링된 페이지가 저장되는 출력 디렉터리에 대해 사용자에게 알립니다.

## 결론
.NET용 GroupDocs.Viewer를 .NET 응용 프로그램에 통합하면 원활한 문서 렌더링 가능성의 세계가 열립니다. 이 튜토리얼에 설명된 단계를 따르면 다양한 문서 형식에서 N개의 연속 페이지를 쉽게 렌더링하여 애플리케이션의 기능과 사용자 경험을 향상시킬 수 있습니다.
## FAQ
### DOCX 파일이 아닌 문서의 페이지를 렌더링할 수 있나요?
예, .NET용 GroupDocs.Viewer는 PDF, PPT, XLS 등을 포함한 광범위한 문서 형식을 지원합니다.
### .NET용 GroupDocs.Viewer는 웹 응용 프로그램에 적합합니까?
전적으로! .NET용 GroupDocs.Viewer는 데스크톱 및 웹 응용 프로그램 모두에 원활하게 통합될 수 있습니다.
### .NET용 GroupDocs.Viewer를 상업적으로 사용하려면 라이센스가 필요합니까?
예, 제공된 구매 링크에서 상업용 라이센스를 얻어 상업용 프로젝트에서 .NET용 GroupDocs.Viewer를 사용할 수 있습니다.
### 렌더링된 페이지의 모양을 사용자 정의할 수 있습니까?
예, .NET용 GroupDocs.Viewer는 렌더링된 문서의 모양과 동작을 사용자 정의하기 위한 다양한 옵션을 제공합니다.
### 도움을 구하고 경험을 공유할 수 있는 커뮤니티 포럼이 있습니까?
예, 제공된 지원 링크를 통해 GroupDocs.Viewer 포럼을 방문하여 커뮤니티에 참여하고 전문가의 도움을 받을 수 있습니다.