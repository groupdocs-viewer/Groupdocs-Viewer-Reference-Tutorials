---
"date": "2025-04-25"
"description": "Dowiedz się, jak konwertować pliki TXT do różnych formatów, takich jak HTML, JPG, PNG i PDF, za pomocą GroupDocs.Viewer dla .NET, korzystając z tego kompleksowego przewodnika."
"title": "Konwertuj TXT do HTML, JPG, PNG, PDF za pomocą GroupDocs.Viewer .NET&#58; Kompletny przewodnik"
"url": "/pl/net/export-conversion/groupdocs-viewer-dotnet-txt-conversion-guide/"
"weight": 1
---

# Konwertuj TXT do wielu formatów za pomocą GroupDocs.Viewer .NET

## Wstęp

Chcesz bez wysiłku przekonwertować dokumenty tekstowe do różnych formatów, takich jak HTML, JPG, PNG lub PDF? Zarządzanie konwersjami dokumentów może być trudne, szczególnie w przypadku wielu stron lub określonych wymagań formatowych. **GroupDocs.Viewer dla .NET** upraszcza proces renderowania plików TXT do różnych formatów wyjściowych, gwarantując dostępność i atrakcyjność wizualną Twoich danych.

![Konwertuj TXT do HTML, JPG, PNG, PDF za pomocą GroupDocs.Viewer dla .NET](/viewer/export-conversion/convert-txt-to-html-jpg-png-pdf.png)

W tym przewodniku przyjrzymy się, jak używać GroupDocs.Viewer dla .NET do przekształcania dokumentów TXT w wielostronicowy HTML, jednostronicowy HTML, JPG, PNG i PDF. Do końca opanujesz:
- Konwersja plików TXT przy użyciu języka C# z GroupDocs.Viewer
- Wdrażanie różnych opcji renderowania dla Twoich potrzeb
- Optymalizacja wydajności podczas konwersji

Przyjrzyjmy się bliżej rozwiązywaniu Twoich problemów związanych z konwersją dokumentów.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz przygotowane następujące rzeczy:
- **Środowisko programistyczne**:Visual Studio 2019 lub nowszy.
- **.NET Framework**: Wersja 4.6.1 lub nowsza.
- **GroupDocs.Viewer dla biblioteki .NET**:
  - Za pomocą konsoli Menedżera pakietów NuGet: `Install-Package GroupDocs.Viewer -Version 25.3.0`
  - Korzystanie z interfejsu wiersza poleceń .NET: `dotnet add package GroupDocs.Viewer --version 25.3.0`

Aby ułatwić sobie pracę, zalecana jest znajomość programowania w języku C# i podstawowych operacji na plikach w środowisku .NET.

## Konfigurowanie GroupDocs.Viewer dla .NET

### Instalacja

Aby rozpocząć, zainstaluj **GroupDocs.Viewer** bibliotekę korzystając z preferowanego menedżera pakietów:

#### Konsola Menedżera Pakietów NuGet
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

#### Interfejs wiersza poleceń .NET
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Koncesjonowanie

