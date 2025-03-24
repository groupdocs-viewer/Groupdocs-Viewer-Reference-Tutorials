---
title: 이미지 크기 제한 설정
linktitle: 이미지 크기 제한 설정
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 .NET 응용 프로그램에서 이미지 크기 제한을 손쉽게 설정하여 문서 보기 환경을 향상시키는 방법을 알아보세요.
weight: 21
url: /ko/net/rendering-options/set-image-size-limits/
---
## 소개
.NET용 GroupDocs.Viewer는 .NET 응용 프로그램 내에서 문서를 원활하게 볼 수 있도록 설계된 강력한 도구입니다. 강력한 기능과 직관적인 인터페이스를 통해 개발자는 문서 보기 기능을 프로젝트에 쉽게 통합하여 사용자 경험과 생산성을 향상시킬 수 있습니다. 이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 이미지 크기 제한을 설정하여 성능과 효율성을 유지하면서 최적의 문서 표시를 보장하는 방법을 살펴보겠습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET용 GroupDocs.Viewer: 개발 환경에 필요한 .NET용 GroupDocs.Viewer 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[웹사이트](https://releases.groupdocs.com/viewer/net/).
2. 개발 환경: 필요한 구성을 사용하여 Visual Studio와 같은 선호하는 .NET 개발 환경을 설정합니다.
3. 문서 디렉터리: 문서가 저장되는 디렉터리를 지정하고 애플리케이션 내에서 해당 디렉터리 경로에 액세스할 수 있는지 확인하세요.

## 네임스페이스 가져오기
구현을 진행하기 전에 .NET용 GroupDocs.Viewer의 기능에 효과적으로 액세스하려면 필수 네임스페이스를 가져와야 합니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1단계: 출력 디렉터리 및 파일 경로 정의
```csharp
string outputDirectory = "Your Document Directory";
string outputFile = Path.Combine(outputDirectory, "result_image_size_limit.jpg");
```
 반드시 교체하세요`"Your Document Directory"` 문서 디렉토리의 실제 경로를 사용하십시오.
## 2단계: 뷰어 개체 초기화 및 문서 경로 지정
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // TestFiles.SAMPLE_DOCX는 샘플 문서의 경로를 나타냅니다.
    // 원하는 문서의 경로로 바꾸세요.
```
 바꾸다`TestFiles.SAMPLE_DOCX` 문서의 경로와 함께. DOCX, PDF 또는 기타 지원되는 파일 형식일 수 있습니다.
## 3단계: JPEG 보기 옵션 구성
```csharp
JpgViewOptions options = new JpgViewOptions(outputFile);
options.MaxWidth = 400;
```
 조정하다`MaxWidth` 요구 사항에 따라 렌더링된 이미지의 최대 너비를 설정하는 속성입니다. 이렇게 하면 이미지가 지정된 너비를 초과하지 않고 최적의 디스플레이가 유지됩니다.
## 4단계: 지정된 옵션으로 문서 렌더링
```csharp
viewer.View(options);
```
이 코드 줄은 렌더링 프로세스를 트리거하여 정의된 크기 제한으로 출력 이미지를 생성합니다.
## 5단계: 성공 메시지 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
렌더링이 성공적으로 완료되면 출력 디렉터리 경로와 함께 성공적인 완료를 나타내는 메시지가 표시됩니다.

## 결론
결론적으로, .NET용 GroupDocs.Viewer를 사용하여 이미지 크기 제한을 설정하는 기술을 익히면 .NET 응용 프로그램 내에서 문서 보기 환경을 크게 향상시킬 수 있습니다. 이 튜토리얼에 설명된 단계별 가이드를 따르면 성능과 효율성을 보장하면서 이미지 표시를 쉽게 최적화할 수 있습니다.
## FAQ
### 렌더링된 이미지의 최대 너비와 높이를 모두 설정할 수 있습니까?
예, 보기 옵션에서 적절한 속성을 사용하여 최대 너비와 높이를 모두 설정할 수 있습니다.
### .NET용 GroupDocs.Viewer는 어떤 문서 형식을 지원합니까?
.NET용 GroupDocs.Viewer는 DOCX, PDF, PPT, XLS 등을 포함한 광범위한 문서 형식을 지원합니다.
### .NET용 GroupDocs.Viewer는 .NET Core와 호환됩니까?
예, .NET용 GroupDocs.Viewer는 .NET Core와의 호환성을 제공하므로 최신 .NET 응용 프로그램에 원활하게 통합될 수 있습니다.
### JPEG 이외의 출력 이미지 형식을 사용자 정의할 수 있나요?
예, .NET용 GroupDocs.Viewer는 PNG, TIFF 및 PDF를 포함한 다양한 출력 형식을 지원합니다.
### 구매하기 전에 테스트할 수 있는 평가판이 있나요?
 예, 다음 사이트에서 무료 평가판을 이용하실 수 있습니다.[웹사이트](https://releases.groupdocs.com/viewer/net/). 구매하기 전에 .NET용 GroupDocs.Viewer의 기능을 살펴보세요.