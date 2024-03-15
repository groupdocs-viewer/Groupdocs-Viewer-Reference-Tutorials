---
title: 렌더 아카이브 폴더
linktitle: 렌더 아카이브 폴더
second_title: GroupDocs.Viewer .NET API
description: 효율적인 문서 렌더링 및 보기 기능을 위해 .NET용 GroupDocs.Viewer를 .NET 응용 프로그램에 완벽하게 통합하세요.
type: docs
weight: 11
url: /ko/net/rendering-archive-files/render-archive-folder/
---
## 소개
오늘날의 디지털 시대에 문서에 원활하게 액세스하고 보는 것은 기업과 개인 모두에게 중요합니다. 다행스럽게도 기술이 발전함에 따라 이제 개발자는 문서 보기 기능을 응용 프로그램에 손쉽게 통합할 수 있는 강력한 도구를 갖게 되었습니다. 그러한 도구 중 하나가 .NET용 GroupDocs.Viewer입니다. 이 라이브러리는 개발자가 .NET 응용 프로그램 내에서 다양한 문서 형식을 렌더링할 수 있도록 지원하는 다목적 라이브러리입니다.
## 전제조건
.NET용 GroupDocs.Viewer를 프로젝트에 통합하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### C# 프로그래밍에 대한 지식
GroupDocs.Viewer for .NET을 효과적으로 활용하려면 C# 프로그래밍 언어에 대한 기본적인 이해가 필요합니다. 클래스, 메소드, 변수 등의 개념을 숙지하세요.
### .NET용 GroupDocs.Viewer 설치
.NET용 GroupDocs.Viewer를 다운로드하여 설치했는지 확인하세요. 제공된 라이브러리에서 라이브러리를 얻을 수 있습니다.[다운로드 링크](https://releases.groupdocs.com/viewer/net/).
### 개발 환경 설정
Visual Studio 또는 .NET 개발을 위해 선호하는 IDE를 사용하여 개발 환경을 구성하세요.

## 네임스페이스 가져오기
.NET용 GroupDocs.Viewer를 프로젝트에 통합하기 전에 해당 기능에 원활하게 액세스하는 데 필요한 네임스페이스를 가져옵니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

이제 .NET용 GroupDocs.Viewer를 사용하여 보관 폴더를 렌더링하는 프로세스를 관리 가능한 단계로 나누어 보겠습니다.
## 1단계: 출력 디렉터리 정의
렌더링된 문서를 저장할 디렉터리를 지정합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2단계: 페이지 파일 경로 형식 정의
개별 페이지 파일의 이름을 지정하는 형식을 설정합니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3단계: 뷰어 개체 인스턴스화
아카이브 파일의 경로를 매개변수로 전달하여 Viewer 클래스의 인스턴스를 만듭니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_ZIP_WITH_FOLDERS))
```
## 4단계: HTML 보기 옵션 구성
포함된 리소스의 형식과 아카이브 내의 대상 폴더를 포함한 HTML 보기 옵션을 설정합니다.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.ArchiveOptions.Folder = "ThirdFolderWithItems";
```
## 5단계: 렌더 아카이브 폴더
구성된 HTML 보기 옵션을 전달하여 Viewer 개체의 View 메서드를 호출합니다.
```csharp
viewer.View(options);
```
## 6단계: 성공 메시지 표시
사용자에게 문서 렌더링 프로세스가 완료되었음을 알리고 출력 디렉터리를 제공합니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
.NET용 GroupDocs.Viewer를 .NET 응용 프로그램에 통합하면 원활한 문서 렌더링 가능성의 세계가 열립니다. 설명된 단계를 따르면 문서 보기 기능을 쉽게 통합하여 애플리케이션의 기능을 향상시킬 수 있습니다.
## FAQ
### .NET용 GroupDocs.Viewer는 모든 문서 형식과 호환됩니까?
.NET용 GroupDocs.Viewer는 PDF, Microsoft Office 문서, 이미지 등을 포함한 광범위한 문서 형식을 지원합니다. 전체 목록은 설명서를 참조하세요.
### 렌더링된 문서의 모양을 사용자 정의할 수 있습니까?
예, .NET용 GroupDocs.Viewer는 워터마킹, 페이지 회전, 확대/축소 등 렌더링된 문서의 모양을 사용자 정의할 수 있는 다양한 옵션을 제공합니다.
### .NET용 GroupDocs.Viewer는 클라우드 저장소 서비스를 지원합니까?
예, 원활한 문서 검색 및 렌더링을 위해 .NET용 GroupDocs.Viewer를 Dropbox, Google Drive, Amazon S3 등 널리 사용되는 클라우드 저장소 서비스와 통합할 수 있습니다.
### 평가 목적으로 사용할 수 있는 평가판이 있습니까?
예. 구매 결정을 내리기 전에 .NET용 GroupDocs.Viewer 무료 평가판을 사용하여 기능을 살펴보실 수 있습니다.
### .NET용 GroupDocs.Viewer와 관련하여 문제가 발생하거나 질문이 있는 경우 어디서 도움을 구할 수 있습니까?
 당신은 방문 할 수 있습니다[GroupDocs.Viewer 포럼](https://forum.groupdocs.com/c/viewer/9) 커뮤니티와 GroupDocs 팀의 지원을 구합니다.