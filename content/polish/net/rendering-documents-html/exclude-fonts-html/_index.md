---
"description": "Dowiedz się, jak wykluczyć czcionki z renderowanego HTML za pomocą GroupDocs.Viewer dla .NET. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby uzyskać płynne wyświetlanie dokumentu."
"linktitle": "Wyklucz czcionki z renderowanego HTML"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Wyklucz czcionki z renderowanego HTML"
"url": "/pl/net/rendering-documents-html/exclude-fonts-html/"
"weight": 10
type: docs
---
# Wyklucz czcionki z renderowanego HTML

## Wstęp
GroupDocs.Viewer dla .NET to potężna biblioteka renderowania dokumentów, która umożliwia deweloperom wyświetlanie ponad 50 formatów dokumentów w ich aplikacjach .NET bez konieczności zewnętrznych zależności. W tym samouczku skupimy się na konkretnej funkcji GroupDocs.Viewer: wykluczaniu czcionek z renderowanego wyjścia HTML. 
## Wymagania wstępne
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:
1. Podstawowa znajomość programowania w językach C# i .NET.
2. GroupDocs.Viewer dla .NET zainstalowany. Możesz go pobrać z [Tutaj](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio lub inne środowisko IDE do programowania w języku C#.

## Importuj przestrzenie nazw
W kodzie C# pamiętaj o uwzględnieniu niezbędnych przestrzeni nazw:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Krok 1: Zdefiniuj katalog wyjściowy
Skonfiguruj katalog, w którym chcesz zapisać wyrenderowane pliki HTML.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Zdefiniuj format ścieżki pliku stronicowania
Określ format ścieżek plików poszczególnych stron renderowanego dokumentu.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 3: Zainicjuj obiekt Viewer
Utwórz obiekt Viewer z dokumentem, który chcesz renderować.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Twój kod wpisz tutaj
}
```
## Krok 4: Ustaw opcje widoku HTML
Zdefiniuj opcje renderowania HTML, w tym format osadzonych zasobów i czcionek, które mają zostać wykluczone.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Krok 5: Renderowanie dokumentu
Przekaż opcje widoku HTML do obiektu Viewer w celu renderowania dokumentu.
```csharp
viewer.View(options);
```
## Krok 6: Lokalizacja wyrenderowanego dokumentu wyjściowego
Poinformuj użytkownika o lokalizacji, w której zapisywane są renderowane pliki HTML.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Wniosek
W tym samouczku nauczyliśmy się, jak używać GroupDocs.Viewer dla .NET, aby wykluczyć czcionki z renderowanego wyjścia HTML. Postępując zgodnie z powyższymi krokami, możesz dostosować proces renderowania do swoich konkretnych wymagań, zapewniając optymalne wyświetlanie dokumentów w swoich aplikacjach.
## Najczęściej zadawane pytania
### Czy mogę wykluczyć wiele czcionek z renderowanego kodu HTML?
Tak, możesz dodać wiele nazw czcionek do `FontsToExclude` listę w opcjach widoku HTML.
### Czy GroupDocs.Viewer jest kompatybilny ze wszystkimi platformami .NET?
Tak, GroupDocs.Viewer obsługuje .NET Framework 4.6.1 i nowsze.
### Czy mogę renderować dokumenty ze zdalnych lokalizacji przechowywania?
Tak, GroupDocs.Viewer obsługuje renderowanie dokumentów z pamięci lokalnej, a także zdalnych lokalizacji i strumieni.
### Czy GroupDocs.Viewer obsługuje responsywny projekt wyników HTML?
Tak, możesz włączyć renderowanie responsywne, odpowiednio dostosowując opcje widoku HTML.
### Czy dla GroupDocs.Viewer dostępna jest pomoc techniczna?
Tak, możesz szukać pomocy i uczestniczyć w dyskusjach na ten temat [Forum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).