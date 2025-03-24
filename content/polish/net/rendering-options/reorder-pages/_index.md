---
title: Zmień kolejność stron w dokumencie
linktitle: Zmień kolejność stron w dokumencie
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak zmienić kolejność stron w dokumencie za pomocą programu GroupDocs.Viewer dla platformy .NET. Postępuj zgodnie z naszym samouczkiem krok po kroku, aby bezproblemowo zarządzać dokumentami.
weight: 19
url: /pl/net/rendering-options/reorder-pages/
---
## Wstęp
W świecie programowania .NET efektywne zarządzanie dokumentami i manipulowanie nimi ma kluczowe znaczenie. GroupDocs.Viewer dla .NET zapewnia zaawansowane rozwiązanie do przeglądania różnych formatów dokumentów w aplikacjach. Jednym z podstawowych zadań, z jakim często spotykają się programiści, jest zmiana kolejności stron w dokumencie. Niezależnie od tego, czy pracujesz z plikami PDF, dokumentami programu Word czy innymi formatami, możliwość zmiany układu stron może usprawnić przepływ pracy i zwiększyć wygodę użytkownika. W tym samouczku omówimy sposób zmiany kolejności stron w dokumencie za pomocą programu GroupDocs.Viewer dla platformy .NET.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że masz skonfigurowane następujące wymagania wstępne:
### 1. Zainstaluj GroupDocs.Viewer dla .NET
 Upewnij się, że w środowisku programistycznym zainstalowano GroupDocs.Viewer for .NET. Można go pobrać z[Tutaj](https://releases.groupdocs.com/viewer/net/) i postępuj zgodnie z instrukcjami instalacji zawartymi w dokumentacji.
### 2. Skonfiguruj swoje środowisko programistyczne
Upewnij się, że na komputerze jest skonfigurowane działające środowisko programistyczne .NET, w tym Visual Studio lub inne preferowane środowisko IDE.
### 3. Uzyskaj przykładowe dokumenty
Przygotuj kilka przykładowych dokumentów do celów testowych. Możesz użyć dowolnego formatu dokumentu obsługiwanego przez GroupDocs.Viewer, takiego jak PDF, DOCX, XLSX itp.

## Importuj przestrzenie nazw
W aplikacji .NET zaimportuj niezbędne przestrzenie nazw wymagane do korzystania z funkcjonalności GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Określ katalog wyjściowy
Zdefiniuj katalog, w którym chcesz zapisać ponownie uporządkowany dokument.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Zdefiniuj ścieżkę pliku wyjściowego
Połącz katalog wyjściowy z żądaną nazwą pliku dla zmienionego dokumentu.
```csharp
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Krok 3: Utwórz instancję obiektu przeglądarki
Utwórz instancję klasy Viewer, podając ścieżkę do dokumentu wejściowego.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    // Tutaj znajdzie się kod umożliwiający zmianę kolejności stron
}
```
## Krok 4: Ustaw opcje widoku PDF
Określ opcje renderowania dokumentu jako PDF i zdefiniuj ścieżkę pliku wyjściowego.
```csharp
PdfViewOptions options = new PdfViewOptions(outputFilePath);
```
## Krok 5: Zdefiniuj kolejność stron
Przekaż numery stron w żądanej kolejności do renderowania.
```csharp
viewer.View(options, 2, 1);
```
## Krok 6: Wyświetl komunikat o powodzeniu
Poinformuj użytkownika, że dokument został pomyślnie wyrenderowany.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Wniosek
Podsumowując, zmiana układu stron w dokumencie jest prosta dzięki GroupDocs.Viewer dla .NET. Wykonując kroki opisane w tym samouczku, możesz efektywnie zarządzać stronami dokumentów w aplikacjach .NET, zwiększając użyteczność i produktywność.
## Często zadawane pytania
### Czy GroupDocs.Viewer dla .NET obsługuje wiele formatów dokumentów?
Tak, GroupDocs.Viewer obsługuje szeroką gamę formatów dokumentów, w tym PDF, DOCX, XLSX, PPTX i inne.
### Czy dostępna jest bezpłatna wersja próbna programu GroupDocs.Viewer dla platformy .NET?
 Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej GroupDocs.Viewer z[Tutaj](https://releases.groupdocs.com/).
### Czy GroupDocs.Viewer dla .NET wymaga stałej licencji na programowanie?
 Chociaż dostępna jest licencja tymczasowa do testowania i programowania, do użytku produkcyjnego wymagana jest licencja stała. Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.groupdocs.com/temporary-license/).
### Czy mogę dostosować wygląd renderowanego dokumentu za pomocą GroupDocs.Viewer dla .NET?
Tak, GroupDocs.Viewer udostępnia różne opcje dostosowywania wyników renderowania, w tym rotację strony, znak wodny i inne.
### Gdzie mogę znaleźć dalszą pomoc lub wsparcie dotyczące programu GroupDocs.Viewer dla platformy .NET?
 Możesz odwiedzić forum GroupDocs.Viewer[Tutaj](https://forum.groupdocs.com/c/viewer/9) w przypadku jakichkolwiek zapytań lub potrzeb wsparcia.