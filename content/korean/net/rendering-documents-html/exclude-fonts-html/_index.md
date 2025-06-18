---
"description": "GroupDocs.Viewer for .NET을 사용하여 렌더링된 HTML에서 글꼴을 제외하는 방법을 알아보세요. 문서를 원활하게 표시하려면 이 단계별 가이드를 따르세요."
"linktitle": "렌더링된 HTML에서 글꼴 제외"
"second_title": "GroupDocs.Viewer .NET API"
"title": "렌더링된 HTML에서 글꼴 제외"
"url": "/ko/net/rendering-documents-html/exclude-fonts-html/"
"weight": 10
---

# 렌더링된 HTML에서 글꼴 제외

## 소개
GroupDocs.Viewer for .NET은 개발자가 외부 종속성 없이 .NET 애플리케이션에서 50개 이상의 문서 형식을 표시할 수 있도록 해주는 강력한 문서 렌더링 라이브러리입니다. 이 튜토리얼에서는 GroupDocs.Viewer의 특정 기능인 렌더링된 HTML 출력에서 글꼴을 제외하는 기능을 중점적으로 살펴보겠습니다. 
## 필수 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. C# 및 .NET 개발에 대한 기본적인 이해.
2. .NET용 GroupDocs.Viewer가 설치되어 있습니다. 다음에서 다운로드할 수 있습니다. [여기](https://releases.groupdocs.com/viewer/net/).
3. C# 개발을 위한 Visual Studio나 다른 IDE.

## 네임스페이스 가져오기
C# 코드에서 필요한 네임스페이스를 포함해야 합니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 1단계: 출력 디렉토리 정의
렌더링된 HTML 파일을 저장할 디렉토리를 설정합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2단계: 페이지 파일 경로 형식 정의
렌더링된 문서의 개별 페이지에 대한 파일 경로 형식을 지정합니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3단계: 뷰어 객체 초기화
렌더링하려는 문서로 Viewer 객체를 인스턴스화합니다.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // 여기에 코드를 입력하세요
}
```
## 4단계: HTML 보기 옵션 설정
내장된 리소스와 제외할 글꼴의 형식을 포함하여 HTML 렌더링에 대한 옵션을 정의합니다.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## 5단계: 문서 렌더링
문서를 렌더링하려면 HTML 보기 옵션을 Viewer 개체에 전달합니다.
```csharp
viewer.View(options);
```
## 6단계: 렌더링된 문서 위치 출력
렌더링된 HTML 파일이 저장된 위치를 사용자에게 알려줍니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
이 튜토리얼에서는 GroupDocs.Viewer for .NET을 사용하여 렌더링된 HTML 출력에서 글꼴을 제외하는 방법을 알아보았습니다. 위에 설명된 단계를 따라 특정 요구 사항에 맞게 렌더링 프로세스를 사용자 지정하여 애플리케이션에서 문서가 최적으로 표시되도록 할 수 있습니다.
## 자주 묻는 질문
### 렌더링된 HTML에서 여러 개의 글꼴을 제외할 수 있나요?
네, 여러 개의 글꼴 이름을 추가할 수 있습니다. `FontsToExclude` HTML 보기 옵션 목록입니다.
### GroupDocs.Viewer는 모든 .NET 프레임워크와 호환됩니까?
네, GroupDocs.Viewer는 .NET Framework 4.6.1 이상을 지원합니다.
### 원격 저장 위치에서 문서를 렌더링할 수 있나요?
네, GroupDocs.Viewer는 로컬 저장소뿐만 아니라 원격 저장소 위치 및 스트림의 문서 렌더링도 지원합니다.
### GroupDocs.Viewer는 HTML 출력에 대한 반응형 디자인을 지원합니까?
네, HTML 보기 옵션을 적절히 조정하여 반응형 렌더링을 활성화할 수 있습니다.
### GroupDocs.Viewer에 대한 기술 지원을 받을 수 있나요?
네, 도움을 요청하고 토론에 참여할 수 있습니다. [GroupDocs.Viewer 포럼](https://forum.groupdocs.com/c/viewer/9).