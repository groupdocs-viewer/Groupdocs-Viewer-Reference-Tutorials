---
date: '2025-12-21'
description: Dowiedz się, jak wyłączyć grupowanie w plikach PDF przy użyciu GroupDocs.Viewer
  dla Javy, korzystając z opcji renderowania PDF do Java HTML, aby zapewnić precyzyjną
  reprezentację tekstu.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: Jak wyłączyć grupowanie w PDF‑ach przy użyciu GroupDocs.Viewer dla Javy
type: docs
url: /pl/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# Jak wyłączyć grupowanie w plikach PDF przy użyciu GroupDocs.Viewer dla Javy

Kiedy potrzebujesz **jak wyłączyć grupowanie** podczas renderowania plików PDF, szczególnie dla złożonych skryptów lub starożytnych języków, precyzyjne rozmieszczenie znaków jest niezbędne. Domyślna funkcja *Character Grouping* może nieprawidłowo łączyć znaki, powodując błędną interpretację treści. W tym przewodniku pokażemy krok po kroku, jak wyłączyć grupowanie przy użyciu GroupDocs.Viewer dla Javy, aby każdy glif pozostał dokładnie tam, gdzie powinien.

![Precyzyjne techniki renderowania z GroupDocs.Viewer dla Javy](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Szybkie odpowiedzi
- **Co robi „disable grouping”?** Wymusza, aby renderer traktował każdy znak jako niezależny element, zachowując dokładny układ.  
- **Która opcja API kontroluje to?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Czy potrzebna jest licencja?** Wersja próbna działa do testów, ale pełna licencja jest wymagana w środowisku produkcyjnym.  
- **Czy mogę jednocześnie generować HTML w Javie z PDF?** Tak — użyj `HtmlViewOptions`, aby utworzyć wyjście HTML przy wyłączonym grupowaniu.  
- **Czy ta funkcja jest ograniczona do PDF?** Głównie dotyczy PDF, ale przeglądarka obsługuje wiele innych formatów.

## Wprowadzenie

Podczas pracy z dokumentami PDF precyzja renderowania jest kluczowa — zwłaszcza przy obsłudze złożonych struktur tekstowych, takich jak hieroglify czy języki wymagające dokładnej reprezentacji znaków. Funkcja „Character Grouping” często powoduje problemy, grupując znaki nieprawidłowo, co prowadzi do błędnej interpretacji zawartości dokumentu. Może to być szczególnie problematyczne dla użytkowników potrzebujących dokładnego odtworzenia układu tekstu w swoich dokumentach.

### Wymagania wstępne

Zanim przejdziesz do implementacji kodu, upewnij się, że spełniasz następujące wymagania:
- **Biblioteki i zależności**: Potrzebujesz GroupDocs.Viewer dla Javy w wersji 25.2 lub nowszej.
- **Konfiguracja środowiska**: Upewnij się, że masz zainstalowany Java Development Kit (JDK) oraz że Twoje IDE jest skonfigurowane do pracy z projektami Maven.
- **Wymagania wiedzy**: Podstawowa znajomość programowania w Javie, szczególnie obsługi ścieżek plików i używania zewnętrznych bibliotek.

## Jak wyłączyć grupowanie w renderowaniu PDF

### Konfiguracja GroupDocs.Viewer dla Javy

#### Instalacja za pomocą Maven

Najpierw zintegrować niezbędną bibliotekę z projektem. Dodaj następującą konfigurację w pliku `pom.xml`:

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

#### Uzyskanie licencji

Aby w pełni wykorzystać GroupDocs.Viewer, rozważ nabycie licencji:
- **Free Trial**: Rozpocznij od wersji próbnej, aby przetestować funkcje.  
- **Temporary License**: Złóż wniosek o tymczasową licencję, jeśli potrzebujesz więcej czasu.  
- **Purchase**: Dla długoterminowych projektów zaleca się zakup licencji.

#### Podstawowa inicjalizacja i konfiguracja

Rozpocznij od skonfigurowania środowiska projektu:

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### Przewodnik po implementacji

#### Funkcja: Wyłączenie grupowania znaków

##### Krok 1: Definiowanie katalogu wyjściowego

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Dlaczego?** Zapewnia to, że wyjście jest uporządkowane i łatwo dostępne.

##### Krok 2: Konfiguracja formatu ścieżki pliku

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Dlaczego?** Pomaga to w systematycznym organizowaniu stron dokumentu PDF.

##### Krok 3: Inicjalizacja opcji widoku HTML

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Dlaczego?** Osadzone zasoby zapewniają, że wszystkie niezbędne elementy są zawarte w pliku HTML każdej strony.

##### Krok 4: Wyłączenie grupowania znaków

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Dlaczego?** Zapewnia to, że znaki są renderowane indywidualnie, zachowując zamierzony układ i znaczenie.

##### Krok 5: Renderowanie dokumentu

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Dlaczego?** Zapewnia to prawidłowe zamknięcie wszystkich zasobów, zapobiegając wyciekom pamięci.

### Generowanie Java HTML z PDF bez grupowania

Klasa `HtmlViewOptions` pozwala generować **java html from pdf** zachowując każdy znak oddzielnie. Jest to szczególnie przydatne, gdy trzeba osadzić renderowane strony w portalu internetowym lub platformie e‑learningowej, gdzie dokładne rozmieszczenie glifów ma znaczenie.

### Porady dotyczące rozwiązywania problemów

- Upewnij się, że ścieżka do dokumentu jest prawidłowa, aby uniknąć `FileNotFoundException`.  
- Sprawdź, czy katalog wyjściowy ma uprawnienia do zapisu.  
- Sprawdź ponownie, czy używasz kompatybilnej wersji GroupDocs.Viewer dla Javy.

## Praktyczne zastosowania

1. **Ochrona języków**: Idealne do renderowania dokumentów w językach takich jak chiński, japoński czy starożytne skrypty, gdzie precyzja znaków ma znaczenie.  
2. **Dokumenty prawne i finansowe**: Gwarantuje dokładność w dokumentach wymagających precyzyjnej reprezentacji tekstu dla zgodności.  
3. **Zasoby edukacyjne**: Idealne do podręczników i prac akademickich zawierających złożone diagramy lub adnotacje.

## Rozważania dotyczące wydajności

- **Optymalizacja użycia zasobów**: Upewnij się, że serwer ma wystarczające zasoby do obsługi dużych plików PDF.  
- **Zarządzanie pamięcią w Javie**: Używaj efektywnych struktur danych i praktyk garbage‑collection, aby skutecznie zarządzać pamięcią.  
- **Przetwarzanie wsadowe**: Podczas renderowania wielu dokumentów przetwarzaj je w partiach, aby zwiększyć przepustowość.

## Zakończenie

Teraz opanowałeś **jak wyłączyć grupowanie** podczas renderowania PDF przy użyciu GroupDocs.Viewer dla Javy. Ta możliwość jest kluczowa dla aplikacji wymagających precyzyjnej reprezentacji tekstu. Aby dalej eksplorować, spróbuj zintegrować tę funkcję z innymi systemami zarządzania dokumentami lub eksperymentuj z dodatkowymi opcjami renderowania.

Kolejne kroki to poznanie bardziej zaawansowanych funkcji GroupDocs.Viewer oraz dopracowanie wydajności przy wdrożeniach na dużą skalę.

## Sekcja FAQ

1. **Co osiąga wyłączenie grupowania znaków?**  
   - Zapewnia to, że znaki są renderowane indywidualnie, zachowując ich pierwotny układ.  
2. **Czy mogę używać tej funkcji z innymi typami dokumentów?**  
   - Tak, choć skupiamy się na PDF, GroupDocs.Viewer obsługuje wiele formatów.  
3. **Jak efektywnie obsługiwać duże dokumenty?**  
   - Używaj przetwarzania wsadowego i optymalizuj zasoby serwera.  
4. **Co zrobić, jeśli katalog wyjściowy nie jest zapisywalny?**  
   - Sprawdź uprawnienia lub wybierz inny katalog z odpowiednimi prawami dostępu.  
5. **Czy istnieją ograniczenia licencyjne dla GroupDocs.Viewer?**  
   - Dostępna jest wersja próbna, ale długoterminowe użycie wymaga zakupionej licencji.

## Najczęściej zadawane pytania

**Q:** *Dlaczego miałbym w ogóle wyłączyć grupowanie znaków?*  
**A:** Wyłączenie grupowania zapobiega łączeniu znaków, które należą do odrębnych glifów, co jest niezbędne w skryptach, gdzie odstępy i kolejność przekazują znaczenie.

**Q:** *Czy ustawienie `setDisableCharsGrouping` dotyczy tylko wyjścia HTML?*  
**A:** Nie, wpływa na podstawowy silnik renderowania PDF, więc każdy format wyjścia (HTML, PNG itp.) odzwierciedli tę zmianę.

**Q:** *Czy mogę połączyć to ustawienie z własnymi czcionkami?*  
**A:** Tak — wystarczy załadować własne czcionki przed inicjalizacją `Viewer`, a zasada grupowania nadal będzie obowiązywać.

**Q:** *Czy wyłączenie grupowania wpływa na wydajność?*  
**A:** Nieznacznie, ponieważ silnik przetwarza każdy znak osobno, ale wpływ jest minimalny w przypadku większości dokumentów.

**Q:** *Czy istnieje sposób, aby przełączać grupowanie na poziomie poszczególnych stron?*  
**A:** Obecnie opcja jest globalna dla jednej instancji `PdfOptions`; aby mieć różne ustawienia, trzeba utworzyć osobne instancje `Viewer` dla różnych stron.

## Zasoby

- [Dokumentacja GroupDocs](https://docs.groupdocs.com/viewer/java/)
- [Referencja API](https://reference.groupdocs.com/viewer/java/)
- [Pobierz GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Kup licencję](https://purchase.groupdocs.com/buy)
- [Wersja próbna](https://releases.groupdocs.com/viewer/java/)
- [Wniosek o tymczasową licencję](https://purchase.groupdocs.com/temporary-license/)
- [Forum wsparcia GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2025-12-21  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs