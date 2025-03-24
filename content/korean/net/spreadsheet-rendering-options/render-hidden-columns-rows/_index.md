---
title: 숨겨진 열과 행 렌더링
linktitle: 숨겨진 열과 행 렌더링
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 스프레드시트에 숨겨진 데이터를 손쉽게 잠금 해제하세요. 숨겨진 열과 행을 표시하려면 단계별 가이드를 따르세요.
weight: 13
url: /ko/net/spreadsheet-rendering-options/render-hidden-columns-rows/
---
## 소개
문서 시각화 영역에서 .NET용 GroupDocs.Viewer는 다양한 문서 형식의 원활한 렌더링을 용이하게 하는 강력한 도구로 우뚝 섰습니다. 흥미로운 기능 중 하나는 스프레드시트 내의 숨겨진 열과 행을 표시하는 기능입니다. 이 튜토리얼에서는 이 기능을 잠금 해제하고 데이터의 잠재력을 활용하는 단계를 자세히 살펴보겠습니다.
## 전제조건
이 여정을 시작하기 전에 다음과 같은 전제 조건이 갖추어져 있는지 확인하세요.
- .NET용 GroupDocs.Viewer: 최신 버전이 설치되어 있는지 확인하세요. 그렇지 않은 경우 다음에서 다운로드할 수 있습니다.[공식 웹 사이트](https://releases.groupdocs.com/viewer/net/).
- 문서 파일: 숨겨진 열과 행을 실험하기 위해 스프레드시트 형식(예: SAMPLE.XLSX)으로 샘플 문서를 준비합니다.
- 개발 환경: Visual Studio 또는 .NET 개발에 적합한 기타 IDE를 사용하여 작업 환경을 설정합니다.
## 네임스페이스 가져오기
.NET 프로젝트에서 GroupDocs.Viewer 기능을 효과적으로 활용하려면 필요한 네임스페이스를 가져옵니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1단계: 출력 디렉터리 설정
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
렌더링된 HTML 페이지가 저장될 출력 디렉터리를 정의합니다. 이에 따라 파일 경로 형식을 조정하십시오.
## 2단계: 뷰어 초기화 및 옵션 구성
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
```
스프레드시트 문서의 경로를 제공하여 뷰어 인스턴스를 만듭니다. 리소스를 포함하고 숨겨진 열과 행의 렌더링을 활성화하도록 HTML 보기 옵션을 구성합니다.
## 3단계: 렌더링 프로세스 실행
```csharp
    viewer.View(options);
}
```
구성된 옵션을 전달하여 뷰어 개체에서 View 메서드를 호출합니다. 그러면 렌더링 프로세스가 시작됩니다.
## 4단계: 출력 확인
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
소스 문서가 성공적으로 렌더링되었는지 확인하고 지정된 디렉터리에서 출력을 찾습니다.
## 결론
.NET용 GroupDocs.Viewer를 사용하면 스프레드시트의 숨겨진 열과 행을 쉽게 잠금 해제할 수 있습니다. 이 튜토리얼은 숨겨진 데이터를 공개하는 필수 단계를 제공하여 문서에 대한 보다 포괄적인 보기를 제공합니다.
## 자주 묻는 질문
### 스프레드시트 외에 다른 문서 형식의 숨겨진 열과 행을 렌더링할 수 있나요?
예, GroupDocs.Viewer는 스프레드시트 외에도 Word, PDF, PowerPoint를 포함한 다양한 문서 형식을 지원합니다.
### 렌더링할 수 있는 숨겨진 열과 행의 수에 제한이 있나요?
GroupDocs.Viewer는 다양한 숨겨진 열과 행에 대한 렌더링을 효율적으로 처리합니다. 그러나 엄청난 양의 숨겨진 데이터가 포함된 극단적인 경우에는 성능에 영향을 미칠 수 있습니다.
### 렌더링된 데이터의 출력 형식을 사용자 정의할 수 있나요?
전적으로! GroupDocs.Viewer는 출력을 사용자 정의할 수 있는 유연한 옵션을 제공하므로 렌더링된 데이터를 특정 요구 사항에 맞게 조정할 수 있습니다.
### GroupDocs.Viewer 사용에 대한 라이센스 고려 사항이 있습니까?
 예, 사용에 적합한 라이센스가 있는지 확인하십시오. 다음에서 라이선스 옵션을 살펴보세요.[GroupDocs 구매](https://purchase.groupdocs.com/buy) 또는[임시 면허증](https://purchase.groupdocs.com/temporary-license/) 시험용.
### 어디서 도움을 구하거나 GroupDocs 커뮤니티에 연결하여 지원을 받을 수 있나요?
 방문하다[GroupDocs.Viewer 포럼](https://forum.groupdocs.com/c/viewer/9) 지원, 토론 및 커뮤니티 상호 작용을 위해.