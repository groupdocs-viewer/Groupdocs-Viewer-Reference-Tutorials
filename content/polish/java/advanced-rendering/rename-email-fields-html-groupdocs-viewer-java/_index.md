---
date: '2026-03-24'
description: Dowiedz się, jak konwertować e‑mail na HTML i zmieniać nazwy pól e‑mail
  przy użyciu GroupDocs Viewer for Java. Ten przewodnik pokazuje renderowanie e‑maila
  jako HTML z niestandardowymi nagłówkami.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: Konwertuj e‑mail na HTML i zmień nazwy pól – GroupDocs Viewer Java
type: docs
url: /pl/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# Konwertuj e‑mail na HTML i zmień nazwy pól – GroupDocs Viewer Java

Jeśli potrzebujesz **konwertować e‑mail na HTML** i nadać nagłówkom e‑maila niestandardowy wygląd, jesteś we właściwym miejscu. W tym samouczku przeprowadzimy Cię krok po kroku przez proces zmiany nazw pól e‑maila, **konwersji e‑maila na HTML** oraz dostosowywania nagłówków e‑maila przy użyciu GroupDocs.Viewer dla Javy. Po zakończeniu będziesz mieć czystą reprezentację HTML z nazwami nagłówków, które preferujesz, co ułatwi odczyt i integrację z Twoimi aplikacjami.

![Zmienianie nazw pól e‑maili podczas konwertowania e‑maili na HTML przy użyciu GroupDocs.Viewer dla Javy](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Czego się nauczysz
- Jak używać GroupDocs.Viewer dla Javy do **konwertowania e‑maila na HTML**.  
- Techniki **zmiany nazw pól e‑maila** takich jak „From”, „To”, „Sent” i „Subject”.  
- Najlepsze praktyki konfiguracji Maven i licencjonowania.  
- Przykłady z życia, w których **dostosowywanie nagłówków e‑maila** przynosi wartość.

## Szybkie odpowiedzi
- **Co oznacza „konwertować e‑mail na HTML”?** Oznacza to renderowanie pliku e‑mail (MSG/EML) jako dokumentu HTML gotowego do wyświetlenia w przeglądarce.  
- **Która biblioteka obsługuje konwersję?** GroupDocs.Viewer dla Javy (v25.2+).  
- **Czy potrzebna jest licencja?** Wersja próbna działa w celach ewaluacyjnych; pełna licencja jest wymagana w środowisku produkcyjnym.  
- **Czy mogę zmienić dowolną nazwę nagłówka?** Tak, każdy standardowy nagłówek e‑maila może być przemapowany za pomocą `fieldTextMap`.  
- **Czy wynikowy plik to HTML czy zasoby osadzone?** Możesz wybrać zasoby osadzone, aby uzyskać pojedynczy, samodzielny plik.

## Co oznacza „konwertować e‑mail na HTML” w kontekście GroupDocs.Viewer?
Konwersja e‑maila na HTML polega na wzięciu surowego pliku e‑mail i wygenerowaniu strony HTML, która wyświetla treść wiadomości wraz z jej metadanymi. Gdy dodatkowo **zmieniasz nazwy pól e‑maila**, domyślne etykiety (np. „From”) są zastępowane własnym tekstem (np. „Nadawca”), co pomaga dopasować terminologię korporacyjną lub poprawić spójność interfejsu użytkownika.

## Dlaczego konwertować e‑mail na HTML i zmieniać nazwy pól e‑maila?
- **Spójna identyfikacja wizualna:** Dostosuj wyjście do języka używanego w Twojej organizacji.  
- **Lepsza wyszukiwalność:** Niestandardowe nagłówki mogą być skuteczniej indeksowane w systemach archiwizacji.  
- **Lepsza integracja UI:** Dostosuj fragment HTML, aby płynnie wpasował się w portale internetowe lub pulpity wsparcia.

## Prerequisites

### Wymagane biblioteki, wersje i zależności
- **GroupDocs.Viewer dla Javy** – wersja 25.2 lub nowsza.  
- **Java Development Kit (JDK)** – wersja 8+.

### Wymagania dotyczące konfiguracji środowiska
- **Maven** do zarządzania zależnościami.  
- IDE, takie jak IntelliJ IDEA, Eclipse lub VS Code.

### Wymagania wstępne wiedzy
Podstawowa znajomość Javy i Mavenu ułatwi szybkie podążanie za instrukcją.

## Konfiguracja GroupDocs.Viewer dla Javy

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
- **Free Trial:** Pobierz wersję próbną z [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Temporary License:** Uzyskaj tymczasową licencję, aby przetestować pełne funkcje bez ograniczeń, pod adresem [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Purchase:** W celu dalszego użytkowania rozważ zakup licencji przez [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

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

## Jak konwertować e‑mail na HTML i zmieniać nazwy pól – krok po kroku

### 1. Ustaw ścieżkę katalogu wyjściowego
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Zastąp `"YOUR_OUTPUT_DIRECTORY"` folderem, w którym mają być zapisywane pliki HTML.*

### 2. Zdefiniuj format ścieżki pliku strony
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` zostanie zastąpione numerem strony podczas renderowania.*

### 3. Utwórz mapowanie pól e‑maila na nowe nazwy
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

### 4. Skonfiguruj opcje widoku HTML
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` osadza CSS/JS wewnątrz HTML, natomiast `setFieldTextMap` stosuje niestandardowe nazwy nagłówków.*

### 5. Renderuj e‑mail do HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Zastąp `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` rzeczywistą ścieżką do swojego pliku MSG.*

#### Wskazówki rozwiązywania problemów
- Upewnij się, że katalog wyjściowy jest zapisywalny.  
- Sprawdź, czy plik wejściowy MSG istnieje i czy ścieżka jest prawidłowa.  
- Użyj tej samej wersji GroupDocs.Viewer (25.2), która została zadeklarowana w Mavenie.

## Praktyczne zastosowania
1. **Raporty e‑mailowe na zamówienie:** Dostosuj nagłówki e‑maili do terminologii korporacyjnej, aby uzyskać czytelniejsze raporty.  
2. **Systemy archiwizacji e‑maili:** Popraw wyszukiwalność, używając ustandaryzowanych nazw nagłówków.  
3. **Platformy wsparcia klienta:** Prezentuj zgłoszenia z spersonalizowanymi etykietami nagłówków, co zwiększa komfort pracy agentów.

## Wskazówki dotyczące wydajności
- Zwalniaj obiekty `Viewer` przy pomocy try‑with‑resources, aby szybko zwolnić pamięć.  
- Profiluj duże partie i rozważ przetwarzanie e‑maili równolegle przy użyciu strumieni, jeśli zajdzie taka potrzeba.

## Podsumowanie
Teraz wiesz, **jak konwertować e‑mail na HTML** oraz **zmieniać nazwy pól e‑maila** i **dostosowywać nagłówki e‑maila** przy użyciu GroupDocs.Viewer dla Javy. Ta technika daje pełną kontrolę nad prezentacją metadanych e‑maila w wyjściu HTML.

### Kolejne kroki
- Eksperymentuj z dodatkowymi mapowaniami pól (np. CC, BCC).  
- Poznaj inne formaty renderowania, takie jak PDF lub PNG.  
- Odwiedź [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) po głębsze informacje o API.

## Najczęściej zadawane pytania

**P: Czy to podejście działa z innymi formatami e‑mail, takimi jak EML?**  
O: Tak, GroupDocs.Viewer obsługuje zarówno pliki MSG, jak i EML; ta sama logika mapowania pól ma zastosowanie.

**P: Czy mogę wygenerować HTML bez osadzonych zasobów?**  
O: Możesz użyć `HtmlViewOptions.forExternalResources(...)`, jeśli wolisz oddzielne pliki CSS/JS.

**P: Jaką wersję GroupDocs.Viewer przetestowano?**  
O: Kod został przetestowany z GroupDocs.Viewer **25.2**.

**P: Czy można zmienić czcionkę lub styl niestandardowych nagłówków?**  
O: Styl można zastosować za pomocą CSS po renderowaniu lub wstrzyknąć własny CSS przy użyciu `HtmlViewOptions.getResourcesPath()`.

**P: Jak programowo uzyskać ścieżkę wygenerowanego pliku HTML?**  
O: Ścieżka pliku podąża za wzorcem określonym w `pageFilePathFormat`; możesz ją zbudować przy pomocy `String.format` i numeru strony.

## Zasoby
- **Documentation:** Kompleksowe przewodniki dostępne pod adresem [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **API Reference:** Szczegółowe informacje o API znajdziesz na [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Download GroupDocs.Viewer:** Najnowszą wersję pobierz ze [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Ostatnia aktualizacja:** 2026-03-24  
**Testowano z:** GroupDocs.Viewer 25.2  
**Autor:** GroupDocs