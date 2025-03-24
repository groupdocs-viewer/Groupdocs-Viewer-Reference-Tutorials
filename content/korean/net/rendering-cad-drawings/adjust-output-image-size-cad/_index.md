---
title: CAD 도면의 출력 이미지 크기 조정
linktitle: CAD 도면의 출력 이미지 크기 조정
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 CAD 도면의 출력 이미지 크기를 조정하는 방법을 알아보세요. 가시성과 유용성을 쉽게 향상시킬 수 있습니다.
weight: 15
url: /ko/net/rendering-cad-drawings/adjust-output-image-size-cad/
---

# CAD 도면의 출력 이미지 크기 조정

## 소개
CAD 도면은 최적의 보기 및 프리젠테이션을 위해 특정 조정이 필요한 경우가 많습니다. .NET용 GroupDocs.Viewer는 CAD 도면 출력을 관리하고 사용자 정의할 수 있는 강력한 도구 세트를 제공합니다. 이 튜토리얼에서는 CAD 도면의 출력 이미지 크기를 조정하는 과정을 단계별로 안내합니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1.  .NET용 GroupDocs.Viewer: 다음에서 .NET용 GroupDocs.Viewer를 다운로드하고 설치합니다.[여기](https://releases.groupdocs.com/viewer/net/).
2. 문서 디렉터리: 문서가 있는 디렉터리를 준비합니다.
3. 기본 이해: .NET 프로그래밍의 기본 개념을 숙지합니다.

## 네임스페이스 가져오기
먼저 GroupDocs.Viewer 기능에 액세스하는 데 필요한 네임스페이스를 가져와야 합니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1단계: 출력 디렉터리 설정
CAD 도면의 출력 이미지를 저장할 디렉토리를 정의합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2단계: 페이지 파일 경로 형식 정의
페이지 파일 경로의 형식을 설정합니다. 이 형식은 개별 페이지의 이름을 지정하고 HTML 파일로 저장하는 데 사용됩니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 3단계: 이미지 크기 조정
뷰어 개체의 using 블록 내에서 적절한 옵션을 설정하여 CAD 도면의 이미지 크기를 조정합니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## 4단계: 출력 디렉터리 표시
문서를 렌더링한 후 성공적인 렌더링을 나타내는 메시지를 표시하고 출력 디렉터리의 위치를 제공합니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
CAD 도면의 출력 이미지 크기를 조정하는 것은 가시성과 유용성을 높이는 데 중요합니다. .NET용 GroupDocs.Viewer를 사용하면 이 프로세스가 간소화되고 효율적이 되어 특정 요구 사항에 따라 출력을 사용자 정의할 수 있습니다.
## FAQ
### CAD 도면 외에 다른 유형의 문서에 대한 출력 이미지 크기를 조정할 수 있나요?
예, .NET용 GroupDocs.Viewer는 다양한 문서 유형을 지원하며 대부분의 문서 형식에 대해 출력 이미지 크기를 조정할 수 있습니다.
### .NET용 GroupDocs.Viewer는 다른 버전의 .NET Framework와 호환됩니까?
예, .NET용 GroupDocs.Viewer는 여러 버전의 .NET 프레임워크와 호환되므로 다양한 환경에서 유연성과 유용성을 보장합니다.
### .NET용 GroupDocs.Viewer에 사용할 수 있는 라이센스 옵션이 있습니까?
예. 필요에 따라 임시 라이선스, 상업용 라이선스 등 다양한 라이선스 옵션을 탐색할 수 있습니다.
### 렌더링된 문서의 출력 형식을 사용자 정의할 수 있습니까?
물론 .NET용 GroupDocs.Viewer는 다양한 사용자 정의 옵션을 제공하므로 원하는 대로 출력 형식을 조정할 수 있습니다.
### .NET용 GroupDocs.Viewer에 대한 추가 지원은 어디서 찾을 수 있나요?
 GroupDocs.Viewer 포럼을 방문할 수 있습니다.[여기](https://forum.groupdocs.com/c/viewer/9) 지원을 받고, 질문하고, 커뮤니티에 참여하세요.