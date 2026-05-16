---
date: '2026-02-18'
description: Naucz się konwertować pliki WMZ i WMF na PDF, HTML, JPG i PNG przy użyciu
  GroupDocs Viewer dla Javy. Ten przewodnik obejmuje GroupDocs Viewer Java oraz konwersję
  grafiki wektorowej w Javie.
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: Jak konwertować WMZ na PDF i inne formaty przy użyciu GroupDocs Viewer dla
  Javy
type: docs
url: /pl/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# Jak konwertować WMZ do PDF i innych formatów przy użyciu GroupDocs Viewer dla Javy

Konwertowanie plików WMZ (Web Metafile) i WMF (Windows Metafile) do bardziej dostępnych formatów — szczególnie **convert WMZ to PDF** — może być trudne, ponieważ te formaty grafiki wektorowej przechowują instrukcje rysowania, a nie dane pikseli. Dzięki **GroupDocs Viewer for Java** możesz renderować dokumenty WMZ/WMF do HTML, JPG, PNG, **PDF** i innych popularnych formatów w zaledwie kilku linijkach kodu.

![Konwertuj dokumenty WMZ/WMF przy użyciu GroupDocs.Viewer dla Javy](/viewer/export-conversion/convert-wmz-wmf-documents.png)

W tym samouczku dowiesz się, jak skonfigurować bibliotekę, renderować pliki WMZ/WMF do żądanego formatu wyjściowego oraz radzić sobie z typowymi problemami. Po zakończeniu będziesz mógł zintegrować **groupdocs viewer java** ze swoimi aplikacjami Java, aby **java convert vector graphics** szybko i niezawodnie.

## Szybkie odpowiedzi
- **Jakie formaty można konwertować z WMZ/WMF?** HTML, JPG, PNG i PDF są w pełni obsługiwane.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna działa do testów; licencja komercyjna usuwa ograniczenia wersji ewaluacyjnej.  
- **Jakiej wersji Java wymaga?** Zalecana jest Java 8 lub nowsza.  
- **Czy mogę renderować tylko wybrane strony?** Tak, możesz określić zakresy stron w opcjach widoku.  
- **Czy zużycie pamięci jest problemem przy dużych plikach?** Użyj try‑with‑resources i renderuj tylko potrzebne strony, aby utrzymać niskie zużycie pamięci.

## Co to jest „convert WMZ to PDF”?
Konwersja WMZ do PDF oznacza pobranie wektorowego pliku WMZ i rasteryzację (lub zachowanie danych wektorowych) w kontenerze PDF. PDF jest powszechnie wyświetlany, przeszukiwalny i drukowalny, co czyni go idealnym do archiwizacji i udostępniania grafiki WMZ.

## Dlaczego warto używać GroupDocs Viewer dla Javy do konwersji grafiki wektorowej?
- **Wysoka wierność**: Biblioteka zachowuje oryginalną jakość rysunku, niezależnie od tego, czy wyjściem jest PDF czy PNG.  
- **Zero zewnętrznych zależności**: Nie ma potrzeby używania natywnych bibliotek Windows; wszystko działa na dowolnej platformie z JDK.  
- **Proste API**: Jedna instancja `Viewer` i pojedyncze wywołanie `view` obsługują całą konwersję.  
- **Skalowalne**: Działa równie dobrze dla jednopostaciowych ikon i wielostronicowych rysunków technicznych.

## Wymagania wstępne

### Wymagane biblioteki
- **GroupDocs.Viewer for Java** – rdzeń silnika renderującego.  
- Java Development Kit (JDK) 8+.

### Konfiguracja środowiska
- IDE, takie jak IntelliJ IDEA lub Eclipse.  
- Maven do zarządzania zależnościami (lub Gradle, jeśli wolisz).

### Wymagania wiedzy
- Znajomość Java I/O (`java.nio.file.Path`).  
- Podstawowa znajomość sposobu renderowania treści przez przeglądarki dokumentów.

## Konfiguracja GroupDocs.Viewer dla Javy

Dodaj repozytorium i zależność do swojego `pom.xml`:

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

> **Wskazówka dotycząca licencji:** Użyj darmowej wersji próbnej do oceny, a następnie zastosuj tymczasową lub zakupioną licencję, aby odblokować pełną funkcjonalność.

Po rozwiązaniu zależności możesz utworzyć instancję `Viewer`, którą będziesz ponownie wykorzystywać w każdym kroku konwersji.

## Przewodnik implementacji

