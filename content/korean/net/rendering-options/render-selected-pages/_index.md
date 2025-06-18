---
"description": "Groupdocs.Viewer for .NET을 사용하여 문서에서 선택한 페이지를 렌더링하는 방법을 알아보세요. 코드 예제가 포함된 단계별 튜토리얼입니다."
"linktitle": "선택한 페이지 렌더링"
"second_title": "GroupDocs.Viewer .NET API"
"title": "선택한 페이지 렌더링"
"url": "/ko/net/rendering-options/render-selected-pages/"
"weight": 17
---

# 선택한 페이지 렌더링

## 소개

이 튜토리얼에서는 Groupdocs.Viewer for .NET을 사용하여 문서에서 선택한 페이지를 렌더링하는 방법을 자세히 살펴보겠습니다. 숙련된 개발자든 초보자든, 이 단계별 가이드를 통해 쉽게 과정을 안내해 드립니다.

## 필수 조건

시작하기에 앞서 다음과 같은 전제 조건이 충족되었는지 확인하세요.

### 1. 설치

개발 환경에 Groupdocs.Viewer for .NET이 설치되어 있는지 확인하세요. 설치되어 있지 않으면 다음에서 다운로드할 수 있습니다. [다운로드 링크](https://releases.groupdocs.com/viewer/net/).

## 네임스페이스 가져오기

C# 코드 파일에서 필요한 클래스와 메서드에 액세스하는 데 필요한 네임스페이스를 가져옵니다. 다음을 사용하여 이 작업을 수행할 수 있습니다. `using` 지령:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

이제 제공된 예제 코드를 여러 단계로 나누어 보겠습니다.

## 1단계: 출력 디렉토리 설정

렌더링된 페이지를 저장할 디렉터리를 정의합니다. 바꾸기 `"Your Document Directory"` 원하는 디렉토리 경로를 사용합니다.

```csharp
string outputDirectory = "Your Document Directory";
```

## 2단계: 페이지 파일 경로 형식 정의

렌더링된 페이지의 파일 경로 형식을 지정합니다. 이 형식은 각 페이지를 출력 디렉터리에 HTML 파일로 저장하는 데 사용됩니다.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## 3단계: 뷰어 객체 인스턴스화

렌더링하려는 문서의 경로를 인수로 전달하여 Viewer 클래스의 인스턴스를 만듭니다.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## 4단계: HTML 보기 옵션 구성

렌더링을 위한 HTML 뷰 옵션을 설정합니다. 이 예에서는 HTML 출력에 리소스를 포함하는 옵션을 구성합니다.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## 5단계: 선택한 페이지 렌더링

렌더링할 페이지 번호를 지정합니다. 이 경우 1페이지부터 3페이지까지 렌더링합니다. 그런 다음 Viewer 객체의 View 메서드를 호출하여 옵션과 페이지 번호를 인수로 전달합니다.

```csharp
viewer.View(options, 1, 3);
```

## 6단계: 결과 출력

마지막으로, 문서가 성공적으로 렌더링되었다는 메시지와 출력 파일이 저장된 위치를 표시합니다.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론

축하합니다! Groupdocs.Viewer for .NET을 사용하여 문서에서 선택한 페이지를 렌더링하는 방법을 성공적으로 익혔습니다. 이 지식을 바탕으로 이제 문서 렌더링 기능을 .NET 애플리케이션에 손쉽게 통합할 수 있습니다.

## 자주 묻는 질문

### 질문: PDF나 이미지 등 다양한 유형의 문서에서 페이지를 렌더링할 수 있나요?

답변: 네, Groupdocs.Viewer for .NET은 PDF, Microsoft Office 문서, 이미지 파일을 포함한 다양한 문서 형식의 페이지 렌더링을 지원합니다.

### 질문: 구매하기 전에 테스트해 볼 수 있는 체험판이 있나요?

A: 예, .NET용 Groupdocs.Viewer의 무료 평가판 버전에 액세스할 수 있습니다. [웹사이트](https://releases.groupdocs.com/).

### 질문: HTML 외에 출력 형식을 사용자 정의할 수 있나요?

답변: 물론입니다. Groupdocs.Viewer for .NET은 HTML 외에도 페이지를 이미지, PDF 등으로 렌더링하는 옵션을 제공합니다.

### 질문: 테스트 목적으로 임시 라이센스를 얻으려면 어떻게 해야 합니까?

A: 임시면허는 다음에서 취득할 수 있습니다. [임시 면허 페이지](https://purchase.groupdocs.com/temporary-license/) Groupdocs 웹사이트에서.

### 질문: 문제가 생기면 어디에서 도움을 구하거나 도움을 받을 수 있나요?

A: 방문하실 수 있습니다 [Groupdocs.Viewer 포럼](https://forum.groupdocs.com/c/viewer/9) 커뮤니티와 개발자로부터 지원과 지침을 받으세요.