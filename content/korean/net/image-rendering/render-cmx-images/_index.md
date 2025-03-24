---
title: CMX 이미지 렌더링
linktitle: CMX 이미지 렌더링
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 CMX 이미지를 다양한 형식으로 손쉽게 렌더링하는 방법을 알아보세요. 문서 관리를 강화하세요.
weight: 13
url: /ko/net/image-rendering/render-cmx-images/
---

# CMX 이미지 렌더링

## 소개
문서 관리 및 조작 영역에서 다양한 형식의 이미지를 렌더링하는 것은 중요한 작업입니다. .NET용 GroupDocs.Viewer는 CMX 이미지를 HTML, JPG, PNG 및 PDF와 같은 다양한 형식으로 렌더링하기 위한 포괄적인 기능을 제공하여 이 프로세스를 단순화합니다. 이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 CMX 이미지를 렌더링하는 단계별 프로세스를 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET 라이브러리용 GroupDocs.Viewer: 다음에서 .NET 라이브러리용 GroupDocs.Viewer를 다운로드하고 설치합니다.[여기](https://releases.groupdocs.com/viewer/net/).
2. 개발 환경: .NET 프레임워크를 사용하여 작업 개발 환경을 설정합니다.
3. CMX 이미지 파일: 렌더링하려는 CMX 이미지 파일을 얻습니다.

## 네임스페이스 가져오기
계속하기 전에 .NET 응용 프로그램에서 GroupDocs.Viewer 기능에 액세스하는 데 필요한 네임스페이스를 가져와야 합니다.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## HTML로 렌더링
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- 출력 디렉터리 정의: 렌더링된 HTML 파일을 저장할 디렉터리를 설정합니다.
- 파일 경로 형식 지정: 출력 HTML 파일의 형식을 정의합니다.
- 뷰어 개체 인스턴스화: CMX 이미지 파일을 사용하여 뷰어 클래스의 인스턴스를 만듭니다.
- HTML 렌더링 옵션: 리소스 포함과 같은 HTML 렌더링 옵션을 구성합니다.
- CMX를 HTML로 렌더링: 뷰어 개체의 View 메서드를 호출하여 CMX 이미지를 HTML로 렌더링합니다.
## JPG로 렌더링
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- 출력 디렉터리 정의: 렌더링된 JPG 파일을 저장할 디렉터리를 설정합니다.
- 파일 경로 형식 지정: 출력 JPG 파일의 형식을 정의합니다.
- 뷰어 개체 인스턴스화: CMX 이미지 파일을 사용하여 뷰어 클래스의 인스턴스를 만듭니다.
- JPG 렌더링 옵션: JPG 렌더링 옵션을 구성합니다.
- CMX를 JPG로 렌더링: 뷰어 개체의 View 메서드를 호출하여 CMX 이미지를 JPG로 렌더링합니다.
## PNG로 렌더링
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- 출력 디렉터리 정의: 렌더링된 PNG 파일을 저장할 디렉터리를 설정합니다.
- 파일 경로 형식 지정: 출력 PNG 파일의 형식을 정의합니다.
- 뷰어 개체 인스턴스화: CMX 이미지 파일을 사용하여 뷰어 클래스의 인스턴스를 만듭니다.
- PNG 렌더링 옵션: PNG 렌더링 옵션을 구성합니다.
- CMX를 PNG로 렌더링: 뷰어 개체의 View 메서드를 호출하여 CMX 이미지를 PNG로 렌더링합니다.
## PDF로 렌더링
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- 출력 디렉터리 정의: 렌더링된 PDF 파일을 저장할 디렉터리를 설정합니다.
- 파일 경로 형식 지정: 출력 PDF 파일의 형식을 정의합니다.
- 뷰어 개체 인스턴스화: CMX 이미지 파일을 사용하여 뷰어 클래스의 인스턴스를 만듭니다.
- PDF 렌더링 옵션: PDF 렌더링 옵션을 구성합니다.
- CMX를 PDF로 렌더링: 뷰어 개체의 View 메서드를 호출하여 CMX 이미지를 PDF로 렌더링합니다.

## 결론
결론적으로 .NET용 GroupDocs.Viewer는 CMX 이미지를 다양한 형식으로 원활하게 렌더링하기 위한 강력한 솔루션을 제공합니다. 이 튜토리얼에 설명된 단계를 따르면 CMX 이미지 렌더링 기능을 .NET 애플리케이션에 쉽게 통합하여 문서 관리 효율성을 높일 수 있습니다.
## FAQ
### CMX 이미지의 특정 페이지를 렌더링할 수 있나요?
예, 렌더링 옵션에서 페이지 번호를 지정하여 특정 페이지를 렌더링할 수 있습니다.
### .NET용 GroupDocs.Viewer는 모든 .NET 프레임워크와 호환됩니까?
예, .NET용 GroupDocs.Viewer는 .NET Core 및 .NET Framework를 포함한 여러 .NET 프레임워크와 호환됩니다.
### GroupDocs.Viewer는 암호화된 CMX 이미지 렌더링을 지원합니까?
예, GroupDocs.Viewer는 적절한 암호 해독 키를 사용하여 암호화된 CMX 이미지 렌더링을 지원합니다.
### 다양한 출력 형식에 대한 렌더링 옵션을 사용자 정의할 수 있습니까?
물론, GroupDocs.Viewer는 요구 사항에 따라 렌더링 매개 변수를 사용자 정의할 수 있는 광범위한 옵션을 제공합니다.
### GroupDocs.Viewer 지원을 위한 커뮤니티 포럼이 있습니까?
 예, 지원 포럼에서 GroupDocs.Viewer 커뮤니티에 도움을 요청하고 참여할 수 있습니다.[여기](https://forum.groupdocs.com/c/viewer/9).