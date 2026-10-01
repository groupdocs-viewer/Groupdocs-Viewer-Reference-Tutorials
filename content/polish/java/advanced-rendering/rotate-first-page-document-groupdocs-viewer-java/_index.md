---
date: '2026-09-30'
description: Dowiedz się, jak obrócić stronę o 90 stopni w Javie przy użyciu GroupDocs
  Viewer, w tym konfigurację, kod oraz wskazówki dotyczące wydajności.
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: Obróć stronę o 90 stopni w Javie przy użyciu GroupDocs Viewer. Przewodnik
  krok po kroku, wskazówki dotyczące wydajności oraz praktyczne przykłady zastosowań
  dla programistów.
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: Obróć stronę o 90 stopni za pomocą GroupDocs Viewer dla Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: Obróć stronę o 90 stopni za pomocą GroupDocs Viewer dla Java
type: docs
url: /pl/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---


# Obróć stronę o 90 stopni przy użyciu GroupDocs Viewer dla Javy

Jeśli potrzebujesz **obrócić stronę o 90 stopni** w dokumencie — niezależnie od tego, czy jest to PDF, plik Word czy arkusz kalkulacyjny — wykonanie tego programowo w Javie oszczędza czas, eliminuje błędy ręczne i pozwala wbudować operację w zautomatyzowane potoki. W tym zaawansowanym przewodniku dowiesz się, jak obrócić pierwszą stronę dowolnego obsługiwanego dokumentu przy użyciu **GroupDocs Viewer for Java**, dlaczego ta funkcja ma znaczenie w rzeczywistych projektach oraz jak utrzymać proces lekki i efektywny pod względem pamięci.

