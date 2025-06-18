---
"description": "GroupDocs.Viewer for .NET의 마법을 경험해 보세요. 문서 보기 기능을 애플리케이션에 완벽하게 통합할 수 있습니다. 지금 무료 평가판을 사용해 보세요!"
"linktitle": "워크시트 이름 가져오기"
"second_title": "GroupDocs.Viewer .NET API"
"title": "워크시트 이름 가져오기"
"url": "/ko/net/spreadsheet-rendering-options/get-worksheets-names/"
"weight": 11
---

# 워크시트 이름 가져오기

## 소개
GroupDocs.Viewer for .NET의 매혹적인 세계에 오신 것을 환영합니다! 개발자이거나 .NET 애플리케이션에서 강력한 문서 보기 기능을 탐색하고 싶은 개발자라면 분명 만족하실 겁니다. 이 포괄적인 가이드에서는 GroupDocs.Viewer를 사용하여 워크시트 이름을 가져오는 복잡한 과정을 자세히 살펴보겠습니다. 자, 이제 안전벨트를 매고 이 흥미진진한 여정을 시작해 볼까요!
## 필수 조건
코딩의 마법에 들어가기 전에 모든 것이 설정되어 있는지 확인해 보겠습니다.
1. .NET용 GroupDocs.Viewer 설치: 다음으로 이동하세요. [다운로드 링크](https://releases.groupdocs.com/viewer/net/) GroupDocs.Viewer for .NET의 최신 버전을 다운로드하세요. 설치 지침에 따라 개발 환경에 원활하게 통합하세요.
2. 문서 준비: 지정된 문서 디렉터리에 대상 문서(예: "file.xlsx"라는 이름의 Excel 파일)가 있는지 확인하세요.
## 네임스페이스 가져오기
이제 필수 구성 요소를 갖추었으니, 필요한 네임스페이스를 가져오는 것으로 시작해 보겠습니다. 이렇게 하면 애플리케이션이 GroupDocs.Viewer for .NET에서 제공하는 기능을 인식하고 활용할 수 있습니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. 문서 디렉토리 설정
```csharp
string outputDirectory = "Your Document Directory";
```
"문서 디렉터리"를 대상 문서가 있는 디렉터리 경로로 바꾸세요.
## 2. 뷰어 초기화
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
이 단계에서는 Excel 파일의 경로를 제공하여 Viewer 클래스의 인스턴스를 생성합니다.
## 3. 보기 정보 옵션 구성
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
여기서는 ViewInfoOptions를 구성하여 HTML 뷰를 생성하고 스프레드시트 렌더링을 위한 추가 옵션을 설정합니다.
## 4. 뷰 정보 검색
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
구성된 옵션에 따라 뷰 정보를 검색하려면 Viewer 인스턴스를 활용합니다.
## 5. 워크시트 이름 표시
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
검색된 페이지를 반복하고 각 워크시트의 이름을 콘솔에 인쇄합니다.
## 결론
축하합니다! GroupDocs.Viewer for .NET을 사용하여 워크시트 이름을 가져오는 과정을 성공적으로 완료했습니다. 이를 통해 애플리케이션 내 문서 보기 기능을 향상시킬 수 있는 무궁무진한 가능성이 열립니다.
## 자주 묻는 질문
### GroupDocs.Viewer for .NET을 다른 문서 형식과 함께 사용할 수 있나요?
물론입니다! GroupDocs.Viewer는 PDF, Microsoft Office 등 다양한 문서 형식을 지원합니다.
### 무료 체험판이 있나요?
예, .NET용 GroupDocs.Viewer를 탐색할 수 있습니다. [무료 체험](https://releases.groupdocs.com/).
### 추가 지원은 어디에서 받을 수 있나요?
로 향하다 [GroupDocs.Viewer 포럼](https://forum.groupdocs.com/c/viewer/9) 지역사회의 지원과 토론을 위해.
### 임시면허를 받을 수 있나요?
물론입니다! 방문하세요 [이 링크](https://purchase.groupdocs.com/temporary-license/) 임시면허를 받으려면.
### 자세한 문서 자료를 이용할 수 있나요?
물론입니다! 확인해 보세요 [공식 문서](https://tutorials.groupdocs.com/viewer/net/) 자세한 정보와 가이드를 보려면 클릭하세요.