---
title: Dostosuj rozmiar strony podczas renderowania wiadomości e-mail
linktitle: Dostosuj rozmiar strony podczas renderowania wiadomości e-mail
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak dostosować rozmiar strony podczas renderowania wiadomości e-mail do formatu PDF przy użyciu programu GroupDocs.Viewer dla platformy .NET. Zwiększ wydajność przeglądania dokumentów.
weight: 10
url: /pl/net/rendering-email-messages/adjust-page-size-email/
---
## Wstęp
W dziedzinie programowania .NET GroupDocs.Viewer zapewnia kompleksowe rozwiązanie do renderowania różnych formatów dokumentów, w tym wiadomości e-mail. W tym samouczku skupiono się na dostosowywaniu rozmiaru strony podczas renderowania wiadomości e-mail do formatu PDF przy użyciu programu GroupDocs.Viewer dla platformy .NET. Wykonując kroki opisane w tym przewodniku, dowiesz się, jak płynnie manipulować rozmiarem strony, aby spełnić Twoje specyficzne wymagania.
## Warunki wstępne
Zanim zagłębisz się w ten samouczek, upewnij się, że spełniasz następujące wymagania wstępne:
### 1. Zainstalowano GroupDocs.Viewer dla .NET
 Upewnij się, że w środowisku programistycznym zainstalowano GroupDocs.Viewer for .NET. Można go pobrać z[Tutaj](https://releases.groupdocs.com/viewer/net/).
### 2. Podstawowe zrozumienie programowania .NET
Zapoznaj się z podstawami programowania .NET, w tym z programowaniem w języku C# i obsługą plików.
### 3. IDE (zintegrowane środowisko programistyczne)
Zainstaluj środowisko IDE, takie jak Visual Studio, umożliwiające pisanie i wykonywanie kodu .NET.

## Importuj przestrzenie nazw
W projekcie C# zaimportuj niezbędne przestrzenie nazw, aby móc korzystać z funkcjonalności GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Krok 1: Ustaw katalog wyjściowy
Zdefiniuj katalog, w którym zostanie zapisany wyjściowy plik PDF.
```csharp
string outputDirectory = "Your Document Directory";
```
## Krok 2: Zdefiniuj ścieżkę pliku
Połącz katalog wyjściowy z nazwą pliku wyjściowego.
```csharp
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## Krok 3: Zainicjuj obiekt przeglądarki
Utwórz instancję klasy Viewer i określ ścieżkę pliku wiadomości e-mail.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
```
## Krok 4: Skonfiguruj opcje widoku PDF
Utwórz instancję PdfViewOptions i ustaw ścieżkę pliku wyjściowego.
```csharp
PdfViewOptions options = new PdfViewOptions(filePath);
```
## Krok 5: Dostosuj rozmiar strony
Zmodyfikuj właściwość rozmiaru strony w opcji EmailOptions opcji PdfViewOptions.
```csharp
options.EmailOptions.PageSize = PageSize.A4;
```
## Krok 6: Renderuj dokument
Wywołaj metodę View obiektu przeglądarki, przekazując skonfigurowane opcje PdfViewOptions.
```csharp
viewer.View(options);
```
## Krok 7: Wyświetl komunikat o powodzeniu
Poinformuj użytkownika o pomyślnym renderowaniu i katalogu wyjściowym.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Wniosek
Podsumowując, w tym samouczku pokazano, jak dostosować rozmiar strony podczas renderowania wiadomości e-mail do formatu PDF przy użyciu programu GroupDocs.Viewer dla platformy .NET. Postępując zgodnie z tymi szczegółowymi instrukcjami, możesz efektywnie manipulować rozmiarami stron, aby spełnić określone wymagania, zwiększając możliwości przeglądania dokumentów i zarządzania nimi w aplikacjach .NET.
## Często zadawane pytania
### Czy GroupDocs.Viewer jest zgodny z różnymi formatami wiadomości e-mail?
GroupDocs.Viewer obsługuje renderowanie różnych formatów wiadomości e-mail, w tym MSG i EML.
### Czy mogę dostosować rozmiar strony do swoich preferencji?
Tak, możesz dostosować rozmiar strony za pomocą opcji PdfViewOptions programu GroupDocs.Viewer, oferując elastyczność w renderowaniu dokumentów.
### Czy GroupDocs.Viewer obsługuje inne formaty dokumentów?
Tak, GroupDocs.Viewer obsługuje szeroką gamę formatów dokumentów, w tym PDF, Microsoft Office, obrazy i inne.
### Czy GroupDocs.Viewer nadaje się do zastosowań na poziomie przedsiębiorstwa?
Absolutnie GroupDocs.Viewer oferuje solidne funkcje odpowiednie zarówno dla aplikacji na małą skalę, jak i na poziomie przedsiębiorstwa, zapewniając wydajne renderowanie dokumentów i zarządzanie nimi.
### Gdzie mogę uzyskać pomoc lub dodatkowe wsparcie dotyczące GroupDocs.Viewer?
 Możesz odwiedzić forum GroupDocs.Viewer[Tutaj](https://forum.groupdocs.com/c/viewer/9) aby szukać pomocy, zadawać pytania i nawiązywać kontakt ze społecznością.