Możesz zacząć od **bezpłatny okres próbny** lub uzyskać **licencja tymczasowa** aby poznać pełne możliwości GroupDocs.Viewer dla .NET bez ograniczeń ewaluacyjnych:
- Bezpłatna wersja próbna: [Pobierz tutaj](https://releases.groupdocs.com/viewer/net/)
- Licencja tymczasowa: [Zapytaj tutaj](https://purchase.groupdocs.com/temporary-license/)

W przypadku ciągłego użytkowania rozważ zakup licencji bezpośrednio od [Dokumenty grupowe](https://purchase.groupdocs.com/buy).

### Podstawowa inicjalizacja

Aby skonfigurować GroupDocs.Viewer w projekcie:

```csharp
using System.IO;
using GroupDocs.Viewer;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");

// Zainicjuj obiekt Viewer za pomocą ścieżki pliku TXT.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Kod renderowania będzie umieszczony tutaj.
}
```

## Przewodnik wdrażania

Teraz przyjrzyjmy się bliżej każdej funkcji i zobaczmy, jak można ją wdrożyć.

### Renderuj dokument TXT do wielostronicowego HTML

#### Przegląd
Ta funkcja pokazuje konwersję dokumentu TXT do wielostronicowego formatu HTML. Każda strona pliku tekstowego jest renderowana jako indywidualny plik HTML z osadzonymi zasobami.

#### Krok 1: Skonfiguruj przeglądarkę

Utwórz `Viewer` obiekt dla pliku źródłowego TXT:

```csharp
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");

// Zainicjuj przeglądarkę przy użyciu przykładowego pliku tekstowego.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Przejdź do kroku 2...
```

#### Krok 2: Skonfiguruj opcje widoku HTML

Organizować coś `HtmlViewOptions` aby renderować każdą stronę osobno:

```csharp
// Skonfiguruj opcje widoku HTML na potrzeby renderowania wielostronicowego.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);

// Wyświetl dokument jako wielostronicowy kod HTML.
viewer.View(options);
}
```

**Wyjaśnienie**:Ten `ForEmbeddedResources()` Metoda ta zapewnia, że zasoby, takie jak obrazy i style, są osadzone bezpośrednio w pliku HTML, co ułatwia ich udostępnianie.

### Renderuj dokument TXT do jednostronicowego HTML

#### Przegląd
Konwertuj dokument TXT na pojedynczą stronę HTML, co jest idealnym rozwiązaniem w przypadku dokumentów, które muszą być wyświetlane jako jedna ciągła strona internetowa.

#### Krok 1: Skonfiguruj przeglądarkę

Zainicjuj `Viewer` obiekt:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");

// Zainicjuj nową instancję przeglądarki dla innego pliku tekstowego.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample2.txt")))
{
    // Przejdź do kroku 2...
```

#### Krok 2: Skonfiguruj opcje HTML pojedynczej strony

Konfiguruj `HtmlViewOptions` z włączonym ustawieniem pojedynczej strony:

```csharp
// Skonfiguruj opcje renderowania na pojedynczej stronie HTML.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
options.RenderToSinglePage = true;

// Wyświetl jako pojedynczą stronę HTML.
viewer.View(options);
}
```

**Wyjaśnienie**:Ten `RenderToSinglePage` Właściwość ta zapewnia, że cała zawartość jest wyświetlana na jednej stronie.

### Renderuj dokument TXT do JPG

#### Przegląd
Funkcja ta umożliwia konwersję dokumentu tekstowego do obrazu JPEG, przydatnego w prezentacjach wizualnych lub celach archiwizacyjnych.

#### Krok 1: Skonfiguruj przeglądarkę

Przygotuj swoje `Viewer` obiekt:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");

// Zainicjuj przeglądarkę przy użyciu pliku przykładowego.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Przejdź do kroku 2...
```

#### Krok 2: Skonfiguruj opcje widoku JPG

Organizować coś `JpgViewOptions` do renderowania obrazu:

```csharp
// Skonfiguruj opcje renderowania jako obrazu JPG.
JpgViewOptions options = new JpgViewOptions(pageFileFullPath);

// Wyrenderuj dokument jako plik JPEG.
viewer.View(options);
}
```

**Wyjaśnienie**:Ten `JpgViewOptions` Klasa określa sposób renderowania i zapisywania każdej strony dokumentu w formacie JPEG.

### Renderuj dokument TXT do PNG

#### Przegląd
Konwertuj dokument tekstowy do formatu PNG, uzyskując wysokiej jakości obraz wyjściowy z obsługą przezroczystości.

#### Krok 1: Skonfiguruj przeglądarkę

Zainicjuj `Viewer` obiekt:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");

// Utwórz instancję przeglądarki dla pliku TXT.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Przejdź do kroku 2...
```

#### Krok 2: Skonfiguruj opcje widoku PNG

Organizować coś `PngViewOptions`:

```csharp
// Skonfiguruj opcje widoku do renderowania jako obraz PNG.
PngViewOptions options = new PngViewOptions(pageFileFullPath);

// Wyrenderuj dokument w formacie PNG.
viewer.View(options);
}
```

**Wyjaśnienie**:Ten `PngViewOptions` Klasa ta umożliwia renderowanie każdej strony z przezroczystością, dzięki czemu nadaje się ona do grafiki warstwowej.

### Renderuj dokument TXT do PDF

#### Przegląd
Funkcja ta doskonale nadaje się do konwersji dokumentów tekstowych do powszechnie dostępnego formatu PDF.

#### Krok 1: Skonfiguruj przeglądarkę

Przygotuj swoje `Viewer` obiekt:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");

// Zainicjuj instancję przeglądarki dla przykładowego pliku tekstowego.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Przejdź do kroku 2...
```

#### Krok 2: Skonfiguruj opcje widoku PDF

Organizować coś `PdfViewOptions`:

```csharp
// Skonfiguruj opcje widoku w celu renderowania jako dokumentu PDF.
PdfViewOptions options = new PdfViewOptions(pageFileFullPath);

// Przekształć dokument w plik PDF.
viewer.View(options);
}
```

**Wyjaśnienie**:Ten `PdfViewOptions` Klasa określa sposób konwersji i zapisywania plików TXT jako dokumentów PDF.

## Wniosek

Dzięki GroupDocs.Viewer dla .NET konwersja dokumentów tekstowych do różnych formatów jest prosta. Ten przewodnik obejmuje transformację plików TXT do wielostronicowego HTML, jednostronicowego HTML, JPG, PNG i PDF przy użyciu języka C#. Niezależnie od tego, czy chcesz poprawić dostępność dokumentu, czy kompatybilność, te metody zapewniają solidne rozwiązania.

Aby uzyskać dalszą pomoc lub zapoznać się z bardziej zaawansowanymi funkcjami, zapoznaj się z [oficjalna dokumentacja GroupDocs.Viewer](https://docs.groupdocs.com/viewer/net/). Miłego kodowania!