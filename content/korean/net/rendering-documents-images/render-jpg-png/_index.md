---
title: 문서를 JPGPNG로 렌더링
linktitle: 문서를 JPGPNG로 렌더링
second_title: GroupDocs.Viewer .NET API
description: 향상된 사용자 경험과 생산성을 위해 GroupDocs.Viewer를 사용하여 .NET에서 문서를 JPG/PNG로 원활하게 렌더링하는 방법을 알아보세요.
weight: 10
url: /ko/net/rendering-documents-images/render-jpg-png/
---
## 소개

.NET 개발 세계에서는 문서를 효율적으로 처리하는 것이 다양한 애플리케이션에 필수적입니다. 문서 관리 시스템, 전자 상거래 플랫폼 또는 콘텐츠가 풍부한 애플리케이션을 구축하는 경우 문서를 원활하게 보는 기능은 매우 중요합니다. JPG 및 PNG와 같은 다양한 형식으로 문서를 렌더링하기 위한 포괄적인 솔루션을 제공하는 .NET용 GroupDocs.Viewer가 활용되는 곳입니다.

## 전제조건

.NET용 GroupDocs.Viewer를 사용하기 전에 확인해야 할 몇 가지 전제 조건이 있습니다.

1. .NET 개발 환경: 컴퓨터에 작동하는 .NET 개발 환경이 설정되어 있는지 확인하세요. 여기에는 .NET SDK 설치가 포함됩니다.

2. GroupDocs.Viewer 라이센스: GroupDocs.Viewer에 대한 유효한 라이센스를 얻습니다. 라이센스를 구매하거나 평가 목적으로 임시 라이센스를 사용할 수 있습니다.

3.  설치: 제공된 파일에서 .NET용 GroupDocs.Viewer를 다운로드하여 설치합니다.[다운로드 링크](https://releases.groupdocs.com/viewer/net/).

4. 문서 파일: 렌더링할 문서 파일을 준비합니다. GroupDocs.Viewer는 DOCX, PDF, PPT 등을 포함한 다양한 형식을 지원합니다.

## 네임스페이스 가져오기

.NET용 GroupDocs.Viewer를 사용하여 문서 렌더링을 시작하려면 필요한 네임스페이스를 프로젝트로 가져와야 합니다. 이를 통해 라이브러리에서 제공하는 기능에 액세스할 수 있습니다.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

.NET용 GroupDocs.Viewer를 사용하면 문서를 JPG 또는 PNG 형식으로 렌더링하는 작업이 간단해집니다. 다음은 이를 달성하는 데 도움이 되는 단계별 가이드입니다.

## 1단계: 출력 디렉터리 정의

먼저 렌더링된 페이지를 저장할 디렉터리를 정의합니다. 이 디렉터리는 존재해야 하며 애플리케이션에서 액세스할 수 있어야 합니다.

```csharp
string outputDirectory = "Your Document Directory";
```

## 2단계: 페이지 파일 경로 형식 정의

 렌더링된 각 페이지의 파일 경로 형식을 지정합니다. GroupDocs.Viewer가 대체됩니다.`{0}` 파일을 저장하는 동안 페이지 번호를 사용하세요.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```

## 3단계: 뷰어 개체 인스턴스화

 인스턴스를 생성합니다.`Viewer` 렌더링하려는 문서 파일의 경로를 제공하여 클래스를 생성합니다.

```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    // 렌더링 코드는 여기에 있습니다.
}
```

## 4단계: 렌더링 옵션 정의

요구 사항에 따라 렌더링 옵션을 지정합니다. JPG/PNG 렌더링의 경우 다음을 사용합니다.`JpgViewOptions` 또는`PngViewOptions`.

```csharp
JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
```

## 5단계: 문서 렌더링

 호출`View` 의 방법`Viewer` 개체를 만들고 이전에 만든 렌더링 옵션을 전달합니다.

```csharp
viewer.View(options);
```

## 6단계: 결과 출력

렌더링 프로세스가 완료되면 사용자에게 성공적인 렌더링에 대해 알리고 렌더링된 페이지가 저장되는 디렉터리를 제공할 수 있습니다.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론

결론적으로, .NET용 GroupDocs.Viewer는 JPG 및 PNG를 포함한 다양한 형식으로 문서를 렌더링하기 위한 강력한 솔루션을 제공합니다. 이 자습서에 설명된 단계를 따르면 문서 렌더링 기능을 .NET 애플리케이션에 원활하게 통합하여 사용자 경험과 생산성을 향상시킬 수 있습니다.

## FAQ

### Q: .NET용 GroupDocs.Viewer를 사용하여 DOCX 이외의 문서를 렌더링할 수 있습니까?

A: 예, GroupDocs.Viewer는 PDF, PPT, XLS 등을 포함한 광범위한 문서 형식을 지원합니다.

### 질문: .NET용 GroupDocs.Viewer에 대한 무료 평가판이 있습니까?

 A: 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.groupdocs.com/).

### Q: 평가 목적으로 임시 라이센스를 얻으려면 어떻게 해야 합니까?

A: 임시 라이센스를 요청할 수 있습니다.[여기](https://purchase.groupdocs.com/temporary-license/).

### 질문: .NET용 GroupDocs.Viewer에 대한 설명서는 어디에서 찾을 수 있습니까?

 A: 자세한 문서가 제공됩니다.[여기](https://tutorials.groupdocs.com/viewer/net/).

### 질문: .NET용 GroupDocs.Viewer와 관련된 지원을 받거나 질문을 할 수 있는 곳은 어디입니까?

 A: 지원 포럼을 방문할 수 있습니다.[여기](https://forum.groupdocs.com/c/viewer/9) 도움을 위해.