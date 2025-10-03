---
"description": "GroupDocs.Viewer for .NET을 사용하여 SVG 및 SVGZ 이미지를 렌더링하는 방법을 알아보세요. 벡터 그래픽을 HTML, JPG, PNG, PDF로 손쉽게 변환할 수 있습니다."
"linktitle": "SVG 및 SVGZ 이미지 렌더링"
"second_title": "GroupDocs.Viewer .NET API"
"title": "SVG 및 SVGZ 이미지 렌더링"
"url": "/ko/net/image-rendering/render-svg-svgz-images/"
"weight": 16
type: docs
---
# SVG 및 SVGZ 이미지 렌더링

## 소개
이 튜토리얼에서는 GroupDocs.Viewer for .NET을 사용하여 SVG 및 SVGZ 이미지를 렌더링하는 과정을 안내합니다. GroupDocs.Viewer for .NET은 개발자가 .NET 애플리케이션에서 다양한 문서 형식을 렌더링할 수 있도록 지원하는 강력한 문서 렌더링 API입니다. SVG와 SVGZ는 벡터 그래픽에 널리 사용되는 이미지 형식이며, GroupDocs.Viewer for .NET을 사용하면 HTML, JPG, PNG, PDF 등 다양한 출력 형식으로 쉽게 렌더링할 수 있습니다.

![GroupDocs.Viewer for .NET을 사용하여 SVG 및 SVGZ 이미지 렌더링](/viewer/image-rendering/render-svg-and-svgz-images.png)

## 필수 조건
시작하기 전에 다음 필수 구성 요소가 설치되고 설정되어 있는지 확인하세요.
1. .NET용 GroupDocs.Viewer: .NET용 GroupDocs.Viewer를 다운로드하여 설치하세요. [여기](https://releases.groupdocs.com/viewer/net/).
2. 개발 환경: Visual Studio와 같은 .NET 개발을 위한 개발 환경이 있는지 확인하세요.
3. 샘플 SVGZ 파일: 테스트용으로 샘플 SVGZ 파일을 준비하세요.

## 네임스페이스 가져오기
코드를 살펴보기 전에 필요한 네임스페이스를 가져와 보겠습니다.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1단계: SVGZ를 HTML로 렌더링
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## 2단계: SVGZ를 JPG로 렌더링
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## 3단계: SVGZ를 PNG로 렌더링
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## 4단계: SVGZ를 PDF로 렌더링
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## 결론
이 튜토리얼에서는 GroupDocs.Viewer for .NET을 사용하여 SVG 및 SVGZ 이미지를 렌더링하는 방법을 알아보았습니다. 몇 가지 간단한 단계만으로 SVGZ 이미지를 HTML, JPG, PNG, PDF 등 다양한 출력 형식으로 변환하여 다양한 환경에서 접근하고 볼 수 있도록 할 수 있습니다.
## 자주 묻는 질문
### GroupDocs.Viewer는 다른 이미지 형식을 렌더링할 수 있나요?
네, GroupDocs.Viewer는 PNG, JPEG, BMP, TIFF, GIF 등 다양한 이미지 형식 렌더링을 지원합니다.
### GroupDocs.Viewer는 .NET Core와 호환됩니까?
네, GroupDocs.Viewer는 .NET Framework와 .NET Core 모두와 호환됩니다.
### 렌더링 옵션을 사용자 정의할 수 있나요?
네, GroupDocs.Viewer는 광범위한 렌더링 옵션을 제공하여 요구 사항에 맞게 출력을 사용자 정의할 수 있습니다.
### GroupDocs.Viewer에 타사 종속성이 필요합니까?
아니요, GroupDocs.Viewer는 독립형 API이며 문서 렌더링을 위해 타사 종속성이 필요하지 않습니다.
### 테스트해 볼 수 있는 체험판이 있나요?
예, GroupDocs.Viewer의 무료 평가판 버전을 다운로드할 수 있습니다. [여기](https://releases.groupdocs.com/) 구매하기 전에 기능을 평가해보세요.