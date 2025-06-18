---
"description": "GroupDocs.Viewer for .NET을 사용하여 문서를 로드할 때 파일 형식을 지정하는 방법을 알아보세요. .NET 애플리케이션에서 다양한 형식을 정확하게 렌더링할 수 있습니다."
"linktitle": "문서를 로드할 때 파일 유형 지정"
"second_title": "GroupDocs.Viewer .NET API"
"title": "문서를 로드할 때 파일 유형 지정"
"url": "/ko/net/advanced-loading/specify-file-type/"
"weight": 10
---

# 문서를 로드할 때 파일 유형 지정

## 소개
GroupDocs.Viewer for .NET은 DOCX, PDF, PPTX 등 다양한 파일 형식을 지원하는 다재다능한 문서 렌더링 API입니다. 문서를 로드할 때 파일 형식을 지정하면 사용자에게 정확한 렌더링과 원활한 보기 환경을 제공할 수 있습니다.

![.NET용 GroupDocs.Viewer에서 문서를 로드할 때 파일 유형 지정](/viewer/advanced-loading/specify-file-type-when-loading-documents-img.png)

## 필수 조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- C# 및 .NET 프레임워크에 대한 기본 지식.
- 시스템에 Visual Studio가 설치되어 있어야 합니다.
- 프로젝트에 .NET용 GroupDocs.Viewer가 설치되어 있습니다. 다음에서 다운로드할 수 있습니다. [여기](https://releases.groupdocs.com/viewer/net/).
##
## 네임스페이스 가져오기
먼저, 필요한 네임스페이스를 C# 코드로 가져와야 합니다. 이 네임스페이스는 문서 렌더링에 필요한 클래스와 메서드에 대한 액세스를 제공합니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1단계: 출력 디렉토리 설정
렌더링된 문서 페이지를 저장할 디렉토리를 정의합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2단계: 페이지 파일 경로 형식 정의
문서의 각 페이지에 대한 출력 HTML 파일의 이름을 지정하는 형식을 지정합니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3단계: 로드 옵션 지정
인스턴스를 생성합니다 `LoadOptions` 클래스를 선택하고 원하는 파일 유형을 설정합니다.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## 4단계: 문서 로드 및 렌더링
사용하세요 `Viewer` 문서를 로드하고 HTML 형식으로 렌더링하는 클래스입니다.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## 5단계: 성공 메시지 표시
문서가 성공적으로 렌더링되었음을 사용자에게 알리고 출력 파일의 위치를 지정합니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
이 튜토리얼에서는 GroupDocs.Viewer for .NET을 사용하여 문서를 로드할 때 파일 형식을 지정하는 방법을 알아보았습니다. 이 간단한 단계를 따르면 .NET 애플리케이션에서 다양한 문서 형식을 정확하게 렌더링할 수 있습니다.
## 자주 묻는 질문
### GroupDocs.Viewer for .NET을 사용하여 DOCX 이외의 문서를 렌더링할 수 있나요?
네, GroupDocs.Viewer는 PDF, PPTX, XLSX 등 다양한 파일 형식을 지원합니다.
### GroupDocs.Viewer for .NET은 .NET Core와 호환됩니까?
네, GroupDocs.Viewer for .NET은 .NET Framework와 .NET Core 모두와 호환됩니다.
### GroupDocs.Viewer에서 생성된 출력 HTML 파일을 사용자 정의할 수 있나요?
네, API가 제공하는 다양한 옵션을 사용하여 HTML 출력을 사용자 정의할 수 있습니다.
### .NET용 GroupDocs.Viewer에 외부 종속성이 필요합니까?
아니요, .NET용 GroupDocs.Viewer는 독립 실행형 라이브러리이므로 외부 종속성이 필요하지 않습니다.
### GroupDocs.Viewer for .NET의 평가판이 있나요?
네, 무료 평가판을 다운로드할 수 있습니다. [여기](https://releases.groupdocs.com/viewer/net/).