---
"description": "Ulepsz przeglądanie dokumentów .NET dzięki GroupDocs.Viewer, aby uzyskać płynne renderowanie. Skorzystaj z naszego samouczka, aby uzyskać wydajną integrację i doskonałe wrażenia użytkownika."
"linktitle": "Renderuj za pomocą zasobów osadzonych lub zewnętrznych"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderuj za pomocą zasobów osadzonych lub zewnętrznych"
"url": "/pl/net/rendering-documents-html/render-html-resources/"
"weight": 12
type: docs
---
# Renderuj za pomocą zasobów osadzonych lub zewnętrznych

## Wstęp

W świecie rozwoju .NET wydajne przeglądanie dokumentów jest kluczowym aspektem wielu aplikacji. GroupDocs.Viewer dla .NET zapewnia potężne rozwiązanie do renderowania dokumentów z osadzonymi lub zewnętrznymi zasobami. W tym samouczku zbadamy, jak wykorzystać GroupDocs.Viewer do płynnego renderowania dokumentów, dzieląc każdy krok na części w celu zapewnienia przejrzystości i zrozumienia.

## Wymagania wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

1. Podstawowa znajomość programowania .NET: konieczna jest znajomość języka programowania C# i platformy .NET.
2. Instalacja GroupDocs.Viewer dla .NET: Pobierz i zainstaluj GroupDocs.Viewer dla .NET z [Tutaj](https://releases.groupdocs.com/viewer/net/).
3. Plik dokumentu do renderowania: Przygotuj przykładowy plik dokumentu (np. DOCX, PDF) do renderowania.

## Importuj przestrzenie nazw

Najpierw zaimportujmy niezbędne przestrzenie nazw dla naszego projektu .NET:

```csharp
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;
using System.IO;
```

Teraz podzielimy proces renderowania dokumentu z osadzonymi lub zewnętrznymi zasobami na łatwiejsze do opanowania kroki:

## Krok 1: Zdefiniuj katalog wyjściowy

```csharp
string outputDirectory = "Your Document Directory";
```

Określ katalog, w którym mają zostać zapisane wyrenderowane strony HTML.

## Krok 2: Zdefiniuj format ścieżki pliku stronicowania

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

Ustaw format ścieżki pliku, w którym będzie zapisywana każda renderowana strona. `{0}` jest symbolem zastępczym numeru strony.

## Krok 3: Zainicjuj instancję przeglądarki

```csharp
using (Viewer viewer = new Viewer("YourDocumentFilePath"))
{
    // Kod inicjalizacji przeglądarki znajduje się tutaj
}
```

Utwórz instancję Viewer, przekazując ścieżkę do pliku dokumentu, który ma zostać wyrenderowany.

## Krok 4: Skonfiguruj opcje widoku HTML

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

Skonfiguruj opcje widoku HTML, określając format osadzonych zasobów i format ścieżki pliku strony.

## Krok 5: Renderowanie dokumentu

```csharp
viewer.View(options);
```

Wywołaj `View` metodę na instancji Viewer, przekazując skonfigurowane opcje widoku HTML.

## Krok 6: Wyświetl ścieżkę katalogu wyjściowego

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in: {outputDirectory}");
```

Wyświetla komunikat informujący o pomyślnym renderowaniu i ścieżkę do katalogu wyjściowego.

## Wniosek

GroupDocs.Viewer dla .NET upraszcza proces renderowania dokumentów z osadzonymi lub zewnętrznymi zasobami, zwiększając możliwości przeglądania dokumentów w aplikacjach .NET. Postępując zgodnie z krokami opisanymi w tym samouczku, programiści mogą bezproblemowo zintegrować funkcjonalność renderowania dokumentów ze swoimi projektami, zapewniając użytkownikom płynne i wydajne przeglądanie dokumentów.

## Najczęściej zadawane pytania

### P: Czy GroupDocs.Viewer dla .NET jest kompatybilny z różnymi formatami dokumentów?

O: Tak, GroupDocs.Viewer obsługuje szeroką gamę formatów dokumentów, w tym DOCX, PDF, XLSX i inne.

### P: Czy mogę dostosować opcje renderowania do moich wymagań?

O: Oczywiście, GroupDocs.Viewer oferuje rozbudowane opcje konfiguracji procesu renderowania, aby spełnić konkretne potrzeby.

### P: Czy jest dostępna bezpłatna wersja próbna programu GroupDocs.Viewer dla platformy .NET?

A: Tak, możesz skorzystać z bezpłatnej wersji próbnej [Tutaj](https://releases.groupdocs.com/).

### P: W jaki sposób mogę uzyskać pomoc lub wsparcie dotyczące integracji GroupDocs.Viewer?

A: Możesz szukać pomocy na forum społeczności GroupDocs.Viewer [Tutaj](https://forum.groupdocs.com/c/viewer/9).

### P: Czy są dostępne licencje tymczasowe do celów testowych?

A: Tak, licencje tymczasowe można uzyskać od [Tutaj](https://purchase.groupdocs.com/temporary-license/).