---
"description": "Opanuj renderowanie dokumentów MS Project za pomocą GroupDocs.Viewer dla .NET. Renderuj notatki, dostosowuj jednostki czasu i eksploruj różne formaty wyjściowe bez wysiłku."
"linktitle": "Notatki dotyczące renderowania i dostosowywania jednostek czasu (MS Project)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Notatki dotyczące renderowania i dostosowywania jednostek czasu (MS Project)"
"url": "/pl/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
type: docs
---
# Notatki dotyczące renderowania i dostosowywania jednostek czasu (MS Project)

## Wstęp
GroupDocs.Viewer for .NET to potężny interfejs API renderowania dokumentów, który umożliwia deweloperom przeglądanie i manipulowanie różnymi formatami dokumentów w ich aplikacjach .NET. W tym samouczku skupimy się na renderowaniu notatek i dostosowywaniu jednostek czasu specjalnie dla dokumentów MS Project.
## Wymagania wstępne
Zanim zaczniemy, upewnij się, że spełniasz następujące wymagania wstępne:
1. GroupDocs.Viewer dla .NET: Upewnij się, że pobrałeś i zainstalowałeś bibliotekę GroupDocs.Viewer dla .NET. Możesz ją pobrać z [Tutaj](https://releases.groupdocs.com/viewer/net/).
2. Środowisko programistyczne: Skonfiguruj preferowane środowisko programistyczne z obsługą .NET.
3. Dokument MS Project: Przygotuj przykładowy dokument MS Project w celu przetestowania.
## Importuj przestrzenie nazw
Najpierw zaimportujmy niezbędne przestrzenie nazw, aby rozpocząć renderowanie dokumentów MS Project:
## Krok 1: Importuj przestrzenie nazw
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Teraz, gdy zaimportowaliśmy wymagane przestrzenie nazw, rozbijmy każdy przykład na kilka kroków, aby ułatwić jego zrozumienie.
## Renderowanie dokumentu MS Project do HTML
Aby przekonwertować dokument MS Project do formatu HTML z dołączonymi notatkami, wykonaj następujące kroki:
### Krok 2: Ustaw katalog wyjściowy i format pliku
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Krok 3: Zainicjuj obiekt Viewer i ustaw opcje
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Krok 4: Renderowanie dokumentu do HTML
```csharp
viewer.View(options);
```
## Renderowanie dokumentu MS Project do formatów obrazów
Możesz również renderować dokumenty MS Project do formatów obrazów, takich jak JPG i PNG. Oto jak:
### Krok 5: Ustaw katalog wyjściowy i format pliku dla JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Krok 6: Zainicjuj obiekt Viewer i ustaw opcje JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Krok 7: Renderowanie dokumentu do formatu JPG
```csharp
viewer.View(options);
```
Powtórz podobne kroki, aby renderować do PNG i innych formatów obrazu.
## Renderowanie dokumentu MS Project do formatu PDF
Aby przekonwertować dokument MS Project do formatu PDF, wykonaj następujące czynności:
### Krok 8: Ustaw katalog wyjściowy i format pliku dla pliku PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Krok 9: Zainicjuj obiekt przeglądarki i ustaw opcje PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Krok 10: Renderowanie dokumentu do formatu PDF
```csharp
viewer.View(options);
```

## Wniosek
Gratulacje! Udało Ci się nauczyć, jak renderować dokumenty MS Project i dostosowywać jednostki czasu za pomocą GroupDocs.Viewer dla .NET. Wprowadź tę wiedzę do swoich projektów, aby zwiększyć możliwości przeglądania dokumentów.
## Najczęściej zadawane pytania
### Czy mogę renderować dokumenty MS Project w innych formatach niż HTML, obrazy i PDF?
Tak, GroupDocs.Viewer dla .NET obsługuje renderowanie do różnych formatów, takich jak DOCX, XLSX, PPTX i inne.
### Czy jest dostępna wersja próbna GroupDocs.Viewer dla .NET?
Tak, możesz otrzymać bezpłatną wersję próbną [Tutaj](https://releases.groupdocs.com/).
### Jak mogę uzyskać tymczasową licencję na GroupDocs.Viewer dla platformy .NET?
Odwiedzać [ten link](https://purchase.groupdocs.com/temporary-license/) aby uzyskać tymczasową licencję.
### Gdzie mogę znaleźć dokumentację dla GroupDocs.Viewer dla .NET?
Zapoznaj się z dokumentacją [Tutaj](https://tutorials.groupdocs.com/viewer/net/).
### Gdzie mogę uzyskać pomoc lub zadać pytania dotyczące GroupDocs.Viewer dla .NET?
Możesz odwiedzić forum wsparcia [Tutaj](https://forum.groupdocs.com/c/viewer/9).