Przejdziemy przez cztery scenariusze konwersji: HTML, JPG, PNG i PDF. Każdy przykład stosuje ten sam schemat — definiuje ścieżkę wyjściową, tworzy instancję `Viewer` z plikiem źródłowym WMZ, konfiguruje odpowiednie opcje widoku i wywołuje `view`.

### Renderowanie WMZ/WMF do HTML

#### Przegląd
Wyjście HTML pozwala osadzić grafikę bezpośrednio w stronach internetowych, przy czym wszystkie zasoby (obrazy, CSS) znajdują się w jednym pliku.

**Krok 1: Definiowanie ścieżki katalogu wyjściowego**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Krok 2: Inicjalizacja Viewer i renderowanie do HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### Renderowanie WMZ/WMF do JPG

#### Przegląd
JPG jest szeroko wspieranym formatem rastrowym, idealnym do szybkich podglądów lub załączników e‑mail.

**Krok 1: Definiowanie ścieżki katalogu wyjściowego**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Krok 2: Inicjalizacja Viewer i renderowanie do JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderowanie WMZ/WMF do PNG

#### Przegląd
PNG obsługuje przezroczystość, co czyni go idealnym dla grafik, które muszą łączyć się z różnymi tłami.

**Krok 1: Definiowanie ścieżki katalogu wyjściowego**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Krok 2: Inicjalizacja Viewer i renderowanie do PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderowanie WMZ/WMF do PDF

#### Przegląd
PDF zapewnia platformowo‑niezależny, przeszukiwalny dokument, który zachowuje oryginalny układ.

**Krok 1: Definiowanie ścieżki katalogu wyjściowego**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Krok 2: Inicjalizacja Viewer i renderowanie do PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| **OutOfMemoryError** przy dużych plikach WMZ | Viewer ładuje cały dokument do pamięci | Renderuj jedną stronę na raz używając `PageStreamViewOptions` lub zwiększ pamięć JVM (`-Xmx`). |
| **Brakujące czcionki** w PDF | Czcionka nie jest osadzona w źródłowym WMZ | Zainstaluj wymagane czcionki na maszynie hosta lub użyj `FontSettings`, aby dostarczyć czcionki niestandardowe. |
| **Pusty wynik PNG** | Nieprawidłowa ścieżka wyjściowa lub niewystarczające uprawnienia do zapisu | Sprawdź, czy `outputDirectory` istnieje i aplikacja ma dostęp do zapisu. |
| **Zasoby HTML nie ładują się** | Użycie `forExternalResources` bez kopiowania plików | Użyj `forEmbeddedResources` dla samodzielnego pliku HTML. |

## Najczęściej zadawane pytania

**P: Czy mogę konwertować WMF do PNG używając tego samego kodu?**  
A: Tak. Przykład PNG działa zarówno dla plików WMZ, jak i WMF; wystarczy zamienić `TestFiles.SAMPLE_WMZ` na swój plik WMF.

**P: Czy można konwertować tylko podzbiór stron?**  
A: Oczywiście. Użyj `PdfViewOptions` (lub odpowiednich opcji dla innych formatów) i wywołaj `setPageNumbers(List<Integer>)` przed renderowaniem.

**P: Czy potrzebna jest osobna licencja dla każdego formatu wyjściowego?**  
A: Nie. Jedna licencja GroupDocs Viewer obejmuje wszystkie obsługiwane formaty, w tym HTML, JPG, PNG i PDF.

**P: Jak “java convert vector graphics” wpływa na wydajność?**  
A: Konwersja wektor‑do‑rastera jest intensywna pod względem CPU. Przy dużych partiach rozważ wielowątkowość i ponowne użycie jednej instancji `Viewer` dla wielu plików.

**P: Czy PDF zachowa jakość wektorową, czy zostanie rasteryzowany?**  
A: Podczas konwersji WMZ/WMF do PDF, GroupDocs Viewer zachowuje instrukcje wektorowe, gdy to możliwe, co skutkuje skalowalnym PDF.

## Podsumowanie

Masz teraz kompletny, gotowy do produkcji przewodnik, jak **convert WMZ to PDF** i inne popularne formaty przy użyciu **GroupDocs Viewer for Java**. Niezależnie od tego, czy tworzysz usługę internetową serwującą grafiki w locie, czy narzędzie archiwizujące przechowujące dokumenty jako PDF, powyższe kroki pomogą Ci szybko osiągnąć cel.

---

**Ostatnia aktualizacja:** 2026-02-18  
**Testowano z:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs