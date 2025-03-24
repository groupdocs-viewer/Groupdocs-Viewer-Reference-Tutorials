---
title: Wyklucz czcionki z renderowanego kodu HTML
linktitle: Wyklucz czcionki z renderowanego kodu HTML
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak wykluczać czcionki z renderowanego kodu HTML przy użyciu narzędzia GroupDocs.Viewer dla platformy .NET. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby uzyskać płynne wyświetlanie dokumentów.
weight: 10
url: /pl/net/rendering-documents-html/exclude-fonts-html/
---

# Wyklucz czcionki z renderowanego kodu HTML

## Wstęp
GroupDocs.Viewer dla .NET to potężna biblioteka do renderowania dokumentów, która umożliwia programistom wyświetlanie ponad 50 formatów dokumentów w aplikacjach .NET bez konieczności stosowania zewnętrznych zależności. W tym samouczku skupimy się na konkretnej funkcji GroupDocs.Viewer: wykluczaniu czcionek z renderowanego wyniku HTML. 
## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
1. Podstawowa znajomość programowania w C# i .NET.
2.  Zainstalowany GroupDocs.Viewer dla .NET. Można go pobrać z[Tutaj](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio lub dowolne inne IDE do programowania w języku C#.

## Importuj przestrzenie nazw
W kodzie C# pamiętaj o uwzględnieniu niezbędnych przestrzeni nazw:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Krok 1: Zdefiniuj katalog wyjściowy
Skonfiguruj katalog, w którym chcesz zapisywać renderowane pliki HTML.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Zdefiniuj format ścieżki pliku strony
Określ format ścieżek plików poszczególnych stron renderowanego dokumentu.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 3: Zainicjuj obiekt przeglądarki
Utwórz instancję obiektu Viewer z dokumentem, który chcesz wyrenderować.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Twój kod trafia tutaj
}
```
## Krok 4: Ustaw opcje widoku HTML
Zdefiniuj opcje renderowania HTML, w tym format osadzonych zasobów i czcionek do wykluczenia.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Krok 5: Renderuj dokument
Przekaż opcje widoku HTML do obiektu Viewer, aby wyrenderować dokument.
```csharp
viewer.View(options);
```
## Krok 6: Wyprowadź lokalizację wyrenderowanego dokumentu
Poinformuj użytkownika o lokalizacji, w której zapisywane są wyrenderowane pliki HTML.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Wniosek
W tym samouczku nauczyliśmy się, jak używać programu GroupDocs.Viewer dla platformy .NET do wykluczania czcionek z renderowanych danych wyjściowych HTML. Wykonując kroki opisane powyżej, możesz dostosować proces renderowania do swoich konkretnych wymagań, zapewniając optymalne wyświetlanie dokumentów w swoich aplikacjach.
## Często zadawane pytania
### Czy mogę wykluczyć wiele czcionek z renderowanego kodu HTML?
 Tak, możesz dodać wiele nazw czcionek do pliku`FontsToExclude` lista w opcjach widoku HTML.
### Czy GroupDocs.Viewer jest kompatybilny ze wszystkimi frameworkami .NET?
Tak, GroupDocs.Viewer obsługuje .NET Framework 4.6.1 i nowsze wersje.
### Czy mogę renderować dokumenty ze zdalnych lokalizacji?
Tak, GroupDocs.Viewer obsługuje renderowanie dokumentów z magazynu lokalnego, a także zdalnych lokalizacji i strumieni.
### Czy GroupDocs.Viewer obsługuje responsywne projektowanie danych wyjściowych HTML?
Tak, możesz włączyć renderowanie responsywne, dostosowując odpowiednio opcje widoku HTML.
### Czy dostępna jest pomoc techniczna dla GroupDocs.Viewer?
 Tak, możesz szukać pomocy i brać udział w dyskusjach na temat[Forum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).