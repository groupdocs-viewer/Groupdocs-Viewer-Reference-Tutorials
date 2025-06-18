---
"date": "2025-04-25"
"description": "Dowiedz się, jak konwertować strony PDF na obrazy PNG, zachowując jednocześnie oryginalne wymiary za pomocą GroupDocs.Viewer dla .NET. Ten przewodnik obejmuje konfigurację, ustawienia i najlepsze praktyki."
"title": "Konwertuj pliki PDF do PNG w oryginalnym rozmiarze za pomocą GroupDocs.Viewer dla .NET"
"url": "/pl/net/export-conversion/convert-pdfs-to-png-groupdocs-viewer-net/"
"weight": 1
---

# Konwertuj pliki PDF do PNG w oryginalnym rozmiarze za pomocą GroupDocs.Viewer dla .NET

## Wstęp

Konwersja plików PDF do obrazów PNG przy zachowaniu oryginalnego rozmiaru strony jest niezbędna do wysokiej jakości digitalizacji dokumentów lub przygotowania treści internetowych. Ten samouczek przeprowadzi Cię przez proces używania GroupDocs.Viewer dla .NET do renderowania stron PDF jako plików PNG, zachowując ich oryginalne wymiary.

![Konwertuj pliki PDF do PNG w oryginalnym rozmiarze za pomocą GroupDocs.Viewer dla .NET](/viewer/export-conversion/convert-pdfs-to-png-with-original-size.png)

**Czego się nauczysz:**
- Jak skonfigurować GroupDocs.Viewer dla .NET w projekcie
- Proces krok po kroku renderowania plików PDF do obrazów PNG przy zachowaniu rozmiarów stron
- Kluczowe opcje konfiguracji i najlepsze praktyki zapewniające optymalną wydajność

Do końca tego samouczka będziesz w stanie bezproblemowo zintegrować tę funkcjonalność ze swoimi aplikacjami. Zacznijmy od wymagań wstępnych niezbędnych do rozpoczęcia.

## Wymagania wstępne

Przed wdrożeniem GroupDocs.Viewer dla .NET w projekcie należy upewnić się, że spełnione są następujące wymagania:

### Wymagane biblioteki i wersje
- **GroupDocs.Viewer dla .NET**: Wersja 25.3.0 lub nowsza.

### Wymagania dotyczące konfiguracji środowiska
- Zgodne środowisko programistyczne, np. Visual Studio.
- Podstawowa znajomość programowania w języku C#.

### Wymagania wstępne dotyczące wiedzy
- Znajomość zarządzania pakietami NuGet.
- Pewne doświadczenie w pracy z plikami PDF i przetwarzaniu obrazów w aplikacjach .NET.

Gdy te wymagania wstępne zostaną spełnione, możemy przystąpić do konfigurowania GroupDocs.Viewer dla platformy .NET.

## Konfigurowanie GroupDocs.Viewer dla .NET

Aby rozpocząć korzystanie z GroupDocs.Viewer dla platformy .NET, wykonaj poniższe kroki instalacji:

### Instalacja za pomocą konsoli NuGet Package Manager
Otwórz projekt w programie Visual Studio i użyj następującego polecenia:
```plaintext
Install-Package GroupDocs.Viewer -Version 25.3.0
```

