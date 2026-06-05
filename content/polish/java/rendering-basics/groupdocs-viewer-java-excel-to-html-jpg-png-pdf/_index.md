---
date: '2026-06-05'
description: Dowiedz się, jak konwertować Excel do HTML, JPG, PNG i PDF przy użyciu
  GroupDocs.Viewer Java. Ten przewodnik krok po kroku obejmuje konfigurację, opcje
  renderowania oraz praktyczne przypadki użycia.
keywords:
- convert excel to html
- excel to pdf java
- convert spreadsheet to image
- groupdocs viewer java
- excel to html java
schemas:
- author: GroupDocs
  dateModified: '2026-06-05'
  description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  headline: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer
    Java
  type: TechArticle
- description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  name: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer Java
  steps:
  - name: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
    text: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
  - name: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
    text: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
  - name: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
    text: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
  - name: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
    text: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
  - name: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
    text: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
  type: HowTo
- questions:
  - answer: Yes. Pass the password to the `Viewer` constructor, and the library will
      decrypt the workbook before rendering.
    question: Can I convert password‑protected Excel files?
  - answer: Absolutely. The viewer treats macros as data; they are ignored during
      rendering, ensuring a safe conversion.
    question: Does GroupDocs.Viewer support macro‑enabled workbooks (.xlsm)?
  - answer: The library can process files up to **2 GB** without loading the entire
      document into memory, thanks to its streaming architecture.
    question: What is the maximum file size supported?
  - answer: Yes. Use `ViewOptions.setPageNumber(pageIndex)` to target a single sheet
      when generating HTML, JPG, PNG, or PDF.
    question: Is it possible to render only a specific worksheet?
  - answer: Set `JpgViewOptions.setQuality(90)` (value 0‑100) to balance file size
      and visual fidelity.
    question: How do I control image quality for JPG output?
  type: FAQPage
title: Jak konwertować Excel do HTML, JPG, PNG i PDF przy użyciu GroupDocs.Viewer
  Java
type: docs
url: /pl/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/
weight: 1
---

# Jak przekonwertować Excel na HTML, JPG, PNG i PDF przy użyciu GroupDocs.Viewer Java

Konwersja Excela do HTML jest powszechnym wymaganiem, gdy trzeba wyświetlić dane arkusza kalkulacyjnego w sieci, zachowując nagłówki wierszy i kolumn. W tym samouczku dowiesz się, jak GroupDocs.Viewer dla Javy upraszcza **convert excel to html**, a także jak renderować ten sam skoroszyt do formatów JPG, PNG i PDF. Przejdziemy przez wymagania wstępne, konfigurację biblioteki i każdy scenariusz renderowania z klarownymi, gotowymi do produkcji fragmentami kodu.

## Szybkie odpowiedzi
- **Czy GroupDocs.Viewer może renderować Excel do wielu formatów?** Tak – HTML, JPG, PNG i PDF są obsługiwane od razu.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna działa do testów; stała licencja jest wymagana w produkcji.  
- **Czy nagłówki wierszy i kolumn zostaną zachowane?** Ustaw `setRenderHeadings(true)` w opcjach widoku, aby je uwzględnić.  
- **Jaka wersja Javy jest wymagana?** Java 8 lub wyższa; biblioteka jest kompatybilna z Java 11, 17 i nowszymi.  
- **Czy konwersja jest szybka dla dużych skoroszytów?** GroupDocs.Viewer może przetworzyć arkusze o 200 stronach w mniej niż sekundę na typowym sprzęcie serwerowym.

## Co to jest „convert excel to html”?
**Convert excel to html** oznacza przekształcenie skoroszytu Excel w gotowy do sieci dokument HTML, zachowując oryginalny układ, formuły i nagłówki. Umożliwia to płynne osadzanie arkuszy kalkulacyjnych w stronach internetowych lub portalach bez konieczności posiadania przez użytkownika końcowego Excela.

