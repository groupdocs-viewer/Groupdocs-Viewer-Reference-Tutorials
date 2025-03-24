---
title: PDF에서 글꼴 라이센스 확인 비활성화
linktitle: PDF에서 글꼴 라이센스 확인 비활성화
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 .NET에서 원활한 문서 보기 기능을 활용하세요. 최소한의 종속성으로 문서 렌더링을 쉽게 통합하고 사용자 정의할 수 있습니다.
weight: 12
url: /ko/net/pdf-rendering-options/disable-font-license-verifications-pdf/
---
## 소개
.NET 개발 영역에서 문서 관리 및 조작은 많은 응용 프로그램의 중요한 측면인 경우가 많습니다. PDF, Word 문서 또는 기타 파일 형식을 보든 이러한 작업을 효율적으로 처리할 수 있는 강력한 도구를 갖는 것이 필수적입니다. 이것이 .NET용 GroupDocs.Viewer가 작동하는 곳입니다. 이 강력한 라이브러리는 개발자에게 문서 보기 기능을 .NET 애플리케이션에 원활하게 통합할 수 있는 기능을 제공합니다.
## 전제조건
.NET용 GroupDocs.Viewer를 사용하기 전에 준비해야 할 몇 가지 전제 조건이 있습니다.
### 1. 비주얼 스튜디오 설치
가장 먼저 시스템에 Visual Studio가 설치되어 있는지 확인하세요. 아직 다운로드하지 않았다면 Microsoft 웹사이트에서 다운로드할 수 있습니다.
### 2. .NET용 GroupDocs.Viewer 다운로드
 다음으로 향하세요.[다운로드 링크](https://releases.groupdocs.com/viewer/net/) .NET용 GroupDocs.Viewer의 최신 버전을 얻으려면 개발 환경 내에서 설정하려면 제공된 설치 지침을 따르세요.
### 3. 임시 면허 취득
 개발 및 테스트 중에 .NET용 GroupDocs.Viewer의 잠재력을 최대한 활용하려면 임시 라이센스를 얻는 것이 좋습니다. 다음 중 하나를 요청할 수 있습니다.[여기](https://purchase.groupdocs.com/temporary-license/).

## 네임스페이스 가져오기
전제 조건을 완료하고 나면 프로젝트에서 .NET용 GroupDocs.Viewer를 활용할 준비가 된 것입니다. 필요한 네임스페이스를 코드베이스로 가져오는 것부터 시작하세요.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

보다 명확한 이해를 위해 제공된 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 출력 디렉터리 정의
렌더링된 문서 페이지를 저장할 디렉터리를 정의하는 것부터 시작하세요.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2단계: 페이지 파일 경로 형식 정의
문서의 개별 페이지에 대한 파일 경로 형식을 설정합니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
## 3단계: 뷰어 개체 초기화
보려는 문서의 경로를 전달하여 Viewer 클래스의 인스턴스를 만듭니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.OXPS_EMBEDDED_FONT))
```
## 4단계: HTML 보기 옵션 구성
문서를 HTML로 보기 위한 옵션을 정의하고 포함된 리소스(예: 이미지)의 형식을 지정합니다.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## 5단계: 글꼴 라이센스 확인 비활성화
원활한 렌더링을 보장하려면 글꼴 라이센스 확인을 비활성화하는 옵션을 활성화하십시오.
```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
## 6단계: 문서 보기
구성된 옵션을 전달하여 Viewer 개체의 View 메서드를 호출합니다.
```csharp
viewer.View(options);
```
## 7단계: 출력 디렉터리 표시
렌더링된 문서 페이지가 저장되는 위치를 사용자에게 알립니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
.NET용 GroupDocs.Viewer는 개발자에게 문서 보기 기능을 .NET 응용 프로그램에 손쉽게 통합할 수 있는 포괄적인 솔루션을 제공합니다. 이 튜토리얼에 설명된 단계를 따르면 이 강력한 라이브러리를 효과적으로 활용하여 문서 관리 작업 흐름을 향상시킬 수 있습니다.
## FAQ
### .NET용 GroupDocs.Viewer는 여러 문서 형식을 처리할 수 있습니까?
예, GroupDocs.Viewer는 PDF, Microsoft Word, Excel, PowerPoint 등을 포함한 광범위한 문서 형식을 지원합니다.
### .NET용 GroupDocs.Viewer는 웹 응용 프로그램에 적합합니까?
물론, GroupDocs.Viewer는 .NET 기술을 사용하여 개발된 데스크톱 및 웹 응용 프로그램 모두에 완벽하게 통합될 수 있습니다.
### GroupDocs.Viewer에는 추가 종속성이 필요합니까?
아니요, .NET용 GroupDocs.Viewer는 종속성이 최소화되어 기존 프로젝트에 쉽게 통합될 수 있습니다.
### 렌더링된 문서의 모양을 사용자 정의할 수 있습니까?
예, GroupDocs.Viewer는 특정 요구 사항에 맞게 렌더링된 문서의 모양과 동작을 사용자 정의할 수 있는 다양한 옵션을 제공합니다.
### .NET용 GroupDocs.Viewer에 대한 기술 지원이 제공됩니까?
 예, 다음을 통해 전담 지원팀으로부터 도움과 지침을 구할 수 있습니다.[법정](https://forum.groupdocs.com/c/viewer/9).