### Instalacja poprzez .NET CLI
Alternatywnie możesz zainstalować go używając .NET CLI za pomocą tego polecenia:
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Etapy uzyskania licencji
1. **Bezpłatna wersja próbna**:Pobierz wersję próbną z [Pliki do pobrania GroupDocs](https://releases.groupdocs.com/viewer/net/).
2. **Licencja tymczasowa**:Uzyskaj tymczasową licencję, aby zapoznać się ze wszystkimi funkcjami na stronie [Strona licencji tymczasowej](https://purchase.groupdocs.com/temporary-license/).
3. **Zakup**:Aby korzystać z usługi dłużej, należy zakupić licencję za pośrednictwem [Kup stronę](https://purchase.groupdocs.com/buy).

### Podstawowa inicjalizacja i konfiguracja
Aby zainicjować GroupDocs.Viewer dla .NET w projekcie C#, wykonaj następujące kroki:
1. Importuj niezbędne przestrzenie nazw:
    ```csharp
    using System;
    using GroupDocs.Viewer;
    using GroupDocs.Viewer.Options;
    ```
2. Skonfiguruj ścieżki do katalogu wejściowego i wyjściowego pliku PDF.
3. Zainicjuj `Viewer` ze ścieżką do dokumentu źródłowego, jak pokazano w tym fragmencie kodu:
   ```csharp
   string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
   string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
   string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";

   using (Viewer viewer = new Viewer(documentPath))
   {
       PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
       viewer.View(viewOptions);
   }
   ```

## Przewodnik wdrażania
W tej sekcji opisano implementację renderowania stron PDF jako obrazów PNG przy zachowaniu ich oryginalnego rozmiaru.

### Renderowanie stron PDF do PNG z oryginalnym rozmiarem strony
#### Przegląd
Ta funkcja umożliwia renderowanie każdej strony dokumentu PDF do obrazu PNG, zachowując jego oryginalne wymiary. Jest to szczególnie przydatne w aplikacjach wymagających precyzyjnej reprezentacji wizualnej dokumentów.

##### Krok 1: Skonfiguruj ścieżki i zainicjuj przeglądarkę
Utwórz zmienne dla ścieżki wejściowej pliku PDF i katalogu wyjściowego:
```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";
```
Zainicjuj `Viewer` klasa ze ścieżką źródłową dokumentu:
```csharp
using (Viewer viewer = new Viewer(documentPath))
{
    // Blok kodu będzie kontynuowany w następnym kroku
}
```
##### Krok 2: Skonfiguruj PngViewOptions
Utwórz instancję `PngViewOptions`, określając wzorzec nazewnictwa plików dla obrazów wyjściowych:
```csharp
PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
```
Skonfiguruj opcje przeglądarki, aby wyświetlać każdą stronę w jej oryginalnym rozmiarze:
```csharp
viewOptions.PdfOptions.RenderOriginalPageSize = true;
```
##### Krok 3: Renderuj strony dokumentu
Zadzwoń `View` metoda na twoją `Viewer` instancja, przekazując skonfigurowane opcje widoku:
```csharp
viewer.View(viewOptions);
```
### Porady dotyczące rozwiązywania problemów
- Sprawdź, czy ścieżki są poprawne i czy katalogi istnieją.
- Sprawdź, czy posiadasz uprawnienia umożliwiające odczyt danych z katalogów wejściowych i zapis do katalogów wyjściowych.

## Zastosowania praktyczne
1. **Digitalizacja dokumentów**:Konwertuj archiwalne dokumenty PDF na obrazy cyfrowe, aby ułatwić dostęp i dystrybucję.
2. **Portale internetowe**:Wyświetlaj podglądy dokumentów na stronach internetowych bez konieczności używania czytników PDF.
3. **Systemy zarządzania treścią (CMS)**:Integracja z platformami CMS umożliwia wydajne zarządzanie i wyświetlanie dużych ilości treści PDF.

## Rozważania dotyczące wydajności
Aby zoptymalizować wydajność aplikacji przy użyciu GroupDocs.Viewer dla .NET:
- Jeśli masz do czynienia z dużymi plikami, ogranicz użycie pamięci, przetwarzając dokumenty w blokach.
- W miarę możliwości należy stosować metody asynchroniczne, aby uniknąć blokowania wątków podczas renderowania.
- Pozbyć się `Viewer` instancji natychmiast po użyciu w celu zwolnienia zasobów.

## Wniosek
W tym samouczku dowiedziałeś się, jak renderować strony PDF jako obrazy PNG, zachowując ich oryginalne rozmiary, używając GroupDocs.Viewer dla .NET. Omówiliśmy konfigurację środowiska, konfigurację niezbędnych opcji dla uzyskania optymalnych wyników i zbadaliśmy praktyczne zastosowania tej funkcjonalności.

Kolejne kroki obejmują eksperymentowanie z innymi opcjami renderowania dostępnymi w GroupDocs.Viewer lub integrację z większymi projektami w celu ulepszenia możliwości zarządzania dokumentami.

## Sekcja FAQ
1. **Jaki jest najlepszy sposób obsługi dużych plików PDF za pomocą GroupDocs.Viewer?**
   - Przetwarzaj dokumenty w mniejszych fragmentach i stosuj metody asynchroniczne, aby utrzymać wydajność.
2. **Czy mogę dostosować nazwy plików wyjściowych PNG?**
   - Tak, poprzez określenie wzorca nazewnictwa w `PngViewOptions`.
3. **Czy możliwe jest renderowanie tylko określonych stron?**
   - Oczywiście, możesz skonfigurować `PageNumbers` W `PngViewOptions` aby określić, które strony mają być renderowane.
4. **Jak obsłużyć licencjonowanie GroupDocs.Viewer?**
   - Dostępne opcje to bezpłatny okres próbny, licencja tymczasowa lub zakup pełnej licencji.
5. **Czy tę konfigurację można stosować w aplikacjach internetowych?**
   - Tak, nadaje się do renderowania plików PDF po stronie serwera w ASP.NET Core i innych frameworkach internetowych opartych na platformie .NET.

## Zasoby
- [Dokumentacja](https://docs.groupdocs.com/viewer/net/)
- [Odniesienie do API](https://reference.groupdocs.com/viewer/net/)
- [Pobierz GroupDocs.Viewer](https://releases.groupdocs.com/viewer/net/)
- [Kup licencję](https://purchase.groupdocs.com/buy)
- [Bezpłatna wersja próbna](https://releases.groupdocs.com/viewer/net/)
- [Licencja tymczasowa](https://purchase.groupdocs.com/temporary-license/)
- [Forum wsparcia](https://forum.groupdocs.com/c/viewer/9)