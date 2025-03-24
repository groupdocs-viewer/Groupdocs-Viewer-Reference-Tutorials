---
title: 렌더링된 HTML에서 글꼴 제외
linktitle: 렌더링된 HTML에서 글꼴 제외
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 렌더링된 HTML에서 글꼴을 제외하는 방법을 알아보세요. 원활한 문서 표시를 위해 이 단계별 가이드를 따르세요.
weight: 10
url: /ko/net/rendering-documents-html/exclude-fonts-html/
---
## 소개
.NET용 GroupDocs.Viewer는 개발자가 외부 종속성 없이 50개 이상의 문서 형식을 .NET 응용 프로그램에 표시할 수 있는 강력한 문서 렌더링 라이브러리입니다. 이 자습서에서는 렌더링된 HTML 출력에서 글꼴을 제외하는 GroupDocs.Viewer의 특정 기능에 중점을 둡니다. 
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. C# 및 .NET 개발에 대한 기본 이해.
2.  .NET용 GroupDocs.Viewer가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.groupdocs.com/viewer/net/).
3. C# 개발을 위한 Visual Studio 또는 기타 IDE.

## 네임스페이스 가져오기
C# 코드에 필요한 네임스페이스를 포함해야 합니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 1단계: 출력 디렉터리 정의
렌더링된 HTML 파일을 저장할 디렉터리를 설정합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2단계: 페이지 파일 경로 형식 정의
렌더링된 문서의 개별 페이지에 대한 파일 경로 형식을 지정합니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3단계: 뷰어 개체 초기화
렌더링하려는 문서로 뷰어 개체를 인스턴스화합니다.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // 귀하의 코드는 여기에 있습니다
}
```
## 4단계: HTML 보기 옵션 설정
제외할 포함된 리소스 및 글꼴의 형식을 포함하여 HTML 렌더링에 대한 옵션을 정의합니다.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## 5단계: 문서 렌더링
HTML 보기 옵션을 Viewer 개체에 전달하여 문서를 렌더링합니다.
```csharp
viewer.View(options);
```
## 6단계: 렌더링된 문서 위치 출력
렌더링된 HTML 파일이 저장되는 위치를 사용자에게 알립니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 렌더링된 HTML 출력에서 글꼴을 제외하는 방법을 배웠습니다. 위에 설명된 단계를 수행하면 특정 요구 사항에 맞게 렌더링 프로세스를 사용자 정의하여 응용 프로그램에서 문서를 최적으로 표시할 수 있습니다.
## FAQ
### 렌더링된 HTML에서 여러 글꼴을 제외할 수 있습니까?
 예, 여러 글꼴 이름을`FontsToExclude` HTML 보기 옵션에 나열됩니다.
### GroupDocs.Viewer는 모든 .NET 프레임워크와 호환됩니까?
예, GroupDocs.Viewer는 .NET Framework 4.6.1 이상을 지원합니다.
### 원격 저장 위치에서 문서를 렌더링할 수 있습니까?
예, GroupDocs.Viewer는 로컬 저장소는 물론 원격 저장소 위치 및 스트림의 문서 렌더링을 지원합니다.
### GroupDocs.Viewer는 HTML 출력에 대한 반응형 디자인을 지원합니까?
예, 그에 따라 HTML 보기 옵션을 조정하여 반응형 렌더링을 활성화할 수 있습니다.
### GroupDocs.Viewer에 대한 기술 지원이 제공됩니까?
 예, 귀하는 다음 사항에 관해 도움을 구하고 토론에 참여할 수 있습니다.[GroupDocs.Viewer 포럼](https://forum.groupdocs.com/c/viewer/9).