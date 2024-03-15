---
title: Renderowanie arkusza XML SpreadSheetML
linktitle: Renderowanie arkusza XML SpreadSheetML
second_title: GroupDocs.Viewer API .NET
description: Poznaj płynne renderowanie plików XML SpreadSheetML w różnych formatach za pomocą GroupDocs.Viewer dla .NET. Bezproblemowa integracja z aplikacjami.
type: docs
weight: 16
url: /pl/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/
---
## Wstęp
Witamy w świecie GroupDocs.Viewer dla .NET! W tym samouczku przeprowadzimy Cię przez proces renderowania plików XML SpreadSheetML przy użyciu GroupDocs.Viewer, potężnej biblioteki .NET. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten przewodnik krok po kroku pomoże Ci bez wysiłku zintegrować renderowanie XML SpreadSheetML z Twoimi aplikacjami.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że masz skonfigurowane następujące wymagania wstępne:
- Środowisko programistyczne z obsługą .NET.
-  Zainstalowana biblioteka GroupDocs.Viewer dla .NET. Możesz go pobrać[Tutaj](https://releases.groupdocs.com/viewer/net/).
- Podstawowa znajomość programowania w języku C#.
## Importuj przestrzenie nazw
Rozpocznij od zaimportowania niezbędnych przestrzeni nazw do projektu C#. Dzięki temu masz dostęp do funkcjonalności udostępnianych przez GroupDocs.Viewer.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Krok 1: Skonfiguruj katalog dokumentów
Zdefiniuj ścieżkę do katalogu dokumentów, w którym zostaną zapisane dane wyjściowe.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Określ ścieżki plików wyjściowych
Skonfiguruj pełne ścieżki plików wyjściowych HTML, JPG, PNG i PDF.
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## Krok 3: Określ opcje ładowania
Jawnie określ typ pliku jako Excel 2003 XML SpreadSheetML, aby był on dokładnie renderowany.
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## Krok 4: Renderuj do wielostronicowego kodu HTML
Skorzystaj z opcji widoku HTML, aby wyrenderować plik XML SpreadSheetML w wielostronicowy dokument HTML.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Krok 5: Renderuj do JPG
Renderuj plik XML SpreadSheetML do obrazu JPG, korzystając z określonych opcji.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Krok 6: Renderuj do PNG
Podobnie wyrenderuj plik do obrazu PNG z określonymi opcjami.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Krok 7: Renderuj do formatu PDF
Na koniec wyrenderuj plik XML SpreadSheetML do dokumentu PDF, korzystając z określonych opcji.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się renderowania plików XML SpreadSheetML przy użyciu programu GroupDocs.Viewer dla platformy .NET. Zwiększ swoje możliwości przeglądania dokumentów, odkrywając więcej funkcji i opcji dostępnych w tej wszechstronnej bibliotece.
## Często zadawane pytania
### Czy GroupDocs.Viewer jest kompatybilny z innymi formatami plików?
Tak, GroupDocs.Viewer obsługuje szeroką gamę formatów dokumentów, w tym PDF, Word, Excel i inne.
### Czy mogę dostosować wygląd renderowanych dokumentów?
Absolutnie! GroupDocs.Viewer oferuje różne opcje dostosowywania, umożliwiające dostosowanie wyników do konkretnych potrzeb.
### Gdzie mogę znaleźć dodatkowe wsparcie i zasoby?
 Odwiedzić[Forum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) o wsparcie społeczności i poznaj[dokumentacja](https://reference.groupdocs.com/viewer/net/)aby uzyskać szczegółowe informacje.
### Czy dostępny jest bezpłatny okres próbny?
 Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.groupdocs.com/).
### Jak uzyskać licencję tymczasową?
 Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.groupdocs.com/temporary-license/).