---
title: 선택한 페이지 렌더링
linktitle: 선택한 페이지 렌더링
second_title: GroupDocs.Viewer .NET API
description: .NET용 Groupdocs.Viewer를 사용하여 문서에서 선택한 페이지를 렌더링하는 방법을 알아보세요. 코드 예제가 포함된 단계별 튜토리얼입니다.
weight: 17
url: /ko/net/rendering-options/render-selected-pages/
---
## 소개

이 자습서에서는 .NET용 Groupdocs.Viewer를 활용하여 문서에서 선택한 페이지를 렌더링하는 방법을 자세히 살펴보겠습니다. 숙련된 개발자이든 이제 막 시작하는 개발자이든 이 단계별 가이드를 통해 프로세스를 쉽게 안내받을 수 있습니다.

## 전제조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

### 1. 설치

 개발 환경에 .NET용 Groupdocs.Viewer가 설치되어 있는지 확인하십시오. 그렇지 않은 경우 다음에서 다운로드할 수 있습니다.[다운로드 링크](https://releases.groupdocs.com/viewer/net/).

## 네임스페이스 가져오기

C# 코드 파일에서 필요한 클래스와 메서드에 액세스하려면 필요한 네임스페이스를 가져옵니다. 다음을 사용하여 이 작업을 수행할 수 있습니다.`using` 지령:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

이제 제공된 예제 코드를 여러 단계로 나누어 보겠습니다.

## 1단계: 출력 디렉터리 설정

 렌더링된 페이지를 저장할 디렉터리를 정의합니다. 바꾸다`"Your Document Directory"` 원하는 디렉토리 경로로.

```csharp
string outputDirectory = "Your Document Directory";
```

## 2단계: 페이지 파일 경로 형식 정의

렌더링된 페이지의 파일 경로 형식을 지정합니다. 이는 각 페이지를 출력 디렉토리에 HTML 파일로 저장하는 데 사용됩니다.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## 3단계: 뷰어 개체 인스턴스화

렌더링하려는 문서의 경로를 인수로 전달하여 Viewer 클래스의 인스턴스를 만듭니다.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## 4단계: HTML 보기 옵션 구성

렌더링을 위한 HTML 보기 옵션을 설정합니다. 이 예에서는 HTML 출력에 리소스를 포함하는 옵션을 구성하고 있습니다.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## 5단계: 선택한 페이지 렌더링

렌더링할 페이지 번호를 지정합니다. 이 경우 페이지 1~3을 렌더링합니다. 그런 다음 뷰어 개체에서 View 메서드를 호출하고 옵션과 페이지 번호를 인수로 전달합니다.

```csharp
viewer.View(options, 1, 3);
```

## 6단계: 결과 출력

마지막으로 문서가 성공적으로 렌더링되었음을 나타내는 메시지와 출력 파일이 저장되는 위치를 표시합니다.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론

축하해요! .NET용 Groupdocs.Viewer를 사용하여 문서에서 선택한 페이지를 렌더링하는 방법을 성공적으로 배웠습니다. 이러한 지식을 바탕으로 이제 문서 렌더링 기능을 .NET 애플리케이션에 쉽게 통합할 수 있습니다.

## FAQ

### Q: PDF나 이미지 등 다양한 유형의 문서에서 페이지를 렌더링할 수 있습니까?

A: 예, .NET용 Groupdocs.Viewer는 PDF, Microsoft Office 문서, 이미지 파일을 비롯한 다양한 문서 형식의 페이지 렌더링을 지원합니다.

### Q: 구매하기 전에 테스트할 수 있는 평가판이 있나요?

 A: 예, 다음에서 .NET용 Groupdocs.Viewer 무료 평가판에 액세스할 수 있습니다.[웹사이트](https://releases.groupdocs.com/).

### Q: HTML 이외의 출력 형식을 사용자 정의할 수 있습니까?

A: 물론 .NET용 Groupdocs.Viewer는 페이지를 HTML 외에 이미지, PDF 등으로 렌더링하는 옵션을 제공합니다.

### Q: 테스트 목적으로 임시 라이센스를 얻으려면 어떻게 해야 합니까?

A: 임시 라이센스는 다음에서 취득할 수 있습니다.[임시 라이센스 페이지](https://purchase.groupdocs.com/temporary-license/) Groupdocs 웹사이트에서.

### 질문: 문제가 발생하면 어디에서 도움을 구하거나 도움을 받을 수 있나요?

 A: 다음을 방문하실 수 있습니다.[Groupdocs.Viewer 포럼](https://forum.groupdocs.com/c/viewer/9) 커뮤니티와 개발자의 지원과 안내를 위해.