---
"description": "GroupDocs.Viewer for .NET을 사용하여 CAD 도면의 출력 이미지 크기를 조정하는 방법을 알아보세요. 손쉽게 가시성과 사용성을 향상시키세요."
"linktitle": "CAD 도면의 출력 이미지 크기 조정"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CAD 도면의 출력 이미지 크기 조정"
"url": "/ko/net/rendering-cad-drawings/adjust-output-image-size-cad/"
"weight": 15
type: docs
---
# CAD 도면의 출력 이미지 크기 조정

## 소개
CAD 도면은 최적의 보기 및 표현을 위해 특정 조정이 필요한 경우가 많습니다. GroupDocs.Viewer for .NET은 CAD 도면 출력을 관리하고 사용자 지정할 수 있는 강력한 도구 세트를 제공합니다. 이 튜토리얼에서는 CAD 도면의 출력 이미지 크기를 단계별로 조정하는 과정을 안내합니다.
## 필수 조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. .NET용 GroupDocs.Viewer: .NET용 GroupDocs.Viewer를 다운로드하여 설치하세요. [여기](https://releases.groupdocs.com/viewer/net/).
2. 문서 디렉토리: 문서가 있는 디렉토리를 준비하세요.
3. 기본 이해: .NET 프로그래밍의 기본 개념을 익혀보세요.

## 네임스페이스 가져오기
먼저, GroupDocs.Viewer 기능에 액세스하는 데 필요한 네임스페이스를 가져와야 합니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1단계: 출력 디렉토리 설정
CAD 도면의 출력 이미지를 저장할 디렉토리를 정의합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2단계: 페이지 파일 경로 형식 정의
페이지 파일 경로 형식을 설정합니다. 이 형식은 개별 페이지의 이름을 지정하고 HTML 파일로 저장하는 데 사용됩니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3단계: 이미지 크기 조정
Viewer 객체의 사용 블록 내부에서 적절한 옵션을 설정하여 CAD 도면의 이미지 크기를 조정합니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## 4단계: 출력 디렉토리 표시
문서를 렌더링한 후 렌더링이 성공했음을 나타내는 메시지를 표시하고 출력 디렉터리의 위치를 제공합니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
CAD 도면의 출력 이미지 크기를 조정하는 것은 가시성과 사용성을 향상시키는 데 매우 중요합니다. GroupDocs.Viewer for .NET을 사용하면 이 과정이 간소화되고 효율적이 되어 특정 요구 사항에 맞게 출력을 맞춤 설정할 수 있습니다.
## 자주 묻는 질문
### CAD 도면 외의 다른 유형의 문서에 대해서도 출력 이미지 크기를 조정할 수 있나요?
네, GroupDocs.Viewer for .NET은 다양한 문서 유형을 지원하며, 대부분 문서 형식에 대해 출력 이미지 크기를 조정할 수 있습니다.
### GroupDocs.Viewer for .NET은 다양한 버전의 .NET 프레임워크와 호환됩니까?
네, GroupDocs.Viewer for .NET은 여러 버전의 .NET 프레임워크와 호환되므로 다양한 환경에서 유연성과 유용성이 보장됩니다.
### GroupDocs.Viewer for .NET에 사용할 수 있는 라이선스 옵션이 있나요?
네, 귀하의 필요에 맞춰 임시 라이선스, 상업용 라이선스 등 다양한 라이선스 옵션을 살펴보실 수 있습니다.
### 렌더링된 문서의 출력 형식을 사용자 정의할 수 있나요?
물론입니다. GroupDocs.Viewer for .NET은 다양한 사용자 정의 옵션을 제공하여 튜토리얼에 맞게 출력 형식을 조정할 수 있습니다.
### GroupDocs.Viewer for .NET에 대한 추가 지원이나 도움말은 어디에서 찾을 수 있나요?
GroupDocs.Viewer 포럼을 방문할 수 있습니다. [여기](https://forum.groupdocs.com/c/viewer/9) 지원을 받고, 질문을 하고, 커뮤니티에 참여하세요.