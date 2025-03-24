---
title: 특정 폴더 렌더링 및 메시지 필터링(Outlook)
linktitle: 특정 폴더 렌더링 및 메시지 필터링(Outlook)
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 Outlook에서 특정 폴더를 렌더링하고 메시지를 필터링하는 방법을 알아보세요. .NET 애플리케이션의 문서 관리를 단순화합니다.
weight: 11
url: /ko/net/rendering-outlook-data-files/render-specific-folders-and-filter-messages-outlook/
---
## 소개
.NET 개발 세계에서는 문서를 효율적으로 관리하고 표시하는 것이 중요합니다. .NET용 GroupDocs.Viewer는 다양한 문서 형식을 원활하게 렌더링하기 위한 강력한 기능을 제공하여 이 작업을 단순화합니다. 이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 Outlook에서 특정 폴더를 렌더링하고 메시지를 필터링하는 방법을 살펴보겠습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 사항을 확인하세요.
1.  .NET용 GroupDocs.Viewer: .NET용 GroupDocs.Viewer를 설치했는지 확인하세요. 다음에서 다운로드할 수 있습니다.[웹사이트](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: 컴퓨터에 .NET Framework가 설치되어 있어야 합니다.
3. C#에 대한 기본 이해: C# 프로그래밍 언어에 익숙하면 튜토리얼을 따라가는 것이 도움이 됩니다.

## 네임스페이스 가져오기
먼저 필요한 네임스페이스를 C# 코드로 가져옵니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 1단계: 출력 디렉터리 정의
```csharp
string outputDirectory = "Your Document Directory";
```
 바꾸다`"Your Document Directory"` 렌더링된 문서를 저장할 디렉터리 경로를 사용하세요.
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 이 줄은 렌더링된 각 페이지의 파일 경로 형식을 정의합니다. 이 예에서는 다음과 같은 HTML 파일을 생성합니다.`page_1.html`, `page_2.html`, 등등.
## 3단계: 뷰어 개체 초기화
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
 여기서는`Viewer` 샘플 Outlook 폴더에 대한 경로가 있는 개체입니다.
## 4단계: HTML 보기 옵션 정의
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.OutlookOptions.Folder = "Входящие";
```
 우리는`HtmlViewOptions` 포함된 리소스의 형식을 지정합니다. 또한 Outlook 폴더를 다음과 같이 렌더링하도록 설정했습니다.`"Входящие"` (들어오는).
## 5단계: 문서 렌더링
```csharp
viewer.View(options);
```
이 줄은 지정된 옵션을 사용하여 렌더링 프로세스를 트리거합니다.
## 6단계: 성공 메시지 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
렌더링 후에는 렌더링 프로세스가 성공적으로 완료되었음을 알리는 이 메시지가 표시되고 사용자에게 출력 디렉터리로 연결됩니다.

## 결론
이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 Outlook에서 특정 폴더를 렌더링하고 메시지를 필터링하는 방법을 살펴보았습니다. 위에 설명된 단계를 수행하면 .NET 애플리케이션 내에서 문서를 효율적으로 관리하고 표시할 수 있습니다.
## FAQ
### .NET용 GroupDocs.Viewer를 사용하여 Outlook 메시지 이외의 문서를 렌더링할 수 있나요?
예, .NET용 GroupDocs.Viewer는 PDF, DOCX, XLSX 등을 포함한 광범위한 문서 형식을 지원합니다.
### .NET용 GroupDocs.Viewer는 .NET Core와 호환됩니까?
예, .NET용 GroupDocs.Viewer는 .NET Framework 및 .NET Core 모두와 호환됩니다.
### 렌더링 출력 형식을 사용자 정의할 수 있나요?
물론 .NET용 GroupDocs.Viewer는 HTML, 이미지 및 PDF 형식을 포함하여 렌더링 출력을 사용자 정의할 수 있는 다양한 옵션을 제공합니다.
### .NET용 GroupDocs.Viewer에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[웹사이트](https://releases.groupdocs.com/).
### .NET용 GroupDocs.Viewer에 대한 도움말이나 지원은 어디서 찾을 수 있나요?
 당신은 방문 할 수 있습니다[GroupDocs.Viewer 포럼](https://forum.groupdocs.com/c/viewer/9) 도움이나 문의사항이 있으면