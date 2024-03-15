---
title: 스트림에서 문서 로드
linktitle: 스트림에서 문서 로드
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 스트림에서 문서를 원활하게 로드하는 방법을 알아보세요. 강력한 문서 보기 기능으로 .NET 애플리케이션을 강화하세요.
type: docs
weight: 12
url: /ko/net/loading-documents/loading-document-stream/
---
## 소개
.NET 개발 영역에서는 문서를 효율적으로 관리하고 보는 것이 가장 중요합니다. 고급 도구와 라이브러리의 출현으로 한때 어렵게 보였던 작업이 이제는 단순화되었습니다. 이러한 도구 중에서 .NET용 GroupDocs.Viewer는 다양한 문서 형식을 원활하게 처리할 수 있는 다목적 솔루션으로 돋보입니다. 이 포괄적인 가이드에서는 .NET용 GroupDocs.Viewer를 사용하여 스트림에서 문서를 로드하는 복잡한 과정을 자세히 살펴봅니다. 숙련된 개발자이든 이제 막 시작하는 개발자이든 이 튜토리얼을 통해 GroupDocs.Viewer의 기능을 효과적으로 활용하는 데 필요한 지식을 얻을 수 있습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. C# 및 .NET Framework에 대한 기본 이해: C# 프로그래밍 언어 및 .NET Framework에 익숙하면 논의된 개념을 이해하는 데 도움이 됩니다.
   
2.  .NET용 GroupDocs.Viewer 설치: 다음에서 .NET용 GroupDocs.Viewer를 다운로드하여 설치합니다.[웹사이트](https://releases.groupdocs.com/viewer/net/).
3. IDE: 코딩 및 테스트를 위해 Visual Studio와 같은 IDE(통합 개발 환경)가 설치되어 있습니다.
4. 문서 스트림: 로드할 문서 스트림을 준비합니다. 이는 파일 스트림이거나 기타 호환 가능한 스트림 소스일 수 있습니다.

## 네임스페이스 가져오기
스트림에서 문서를 로드하는 코드를 구현하기 전에 필요한 네임스페이스를 가져와야 합니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1단계: 출력 디렉터리 정의
```csharp
string outputDirectory = "Your Document Directory";
```
렌더링된 문서가 저장될 디렉터리 경로를 설정합니다.
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
각 페이지의 파일 경로 형식을 정의합니다. 여기서 "{0}"은 페이지 번호로 대체됩니다.
## 3단계: 문서 스트림 가져오기
```csharp
Stream stream = GetFileStream();
```
원하는 소스에서 문서 스트림을 얻습니다. 이는 파일 스트림, 메모리 스트림 또는 기타 호환 가능한 스트림일 수 있습니다.
## 4단계: 뷰어를 사용하여 문서 로드
```csharp
using (Viewer viewer = new Viewer(stream)) 
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
문서 스트림을 사용하여 Viewer 클래스의 새 인스턴스를 초기화합니다. 그런 다음 HTML 보기 옵션을 구성하고 문서를 렌더링합니다.
## 5단계: 출력 디렉터리 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
문서가 성공적으로 렌더링되었음을 사용자에게 알리고 출력이 저장되는 위치를 제공합니다.

## 결론
결론적으로 .NET용 GroupDocs.Viewer는 스트림에서 문서를 쉽게 로드하고 볼 수 있는 강력한 솔루션을 제공합니다. 이 자습서에 설명된 단계를 따르면 문서 보기 기능을 .NET 애플리케이션에 원활하게 통합하여 사용자 경험과 생산성을 향상시킬 수 있습니다.
## 자주 묻는 질문
### .NET용 GroupDocs.Viewer는 다양한 문서 형식을 처리할 수 있습니까?
예, GroupDocs.Viewer는 PDF, DOCX, XLSX, PPTX 등을 포함한 광범위한 문서 형식을 지원합니다.
### .NET용 GroupDocs.Viewer는 웹 및 데스크톱 응용 프로그램 모두에 적합합니까?
전적으로! GroupDocs.Viewer는 .NET을 사용하여 개발된 웹 및 데스크톱 응용 프로그램 모두에 완벽하게 통합될 수 있습니다.
### GroupDocs.Viewer는 문서 렌더링을 위한 사용자 정의 옵션을 제공합니까?
예, 요구 사항에 따라 워터마킹, 페이지 회전, 확대/축소 수준 등 문서 렌더링의 다양한 측면을 사용자 정의할 수 있습니다.
### 상업용 프로젝트에서 .NET용 GroupDocs.Viewer를 사용할 수 있습니까?
예, GroupDocs.Viewer는 상업용 프로젝트에 적합한 라이센스 옵션을 제공합니다. 공식 라이센스를 구매하시면 됩니다.[웹사이트](https://purchase.groupdocs.com/temporary-license/).
### .NET용 GroupDocs.Viewer에 대한 기술 지원이 제공됩니까?
 예. 에서 제공하는 전용 지원 포럼에서 기술 지원과 지침을 구할 수 있습니다.[GroupDocs.뷰어](https://forum.groupdocs.com/c/viewer/9).