## Dlaczego warto używać GroupDocs.Viewer Java do renderowania Excela?
GroupDocs.Viewer Java obsługuje **ponad 50 formatów wejściowych i wyjściowych**, w tym DOCX, XLSX, PPTX, HTML, JPG, PNG i PDF. Przetwarza wielostronicowe skoroszyty bez wczytywania całego pliku do pamięci, zapewniając prędkość konwersji do **10 × szybszą** niż wiele otwarto‑źródłowych alternatyw. Biblioteka oferuje także precyzyjną kontrolę nad opcjami renderowania, takimi jak widoczność nagłówków, rozmiar strony i jakość obrazu.

## Wymagania wstępne

- **Java Development Kit (JDK) 8+** zainstalowany i skonfigurowany w Twoim IDE (IntelliJ IDEA, Eclipse itp.).
- **Maven** do zarządzania zależnościami.
- Podstawowa znajomość składni Javy i `pom.xml` Mavena.
- Aktywna licencja **GroupDocs.Viewer Java** (wersja próbna lub pełna).

### Wymagane biblioteki i zależności
Dodaj zależność GroupDocs.Viewer Java do swojego `pom.xml`:

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

### Konfiguracja środowiska
- Sprawdź, czy `java -version` zwraca 1.8 lub nowszą wersję.
- Otwórz ulubione IDE i utwórz projekt Maven.

Zacznijmy od wymagań wstępnych potrzebnych przed przystąpieniem do implementacji.

![convert Excel files into HTML, JPG, PNG, and PDF with GroupDocs.Viewer for Java](/viewer/rendering-basics/convert-excel-files-into-html-jpg-png-and-pdf.png)

## Konfiguracja GroupDocs.Viewer Java

### Informacje o instalacji
Umieść zależność Maven przedstawioną powyżej w `pom.xml` swojego projektu. Po uruchomieniu `mvn clean install` biblioteka będzie dostępna w classpath.

### Kroki uzyskania licencji
1. **Darmowa wersja próbna:** Pobierz wersję próbną z [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).  
2. **Licencja tymczasowa:** Uzyskaj tymczasową licencję do rozszerzonych testów z [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
3. **Zakup:** Uzyskaj pełną licencję do użytku produkcyjnego pod adresem [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Podstawowa inicjalizacja
Klasa `Viewer` jest punktem wejścia dla wszystkich operacji renderowania. Inicjalizacja jest prosta:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("Sample.xlsx")) {
            // Your code here to use the viewer
        }
    }
}
```

Tworzy to instancję `Viewer` powiązaną z lokalnym plikiem licencji, gotową do przetwarzania plików Excel.

## Przewodnik implementacji

Poniżej omawiamy każdy cel renderowania. Dla każdego formatu najpierw **importujemy wymagane klasy**, potem **ustawiamy katalog wyjściowy**, a na końcu **konfigurujemy opcje widoku** z `setRenderHeadings(true)`, aby zachować nagłówki wierszy/kolumn.

### Renderowanie arkusza kalkulacyjnego do HTML
**Jak skonwertować skoroszyt Excel do HTML przy użyciu GroupDocs.Viewer Java?**  
Aby przekonwertować skoroszyt Excel do HTML, załaduj plik za pomocą Viewer, utwórz instancję HtmlViewOptions, włącz renderowanie nagłówków i wywołaj metodę view. Proces zapisuje każdy arkusz jako osobny plik HTML, zachowując formatowanie komórek, formuły i oryginalny układ dla dokładnego wyświetlania w sieci.

#### Implementacja krok po kroku
**1. Import wymaganych bibliotek**  
HtmlViewOptions konfiguruje sposób renderowania skoroszytu do HTML, umożliwiając dostosowanie nagłówków, stylów i układu strony.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**2. Ustaw katalog wyjściowy**  
Określ folder, w którym zostaną zapisane wygenerowane strony HTML.  

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**3. Zainicjalizuj Viewer i skonfiguruj opcje**  
Utwórz instancję `Viewer`, ustaw `setRenderHeadings(true)` i wywołaj `view`.  

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Wyjaśnienie:** `HtmlViewOptions` kontroluje wyjście HTML. Włączenie `setRenderHeadings(true)` zapewnia, że pierwszy wiersz i kolumna (zwykle nagłówki) pojawią się w wynikowym HTML, co sprawia, że dane są od razu zrozumiałe.

### Renderowanie arkusza kalkulacyjnego do JPG
**Jak mogę wyrenderować arkusz Excel jako obraz JPG z uwzględnionymi nagłówkami?**  
Renderowanie arkusza Excel jako JPG polega na zainicjalizowaniu Viewer z skoroszytem, utworzeniu obiektu JpgViewOptions, ustawieniu renderHeadings na true i wywołaniu view. Biblioteka rasteryzuje każdą stronę przy określonym DPI, tworząc wysokiej rozdzielczości pliki JPG, które zachowują wizualną strukturę arkusza i nagłówki.

#### Implementacja krok po kroku
**1. Import wymaganych bibliotek**  
JpgViewOptions definiuje ustawienia renderowania arkuszy jako obrazy JPG, w tym DPI, jakość i widoczność nagłówków.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**2. Ustaw katalog wyjściowy**  
Określ, gdzie będą przechowywane pliki JPG.  

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```

