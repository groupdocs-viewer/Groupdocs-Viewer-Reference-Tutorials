---
title: Przewracaj i obracaj strony
linktitle: Przewracaj i obracaj strony
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak zintegrować Groupdocs.Viewer dla .NET z aplikacjami, aby zapewnić płynne renderowanie, odwracanie i obracanie dokumentów.
weight: 12
url: /pl/net/rendering-options/flip-rotate-pages/
---
## Wstęp
tym samouczku zagłębimy się w funkcjonalności Groupdocs.Viewer dla .NET, ze szczególnym uwzględnieniem przerzucania i obracania stron. Groupdocs.Viewer dla .NET to potężne narzędzie przeznaczone do renderowania dokumentów w różnych formatach w aplikacjach .NET. Niezależnie od tego, czy tworzysz system zarządzania dokumentami, czy chcesz zintegrować funkcje przeglądania dokumentów ze swoim oprogramowaniem, Groupdocs.Viewer dla .NET stanowi wydajne rozwiązanie.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz skonfigurowane następujące wymagania wstępne:
### Instalowanie Groupdocs.Viewer dla .NET
 Aby używać Groupdocs.Viewer dla .NET, musisz zainstalować pakiet za pomocą Menedżera pakietów NuGet. Szczegółowe instrukcje dotyczące instalacji można znaleźć w pliku[dokumentacja](https://tutorials.groupdocs.com/viewer/net/).

## Importuj przestrzenie nazw
Upewnij się, że w projekcie zaimportowano niezbędne przestrzenie nazw, aby efektywnie korzystać z Groupdocs.Viewer dla .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Podzielmy proces przerzucania i obracania stron za pomocą Groupdocs.Viewer dla .NET na proste kroki:
## Krok 1: Ustaw katalog wyjściowy i ścieżkę pliku
Zdefiniuj katalog, w którym chcesz zapisać plik wyjściowy i podaj ścieżkę do pliku wyjściowego.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Krok 2: Zainicjuj obiekt przeglądarki
Utwórz instancję klasy Viewer, przekazując ścieżkę do dokumentu, który chcesz wyświetlić.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Krok 3: Skonfiguruj opcje widoku
Skonfiguruj opcje widoku, takie jak określenie formatu pliku wyjściowego i wszelkich dodatkowych ustawień, takich jak rotacja strony.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Krok 4: Renderuj dokument
Wywołaj metodę View obiektu Viewer i przekaż opcje widoku.
```csharp
viewer.View(viewOptions);
```
## Krok 5: Wyświetl komunikat o powodzeniu
Poinformuj użytkownika, że dokument został pomyślnie wyrenderowany i określ katalog wyjściowy do weryfikacji.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Wniosek
Podsumowując, Groupdocs.Viewer dla .NET oferuje zaawansowane możliwości renderowania dokumentów, w tym przewracania i obracania stron. Wykonując kroki opisane w tym samouczku, możesz bezproblemowo zintegrować te funkcje z aplikacjami .NET, poprawiając komfort przeglądania dokumentów dla użytkowników.
## Często zadawane pytania
### Czy Groupdocs.Viewer dla .NET jest kompatybilny ze wszystkimi formatami dokumentów?
Tak, Groupdocs.Viewer dla .NET obsługuje szeroką gamę formatów dokumentów, w tym DOCX, PDF, PPTX i inne.
### Czy mogę dostosować opcje wyświetlania poza przerzucaniem i obracaniem stron?
Oczywiście Groupdocs.Viewer dla .NET zapewnia różne opcje dostosowywania przeglądania dokumentów, dzięki czemu możesz dostosować środowisko do swoich wymagań.
### Czy dostępna jest bezpłatna wersja próbna programu Groupdocs.Viewer dla platformy .NET?
 Tak, możesz skorzystać z bezpłatnej wersji próbnej Groupdocs.Viewer dla .NET, odwiedzając stronę[strona internetowa](https://releases.groupdocs.com/).
### Jak mogę uzyskać pomoc dotyczącą Groupdocs.Viewer dla platformy .NET?
 Możesz szukać pomocy i nawiązywać kontakt ze społecznością za pośrednictwem[Forum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9).
### Gdzie mogę uzyskać tymczasową licencję na Groupdocs.Viewer dla .NET?
 Tymczasowe licencje na Groupdocs.Viewer dla .NET można uzyskać w witrynie[strona zakupu](https://purchase.groupdocs.com/temporary-license/).