---
date: '2026-06-15'
description: Dowiedz się, jak konwertować Excel do PDF w Javie i dzielić arkusze Excel
  według rows and columns przy użyciu GroupDocs Viewer. Zawiera setup, code i best
  practices.
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
schemas:
- author: GroupDocs
  dateModified: '2026-06-15'
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  type: TechArticle
- description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  steps:
  - name: Set Up Paths and Initialize the Viewer
    text: First, define where the split pages will be saved and create a `Viewer`
      instance for the source workbook.
  - name: Configure Rows Per Page
    text: Tell the viewer how many rows each page should contain.
  - name: Render the Document
    text: Finally, render the workbook using the options you defined.
  - name: Set Up Paths and Initialize the Viewer
    text: The setup mirrors the row‑only example, only the file name changes.
  - name: Configure Rows and Columns Per Page
    text: Specify both dimensions to create a grid‑style split.
  - name: Render the Document
    text: Render using the same `view` call.
  type: HowTo
- questions:
  - answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
    question: Can I generate a PDF instead of HTML?
  - answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
    question: Is it possible to split based on cell content rather than fixed rows/columns?
  - answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
    question: Does GroupDocs Viewer support older Excel formats (XLS)?
  - answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
    question: How do I embed the generated HTML into a Spring MVC view?
  - answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
    question: What license do I need for commercial deployment?
  type: FAQPage
title: Konwertuj Excel do PDF w Javie i podziel arkusze według Rows & Columns
type: docs
url: /pl/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# Konwertuj Excel do PDF w Javie i podziel arkusze według wierszy i kolumn (Java)

Duże skoroszyty Excel często zawierają więcej danych niż można wygodnie wyświetlić na jednym ekranie lub wydrukować na jednej stronie. **convert excel to pdf java** jest powszechnym wymaganiem, gdy potrzebny jest statyczny, łatwy do udostępnienia format, podczas gdy **splitting Excel sheets by rows and columns** ułatwia konsumowanie danych w układach internetowych lub drukowanych. W tym przewodniku przeprowadzimy oba zadania przy użyciu **GroupDocs Viewer for Java**, pokażemy, jak skonfigurować paginację oraz wyjaśnimy najlepsze praktyki dotyczące wydajności i rozwiązywania problemów.

