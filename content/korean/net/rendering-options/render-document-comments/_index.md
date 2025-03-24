---
title: 주석이 포함된 문서 렌더링
linktitle: 주석이 포함된 문서 렌더링
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 주석이 포함된 문서를 렌더링하는 방법을 알아보세요. 원활한 통합을 위한 단계별 가이드를 따르세요.
weight: 13
url: /ko/net/rendering-options/render-document-comments/
---
## 소개
.NET용 GroupDocs.Viewer는 개발자가 문서 렌더링 기능을 .NET 응용 프로그램에 원활하게 통합할 수 있게 해주는 강력한 라이브러리입니다. Word 문서, Excel 스프레드시트, PowerPoint 프리젠테이션, PDF 파일 또는 기타 형식을 표시해야 하는 경우 GroupDocs.Viewer는 간단한 솔루션을 제공합니다.
이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 주석이 포함된 문서를 렌더링하는 방법에 중점을 둡니다. 전제 조건, 네임스페이스 가져오기를 안내하고 주석이 포함된 문서를 렌더링하는 단계별 가이드를 제공하여 각 개념을 철저하게 이해할 수 있도록 돕습니다.
## 전제조건
.NET용 GroupDocs.Viewer를 사용하여 주석이 포함된 문서 렌더링을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### .NET 개발 환경 설정
.NET 개발을 위한 개발 환경이 설정되어 있는지 확인하세요. Visual Studio 및 .NET SDK와 같은 호환 가능한 IDE가 컴퓨터에 설치되어 있어야 합니다.
### .NET 설치용 GroupDocs.Viewer
웹 사이트에서 .NET용 GroupDocs.Viewer를 다운로드하여 설치하거나 제공된 다운로드 링크를 사용하십시오.
[.NET용 GroupDocs.Viewer 다운로드](https://releases.groupdocs.com/viewer/net/)

## 네임스페이스 가져오기
시작하려면 필요한 네임스페이스를 .NET 프로젝트로 가져옵니다. 이러한 네임스페이스는 주석이 포함된 문서 렌더링에 필요한 클래스 및 메서드에 대한 액세스를 제공합니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 1단계: 출력 디렉터리 정의
주석이 포함된 렌더링된 문서가 저장될 출력 디렉터리를 설정합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2단계: 페이지 파일 경로 형식 정의
주석이 포함된 렌더링된 문서의 개별 페이지에 대한 파일 경로 형식을 정의합니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3단계: 뷰어 개체 인스턴스화
 인스턴스를 생성합니다.`Viewer` 클래스, 주석이 포함된 문서 경로를 매개변수로 전달합니다.
```csharp
using (Viewer viewer = new Viewer("Path to Your Document with Comments"))
{
    // 렌더링 옵션
}
```
## 4단계: 렌더링 옵션 구성
포함된 리소스 및 설명에 대한 설정을 포함하여 렌더링 옵션을 지정합니다.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.RenderComments = true;
```
## 5단계: 주석이 포함된 문서 렌더링
 호출`View` 의 방법`Viewer` 객체, 렌더링 옵션을 전달합니다.
```csharp
viewer.View(options);
```
## 6단계: 성공 메시지 표시
주석이 포함된 문서가 성공적으로 렌더링되었음을 사용자에게 알립니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 주석이 포함된 문서를 렌더링하는 프로세스를 다루었습니다. 단계별 가이드를 따르고 전제 조건을 충족하는지 확인하면 문서 렌더링 기능을 .NET 애플리케이션에 원활하게 통합할 수 있습니다.
## FAQ
### GroupDocs.Viewer는 복잡한 형식의 문서를 렌더링할 수 있습니까?
예, GroupDocs.Viewer는 표, 이미지, 글꼴 등 다양한 서식 요소가 포함된 문서 렌더링을 지원합니다.
### GroupDocs.Viewer는 다른 문서 형식과 호환됩니까?
물론, GroupDocs.Viewer는 PDF, DOCX, XLSX, PPTX 등을 포함한 광범위한 문서 형식을 렌더링할 수 있습니다.
### 특정 요구 사항에 맞게 렌더링 옵션을 사용자 정의할 수 있습니까?
예, GroupDocs.Viewer는 응용 프로그램의 필요에 따라 출력을 맞춤화할 수 있는 유연한 렌더링 옵션을 제공합니다.
### GroupDocs.Viewer는 외부 소스의 문서 렌더링을 지원합니까?
예, 로컬 파일, 스트림, URL을 포함한 다양한 소스의 문서를 렌더링할 수 있습니다.
### GroupDocs.Viewer에 사용할 수 있는 평가판이 있습니까?
예, GroupDocs.Viewer 무료 평가판을 시작하여 기능을 살펴볼 수 있습니다.