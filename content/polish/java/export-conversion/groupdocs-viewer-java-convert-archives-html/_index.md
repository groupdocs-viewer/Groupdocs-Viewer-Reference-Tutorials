---
date: '2026-08-03'
description: Dowiedz się, jak konwertować zip do html przy użyciu GroupDocs.Viewer
  Java, ustawiać liczbę elementów na stronę, osadzać zasoby html oraz efektywnie konwertować
  archiwa wsadowo.
keywords:
- convert zip to html
- how to batch convert
- embed resources html
- batch convert archives
- how to convert archives
lastmod: '2026-08-03'
og_description: Dowiedz się, jak konwertować zip do html przy użyciu GroupDocs.Viewer
  Java, ustawiać liczbę elementów na stronę, osadzać zasoby html oraz efektywnie konwertować
  archiwa wsadowo. Follow step-by-step code and performance tips.
og_image_alt: 'Guide: convert zip to html with GroupDocs.Viewer Java, showing pagination
  and embedded resources'
og_title: Konwertuj zip do html i ustaw liczbę elementów na stronę z GroupDocs.Viewer
  Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-03'
  description: Learn how to convert zip to html using GroupDocs.Viewer Java, set items
    per page, embed resources html, and batch convert archives efficiently.
  headline: Convert zip to html and set items per page with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: GroupDocs.Viewer Java is a server‑side library that renders over 50 document
      and archive formats—including ZIP and RAR—into HTML, PDF, or image files without
      requiring external applications.
    question: What is GroupDocs.Viewer Java?
  - answer: Visit the [free trial link](https://releases.groupdocs.com/viewer/java/)
      to download and test.
    question: How can I obtain a free trial of GroupDocs.Viewer?
  - answer: Yes, the viewer supports PDFs, Word, Excel, PowerPoint, and 35+ additional
      formats.
    question: Can I convert other document types besides archives?
  - answer: Reduce the number of items per page, enable streaming, or process archives
      in smaller batches to improve speed.
    question: What should I do if rendering is slow?
  - answer: Reach out via the [support forum](https://forum.groupdocs.com/c/viewer/9).
    question: Where can I get help or support?
  type: FAQPage
tags:
- convert zip
- GroupDocs.Viewer
- Java archive conversion
- html rendering
- batch conversion
title: Konwertuj zip do html i ustaw liczbę elementów na stronę z GroupDocs.Viewer
  Java
type: docs
url: /pl/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Konwertuj zip do html i ustaw liczbę elementów na stronę za pomocą GroupDocs.Viewer Java

W wielu aplikacjach internetowych trzeba wyświetlać zawartość archiwum ZIP lub RAR bezpośrednio w przeglądarce. Dzięki GroupDocs.Viewer for Java możesz **convert zip to html** w jednym kroku, kontrolować liczbę wpisów archiwum wyświetlanych na każdej stronie, osadzać wszystkie obrazy i CSS oraz przetwarzać hurtowo dziesiątki archiwów. Ten samouczek przeprowadzi Cię przez pełny przepływ pracy, od konfiguracji Maven po renderowanie wielostronicowe, i wyjaśni, dlaczego każde ustawienie ma znaczenie dla wydajności i użyteczności.

![Convert Archives to HTML with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Szybkie odpowiedzi
- **Co kontroluje „set items per page”?** Określa, ile plików lub folderów z archiwum pojawia się na każdej wygenerowanej stronie HTML.  
- **Czy mogę osadzić obrazy i CSS bezpośrednio w HTML?** Tak – użyj opcji `forEmbeddedResources`, aby osadzić zasoby w HTML.  
- **Czy konwersja wsadowa jest możliwa?** Zdecydowanie; możesz iterować po kolekcji archiwów i renderować każde z tymi samymi ustawieniami.  
- **Czy potrzebuję Maven, aby używać GroupDocs.Viewer?** Tak, dodaj zależność Maven `groupdocs-viewer`, jak pokazano poniżej.  
- **Jakie formaty wyjściowe są obsługiwane?** Dostępne są zarówno jednopostaciowy HTML, jak i wielostronicowy HTML, a biblioteka obsługuje ponad 50 typów archiwów wejściowych.

## Co to jest „set items per page” w GroupDocs.Viewer?
Ustawienie **set items per page** należy do opcji renderowania archiwum. Informuje podgląd, ile wpisów archiwum (plików lub folderów) powinno być wyświetlanych na każdej stronie HTML przy generowaniu dokumentu HTML wielostronicowego. Dostosowanie tej wartości pomaga zrównoważyć rozmiar strony i szybkość nawigacji, szczególnie w przypadku dużych archiwów.

## Dlaczego osadzać zasoby w HTML?
Osadzanie zasobów (obrazów, CSS, czcionek) bezpośrednio w pliku HTML tworzy pojedynczy, przenośny dokument, który można otworzyć bez plików zewnętrznych. Jest to idealne rozwiązanie dla załączników e‑mail, przeglądania offline lub osadzania wyniku w innych stronach internetowych. To podejście upraszcza również wdrażanie, ponieważ nie trzeba zarządzać zewnętrznymi ścieżkami zasobów.

## Wymagania wstępne

- **Wymagane biblioteki:** Dołącz GroupDocs.Viewer w wersji 25.2 lub nowszej.  
- **Środowisko:** Zainstalowany i skonfigurowany Java Development Kit (JDK).  
- **Wiedza:** Podstawowa znajomość Javy i zarządzania zależnościami Maven.  

## Konfiguracja Maven GroupDocs Viewer

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
GroupDocs.Viewer oferuje **link do wersji próbnej**, tymczasową licencję lub pełną opcję zakupu. Wybierz tę, która pasuje do harmonogramu Twojego projektu.

### Podstawowa inicjalizacja
Po konfiguracji Maven, wprowadź viewer do swojego kodu:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Jak renderować archiwa do jednopostaciowego html
Viewer jest klasą podstawową, która ładuje dokument lub archiwum do renderowania.

Aby wygenerować pojedynczy plik HTML zawierający całe archiwum, utwórz instancję `Viewer` dla pliku ZIP i użyj `HtmlViewOptions.forEmbeddedResources()`, aby osadzić wszystkie obrazy, CSS i czcionki. Renderowanie archiwum z tymi opcjami tworzy jedną samodzielną stronę odpowiednią do e‑maila lub użytku offline.

### Krok 1: Zdefiniuj katalog wyjściowy
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Krok 2: Ustaw nazwę pliku dla jednopostaciowego wyjścia
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Krok 3: Zainicjalizuj viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Krok 4: Skonfiguruj opcje renderowania (osadzanie zasobów w html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Krok 5: Renderuj jako jedną stronę
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Jak renderować archiwa do wielostronicowego html i ustawić liczbę elementów na stronę
`HtmlViewOptions` konfiguruje sposób, w jaki viewer renderuje wyjście HTML, w tym paginację i osadzanie zasobów.

Aby podzielić archiwum na wiele stron, utwórz `HtmlViewOptions.forEmbeddedResources()` i ustaw żądany rozmiar strony za pomocą `options.setItemsPerPage(20)`. Viewer wygeneruje oddzielne pliki HTML, z których każdy wyświetli do określonej liczby wpisów, co poprawia nawigację w dużych archiwach i zapewnia szybsze ładowanie.

### Krok 1: Ponownie użyj katalogu wyjściowego
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Krok 2: Zdefiniuj format nazwy pliku dla wielu stron
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Krok 3: Ponownie zainicjalizuj viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Krok 4: Skonfiguruj opcje wielostronicowe (osadzanie zasobów w html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Krok 5: Ustaw liczbę elementów na stronę (główne słowo kluczowe w akcji)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Praktyczne zastosowania

- **Systemy zarządzania dokumentami:** Dodaj funkcję podglądu archiwum bez instalowania dodatkowych przeglądarek.  
- **Portale internetowe:** Zapewnij użytkownikom szybki, bezpobieralny sposób przeglądania zgrupowanych dokumentów.  
- **Narzędzia współpracy:** Pozwól zespołom przeglądać współdzielone archiwa bezpośrednio w przeglądarce.

## Rozważania dotyczące wydajności

- **Zarządzanie zasobami:** Utrzymuj niskie zużycie pamięci, przetwarzając archiwa w strumieniach; viewer może obsługiwać archiwa do 500 MB bez wczytywania całego pliku do pamięci.  
- **Konwersja wsadowa archiwów:** Przejdź przez listę plików archiwów i wywołaj tę samą logikę renderowania, aby zmaksymalizować przepustowość.  
- **Strategia buforowania:** Przechowuj renderowany HTML w pamięci podręcznej, jeśli to samo archiwum jest często dostępne, co skraca czas ponownego przetwarzania nawet o 70 %.

## Najczęściej zadawane pytania

**P: Co to jest GroupDocs.Viewer Java?**  
A: GroupDocs.Viewer Java jest biblioteką po stronie serwera, która renderuje ponad 50 formatów dokumentów i archiwów — w tym ZIP i RAR — do HTML, PDF lub plików graficznych, bez potrzeby używania zewnętrznych aplikacji.

**P: Jak mogę uzyskać darmową wersję próbną GroupDocs.Viewer?**  
A: Odwiedź [free trial link](https://releases.groupdocs.com/viewer/java/), aby pobrać i przetestować.

**P: Czy mogę konwertować inne typy dokumentów oprócz archiwów?**  
A: Tak, viewer obsługuje PDF-y, Word, Excel, PowerPoint oraz ponad 35 dodatkowych formatów.

**P: Co zrobić, gdy renderowanie jest wolne?**  
A: Zmniejsz liczbę elementów na stronę, włącz strumieniowanie lub przetwarzaj archiwa w mniejszych partiach, aby zwiększyć szybkość.

**P: Gdzie mogę uzyskać pomoc lub wsparcie?**  
A: Skontaktuj się poprzez [support forum](https://forum.groupdocs.com/c/viewer/9).

**P: Czy można osadzić CSS i obrazy bezpośrednio w HTML?**  
A: Zdecydowanie — użyj `HtmlViewOptions.forEmbeddedResources`, jak pokazano w przykładach.

**P: Jak wykonać konwersję wsadową folderu archiwów?**  
A: Iteruj po każdym pliku za pomocą pętli `for`, stosując tę samą konfigurację `Viewer` i `HtmlViewOptions` dla każdej iteracji.

## Zasoby

- **Dokumentacja:** Zagłęb się w funkcjonalność z [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/).  
- **Referencja API:** Przeglądaj pełne API na [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Pobieranie:** Pobierz najnowsze pliki binarne ze [download page](https://releases.groupdocs.com/viewer/java/).  
- **Zakup i licencjonowanie:** Przejrzyj opcje na [purchase page](https://purchase.groupdocs.com/buy).  
- **Wsparcie i społeczność:** Dołącz do dyskusji na [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9).

---

**Ostatnia aktualizacja:** 2026-08-03  
**Testowano z:** GroupDocs.Viewer 25.2  
**Autor:** GroupDocs

## Powiązane samouczki

- [Jak konwertować zip do HTML i renderować foldery zip w Javie za pomocą GroupDocs.Viewer](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [konwertować zip do pdf za pomocą GroupDocs.Viewer Java - Niestandardowe nazwy plików](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [Jak konwertować DOCX do HTML przy użyciu GroupDocs.Viewer dla Java: Przewodnik krok po kroku](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)