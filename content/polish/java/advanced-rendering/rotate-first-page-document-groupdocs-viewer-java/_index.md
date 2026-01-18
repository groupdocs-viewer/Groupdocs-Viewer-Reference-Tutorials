---
date: '2026-01-18'
description: Dowiedz się, jak obrócić stronę o 90 stopni w Javie przy użyciu GroupDocs
  Viewer, w tym konfigurację, kod i wskazówki dotyczące wydajności.
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: Obróć stronę o 90 stopni przy użyciu GroupDocs Viewer dla Javy
type: docs
url: /pl/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# Obróć stronę o 90 stopni przy użyciu GroupDocs Viewer dla Javy

Kiedy potrzebujesz **obrócić stronę o 90 stopni** w dokumencie — niezależnie czy to PDF, plik Word czy arkusz kalkulacyjny — zrobienie tego programowo oszczędza czas i eliminuje błędy ręczne. W tym zaawansowanym przewodniku przeprowadzimy Cię krok po kroku przez proces obracania pierwszej strony dowolnego obsługiwanego dokumentu przy użyciu **GroupDocs Viewer dla Javy**. Po zakończeniu będziesz mieć gotowy fragment kodu, który możesz wstawić do własnych projektów.

![Obróć pierwszą stronę dokumentu przy użyciu GroupDocs.Viewer dla Javy](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Szybkie odpowiedzi
- **Co oznacza „obrócić stronę o 90 stopni”?** Obraca wybraną stronę w prawo o ćwierć obrotu.  
- **Która biblioteka obsługuje obrót?** GroupDocs Viewer dla Javy udostępnia metodę `rotatePage`.  
- **Czy mogę obracać strony PDF przy użyciu Javy?** Tak — użyj tej samej metody `rotatePage`; działa dla PDF, DOCX, XLSX i innych.  
- **Czy potrzebna jest licencja?** Bezpłatna wersja próbna wystarcza do rozwoju; licencja płatna jest wymagana w środowisku produkcyjnym.  
- **Czy operacja jest pamięcio‑intensywna?** Nie, pod warunkiem szybkiego zamykania instancji `Viewer`; zobacz wskazówki dotyczące wydajności poniżej.

## Co to znaczy „obrócić stronę o 90 stopni”?
Obrócenie strony o 90 stopni zmienia jej orientację z pionowej na poziomą (lub odwrotnie) bez modyfikacji zawartości. Jest to szczególnie przydatne przy prezentacjach, drukowaniu grafik wyłącznie w trybie poziomym lub korygowaniu zeskanowanych dokumentów, które zostały zarejestrowane w pozycji bocznej.

## Dlaczego obracać strony przy użyciu GroupDocs Viewer dla Javy?
GroupDocs Viewer upraszcza obsługę dziesiątek formatów plików. Umożliwia stosowanie transformacji na poziomie stron — takich jak obrót — przy zachowaniu oryginalnego pliku. API jest płynne, wątkowo‑bezpieczne i działa na dowolnym środowisku Java 8+.

## Wymagania wstępne

- **GroupDocs.Viewer dla Javy** (najnowsza wersja)
- **JDK 8** lub nowszy
- **Maven** (lub Gradle) do zarządzania zależnościami
- IDE, np. IntelliJ IDEA lub Eclipse
- Podstawowa znajomość Java I/O

## Konfiguracja GroupDocs.Viewer dla Javy

Dodaj repozytorium GroupDocs i zależność do pliku `pom.xml`. Ten fragment pozostaje niezmieniony w stosunku do oryginalnego tutorialu:

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

### Uzyskiwanie licencji
- **Bezpłatna wersja próbna** – pobierz ze strony GroupDocs.  
- **Licencja tymczasowa** – zamów, jeśli potrzebujesz wydłużonego okresu oceny.  
- **Pełna licencja** – zakup do wdrożeń produkcyjnych.

### Podstawowa inicjalizacja Viewera
Poniższy kod pokazuje minimalny sposób utworzenia instancji `Viewer`. Zachowaj go dokładnie tak, jak jest podany:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Implementacja krok po kroku: Obróć pierwszą stronę o 90 stopni

### 1. Importuj wymagane pakiety
Te importy dają dostęp do opcji renderowania PDF oraz enumu rotacji.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Zdefiniuj lokalizacje wyjściowe i utwórz Viewer
Zastąp ścieżki zastępcze rzeczywistymi katalogami.

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

### 3. Skonfiguruj opcje widoku PDF i zastosuj obrót
Metoda `rotatePage` przyjmuje numer strony (liczony od 1) oraz wartość enumu `Rotation`.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Renderuj dokument
Na koniec wywołaj `view`, aby wygenerować obrócony plik PDF.

```java
viewer.view(viewOptions);
```

#### Jak to działa
- **PdfViewOptions** informuje Viewer, że wynik ma być plikiem PDF.  
- **rotatePage(int, Rotation)** obraca wyłącznie podaną stronę, pozostawiając pozostałe niezmienione.  
- Metoda obsługuje wartości `ON_90_DEGREE`, `ON_180_DEGREE` i `ON_270_DEGREE`.

## Typowe problemy i rozwiązania
| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|---------|--------------|-----|
| **FileNotFoundException** | Nieprawidłowa ścieżka lub brak folderu | Sprawdź, czy `YOUR_OUTPUT_DIRECTORY` i `YOUR_DOCUMENT_DIRECTORY` istnieją i są czytelne. |
| **Unsupported file format** | Próba obrócenia formatu nieobsługiwanego przez Viewer | Sprawdź stronę [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Użyto niewłaściwego numeru strony (liczba od 0) | Pamiętaj, że `rotatePage` używa indeksacji **od 1**. |
| **Out‑of‑memory errors on large docs** | Renderowanie wielu dużych plików w jednym wątku | Przetwarzaj dokumenty kolejno lub użyj puli wątków z ograniczoną równoległością. |

## Praktyczne zastosowania

1. **Dostosowanie prezentacji** – zamień pionowy slajd na poziomy w locie.  
2. **Masowa korekta dokumentów** – automatyzuj naprawę zeskanowanych PDF‑ów, które zostały zarejestrowane bokiem.  
3. **Gotowy do druku wynik** – zapewnij prawidłowe drukowanie grafik w trybie poziomym na papierze ustawionym pionowo.

## Wskazówki dotyczące wydajności

- **Zamykaj zasoby od razu** – blok `try‑with‑resources` automatycznie zwalnia `Viewer`.  
- **Przetwarzanie wsadowe** – przy obsłudze wielu plików używaj jednej instancji `Viewer` na wątek, aby zmniejszyć narzut.  
- **Monitoruj pamięć** – dla dokumentów większych niż 100 MB rozważ strumieniowanie wyniku na dysk zamiast trzymania go w pamięci.

## Najczęściej zadawane pytania

**P: Czy mogę obrócić wiele stron jednocześnie?**  
O: Tak — wywołaj `rotatePage()` dla każdego numeru strony, który chcesz obrócić.

**P: Czy istnieje sposób cofnięcia obrotu po renderowaniu?**  
O: Nie bezpośrednio. Należy ponownie wyrenderować dokument bez opcji obrotu.

**P: Które formaty plików obsługują obrót stron w GroupDocs Viewer?**  
O: DOCX, PDF, PPTX, XLSX i wiele innych wymienionych w oficjalnej dokumentacji.

**P: Jak mogę automatycznie obracać strony w partii dokumentów?**  
O: Umieść kod w pętli iterującej po kolekcji ścieżek plików, stosując tę samą logikę `rotatePage` dla każdego z nich.

**P: Jaka jest najlepsza praktyka obsługi błędów podczas obrotu?**  
O: Otocz użycie Viewera blokiem `try‑catch`, zaloguj wyjątek i opcjonalnie kontynuuj przetwarzanie kolejnego pliku.

## Zasoby

- **Dokumentacja**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Referencja API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Pobieranie**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Zakup**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Bezpłatna wersja próbna**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Licencja tymczasowa**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Wsparcie**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Ostatnia aktualizacja:** 2026-01-18  
**Testowano z:** GroupDocs Viewer 25.2 dla Javy  
**Autor:** GroupDocs  

---