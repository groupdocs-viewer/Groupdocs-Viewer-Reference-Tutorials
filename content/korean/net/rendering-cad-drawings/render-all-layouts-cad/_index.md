---
title: CAD 도면의 모든 레이아웃 렌더링
linktitle: CAD 도면의 모든 레이아웃 렌더링
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 CAD 도면의 모든 레이아웃을 렌더링하는 방법을 알아보세요. 원활한 통합을 위해 포괄적인 튜토리얼을 따르십시오.
weight: 11
url: /ko/net/rendering-cad-drawings/render-all-layouts-cad/
---

# CAD 도면의 모든 레이아웃 렌더링

## 소개
문서 관리 및 시각화 영역에서 .NET용 GroupDocs.Viewer는 개발자가 .NET 응용 프로그램 내에서 다양한 문서 유형을 쉽게 렌더링할 수 있도록 지원하는 다목적 솔루션으로 우뚝 서 있습니다. 수많은 기능 중에는 복잡한 레이아웃을 포함하여 CAD 도면을 효율적으로 렌더링하는 기능이 있습니다. 이 튜토리얼에서는 .NET용 GroupDocs.Viewer를 활용하여 CAD 도면에 있는 모든 레이아웃을 렌더링하는 프로세스를 자세히 살펴보겠습니다. 
## 전제조건
이 튜토리얼을 시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. .NET 개발에 대한 기본 이해: .NET 개발 기본 사항에 익숙하면 이 자습서에 설명된 구현 단계를 이해하는 데 도움이 됩니다.
2.  .NET용 GroupDocs.Viewer 설치: .NET용 GroupDocs.Viewer 라이브러리를 설치했는지 확인하십시오. 다음에서 다운로드할 수 있습니다.[웹사이트](https://releases.groupdocs.com/viewer/net/).
3. CAD 도면 파일: 렌더링하려는 CAD 도면 파일을 얻습니다. 여기에는 여러 레이아웃이 있는 DWG 파일이 포함될 수 있습니다.
4. 개발 환경: 필요한 도구와 종속성을 사용하여 선호하는 개발 환경을 설정합니다.

## 네임스페이스 가져오기
먼저 필요한 네임스페이스를 .NET 프로젝트로 가져왔는지 확인하세요. 이러한 네임스페이스는 GroupDocs.Viewer를 사용하여 CAD 도면을 렌더링하는 데 필요한 기능에 대한 액세스를 제공합니다.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 2단계: System.IO 네임스페이스 가져오기
```csharp
using System.IO;
```
## 1단계: 출력 디렉터리 지정
```csharp
string outputDirectory = "Your Document Directory";
```
렌더링된 출력을 저장할 디렉터리를 정의합니다.
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
렌더링된 페이지의 파일 경로 형식을 설정합니다. 이 경우 페이지는 HTML 파일로 저장됩니다.
## 3단계: 뷰어 개체 인스턴스화
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
CAD 드로잉 파일의 경로를 매개변수로 전달하여 Viewer 클래스의 인스턴스를 만듭니다.
## 4단계: HTML 보기 옵션 구성
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.CadOptions.RenderLayouts = true;
```
CAD 도면에 대해 레이아웃을 렌더링하도록 지정하여 HTML 보기 옵션을 구성합니다.
## 5단계: CAD 도면 렌더링
```csharp
viewer.View(options);
```
CAD 도면을 렌더링하기 위해 구성된 옵션을 전달하여 뷰어 개체의 View 메서드를 호출합니다.
## 6단계: 출력 디렉터리 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
성공적인 렌더링과 출력 디렉터리의 위치를 사용자에게 알립니다.

## 결론
이 자습서에서는 .NET용 GroupDocs.Viewer를 활용하여 CAD 도면에 있는 모든 레이아웃을 렌더링하는 방법을 살펴보았습니다. 단계별 가이드를 따르고 제공된 코드 조각을 구현하면 이 기능을 .NET 애플리케이션에 원활하게 통합하여 문서 시각화 기능을 향상시킬 수 있습니다.
## FAQ
### GroupDocs.Viewer는 다양한 CAD 형식과 호환됩니까?
예, GroupDocs.Viewer는 DWG 및 DXF와 같은 형식의 CAD 도면 렌더링을 지원합니다.
### 내 응용 프로그램의 요구 사항에 따라 렌더링 출력을 사용자 정의할 수 있습니까?
물론, GroupDocs.Viewer는 이미지 품질, 페이지 크기 등을 포함하여 렌더링 출력을 사용자 정의하기 위한 다양한 옵션을 제공합니다.
### GroupDocs.Viewer를 상업적으로 사용하려면 추가 라이센스가 필요합니까?
예, 상업적인 용도로 사용하려면 라이센스를 취득해야 할 수도 있습니다. 테스트 목적으로 임시 라이센스를 얻거나 웹사이트에서 상업용 라이센스를 구입할 수 있습니다.
### GroupDocs.Viewer를 사용하여 CAD 도면을 비동기적으로 렌더링할 수 있습니까?
예, GroupDocs.Viewer는 비동기 렌더링 기능을 제공하므로 메인 스레드를 차단하지 않고도 대규모 CAD 도면을 효율적으로 처리할 수 있습니다.
### GroupDocs.Viewer는 문제 해결 및 기술 지원을 제공합니까?
 물론, 접근 가능한 GroupDocs.Viewer 커뮤니티 포럼에서 지원과 도움을 구할 수 있습니다.[여기](https://forum.groupdocs.com/c/viewer/9).