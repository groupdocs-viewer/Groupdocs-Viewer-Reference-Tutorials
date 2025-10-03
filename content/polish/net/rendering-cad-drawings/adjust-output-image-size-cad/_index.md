---
"description": "Dowiedz się, jak dostosować rozmiar obrazu wyjściowego dla rysunków CAD za pomocą GroupDocs.Viewer dla .NET. Bezproblemowo zwiększ widoczność i użyteczność."
"linktitle": "Dostosuj rozmiar obrazu wyjściowego dla rysunków CAD"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Dostosuj rozmiar obrazu wyjściowego dla rysunków CAD"
"url": "/pl/net/rendering-cad-drawings/adjust-output-image-size-cad/"
"weight": 15
type: docs
---
# Dostosuj rozmiar obrazu wyjściowego dla rysunków CAD

## Wstęp
Rysunki CAD często wymagają określonych dostosowań w celu optymalnego wyświetlania i prezentacji. GroupDocs.Viewer dla .NET zapewnia potężny zestaw narzędzi do zarządzania i dostosowywania wyników rysunków CAD. W tym samouczku przeprowadzimy Cię przez proces dostosowywania rozmiaru obrazu wyjściowego dla rysunków CAD krok po kroku.
## Wymagania wstępne
Zanim zaczniesz, upewnij się, że spełniasz następujące wymagania wstępne:
1. GroupDocs.Viewer dla .NET: Pobierz i zainstaluj GroupDocs.Viewer dla .NET z [Tutaj](https://releases.groupdocs.com/viewer/net/).
2. Katalog dokumentów: Przygotuj katalog, w którym będzie się znajdował Twój dokument.
3. Podstawowa wiedza: Zapoznaj się z podstawowymi koncepcjami programowania .NET.

## Importuj przestrzenie nazw
Najpierw należy zaimportować niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności GroupDocs.Viewer:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Ustaw katalog wyjściowy
Zdefiniuj katalog, w którym chcesz przechowywać obrazy wyjściowe rysunków CAD:
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Zdefiniuj format ścieżki pliku stronicowania
Ustaw format ścieżek plików stronicowania. Ten format będzie używany do nazywania i zapisywania poszczególnych stron jako plików HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 3: Dostosuj rozmiar obrazu
Wewnątrz bloku użycia dla obiektu Przeglądarka dostosuj rozmiar obrazu dla rysunków CAD, ustawiając odpowiednie opcje:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Krok 4: Wyświetl katalog wyjściowy
Po wyrenderowaniu dokumentu wyświetl komunikat informujący o pomyślnym wyrenderowaniu i podaj lokalizację katalogu wyjściowego:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Wniosek
Dostosowanie rozmiaru obrazu wyjściowego dla rysunków CAD jest kluczowe dla zwiększenia ich widoczności i użyteczności. Dzięki GroupDocs.Viewer dla .NET proces ten staje się usprawniony i wydajny, umożliwiając dostosowanie wyjścia do konkretnych wymagań.
## Najczęściej zadawane pytania
### Czy mogę dostosować rozmiar obrazu wyjściowego w innych typach dokumentów niż rysunki CAD?
Tak, GroupDocs.Viewer dla platformy .NET obsługuje różne typy dokumentów, a rozmiar obrazu wyjściowego można dostosować do większości formatów dokumentów.
### Czy GroupDocs.Viewer dla .NET jest kompatybilny z różnymi wersjami platformy .NET?
Tak, GroupDocs.Viewer dla .NET jest kompatybilny z wieloma wersjami platformy .NET, co zapewnia elastyczność i użyteczność w różnych środowiskach.
### Czy są dostępne jakieś opcje licencjonowania dla GroupDocs.Viewer dla .NET?
Tak, możesz rozważyć różne opcje licencjonowania, w tym licencje tymczasowe i licencje komercyjne, które dopasują się do Twoich potrzeb.
### Czy mogę dostosować format wyjściowy renderowanych dokumentów?
Oczywiście, GroupDocs.Viewer dla .NET oferuje różne opcje dostosowywania, pozwalające dostosować format wyjściowy do Twoich samouczków.
### Gdzie mogę znaleźć dodatkową pomoc lub wsparcie dotyczące GroupDocs.Viewer dla .NET?
Możesz odwiedzić forum GroupDocs.Viewer [Tutaj](https://forum.groupdocs.com/c/viewer/9) aby uzyskać wsparcie, zadać pytania i nawiązać kontakt ze społecznością.