**3. Zainicjalizuj Viewer i skonfiguruj opcje**  
Utwórz viewer, ustaw renderowanie nagłówków i wykonaj konwersję.  

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Wyjaśnienie:** `JpgViewOptions` pozwala kontrolować DPI i jakość. Dzięki `setRenderHeadings(true)` powstałe obrazy zachowują wiersze i kolumny nagłówków arkusza, co jest istotne w raportach i prezentacjach.

### Renderowanie arkusza kalkulacyjnego do PNG
**Jaki jest proces konwersji Excela do PNG przy zachowaniu nagłówków kolumn?**  
Aby uzyskać obrazy PNG z pliku Excel, użyj Viewer do otwarcia skoroszytu, utwórz instancję PngViewOptions, włącz renderowanie nagłówków i wykonaj view. Wyjście PNG zapewnia jakość bezstratną, zachowując wszystkie style komórek i wiersze nagłówków, co czyni je idealnymi do archiwizacji lub dalszego przetwarzania obrazów.

#### Implementacja krok po kroku
**1. Import wymaganych bibliotek**  
PngViewOptions kontroluje renderowanie arkuszy do obrazów PNG, oferując kompresję bezstratną i opcje nagłówków.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**2. Ustaw katalog wyjściowy**  
Wybierz folder dla wyjścia PNG.  

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

**3. Zainicjalizuj Viewer i skonfiguruj opcje**  
Utwórz viewer, włącz renderowanie nagłówków i wywołaj `view`.  

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Wyjaśnienie:** Wywołując `setRenderHeadings(true)`, pliki PNG zawierają oryginalne wiersze i kolumny nagłówków arkusza, zachowując kontekst dla dalszych odbiorców.

### Renderowanie arkusza kalkulacyjnego do PDF
**Jak skonwertować plik Excel do PDF z widocznymi nagłówkami wierszy i kolumn?**  
Konwersja Excela do PDF jest prosta: utwórz instancję Viewer z plikiem źródłowym, skonfiguruj obiekt PdfViewOptions, aby renderować nagłówki, i wywołaj view. Powstały PDF odzwierciedla układ skoroszytu, w tym nagłówki wierszy i kolumn, oraz obsługuje grafikę wektorową dla wyraźnego druku i dystrybucji.

