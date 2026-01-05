---
date: '2026-01-05'
description: Dowiedz się, jak zmienić nazwy pól e‑mail, przekonwertować e‑mail na
  HTML oraz dostosować nagłówki e‑mail przy użyciu GroupDocs.Viewer dla Javy.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: Jak zmienić nazwy pól e‑mail podczas renderowania wiadomości e‑mail do HTML
  przy użyciu GroupDocs.Viewer Java
type: docs
url: /pl/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# Jak zmienić nazwy pól e‑mail podczas renderowania e‑maili do HTML przy użyciu GroupDocs.Viewer Java

Zastanawiasz się **jak zmienić nazwy pól e‑mail** podczas konwertowania e‑maila do HTML? W tym przewodniku przeprowadzimy Cię krok po kroku przez proces zmiany nazw pól e‑mail, **konwersji e‑maila do HTML** oraz **dostosowywania nagłówków e‑mail** przy użyciu GroupDocs.Viewer for Java. Po zakończeniu będziesz mieć czystą reprezentację HTML z wybranymi nazwami nagłówków, co ułatwi odczyt i integrację wyniku z Twoimi aplikacjami.

![Zmienianie nazw pól e‑mail przy konwertowaniu e‑maili do HTML przy użyciu GroupDocs.Viewer dla Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Co się nauczysz
- Jak używać GroupDocs.Viewer for Java do **konwersji e‑maila do HTML**.  
- Techniki **zmiany nazw pól e‑mail**, takich jak „From”, „To”, „Sent” i „Subject”.  
- Najlepsze praktyki konfigurowania Maven i licencjonowania.  
- Przykłady rzeczywistych scenariuszy, w których **dostosowywanie nagłówków e‑mail** przynosi wartość.

## Szybkie odpowiedzi
- **Co oznacza „jak zmienić nazwy pól e‑mail”?** Odnosi się do mapowania domyślnych nazw nagłówków e‑mail na własne etykiety podczas renderowania.  
- **Która biblioteka obsługuje konwersję?** GroupDocs.Viewer for Java (v25.2+).  
- **Czy potrzebna jest licencja?** Wersja próbna działa w celach oceny; pełna licencja jest wymagana w środowisku produkcyjnym.  
- **Czy mogę zmienić dowolną nazwę nagłówka?** Tak, każdy standardowy nagłówek e‑mail może być przemapowany za pomocą `fieldTextMap`.  
- **Czy wynik to HTML czy zasoby osadzone?** Możesz wybrać zasoby osadzone, aby uzyskać pojedynczy, samodzielny plik.

## Co oznacza „jak zmienić nazwy pól e‑mail” w kontekście GroupDocs.Viewer?
Zmiana nazw pól e‑mail polega na zastąpieniu domyślnych etykiet (np. „From”) własnym tekstem (np. „Nadawca”) podczas renderowania e‑maila do HTML. Jest to przydatne, aby dopasować wynik do terminologii korporacyjnej lub poprawić czytelność dla użytkownika końcowego.

## Dlaczego konwertować e‑mail do HTML i dostosowywać nagłówki e‑mail?
- **Spójna identyfikacja marki:** Dopasuj język organizacji we wszystkich komunikacjach.  
- **Lepsza wyszukiwalność:** Niestandardowe nagłówki mogą być skuteczniej indeksowane w systemach archiwizacji.  
- **Lepsza integracja UI:** Dostosuj fragment HTML, aby płynnie wpasował się w portale internetowe lub pulpity wsparcia.

## Wymagania wstępne

### Wymagane biblioteki, wersje i zależności
- **GroupDocs.Viewer for Java** – wersja 25.2 lub nowsza.  
- **Java Development Kit (JDK)** – wersja 8+.

### Wymagania dotyczące konfiguracji środowiska
- **Maven** do zarządzania zależnościami.  
- IDE, takie jak IntelliJ IDEA, Eclipse lub VS Code.

### Wymagania wiedzy
Podstawowa znajomość Javy i Mavenu ułatwi szybkie podążanie za instrukcjami.

## Konfiguracja GroupDocs.Viewer for Java

### Konfiguracja Maven
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

### Kroki uzyskania licencji
- **Bezpłatna wersja próbna:** Pobierz wersję próbną z [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Licencja tymczasowa:** Uzyskaj tymczasową licencję, aby przetestować pełne funkcje bez ograniczeń, pod adresem [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Zakup:** Aby kontynuować korzystanie, rozważ zakup licencji poprzez [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Podstawowa inicjalizacja i konfiguracja
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
Dostosuj ścieżkę pliku, aby wskazywała na Twój plik `.msg`.

## Przewodnik implementacji

### Zmiana nazw pól e‑mail – krok po kroku

#### 1. Ustaw ścieżkę katalogu wyjściowego
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Zastąp `"YOUR_OUTPUT_DIRECTORY"` folderem, w którym chcesz zapisywać pliki HTML.*

#### 2. Zdefiniuj format ścieżki pliku strony
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` zostanie zastąpione numerem strony podczas renderowania.*

#### 3. Utwórz mapowanie pól e‑mail na nowe nazwy
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*Tutaj zmieniamy domyślne etykiety na własne.*

#### 4. Skonfiguruj opcje widoku HTML
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` osadza CSS/JS w HTML, natomiast `setFieldTextMap` stosuje niestandardowe nazwy nagłówków.*

#### 5. Renderuj e‑mail do HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Zastąp `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` rzeczywistą ścieżką do pliku MSG.*

#### Wskazówki rozwiązywania problemów
- Sprawdź, czy katalog wyjściowy jest zapisywalny.  
- Upewnij się, że plik MSG istnieje i ścieżka jest prawidłowa.  
- Używaj tej samej wersji GroupDocs.Viewer (25.2), co zadeklarowano w Maven.

## Praktyczne zastosowania
1. **Niestandardowe raporty e‑mail:** Dopasuj nagłówki e‑mail do terminologii korporacyjnej, aby uzyskać czytelniejsze raporty.  
2. **Systemy archiwizacji e‑mail:** Popraw wyszukiwalność, stosując ustandaryzowane nazwy nagłówków.  
3. **Platformy wsparcia klienta:** Prezentuj zgłoszenia z spersonalizowanymi etykietami nagłówków dla lepszych doświadczeń agentów.

## Względy wydajnościowe
- Zwalniaj obiekty `Viewer` przy użyciu try‑with‑resources, aby szybko zwolnić pamięć.  
- Profiluj duże partie i rozważ przetwarzanie e‑maili równolegle przy użyciu strumieni, jeśli to konieczne.

## Podsumowanie
Teraz wiesz **jak zmienić nazwy pól e‑mail** podczas **konwersji e‑maila do HTML** oraz **dostosowywania nagłówków e‑mail** przy użyciu GroupDocs.Viewer for Java. Ta technika daje pełną kontrolę nad prezentacją metadanych e‑mail w wynikach HTML.

### Kolejne kroki
- Eksperymentuj z dodatkowymi mapowaniami pól (np. CC, BCC).  
- Poznaj inne formaty renderowania, takie jak PDF lub PNG.  
- Odwiedź [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) po głębsze informacje o API.

## Sekcja FAQ
1. **Czy mogę zmienić wszystkie nagłówki e‑mail przy użyciu tej metody?**  
   - Tak, możesz mapować dowolny standardowy nagłówek e‑mail na nową nazwę zgodnie z potrzebami.  
2. **Czy można używać GroupDocs.Viewer bez licencji?**  
   - Dostępna jest wersja próbna do testów, ale pełna wersja wymaga ważnej licencji.  
3. **Jak efektywnie obsługiwać duże wolumeny e‑mail przy użyciu GroupDocs.Viewer?**  
   - Rozważ przetwarzanie wsadowe i optymalizację zasobów systemowych, aby skutecznie zarządzać większymi zestawami danych.  
4. **Czy mogę zintegrować to rozwiązanie z istniejącą aplikacją Java?**  
   - Oczywiście, integracja jest prosta dzięki zależnościom Maven.  
5. **Gdzie mogę uzyskać wsparcie w razie problemów?**  
   - Odwiedź [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) po pomoc społeczności i oficjalną.

## Najczęściej zadawane pytania

**P: Czy to podejście działa z innymi formatami e‑mail, takimi jak EML?**  
O: Tak, GroupDocs.Viewer obsługuje zarówno pliki MSG, jak i EML; ta sama logika mapowania pól obowiązuje.

**P: Czy mogę wygenerować HTML bez osadzonych zasobów?**  
O: Możesz użyć `HtmlViewOptions.forExternalResources(...)`, jeśli wolisz oddzielne pliki CSS/JS.

**P: Jaką wersję GroupDocs.Viewer przetestowano?**  
O: Kod został przetestowany z GroupDocs.Viewer **25.2**.

**P: Czy można zmienić czcionkę lub styl niestandardowych nagłówków?**  
O: Styl można zastosować za pomocą CSS po renderowaniu lub wstrzyknąć własny CSS przy użyciu `HtmlViewOptions.getResourcesPath()`.

**P: Jak programowo uzyskać ścieżkę wygenerowanego pliku HTML?**  
O: Ścieżka pliku podąża za wzorcem określonym w `pageFilePathFormat`; możesz ją skonstruować przy pomocy `String.format` z numerem strony.

## Zasoby
- **Dokumentacja:** Kompleksowe przewodniki dostępne pod adresem [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **Referencja API:** Szczegółowe informacje o API znajdziesz na [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Pobierz GroupDocs.Viewer:** Najnowszą wersję uzyskaj ze [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Ostatnia aktualizacja:** 2026-01-05  
**Testowano z:** GroupDocs.Viewer 25.2  
**Autor:** GroupDocs