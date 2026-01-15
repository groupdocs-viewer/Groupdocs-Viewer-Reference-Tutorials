---
date: '2026-01-15'
description: Dowiedz się, jak używać GroupDocs Viewer do generowania HTML z dokumentów
  projektowych w określonych przedziałach czasowych. Ten przewodnik obejmuje konfigurację,
  kod oraz praktyczne przypadki użycia.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Jak używać GroupDocs Viewer do renderowania dokumentów projektowych w interwałach
  czasowych w Javie
type: docs
url: /pl/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Jak używać GroupDocs Viewer do renderowania dokumentów projektów w interwałach czasowych w Javie

Jeśli szukasz **jak używać GroupDocs**, aby renderować harmonogramy projektów w określonym przedziale czasowym, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię przez cały proces — od konfiguracji Maven po generowanie HTML z dokumentów projektów — abyś mógł osadzić precyzyjne widoki osi czasu bezpośrednio w swoich aplikacjach.

![Renderowanie dokumentów projektów w interwałach czasowych przy użyciu GroupDocs.Viewer dla Javy](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Szybkie odpowiedzi
- **Co robi ta funkcja?** Renderuje tylko część pliku Microsoft Project, która mieści się pomiędzy datą początkową a końcową.  
- **Jaki format wyjściowy jest używany?** HTML z osadzonymi zasobami, idealny do integracji z siecią.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna wystarcza do oceny; pełna licencja jest wymagana w środowisku produkcyjnym.  
- **Czy mogę zmienić zakres dat w czasie działania?** Tak — dostosuj wartości `setStartDate` i `setEndDate` w opcjach renderowania.  
- **Czy jest to obsługiwane we wszystkich wersjach Javy?** Działa z Java 8+ pod warunkiem użycia GroupDocs.Viewer 25.2 lub nowszej.

## Co oznacza „jak używać GroupDocs” w tym kontekście?
GroupDocs Viewer to biblioteka Java, która konwertuje ponad 100 formatów plików na reprezentacje przyjazne dla sieci. Kiedy **jak używać GroupDocs** dla plików projektowych, zyskujesz możliwość wyodrębniania, wizualizacji i udostępniania danych harmonogramu bez konieczności posiadania Microsoft Project po stronie klienta.

## Dlaczego renderować dokumenty projektów w interwałach czasowych?
- **Skoncentrowana analiza:** Pokaż tylko fazę, która Cię interesuje (np. Q3 2024).  
- **Wydajność:** Mniejszy rozmiar HTML oznacza szybsze ładowanie stron.  
- **Integracja:** Osadź widoki osi czasu w pulpitach, portalach raportowych lub własnych narzędziach PM.  

## Wymagania wstępne

- **GroupDocs.Viewer for Java** wersja 25.2 lub wyższa.  
- Java Development Kit (JDK) 8 lub nowszy.  
- IDE, takie jak IntelliJ IDEA lub Eclipse.  
- Podstawowa znajomość Maven.  

## Konfiguracja GroupDocs.Viewer dla Javy

### Zależność Maven

Add the repository and dependency to your `pom.xml`:

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

1. **Darmowa wersja próbna** – Pobierz wersję próbną ze [strony pobierania GroupDocs](https://releases.groupdocs.com/viewer/java/).  
2. **Licencja tymczasowa** – Uzyskaj tymczasową licencję do rozszerzonego testowania poprzez [ten link](https://purchase.groupdocs.com/temporary-license/).  
3. **Zakup** – Do nieograniczonego użycia produkcyjnego, kup licencję na [stronie zakupu GroupDocs](https://purchase.groupdocs.com/buy).

### Podstawowa inicjalizacja Viewer

The following snippet shows how to create a `Viewer` instance that points to a Microsoft Project file (`.mpp`):

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## Przewodnik krok po kroku

### 1. Zdefiniuj katalog wyjściowy

Create a folder where the generated HTML pages will be saved:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Dlaczego?* Utrzymywanie renderowanych plików w porządku ułatwia ich serwowanie z serwera WWW lub osadzanie w interfejsie użytkownika.

### 2. Zainicjalizuj Viewer z plikiem projektu

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*Dlaczego?* Załadowanie dokumentu przygotowuje wewnętrzny parser i udostępnia metadane specyficzne dla projektu.

### 3. Pobierz informacje o widoku dla plików projektowych

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*Dlaczego?* `ProjectManagementViewInfo` dostarcza daty rozpoczęcia i zakończenia harmonogramu, które później użyjesz do ograniczenia zakresu renderowania.

### 4. Skonfiguruj opcje renderowania HTML (Generowanie HTML z projektu)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Dlaczego?* Ustawienie `StartDate` i `EndDate` informuje GroupDocs, aby **generować HTML z danych projektu** tylko w tym przedziale.

### 5. Wykonaj proces renderowania

```java
viewer.view(viewOptions);
```

*Dlaczego?* To wywołanie generuje serię samodzielnych stron HTML, które przedstawiają wybrany fragment czasowy harmonogramu projektu.

## Częste pułapki i rozwiązywanie problemów

- **Nieprawidłowe ścieżki plików** – Sprawdź dwukrotnie, czy zarówno plik źródłowy `.mpp`, jak i katalog wyjściowy istnieją.  
- **Nieobsługiwany typ pliku** – Upewnij się, że dokument jest w obsługiwanym formacie Project (np. `.mpp`, `.mpt`).  
- **Błędy licencji** – Licencja próbna może narzucać limity renderowania; przejdź na pełną licencję, aby uzyskać nieograniczone użycie.  

## Praktyczne zastosowania

1. **Analiza osi czasu projektu** – Pokaż interesariuszom tylko bieżącą fazę.  
2. **Automatyczne raportowanie** – Generuj raporty HTML ograniczone w czasie dla cotygodniowych aktualizacji statusu.  
3. **Integracja z pulpitami** – Osadź renderowane strony w narzędziach BI lub własnych portalach.  
4. **Archiwizacja** – Przechowuj przyjazny dla sieci migawkowy zapis harmonogramu projektu na przyszłość.  

## Wskazówki dotyczące wydajności

- Użyj opcji *embedded resources*, aby każda strona HTML była samodzielna, co zmniejsza liczbę żądań HTTP.  
- Dla bardzo dużych projektów rozważ renderowanie w mniejszych fragmentach dat, aby utrzymać niskie zużycie pamięci.  
- Usuń pliki tymczasowe po ich udostępnieniu, aby uniknąć nadmiernego zajęcia dysku.  

## Podsumowanie

Teraz wiesz **jak używać GroupDocs** Viewer do renderowania dokumentów projektów w określonym przedziale czasowym i **generować HTML z danych projektu** w Javie. Ta funkcja upraszcza wizualizacje osi czasu, zwiększa efektywność raportowania i płynnie integruje się z nowoczesnymi aplikacjami internetowymi.

### Kolejne kroki
- Zbadaj dodatkowe funkcje Viewer, takie jak znakowanie wodą, ochrona hasłem lub niestandardowe stylowanie CSS.  
- Połącz ten pipeline renderowania z API REST, aby udostępniać widoki osi czasu na żądanie.  

## Najczęściej zadawane pytania

**Q: Jakie formaty plików obsługuje GroupDocs.Viewer?**  
**A:** GroupDocs.Viewer obsługuje szeroką gamę formatów, w tym Microsoft Project (MPP), PDF, Word, Excel, PowerPoint i wiele innych.

**Q: Jak rozpocząć korzystanie z darmowej wersji próbnej GroupDocs.Viewer?**  
**A:** Możesz pobrać wersję próbną ze [tutaj](https://releases.groupdocs.com/viewer/java/).

**Q: Czy mogę renderować dokumenty bez osadzania zasobów?**  
**A:** Tak, możesz wybrać inną opcję widoku HTML, która odwołuje się do zewnętrznych zasobów zamiast ich osadzania.

**Q: Co zrobić, jeśli mój dokument jest zbyt duży do renderowania?**  
**A:** Rozważ podzielenie dokumentu na mniejsze sekcje lub renderowanie tylko wymaganego zakresu dat, jak pokazano powyżej.

**Q: Jak radzić sobie z błędami renderowania?**  
**A:** Zweryfikuj wszystkie ustawienia konfiguracyjne, upewnij się, że masz ważną licencję i skonsultuj dokumentację GroupDocs w celu uzyskania szczegółowych kodów błędów.

## Zasoby
- **Dokumentacja**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Referencja API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Pobieranie**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Zakup**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Darmowa wersja próbna**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Licencja tymczasowa**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Wsparcie**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

**Ostatnia aktualizacja:** 2026-01-15  
**Testowano z:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs