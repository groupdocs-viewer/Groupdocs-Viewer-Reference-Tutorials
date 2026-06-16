---
date: '2026-04-10'
description: Dowiedz się, jak skonfigurować logowanie w GroupDocs.Viewer dla Javy,
  w tym jak dodać logger konsolowy i logger plikowy, aby uzyskać lepsze renderowanie
  dokumentów.
keywords:
- how to configure logging
- add console logger
- add file logger
- java logging best practices
- html view options
title: Jak skonfigurować logowanie w GroupDocs.Viewer dla Javy
type: docs
url: /pl/java/getting-started/groupdocs-viewer-java-logging-setup/
weight: 1
---

# Jak skonfigurować logowanie w GroupDocs.Viewer dla Javy

W tym samouczku dowiesz się **jak skonfigurować logowanie** w GroupDocs.Viewer dla Javy, co zapewnia wgląd w czasie rzeczywistym w pipeline renderowania dokumentów i pomaga szybko rozwiązywać problemy.

## Szybkie odpowiedzi
- **Co zapewnia logowanie?** Informacje zwrotne w czasie rzeczywistym o operacjach renderowania i szczegóły błędów.  
- **Który logger wypisuje na konsolę?** `ConsoleLogger` (dodaj logger konsoli).  
- **Który logger zapisuje do pliku?** `FileLogger` (dodaj logger pliku).  
- **Czy potrzebna jest licencja, aby włączyć logowanie?** Nie, logowanie działa zarówno w wersji próbnej, jak i licencjonowanej.  
- **Czy mogę dostosować format logu?** Tak, poprzez rozszerzenie klas loggera.

## Wprowadzenie
Ulepsz proces renderowania dokumentów w aplikacjach Java przy użyciu **GroupDocs.Viewer for Java**. Ten przewodnik przeprowadzi Cię przez konfigurowanie logowania zarówno na konsolę, jak i do pliku, dostarczając kluczowych informacji o tym, jak działa renderowanie dokumentów.

![Console and File Logging with GroupDocs.Viewer for Java](/viewer/getting-started/console-and-file-logging-java.png)

**Kluczowe punkty nauki:**
- Skonfiguruj logowanie w GroupDocs.Viewer dla Javy.  
- Zaimplementuj zarówno systemy logowania konsolowego, jak i opartego na pliku.  
- Renderuj dokumenty do HTML z osadzonymi zasobami przy użyciu GroupDocs.Viewer.

## Wymagania wstępne
Ensure you have:
1. **Wymagane biblioteki:**  
   - Biblioteka GroupDocs.Viewer for Java (wersja 25.2 lub nowsza).  

2. **Wymagania dotyczące środowiska:**  
   - Zainstalowany Java Development Kit (JDK) w systemie.  
   - Zintegrowane środowisko programistyczne (IDE) takie jak IntelliJ IDEA lub Eclipse.  

3. **Wymagania wiedzy:**  
   - Podstawowa znajomość programowania w Javie.  
   - Znajomość Maven do zarządzania zależnościami.  

Mając te wymagania spełnione, jesteś gotowy, aby skonfigurować GroupDocs.Viewer dla Javy!

## Konfiguracja GroupDocs.Viewer dla Javy
Aby używać GroupDocs.Viewer, dodaj go jako zależność w swoim projekcie przy użyciu Maven. Oto jak:

### Konfiguracja Maven
Dodaj następującą konfigurację w pliku `pom.xml`:
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
- **Bezpłatna wersja próbna:** Pobierz wersję próbną z [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Licencja tymczasowa:** Uzyskaj tymczasową licencję, aby usunąć ograniczenia wersji próbnej, pod adresem [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Zakup:** Aby uzyskać pełny dostęp, rozważ zakup licencji pod adresem [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Podstawowa inicjalizacja
Zainicjalizuj GroupDocs.Viewer przy użyciu następującego wzorca:
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

// Initialize with sample PDF file and settings
try (Viewer viewer = new Viewer("path/to/your/document.pdf")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```

Ta konfiguracja stanowi podstawę dla bardziej złożonych ustawień logowania.

## Jak skonfigurować logowanie
Poznaj, jak **dodać logger konsoli** i **dodać logger pliku** w GroupDocs.Viewer.

### Funkcja 1: Logowanie do konsoli
#### Przegląd
Logowanie do konsoli zapewnia natychmiastową informację zwrotną w terminalu, przydatną podczas fazy rozwoju lub debugowania.

#### Kroki
##### Krok 1: Import wymaganych klas
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.ConsoleLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

##### Krok 2: Skonfiguruj ustawienia logowania
Użyj `ConsoleLogger`, aby kierować logi na konsolę.
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new ConsoleLogger()))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
**Wyjaśnienie**  
- **ConsoleLogger:** Ta klasa kieruje logi na konsolę, zapewniając widok operacji w czasie rzeczywistym.  
- **HtmlViewOptions.forEmbeddedResources:** Generuje HTML z osadzonymi zasobami dla każdej strony, przykład efektywnego użycia **opcji widoku HTML**.

#### Wskazówki rozwiązywania problemów
Upewnij się, że ścieżka do dokumentu jest poprawna i dostępna. Zweryfikuj, czy instrukcje logowania są odpowiednio skonfigurowane w ustawieniach konsoli.

### Funkcja 2: Logowanie do pliku
#### Przegląd
Logowanie do pliku pomaga utrzymać trwały zapis operacji, przydatny do audytu lub analizy po zdarzeniu.

#### Kroki
##### Krok 1: Import wymaganych klas
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.FileLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

##### Krok 2: Skonfiguruj logowanie oparte na pliku
Użyj `FileLogger`, aby zapisywać logi do określonego pliku.
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new FileLogger("output.log")))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
**Wyjaśnienie**  
- **FileLogger:** Ta klasa kieruje logi do pliku o nazwie `output.log`.  
- **ViewerSettings z FileLogger:** Konfiguruje GroupDocs.Viewer do **przechwytywania logów widoku** w określonym pliku logów.

#### Wskazówki rozwiązywania problemów
Upewnij się, że katalog dla pliku wyjściowego jest zapisywalny. Sprawdź uprawnienia do pliku, jeśli logowanie nie działa.

## Praktyczne zastosowania
GroupDocs.Viewer może zwiększyć możliwości zarządzania dokumentami i renderowania:
1. **Portale internetowe:** Renderuj dokumenty w locie dla użytkowników sieci bez bezpośredniego pobierania.  
2. **Systemy korporacyjne:** Integruj z narzędziami CRM, aby wyświetlać kontrakty lub umowy.  
3. **Wewnętrzne pulpity:** Udostępniaj dostępne widoki raportów i prezentacji w intranetach.

## Rozważania dotyczące wydajności i najlepsze praktyki logowania w Javie
Podczas używania GroupDocs.Viewer w Javie, pamiętaj o następujących kwestiach:
- **Optymalizacja użycia zasobów:** Monitoruj zużycie pamięci przy renderowaniu dużych dokumentów.  
- **Zarządzanie pamięcią w Javie:** Używaj try‑with‑resources do automatycznego czyszczenia zasobów.  
- **Głośność logowania:** Dostosuj poziomy loggera (np. INFO, DEBUG), aby zrównoważyć szczegółowość z wpływem na wydajność — istotna część **najlepszych praktyk logowania w Javie**.  

## Zakończenie
Nauczyłeś się **jak skonfigurować logowanie** w GroupDocs.Viewer dla Javy, niezależnie od tego, czy potrzebujesz szybkiego podglądu w konsoli, czy trwałego zapisu w pliku. Ta możliwość jest nieoceniona przy debugowaniu, monitorowaniu i audycie aplikacji. Eksploruj dalsze konfiguracje, eksperymentuj z własnymi loggerami i integruj GroupDocs.Viewer z innymi systemami, aby zwiększyć ich niezawodność.

Gotowy, aby podnieść swoje umiejętności implementacji na wyższy poziom? Spróbuj skonfigurować logowanie w różnych środowiskach i obserwuj, jak zwiększa to niezawodność Twojej aplikacji!

## Zasoby
- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download](https://downloads.groupdocs.com/viewer/java/)

---

**Ostatnia aktualizacja:** 2026-04-10  
**Testowano z:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs