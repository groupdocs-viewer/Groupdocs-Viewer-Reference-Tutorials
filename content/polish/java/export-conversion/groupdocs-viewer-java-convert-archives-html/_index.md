---
date: '2026-02-23'
description: Dowiedz się, jak ustawić liczbę elementów na stronę, osadzić zasoby HTML
  oraz wsadowo konwertować archiwa na jednopaginowy lub wielostronicowy HTML przy
  użyciu GroupDocs.Viewer Java.
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 'Ustaw liczbę elementów na stronę: konwertuj archiwa do HTML przy użyciu GroupDocs.Viewer
  Java'
type: docs
url: /pl/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Set Items Per Page: Konwertuj archiwa do HTML przy użyciu GroupDocs.Viewer Java

Konwertowanie plików archiwów, takich jak ZIP lub RAR, do przyjaznego dla sieci HTML jest częstą potrzebą, gdy chcesz udostępniać lub przeglądać dokumenty bezpośrednio w przeglądarce. W tym przewodniku dowiesz się **jak ustawić liczbę elementów na stronę** podczas renderowania archiwów, jak osadzić zasoby HTML w celu uzyskania samodzielnego wyniku oraz jak efektywnie konwertować archiwa partiami przy użyciu GroupDocs.Viewer Java.

![Convert Archives to HTML with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Quick Answers
- **Co kontroluje „set items per page”?** Określa, ile plików lub folderów z archiwum pojawia się na każdej wygenerowanej stronie HTML.  
- **Czy mogę osadzić obrazy i CSS bezpośrednio w HTML?** Tak – użyj opcji `forEmbeddedResources`, aby osadzić zasoby HTML.  
- **Czy konwersja wsadowa jest możliwa?** Oczywiście; możesz iterować po kolekcji archiwów i renderować każde z nich przy użyciu tych samych ustawień.  
- **Czy potrzebuję Maven, aby używać GroupDocs.Viewer?** Tak, dodaj zależność `maven groupdocs viewer`, jak pokazano poniżej.  
- **Jakie formaty wyjściowe są obsługiwane?** Dostępne są Single‑page HTML Java oraz multi‑page HTML Java.

## Czym jest „set items per page” w GroupDocs.Viewer?
Ustawienie **set items per page** należy do opcji renderowania archiwów. Informuje przeglądarkę, ile wpisów archiwum (plików lub folderów) powinno być wyświetlanych na każdej stronie HTML, gdy generujesz dokument HTML wielostronicowy. Dostosowanie tej wartości pomaga zrównoważyć rozmiar strony i szybkość nawigacji, szczególnie w przypadku dużych archiwów.

## Dlaczego osadzać zasoby HTML?
Osadzanie zasobów (obrazów, CSS, czcionek) bezpośrednio w pliku HTML tworzy pojedynczy, przenośny dokument, który można otworzyć bez plików zewnętrznych. Jest to idealne rozwiązanie dla załączników e‑mail, przeglądania offline lub osadzania wyniku w innych stronach internetowych.

## Wymagania wstępne

- **Wymagane biblioteki:** Dołącz GroupDocs.Viewer w wersji 25.2 lub nowszej.  
- **Środowisko:** Zainstalowany i skonfigurowany Java Development Kit (JDK).  
- **Wiedza:** Podstawowa znajomość Javy i zarządzania zależnościami Maven.  

## Konfiguracja Maven dla GroupDocs Viewer

Add the GroupDocs repository and the viewer dependency to your `pom.xml`:

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
Po skonfigurowaniu Maven, wprowadź viewer do swojego kodu:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Jak renderować archiwa do HTML jednopostaciowego

### Krok 1: Zdefiniuj katalog wyjściowy
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Krok 2: Ustaw nazwę pliku dla wyjścia jednopostaciowego
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Krok 3: Zainicjalizuj Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Krok 4: Skonfiguruj opcje renderowania (osadzanie zasobów HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Krok 5: Renderuj jako jedną stronę
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Jak renderować archiwa do HTML wielostronicowego i ustawić liczbę elementów na stronę

### Krok 1: Ponownie użyj katalogu wyjściowego
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Krok 2: Zdefiniuj format nazwy pliku dla wielu stron
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Krok 3: Ponownie zainicjalizuj Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Krok 4: Skonfiguruj opcje wielostronicowe (osadzanie zasobów HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Krok 5: Ustaw liczbę elementów na stronę (główne słowo kluczowe w akcji)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Praktyczne zastosowania

- **Systemy zarządzania dokumentami:** Dodaj funkcję podglądu archiwów bez instalowania dodatkowych przeglądarek.  
- **Portale internetowe:** Zapewnij użytkownikom szybki, bezpobieralny sposób przeglądania zgrupowanych dokumentów.  
- **Narzędzia współpracy:** Pozwól zespołom przeglądać udostępnione archiwa bezpośrednio w przeglądarce.  

## Wskazówki dotyczące wydajności

- **Zarządzanie zasobami:** Monitoruj zużycie pamięci; rozważ dostosowanie garbage‑collectora JVM dla dużych partii.  
- **Wsadowa konwersja archiwów:** Przejdź pętlą przez listę plików archiwów i wywołuj tę samą logikę renderowania, aby zmaksymalizować przepustowość.  
- **Strategia buforowania:** Przechowuj wygenerowany HTML w pamięci podręcznej, jeśli to samo archiwum jest często dostępne.  

## Najczęściej zadawane pytania

**P: Czym jest GroupDocs.Viewer Java?**  
O: Wszechstronna biblioteka do renderowania dokumentów — w tym archiwów — do formatów takich jak HTML, PDF i obrazy.

**P: Jak mogę uzyskać darmową wersję próbną GroupDocs.Viewer?**  
O: Odwiedź [link do wersji próbnej](https://releases.groupdocs.com/viewer/java/), aby pobrać i przetestować.

**P: Czy mogę konwertować inne typy dokumentów oprócz archiwów?**  
O: Tak, viewer obsługuje PDF‑y, Word, Excel i wiele innych formatów.

**P: Co zrobić, gdy renderowanie jest wolne?**  
O: Zmniejsz liczbę elementów na stronę, włącz streaming lub przetwarzaj archiwa w mniejszych partiach.

**P: Gdzie mogę uzyskać pomoc lub wsparcie?**  
O: Skontaktuj się poprzez [forum wsparcia](https://forum.groupdocs.com/c/viewer/9).

**P: Czy można osadzić CSS i obrazy bezpośrednio w HTML?**  
O: Oczywiście — użyj `HtmlViewOptions.forEmbeddedResources`, jak pokazano w przykładach.

**P: Jak wykonać wsadową konwersję folderu archiwów?**  
O: Iteruj po każdym pliku za pomocą pętli `for`, stosując tę samą konfigurację `Viewer` i `HtmlViewOptions` dla każdej iteracji.

## Zasoby

- **Dokumentacja:** Zagłęb się w funkcjonalność w [dokumentacji GroupDocs](https://docs.groupdocs.com/viewer/java/).  
- **Referencja API:** Przeglądaj pełne API na [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Pobieranie:** Pobierz najnowsze pliki binarne ze [strony pobierania](https://releases.groupdocs.com/viewer/java/).  
- **Zakup i licencjonowanie:** Zapoznaj się z opcjami na [stronie zakupu](https://purchase.groupdocs.com/buy).  
- **Wsparcie i społeczność:** Dołącz do dyskusji na [forum GroupDocs](https://forum.groupdocs.com/c/viewer/9).

---

**Ostatnia aktualizacja:** 2026-02-23  
**Testowano z:** GroupDocs.Viewer 25.2  
**Autor:** GroupDocs