![Obróć pierwszą stronę dokumentu przy użyciu GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Szybkie odpowiedzi
- **Co oznacza „rotate page 90 degrees”?** Obraca wybraną stronę zgodnie z ruchem wskazówek zegara o ćwierć obrotu.  
- **Która biblioteka obsługuje rotację?** GroupDocs Viewer for Java udostępnia metodę `rotatePage`.  
- **Czy mogę obracać strony PDF w Javie?** Tak — użyj tej samej metody `rotatePage`; działa dla PDF, DOCX, XLSX i innych.  
- **Czy potrzebna jest licencja?** Bezpłatna wersja próbna działa w środowisku deweloperskim; płatna licencja jest wymagana w produkcji.  
- **Czy operacja jest intensywna pod względem pamięci?** Nie, jeśli szybko zamkniesz instancję `Viewer`; zobacz wskazówki dotyczące wydajności poniżej.

## Co to jest „rotate page 90 degrees”?
Obrócenie strony o 90 stopni zmienia jej orientację z pionowej na poziomą (lub odwrotnie) bez zmiany zawartości. Jest to przydatne przy prezentacjach, drukowaniu grafik wyłącznie w trybie poziomym lub korekcji zeskanowanych dokumentów, które zostały zarejestrowane bokiem. Rotacja jest stosowana w czasie renderowania, pozostawiając oryginalny plik niezmieniony.

## Dlaczego obracać strony programowo przy użyciu GroupDocs Viewer for Java?
GroupDocs Viewer obsługuje **ponad 50 formatów wejściowych i wyjściowych** — w tym PDF, DOCX, PPTX, XLSX i wiele typów obrazów — dzięki czemu możesz renderować dowolny dokument bez zewnętrznych konwerterów. API jest płynne, bezpieczne wątkowo i działa na dowolnym środowisku Java 8+, co czyni je niezawodnym wyborem dla automatyzacji klasy enterprise, która musi konsekwentnie obsługiwać dziesiątki typów plików.

## Wymagania wstępne

- GroupDocs Viewer for Java (najnowsza wersja)
- JDK 8 lub nowszy
- Maven (lub Gradle) do zarządzania zależnościami
- IDE, takie jak IntelliJ IDEA lub Eclipse
- Podstawowa znajomość Java I/O

## Konfiguracja GroupDocs.Viewer dla Java

Dodaj repozytorium GroupDocs i zależność do swojego `pom.xml`. Ten fragment pozostaje niezmieniony w stosunku do oryginalnego samouczka:

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
- **Free trial** – pobierz ze strony GroupDocs.  
- **Temporary license** – zamów, jeśli potrzebujesz wydłużonego okresu oceny.  
- **Full license** – zakup do wdrożeń produkcyjnych.

### Podstawowa inicjalizacja Viewer
Klasa `Viewer` jest punktem wejścia, który ładuje dokument i udostępnia metody renderowania oraz transformacji. Zachowaj kod dokładnie taki, jak pokazano:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Jak obrócić stronę PDF w Javie przy użyciu GroupDocs Viewer
Załaduj docelowy plik przy użyciu `Viewer`, określ numer strony i wywołaj `rotatePage`. Metoda działa dla PDF, DOCX, PPTX, XLSX oraz innych formatów obsługiwanych przez bibliotekę. Po rotacji możesz wyrenderować dokument do nowego PDF lub przesłać go bezpośrednio do klienta, zapewniając, że oryginalny plik pozostaje nienaruszony.

## Implementacja krok po kroku: obrót pierwszej strony o 90 stopni

### 1. Importuj wymagane pakiety
`PdfViewOptions` informuje Viewer, aby wyjściowo generował plik PDF, natomiast enum `Rotation` definiuje kąt. Obie klasy należą do pakietu `com.groupdocs.viewer.options`.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Zdefiniuj lokalizacje wyjściowe i utwórz Viewer
Zastąp ścieżki zastępcze rzeczywistymi katalogami. Konstruktor `Viewer` przyjmuje obiekt `File`, który wskazuje na dokument źródłowy.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. Skonfiguruj opcje widoku PDF i zastosuj rotację
Metoda `rotatePage(int, Rotation)` przyjmuje indeks strony **liczony od 1** oraz wartość enum `Rotation`. W tym przykładzie używamy `Rotation.ON_90_DEGREE`, aby obrócić pierwszą stronę zgodnie z ruchem wskazówek zegara.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Renderuj dokument
Wywołanie `view` z skonfigurowanymi opcjami zapisuje obrócony PDF w folderze wyjściowym.

```java
viewer.view(viewOptions);
```

#### Jak to działa
- **PdfViewOptions** kieruje Viewer do generowania pliku wyjściowego PDF.  
- **rotatePage(int, Rotation)** obraca tylko określoną stronę, pozostawiając pozostałe niezmienione.  
- Metoda obsługuje trzy stałe rotacji: `ON_90_DEGREE`, `ON_180_DEGREE` i `ON_270_DEGREE`.

## Typowe problemy i rozwiązania

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|---------|--------------|-----|
| **FileNotFoundException** | Nieprawidłowa ścieżka lub brakujący folder | Sprawdź, czy `YOUR_OUTPUT_DIRECTORY` i `YOUR_DOCUMENT_DIRECTORY` istnieją i są czytelne. |
| **Unsupported file format** | Próba obrócenia formatu nieobsługiwanego przez Viewer | Sprawdź stronę [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Użycie niewłaściwego numeru strony (liczony od 0) | Pamiętaj, że `rotatePage` używa indeksacji **liczonej od 1**. |
| **Out‑of‑memory errors on large docs** | Renderowanie wielu dużych plików w jednym wątku | Przetwarzaj dokumenty kolejno lub użyj puli wątków o ograniczonej współbieżności. |

## Praktyczne zastosowania

1. **Dostosowanie prezentacji** – Konwertuj slajd w orientacji pionowej na poziomą w locie, aby uzyskać lepszy efekt wizualny.  
2. **Masowa korekta dokumentów** – Automatyzuj naprawę zeskanowanych PDF‑ów, które zostały zarejestrowane bokiem, oszczędzając godziny ręcznej pracy.  
3. **Wynik gotowy do druku** – Zapewnij prawidłowe drukowanie grafik w orientacji poziomej na papierze w orientacji pionowej bez ręcznej rotacji w sterowniku drukarki.  

## Wskazówki dotyczące wydajności

- **Zamykaj zasoby niezwłocznie** – blok `try‑with‑resources` automatycznie zwalnia `Viewer`, zwalniając pamięć.  
- **Przetwarzanie wsadowe** – ponownie używaj jednej instancji `Viewer` na wątek, aby zmniejszyć narzut inicjalizacji.  
- **Monitoruj pamięć** – dla dokumentów większych niż 100 MB, strumieniuj wyjście na dysk zamiast trzymać cały plik w pamięci; GroupDocs Viewer może przetwarzać pliki 200 MB, używając mniej niż 250 MB RAM.  

## Najczęściej zadawane pytania

**Q: Czy mogę obrócić wiele stron jednocześnie?**  
A: Tak — wywołaj `rotatePage()` dla każdego numeru strony, którą chcesz obrócić, albo w pętli, albo łańcuchując wywołania.

**Q: Czy istnieje sposób na cofnięcie rotacji po renderowaniu?**  
A: Nie bezpośrednio. Należy ponownie wyrenderować dokument bez opcji rotacji.

**Q: Które formaty plików obsługują rotację stron w GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX i wiele innych formatów wymienionych w oficjalnej dokumentacji.

**Q: Jak mogę automatycznie obracać strony w partii dokumentów?**  
A: Umieść logikę rotacji w pętli iterującej po kolekcji ścieżek plików, stosując tę samą konfigurację `rotatePage` dla każdego pliku.

**Q: Jaka jest najlepsza praktyka obsługi błędów podczas rotacji?**  
A: Otocz użycie Viewer w bloku `try‑catch`, zaloguj szczegóły wyjątku i opcjonalnie kontynuuj przetwarzanie kolejnego pliku, aby uniknąć zatrzymania całej partii przez pojedynczy błąd.

## Zasoby

- **Dokumentacja**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Referencja API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Pobierz**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Zakup**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Bezpłatna wersja próbna**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Licencja tymczasowa**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Wsparcie**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Ostatnia aktualizacja:** 2026-09-30  
**Testowano z:** GroupDocs Viewer 25.2 for Java  
**Autor:** GroupDocs

## Powiązane samouczki

- [Jak obrócić konkretne strony PDF przy użyciu GroupDocs.Viewer dla Java](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [Ładowanie dokumentu z URL w Javie – samouczek GroupDocs.Viewer](/viewer/java/document-loading/)
- [Widoki dokumentów Groupdocs Viewer Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)