---
title: Renderuj notatki i dopasowuj jednostki czasu (MS Project)
linktitle: Renderuj notatki i dopasowuj jednostki czasu (MS Project)
second_title: GroupDocs.Viewer API .NET
description: Opanuj renderowanie dokumentów MS Project za pomocą GroupDocs.Viewer dla .NET. Renderuj notatki, dostosowuj jednostki czasu i bez wysiłku eksploruj różne formaty wyjściowe.
type: docs
weight: 11
url: /pl/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---
## Wstęp
GroupDocs.Viewer dla .NET to potężny interfejs API do renderowania dokumentów, który umożliwia programistom przeglądanie i manipulowanie różnymi formatami dokumentów w aplikacjach .NET. W tym samouczku skupimy się na renderowaniu notatek i dostosowywaniu jednostek czasu specjalnie dla dokumentów MS Project.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. GroupDocs.Viewer dla .NET: Upewnij się, że pobrałeś i zainstalowałeś bibliotekę GroupDocs.Viewer dla .NET. Można go pobrać z[Tutaj](https://releases.groupdocs.com/viewer/net/).
2. Środowisko programistyczne: skonfiguruj preferowane środowisko programistyczne z obsługą .NET.
3. Dokument MS Project: przygotuj przykładowy dokument MS Project do testowania.
## Importuj przestrzenie nazw
Najpierw zaimportujmy niezbędne przestrzenie nazw, aby rozpocząć renderowanie dokumentów MS Project:
## Krok 1: Importuj przestrzenie nazw
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Teraz, gdy zaimportowaliśmy wymagane przestrzenie nazw, podzielmy każdy przykład na wiele kroków, aby uzyskać kompleksowe zrozumienie.
## Renderowanie dokumentu MS Project do formatu HTML
Aby wyrenderować dokument MS Project do formatu HTML z dołączonymi notatkami, wykonaj następujące kroki:
### Krok 2: Ustaw katalog wyjściowy i format pliku
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Krok 3: Zainicjuj obiekt przeglądarki i ustaw opcje
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Krok 4: Renderuj dokument do formatu HTML
```csharp
viewer.View(options);
```
## Renderowanie dokumentu MS Project do formatów obrazu
Możesz także renderować dokumenty MS Project do formatów obrazów, takich jak JPG i PNG. Oto jak:
### Krok 5: Ustaw katalog wyjściowy i format pliku dla JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Krok 6: Zainicjuj obiekt przeglądarki i ustaw opcje JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Krok 7: Renderuj dokument do formatu JPG
```csharp
viewer.View(options);
```
Powtórz podobne kroki w przypadku renderowania do formatu PNG i innych formatów obrazu.
## Renderowanie dokumentu MS Project do formatu PDF
Aby wyrenderować dokument MS Project do formatu PDF, wykonaj następujące czynności:
### Krok 8: Ustaw katalog wyjściowy i format pliku PDF
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
### Krok 10: Renderuj dokument do formatu PDF
```csharp
viewer.View(options);
```

## Wniosek
Gratulacje! Pomyślnie nauczyłeś się renderować dokumenty MS Project i dostosowywać jednostki czasu za pomocą GroupDocs.Viewer dla .NET. Wykorzystaj tę wiedzę w swoich projektach, aby zwiększyć możliwości przeglądania dokumentów.
## Często zadawane pytania
### Czy mogę renderować dokumenty MS Project do innych formatów oprócz HTML, obrazów i PDF?
Tak, GroupDocs.Viewer dla .NET obsługuje renderowanie do różnych formatów, takich jak DOCX, XLSX, PPTX i innych.
### Czy dostępna jest wersja próbna programu GroupDocs.Viewer dla platformy .NET?
 Tak, możesz uzyskać bezpłatną wersję próbną od[Tutaj](https://releases.groupdocs.com/).
### Jak mogę uzyskać tymczasową licencję na GroupDocs.Viewer dla .NET?
 Odwiedzać[ten link](https://purchase.groupdocs.com/temporary-license/) w celu uzyskania licencji tymczasowej.
### Gdzie mogę znaleźć dokumentację GroupDocs.Viewer dla .NET?
 Zapoznaj się z dokumentacją[Tutaj](https://reference.groupdocs.com/viewer/net/).
### Gdzie mogę uzyskać pomoc lub zadać pytania dotyczące GroupDocs.Viewer dla .NET?
 Możesz odwiedzić forum pomocy technicznej[Tutaj](https://forum.groupdocs.com/c/viewer/9).