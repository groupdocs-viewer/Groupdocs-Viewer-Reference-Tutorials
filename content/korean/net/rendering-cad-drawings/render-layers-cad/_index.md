---
title: CAD 도면의 레이어 렌더링
linktitle: CAD 도면의 레이어 렌더링
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 .NET 응용 프로그램에서 CAD 도면을 원활하게 렌더링합니다. 렌더링 옵션을 살펴보고 레이어를 사용자 정의하는 등의 작업을 수행해 보세요.
weight: 13
url: /ko/net/rendering-cad-drawings/render-layers-cad/
---

# CAD 도면의 레이어 렌더링

## 소개
.NET용 GroupDocs.Viewer는 개발자가 문서 렌더링 기능을 .NET 응용 프로그램에 원활하게 통합할 수 있게 해주는 강력한 도구입니다. CAD 도면, PDF, Microsoft Office 문서 등을 렌더링해야 하는 경우 GroupDocs.Viewer는 포괄적인 솔루션을 제공합니다.
## 전제조건
.NET용 GroupDocs.Viewer를 사용하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- C# 프로그래밍 언어에 대한 기본 이해.
- .NET 개발 환경이 컴퓨터에 설정되었습니다.
-  .NET용 GroupDocs.Viewer가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.groupdocs.com/viewer/net/).
-  참조용으로 .NET용 GroupDocs.Viewer 문서에 액세스할 수 있습니다.[여기](https://tutorials.groupdocs.com/viewer/net/).

## 네임스페이스 가져오기
.NET용 GroupDocs.Viewer 사용을 시작하려면 프로젝트에 필요한 네임스페이스를 가져와야 합니다. 다음과 같이하세요:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

제공된 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 출력 디렉터리 정의
```csharp
string outputDirectory = "Your Document Directory";
```
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3단계: 뷰어 개체 초기화
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    // 코드 블록이 계속됩니다...
}
```
## 4단계: HTML 보기 옵션 설정
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## 5단계: CAD 레이어 정의
```csharp
options.CadOptions.Layers = new List<Layer>
{
    new Layer("QUADRANT")
};
```
## 6단계: 문서 렌더링
```csharp
viewer.View(options);
```
## 7단계: 렌더링된 문서 위치 출력
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
.NET용 GroupDocs.Viewer를 사용하면 .NET 응용 프로그램에서 CAD 도면을 렌더링하는 과정이 원활해집니다. 이 가이드에 설명된 단계를 따르면 문서 렌더링 기능을 프로젝트에 쉽게 통합할 수 있습니다.
## FAQ
### GroupDocs.Viewer는 모든 유형의 CAD 도면과 호환됩니까?
예, GroupDocs.Viewer는 DWG 및 DXF를 포함한 광범위한 CAD 도면 형식의 렌더링을 지원합니다.
### CAD 도면의 렌더링 옵션을 사용자 정의할 수 있습니까?
물론 GroupDocs.Viewer는 렌더링할 레이어를 지정하거나 출력 형식을 설정하는 등 다양한 사용자 정의 옵션을 제공합니다.
### GroupDocs.Viewer에서 문서를 렌더링하려면 인터넷 연결이 필요합니까?
아니요, GroupDocs.Viewer는 인터넷 연결 없이 로컬로 렌더링을 수행합니다.
### .NET용 GroupDocs.Viewer에 대한 무료 평가판이 있습니까?
 예, .NET용 GroupDocs.Viewer 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.groupdocs.com/).
### .NET용 GroupDocs.Viewer에 대한 지원은 어디서 받을 수 있나요?
 기술 지원이나 문의 사항이 있는 경우 GroupDocs.Viewer 포럼을 방문하세요.[여기](https://forum.groupdocs.com/c/viewer/9).