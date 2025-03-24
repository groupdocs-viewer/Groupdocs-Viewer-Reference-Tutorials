---
title: XML SpreadSheetML 렌더링
linktitle: XML SpreadSheetML 렌더링
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 다양한 형식의 XML SpreadSheetML 파일을 원활하게 렌더링해 보세요. 귀하의 애플리케이션에 쉽게 통합됩니다.
weight: 16
url: /ko/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/
---
## 소개
.NET용 GroupDocs.Viewer의 세계에 오신 것을 환영합니다! 이 튜토리얼에서는 강력한 .NET 라이브러리인 GroupDocs.Viewer를 사용하여 XML SpreadSheetML 파일을 쉽게 렌더링하는 과정을 안내합니다. 숙련된 개발자이든 이제 막 시작하는 개발자이든 이 단계별 가이드는 XML SpreadSheetML 렌더링을 애플리케이션에 손쉽게 통합하는 데 도움이 될 것입니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.
- .NET을 지원하는 개발 환경입니다.
-  .NET 라이브러리용 GroupDocs.Viewer가 설치되었습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.groupdocs.com/viewer/net/).
- C# 프로그래밍에 대한 기본적인 이해.
## 네임스페이스 가져오기
필요한 네임스페이스를 C# 프로젝트로 가져오는 것부터 시작하세요. 이렇게 하면 GroupDocs.Viewer에서 제공하는 기능에 액세스할 수 있습니다.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1단계: 문서 디렉토리 설정
출력이 저장될 문서 디렉터리의 경로를 정의합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
## 2단계: 출력 파일 경로 지정
HTML, JPG, PNG 및 PDF 출력 파일의 전체 경로를 설정합니다.
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## 3단계: 로드 옵션 지정
정확하게 렌더링하려면 파일 형식을 Excel 2003 XML SpreadSheetML로 명시적으로 지정하세요.
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## 4단계: 다중 페이지 HTML로 렌더링
HTML 보기 옵션을 활용하여 XML SpreadSheetML 파일을 다중 페이지 HTML 문서로 렌더링합니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## 5단계: JPG로 렌더링
지정된 옵션을 사용하여 XML SpreadSheetML 파일을 JPG 이미지로 렌더링합니다.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 6단계: PNG로 렌더링
마찬가지로 지정된 옵션을 사용하여 파일을 PNG 이미지로 렌더링합니다.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 7단계: PDF로 렌더링
마지막으로 지정된 옵션을 사용하여 XML SpreadSheetML 파일을 PDF 문서로 렌더링합니다.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 결론
축하해요! .NET용 GroupDocs.Viewer를 사용하여 XML SpreadSheetML 파일을 렌더링하는 방법을 성공적으로 배웠습니다. 이 다용도 라이브러리에서 제공하는 더 많은 기능과 옵션을 탐색하여 문서 보기 기능을 향상하세요.
## 자주 묻는 질문
### GroupDocs.Viewer는 다른 파일 형식과 호환됩니까?
예, GroupDocs.Viewer는 PDF, Word, Excel 등을 포함한 광범위한 문서 형식을 지원합니다.
### 렌더링된 문서의 모양을 사용자 정의할 수 있습니까?
전적으로! GroupDocs.Viewer는 다양한 사용자 정의 옵션을 제공하므로 특정 요구 사항에 맞게 출력을 조정할 수 있습니다.
### 추가 지원과 리소스는 어디에서 찾을 수 있나요?
 방문하다[GroupDocs.Viewer 포럼](https://forum.groupdocs.com/c/viewer/9) 지역사회 지원을 위해[선적 서류 비치](https://tutorials.groupdocs.com/viewer/net/)자세한 정보를 보려면.
### 무료 평가판이 제공되나요?
 예, 무료 평가판에 액세스할 수 있습니다[여기](https://releases.groupdocs.com/).
### 임시면허는 어떻게 취득하나요?
 임시면허를 취득할 수 있습니다.[여기](https://purchase.groupdocs.com/temporary-license/).