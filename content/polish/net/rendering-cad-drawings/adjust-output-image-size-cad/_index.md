---
title: Dostosuj rozmiar obrazu wyjściowego dla rysunków CAD
linktitle: Dostosuj rozmiar obrazu wyjściowego dla rysunków CAD
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak dostosować rozmiar obrazu wyjściowego dla rysunków CAD za pomocą programu GroupDocs.Viewer dla platformy .NET. Bez wysiłku zwiększ widoczność i użyteczność.
weight: 15
url: /pl/net/rendering-cad-drawings/adjust-output-image-size-cad/
---

# Dostosuj rozmiar obrazu wyjściowego dla rysunków CAD

## Wstęp
Rysunki CAD często wymagają specyficznych dostosowań w celu zapewnienia optymalnego przeglądania i prezentacji. GroupDocs.Viewer dla .NET zapewnia potężny zestaw narzędzi do zarządzania i dostosowywania wyników rysunków CAD. W tym samouczku przeprowadzimy Cię krok po kroku przez proces dostosowywania rozmiaru obrazu wyjściowego dla rysunków CAD.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące wymagania wstępne:
1.  GroupDocs.Viewer dla .NET: Pobierz i zainstaluj GroupDocs.Viewer dla .NET z[Tutaj](https://releases.groupdocs.com/viewer/net/).
2. Katalog dokumentów: Przygotuj katalog, w którym znajduje się Twój dokument.
3. Podstawowe zrozumienie: Zapoznaj się z podstawowymi koncepcjami programowania .NET.

## Importuj przestrzenie nazw
Najpierw zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcji GroupDocs.Viewer:
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
## Krok 2: Zdefiniuj format ścieżki pliku strony
Ustaw format ścieżek plików stronicowania. Ten format będzie używany do nazywania i zapisywania poszczególnych stron jako plików HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Krok 3: Dostosuj rozmiar obrazu
Wewnątrz bloku użytkowego obiektu Przeglądarka dostosuj rozmiar obrazu dla rysunków CAD, ustawiając odpowiednie opcje:
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
Dostosowanie rozmiaru obrazu wyjściowego dla rysunków CAD ma kluczowe znaczenie dla poprawy ich widoczności i użyteczności. Dzięki GroupDocs.Viewer dla .NET proces ten staje się usprawniony i wydajny, umożliwiając dostosowanie wyników do konkretnych wymagań.
## Często zadawane pytania
### Czy mogę dostosować rozmiar obrazu wyjściowego dla innych typów dokumentów niż rysunki CAD?
Tak, GroupDocs.Viewer dla .NET obsługuje różne typy dokumentów i można dostosować rozmiar obrazu wyjściowego dla większości formatów dokumentów.
### Czy GroupDocs.Viewer dla .NET jest kompatybilny z różnymi wersjami platformy .NET?
Tak, GroupDocs.Viewer dla .NET jest kompatybilny z wieloma wersjami platformy .NET, zapewniając elastyczność i użyteczność w różnych środowiskach.
### Czy są dostępne opcje licencjonowania programu GroupDocs.Viewer dla platformy .NET?
Tak, możesz poznać różne opcje licencjonowania, w tym licencje tymczasowe i licencje komercyjne, w zależności od potrzeb.
### Czy mogę dostosować format wyjściowy renderowanych dokumentów?
Oczywiście GroupDocs.Viewer dla .NET oferuje różne opcje dostosowywania, umożliwiając dostosowanie formatu wyjściowego do własnych preferencji.
### Gdzie mogę znaleźć dodatkowe wsparcie lub pomoc dotyczącą GroupDocs.Viewer dla .NET?
 Możesz odwiedzić forum GroupDocs.Viewer[Tutaj](https://forum.groupdocs.com/c/viewer/9) aby uzyskać wsparcie, zadawać pytania i nawiązywać kontakt ze społecznością.