---
"description": "Dowiedz się, jak zintegrować Groupdocs.Viewer for .NET ze swoimi aplikacjami, aby umożliwić płynne renderowanie, odwracanie i obracanie dokumentów."
"linktitle": "Przerzucanie i obracanie stron"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Przerzucanie i obracanie stron"
"url": "/pl/net/rendering-options/flip-rotate-pages/"
"weight": 12
type: docs
---
# Przerzucanie i obracanie stron

## Wstęp
tym samouczku zagłębimy się w funkcjonalności Groupdocs.Viewer dla .NET, skupiając się szczególnie na odwracaniu i obracaniu stron. Groupdocs.Viewer dla .NET to potężne narzędzie zaprojektowane do renderowania dokumentów w różnych formatach w aplikacjach .NET. Niezależnie od tego, czy rozwijasz system zarządzania dokumentami, czy musisz zintegrować możliwości przeglądania dokumentów ze swoim oprogramowaniem, Groupdocs.Viewer dla .NET zapewnia wydajne rozwiązanie.
## Wymagania wstępne
Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:
### Instalowanie Groupdocs.Viewer dla .NET
Aby użyć Groupdocs.Viewer dla .NET, musisz zainstalować pakiet za pomocą NuGet Package Manager. Szczegółowe instrukcje instalacji znajdziesz w [dokumentacja](https://tutorials.groupdocs.com/viewer/net/).

## Importuj przestrzenie nazw
Upewnij się, że w projekcie zaimportowano niezbędne przestrzenie nazw, aby móc efektywnie wykorzystać Groupdocs.Viewer dla .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Podzielmy proces przerzucania i obracania stron za pomocą Groupdocs.Viewer dla platformy .NET na proste kroki:
## Krok 1: Ustaw katalog wyjściowy i ścieżkę pliku
Zdefiniuj katalog, w którym ma zostać zapisany plik wyjściowy i podaj ścieżkę do pliku wyjściowego.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Krok 2: Zainicjuj obiekt Viewer
Utwórz wystąpienie klasy Viewer, przekazując ścieżkę do dokumentu, który chcesz wyświetlić.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Krok 3: Skonfiguruj opcje widoku
Skonfiguruj opcje widoku, takie jak określenie formatu pliku wyjściowego i wszelkich dodatkowych ustawień, jak na przykład obrót strony.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Krok 4: Renderowanie dokumentu
Wywołaj metodę View obiektu Viewer i przekaż opcje widoku.
```csharp
viewer.View(viewOptions);
```
## Krok 5: Wyświetl komunikat o powodzeniu
Poinformuj użytkownika, że dokument został pomyślnie wyrenderowany i określ katalog wyjściowy w celu weryfikacji.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Wniosek
Podsumowując, Groupdocs.Viewer dla .NET oferuje potężne możliwości renderowania dokumentów, w tym odwracanie i obracanie stron. Postępując zgodnie z krokami opisanymi w tym samouczku, możesz bezproblemowo zintegrować te funkcje ze swoimi aplikacjami .NET, ulepszając doświadczenia przeglądania dokumentów dla swoich użytkowników.
## Najczęściej zadawane pytania
### Czy Groupdocs.Viewer dla .NET jest kompatybilny ze wszystkimi formatami dokumentów?
Tak, Groupdocs.Viewer dla platformy .NET obsługuje szeroką gamę formatów dokumentów, w tym DOCX, PDF, PPTX i inne.
### Czy mogę dostosować opcje wyświetlania poza przewracaniem i obracaniem stron?
Oczywiście, Groupdocs.Viewer dla platformy .NET oferuje różne opcje dostosowywania przeglądania dokumentów, umożliwiając dostosowanie sposobu wyświetlania do własnych wymagań.
### Czy jest dostępna bezpłatna wersja próbna Groupdocs.Viewer dla .NET?
Tak, możesz skorzystać z bezpłatnej wersji próbnej Groupdocs.Viewer dla .NET, odwiedzając stronę [strona internetowa](https://releases.groupdocs.com/).
### Gdzie mogę uzyskać pomoc techniczną dotyczącą Groupdocs.Viewer dla platformy .NET?
Możesz szukać pomocy i angażować się w życie społeczności poprzez [Forum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9).
### Gdzie mogę uzyskać tymczasową licencję na Groupdocs.Viewer dla platformy .NET?
Tymczasowe licencje na Groupdocs.Viewer dla .NET można uzyskać w [strona zakupu](https://purchase.groupdocs.com/temporary-license/).