![Podziel arkusze Excel według wierszy i kolumn przy użyciu GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[Podziel arkusze Excel według wierszy i kolumn przy użyciu GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## Szybkie odpowiedzi
- **Jakiej biblioteki użyto?** GroupDocs Viewer for Java.  
- **Czy mogę podzielić zarówno wiersze, jak i kolumny?** Tak – możesz zdefiniować rows‑per‑page i columns‑per‑page razem.  
- **Czy potrzebuję licencji?** Licencja próbna lub tymczasowa działa w fazie rozwoju; pełna licencja jest wymagana w środowisku produkcyjnym.  
- **Jakie formaty wyjściowe są obsługiwane?** Pokazano HTML (zasoby osadzone); PDF można wygenerować przy użyciu tych samych opcji.  
- **Czy Maven jest wymagany?** Maven jest zalecaną metodą zarządzania zależnościami.  
- **Czy mogę także konwertować Excel do PDF?** Oczywiście – wystarczy zamienić `HtmlViewOptions` na `PdfViewOptions` i ponownie użyć tych samych ustawień paginacji.

## Co to jest „Jak podzielić Excel”?
Podzielenie arkusza Excel oznacza rozdzielenie pojedynczego arkusza roboczego na wiele stron lub plików w oparciu o stałą liczbę wierszy, kolumn lub obu tych elementów. Technika ta jest przydatna, gdy trzeba tworzyć raporty paginowane, osadzać dane w stronach internetowych lub generować sekcje do druku bez ładowania całego skoroszytu naraz.

## Dlaczego używać GroupDocs Viewer for Java?
GroupDocs Viewer przetwarza arkusze kalkulacyjne w jednym przebiegu i automatycznie je paginuje, eliminując ręczne obliczenia. **Szybkie renderowanie przetwarza 250‑stronnicowy skoroszyt XLSX w mniej niż 2 sekundy na typowym serwerze dwurdzeniowym**, a **biblioteka obsługuje ponad 50 formatów wejściowych i wyjściowych**, w tym XLS, XLSX, CSV, PDF i HTML. Działa na każdej platformie zgodnej z JVM — Windows, Linux, macOS, kontenery Docker lub środowiska serverless w chmurze — więc możesz ją zintegrować tam, gdzie działa Twoja aplikacja Java.

## Wymagania wstępne
- Java 17 lub nowsza zainstalowana.  
- IDE, takie jak IntelliJ IDEA lub Eclipse.  
- Maven do zarządzania zależnościami.  
- Podstawowa znajomość Javy oraz obsługi plików Excel.

### Wymagane biblioteki, wersje i zależności
Dodaj repozytorium GroupDocs oraz zależność viewer do swojego `pom.xml`:

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

### Uzyskanie licencji
Uzyskaj darmową wersję próbną, tymczasową licencję lub zakup pełną licencję od [GroupDocs](https://purchase.groupdocs.com/buy).

## Jak konwertować Excel do PDF w Javie?

Klasa `Viewer` jest podstawowym komponentem GroupDocs Viewer, który ładuje dokument i udostępnia metody renderowania dla różnych formatów wyjściowych. `SpreadsheetOptions` pozwala kontrolować ustawienia paginacji, takie jak rows‑per‑page i columns‑per‑page przy renderowaniu arkuszy kalkulacyjnych.

Załaduj plik Excel przy pomocy `new Viewer("source.xlsx")`, skonfiguruj `SpreadsheetOptions` dla paginacji i wywołaj `viewer.view(pdfOptions, stream)` – to jednorazowe wywołanie konwertuje skoroszyt do PDF, respektując ustalone limity wierszy/kolumn. Konwersja zachowuje formuły, obrazy i style komórek, dostarczając wierną kopię PDF gotową do dystrybucji.

## Jak podzielić arkusze Excel według wierszy

Podzielenie według wierszy tworzy serię stron HTML, z których każda zawiera stałą liczbę wierszy (np. 15). Podejście to jest idealne dla pulpitów wyświetlających ograniczoną liczbę rekordów na widok. Viewer wygeneruje osobne pliki HTML, takie jak `page_0.html`, `page_1.html` itd., każdy zawierający określoną liczbę wierszy. Umożliwia to ładowanie tylko potrzebnej części w interfejsie webowym, zmniejszając zużycie pasma i czas renderowania.

### Definicja kotwicy
`Viewer` jest podstawową klasą GroupDocs Viewer, która ładuje dokument i koordynuje renderowanie do wybranego formatu wyjściowego.

### Implementacja krok po kroku

#### Krok 1: Ustaw ścieżki i zainicjalizuj Viewer
Najpierw określ, gdzie zostaną zapisane podzielone strony i utwórz instancję `Viewer` dla źródłowego skoroszytu.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### Krok 2: Skonfiguruj wiersze na stronę
Powiedz viewerowi, ile wierszy ma znajdować się na każdej stronie.

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### Krok 3: Renderuj dokument
Na koniec renderuj skoroszyt przy użyciu zdefiniowanych opcji.

```java
viewer.view(viewOptions);
```

## Jak podzielić arkusze Excel według wierszy i kolumn

Czasami pojedyncza strona musi wyświetlać macierz wierszy **i** kolumn (np. 15 wierszy × 7 kolumn). Daje to pełną kontrolę nad układem każdej strony HTML. Powstałe strony wyświetlają prostokątny blok komórek, np. wiersze 1‑15 i kolumny A‑G na pierwszej stronie, wiersze 16‑30 i kolumny H‑N na kolejnej. Pagowanie w stylu siatki jest przydatne przy tworzeniu raportów do druku, które pasują do standardowych rozmiarów papieru.

### Definicja kotwicy
`SpreadsheetOptions` konfiguruje, ile wierszy i kolumn pojawia się na każdej generowanej stronie.

### Implementacja krok po kroku

#### Krok 1: Ustaw ścieżki i zainicjalizuj Viewer
Ustawienia są analogiczne do przykładu podziału tylko wierszy, zmienia się jedynie nazwa pliku.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### Krok 2: Skonfiguruj wiersze i kolumny na stronę
Określ oba wymiary, aby stworzyć podział w stylu siatki.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### Krok 3: Renderuj dokument
Renderuj przy użyciu tego samego wywołania `view`.

```java
viewer.view(options);
```

## Praktyczne zastosowania
- **Generate Excel report Java**: Przekształć duże modele finansowe w serię paginowanych raportów HTML.  
- **GroupDocs Viewer Excel**: Osadź podzielone strony bezpośrednio w portalu internetowym dla interaktywnej eksploracji danych.  
- **Render Excel HTML Java**: Udostępnij wygenerowane strony HTML za pośrednictwem servletu lub kontrolera Spring dla szybkiego renderowania po stronie klienta.  

## Rozważania dotyczące wydajności
- **Memory usage** – Duże skoroszyty mogą zużywać znaczną ilość pamięci heap; rozważ zwiększenie ustawienia JVM `-Xmx`.  
- **Chunk size** – Wybierz liczbę wierszy/kolumn, która równoważy rozmiar strony i szybkość renderowania.  
- **Version updates** – Utrzymuj GroupDocs Viewer w najnowszej wersji, aby korzystać z ulepszeń wydajności; najnowsze wydanie 25.2 zwiększa szybkość renderowania nawet o 30 % w porównaniu z 24.x.

## Typowe problemy i rozwiązywanie

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|---------|--------------|-----|
| `OutOfMemoryError` | Renderowanie bardzo dużego arkusza z zbyt wieloma wierszami na stronę | Zredukuj `countRowsPerPage` lub zwiększ pamięć heap JVM |
| Puste pliki wyjściowe | Nieprawidłowa ścieżka pliku lub brak uprawnień do zapisu | Sprawdź, czy `outputDirectory` istnieje i jest zapisywalny |
| Zasoby HTML nie ładują się | Używanie `forEmbeddedResources`, ale serwowanie plików z innego bazowego URL | Serwuj cały folder wyjściowy lub przełącz na `forExternalResources` |

## Najczęściej zadawane pytania

**Q: Czy mogę wygenerować PDF zamiast HTML?**  
A: Tak. Zastąp `HtmlViewOptions` przez `PdfViewOptions` i zachowaj tę samą konfigurację `SpreadsheetOptions`.

**Q: Czy istnieje możliwość podziału w oparciu o zawartość komórek, a nie stałe wiersze/kolumny?**  
A: Podział oparty na zawartości nie jest wbudowany w GroupDocs Viewer, ale możesz wstępnie przetworzyć skoroszyt przy pomocy Apache POI, aby utworzyć osobne arkusze przed renderowaniem.

**Q: Czy GroupDocs Viewer obsługuje starsze formaty Excel (XLS)?**  
A: Absolutnie. Viewer obsługuje XLS, XLSX, CSV i inne formaty arkuszy kalkulacyjnych.

**Q: Jak osadzić wygenerowany HTML w widoku Spring MVC?**  
A: Udostępnij folder wyjściowy jako zasób statyczny i odwołuj się do wygenerowanych `page_0.html`, `page_1.html` itd. w szablonach Thymeleaf lub JSP.

**Q: Jaką licencję potrzebuję do wdrożenia komercyjnego?**  
A: Wymagana jest pełna licencja produkcyjna od GroupDocs; licencje trial są przeznaczone wyłącznie do oceny.

## Zasoby
- **Dokumentacja**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Referencja API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Pobierz**: [GroupDocs Viewer Java Releases](https://releases.groupdocs.com/viewer/java/)
- **Kup licencję GroupDocs**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Bezpłatna wersja próbna**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Uzyskaj tymczasową licencję**: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Forum wsparcia GroupDocs**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Ostatnia aktualizacja:** 2026-06-15  
**Testowano z:** GroupDocs Viewer 25.2 for Java  
**Autor:** GroupDocs  

## Powiązane samouczki

- [Renderowanie ukrytych wierszy i kolumn w arkuszach Java przy użyciu GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Pomijanie renderowania pustych wierszy w Javie przy użyciu GroupDocs.Viewer: przewodnik wydajnościowy](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [Kompletny przewodnik: konwersja Excel 2003 XML do HTML/JPG/PNG/PDF przy użyciu GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)