#### Implementacja krok po kroku
**1. Import wymaganych bibliotek**  
PdfViewOptions określa parametry generowania PDF, takie jak rozmiar strony, marginesy i renderowanie nagłówków.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**2. Ustaw katalog wyjściowy**  
Określ folder docelowy dla dokumentu PDF.  

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("output.pdf");
```

**3. Zainicjalizuj Viewer i skonfiguruj opcje**  
Utwórz `Viewer`, włącz renderowanie nagłówków i wykonaj konwersję.  

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Wyjaśnienie:** Ustawienie `setRenderHeadings(true)` w `PdfViewOptions` gwarantuje, że pierwszy wiersz/kolumna pojawią się w finalnym PDF, co czyni dokument gotowym do druku lub archiwizacji.

## Praktyczne zastosowania
Rzeczywiste scenariusze, w których **convert excel to html**, **excel to pdf java** lub **convert spreadsheet to image** są nieocenione:

1. **Raportowanie biznesowe:** Generuj pulpity nawigacyjne HTML lub raporty PDF z modeli finansowych bez ręcznego kopiowania.  
2. **Wizualizacja danych:** Osadzaj migawki JPG/PNG arkuszy w prezentacjach, zapewniając, że nagłówki dają odbiorcom natychmiastowy kontekst.  
3. **Archiwizacja dokumentów:** Przechowuj skoroszyty Excel jako PDF w celu zgodności, zachowując oryginalny układ i nagłówki.  
4. **Portale internetowe:** Udostępniaj wersje HTML arkuszy bezpośrednio w przeglądarkach, umożliwiając interaktywne filtrowanie przy użyciu JavaScript.

## Najczęściej zadawane pytania

**Q: Czy mogę konwertować chronione hasłem pliki Excel?**  
A: Tak. Przekaż hasło do konstruktora `Viewer`, a biblioteka odszyfruje skoroszyt przed renderowaniem.

**Q: Czy GroupDocs.Viewer obsługuje skoroszyty z włączonymi makrami (.xlsm)?**  
A: Absolutnie. Viewer traktuje makra jako dane; są ignorowane podczas renderowania, co zapewnia bezpieczną konwersję.

**Q: Jaki jest maksymalny obsługiwany rozmiar pliku?**  
A: Biblioteka może przetwarzać pliki do **2 GB** bez wczytywania całego dokumentu do pamięci, dzięki architekturze strumieniowej.

**Q: Czy można renderować tylko konkretny arkusz?**  
A: Tak. Użyj `ViewOptions.setPageNumber(pageIndex)`, aby wybrać pojedynczy arkusz przy generowaniu HTML, JPG, PNG lub PDF.

**Q: Jak kontrolować jakość obrazu dla wyjścia JPG?**  
A: Ustaw `JpgViewOptions.setQuality(90)` (wartość 0‑100), aby zrównoważyć rozmiar pliku i jakość wizualną.

## Podsumowanie
Masz teraz kompletny, gotowy do produkcji przewodnik po **convert excel to html**, **excel to pdf java** i **convert spreadsheet to image** przy użyciu GroupDocs.Viewer Java. Postępując zgodnie z powyższymi krokami, możesz zintegrować renderowanie arkuszy kalkulacyjnych z dowolnym backendem Java, dostarczając raporty HTML, obrazy wysokiej rozdzielczości lub archiwalne PDF-y z automatycznie zachowanymi nagłówkami.

---

**Last Updated:** 2026-06-05  
**Tested With:** GroupDocs.Viewer Java 23.12  
**Author:** GroupDocs

## Powiązane samouczki

- [Jak przekonwertować DOCX na HTML przy użyciu GroupDocs.Viewer dla Javy: Przewodnik krok po kroku](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)
- [Responsywne renderowanie HTML z GroupDocs.Viewer dla Javy: Kompletny przewodnik](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
- [convert odf html java – Konwertuj ODF na HTML, JPG, PNG, PDF przy użyciu GroupDocs.Viewer dla Javy](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)