---
date: '2026-03-29'
description: Dowiedz się, jak obrócić stronę o 90 stopni w Javie przy użyciu GroupDocs
  Viewer, w tym konfigurację, kod oraz wskazówki dotyczące wydajności.
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: Obróć stronę o 90 stopni przy użyciu GroupDocs Viewer dla Javy
type: docs
url: /pl/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# Obróć stronę o 90 stopni za pomocą GroupDocs Viewer dla Javy

Kiedy potrzebujesz **obrócić stronę o 90 stopni** w dokumencie — niezależnie od tego, czy jest to PDF, plik Word czy arkusz kalkulacyjny — wykonanie tego programowo oszczędza czas i eliminuje błędy ręczne. W tym zaawansowanym przewodniku przeprowadzimy Cię krok po kroku przez dokładne czynności, aby obrócić pierwszą stronę dowolnego obsługiwanego dokumentu przy użyciu **GroupDocs Viewer for Java**. Po zakończeniu będziesz mieć wielokrotnego użytku fragment kodu, który możesz wstawić do własnych projektów.  
Omówimy także, dlaczego obracanie stron w Javie ma znaczenie, typowe scenariusze, w których ta technika się sprawdza, oraz jak utrzymać operację lekką.

![Obróć pierwszą stronę dokumentu za pomocą GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Szybkie odpowiedzi
- **Co oznacza „rotate page 90 degrees”?** Obraca wybraną stronę zgodnie z ruchem wskazówek zegara o ćwierć obrotu.  
- **Która biblioteka obsługuje obrót?** GroupDocs Viewer for Java udostępnia metodę `rotatePage`.  
- **Czy mogę obracać strony PDF w Javie?** Tak — użyj tego samego wywołania `rotatePage`; działa dla PDF, DOCX, XLSX i innych.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w środowisku deweloperskim; płatna licencja jest wymagana w produkcji.  
- **Czy operacja jest intensywna pod względem pamięci?** Nie, jeśli szybko zamkniesz instancję `Viewer`; zobacz wskazówki dotyczące wydajności poniżej.

## Co to jest „rotate page 90 degrees”?
Obrócenie strony o 90 stopni zmienia jej orientację z pionowej na poziomą (lub odwrotnie) bez zmiany zawartości. Jest to szczególnie przydatne przy prezentacjach, drukowaniu grafik wyłącznie w trybie poziomym lub korygowaniu zeskanowanych dokumentów, które zostały zarejestrowane w pozycji bocznej.

## Dlaczego obracać strony programowo za pomocą GroupDocs Viewer for Java?
GroupDocs Viewer ukrywa złożoność obsługi dziesiątek formatów plików. Umożliwia stosowanie transformacji na poziomie stron — takich jak obrót — przy zachowaniu oryginalnego pliku w nienaruszonym stanie. API jest płynne, wątkowo‑bezpieczne i działa na dowolnym środowisku Java 8+, co czyni je niezawodnym wyborem do automatyzacji klasy korporacyjnej.

## Wymagania wstępne
- **GroupDocs.Viewer for Java** (najnowsza wersja)
- **JDK 8** lub nowszy
- **Maven** (lub Gradle) do zarządzania zależnościami
- IDE, takie jak IntelliJ IDEA lub Eclipse
- Podstawowa znajomość Java I/O

## Konfiguracja GroupDocs.Viewer for Java
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
- **Temporary license** – poproś, jeśli potrzebujesz wydłużonego okresu oceny.  
- **Full license** – zakup do wdrożeń produkcyjnych.

### Podstawowa inicjalizacja Viewer
Poniższy kod pokazuje minimalny sposób utworzenia instancji `Viewer`. Zachowaj go dokładnie tak, jak jest przedstawiony:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Jak obrócić stronę PDF w Javie za pomocą GroupDocs Viewer
Chociaż API działa na wielu formatach, PDF jest najczęstszym przypadkiem użycia do obracania stron. Używana jest ta sama metoda `rotatePage`, więc wystarczy wskazać Viewerowi plik PDF i określić numer strony.

## Implementacja krok po kroku: Obróć pierwszą stronę o 90 stopni

### 1. Importuj wymagane pakiety
Te importy zapewniają dostęp do opcji renderowania PDF oraz wyliczenia Rotation.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Zdefiniuj miejsca wyjściowe i utwórz Viewer
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
Metoda `rotatePage` przyjmuje numer strony (liczony od 1) oraz wartość wyliczenia `Rotation`.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Renderuj dokument
Na koniec wywołaj `view`, aby wygenerować obrócony PDF.

```java
viewer.view(viewOptions);
```

#### Jak to działa
- **PdfViewOptions** informuje Viewer, aby wyjściowo generował plik PDF.  
- **rotatePage(int, Rotation)** obraca tylko wskazaną stronę, pozostawiając pozostałe niezmienione.  
- Metoda obsługuje `ON_90_DEGREE`, `ON_180_DEGREE` i `ON_270_DEGREE`.

## Typowe problemy i rozwiązania
| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|---------|--------------|-----|
| **FileNotFoundException** | Nieprawidłowa ścieżka lub brakujący folder | Sprawdź, czy `YOUR_OUTPUT_DIRECTORY` i `YOUR_DOCUMENT_DIRECTORY` istnieją i są czytelne. |
| **Unsupported file format** | Próba obrócenia formatu nieobsługiwanego przez Viewer | Sprawdź stronę [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Użycie niewłaściwego numeru strony (liczonego od 0) | Pamiętaj, że `rotatePage` używa indeksacji **od 1**. |
| **Out‑of‑memory errors on large docs** | Renderowanie wielu dużych plików w jednym wątku | Przetwarzaj dokumenty kolejno lub użyj puli wątków o ograniczonej współbieżności. |

## Praktyczne zastosowania
1. **Dostosowanie prezentacji** – Konwertuj slajd w orientacji pionowej na poziomą w locie.  
2. **Masowa korekta dokumentów** – Automatyzuj naprawę zeskanowanych PDF‑ów, które zostały zarejestrowane w pozycji bocznej.  
3. **Wynik gotowy do druku** – Zapewnij prawidłowe drukowanie grafik w orientacji poziomej na papierze w orientacji pionowej.

## Wskazówki dotyczące wydajności
- **Zamykaj zasoby niezwłocznie** – blok `try‑with‑resources` automatycznie zwalnia `Viewer`.  
- **Przetwarzanie wsadowe** – przy obsłudze wielu plików, ponownie używaj jednej instancji `Viewer` na wątek, aby zmniejszyć narzut.  
- **Monitoruj pamięć** – dla dokumentów większych niż 100 MB rozważ strumieniowanie wyniku na dysk zamiast trzymania go w pamięci.

## Najczęściej zadawane pytania

**Q: Czy mogę obrócić wiele stron jednocześnie?**  
A: Tak — wywołaj `rotatePage()` dla każdego numeru strony, którą chcesz obrócić.

**Q: Czy istnieje sposób na cofnięcie obrotu po renderowaniu?**  
A: Nie bezpośrednio. Należy ponownie wyrenderować dokument bez opcji obrotu.

**Q: Które formaty plików obsługują obrót stron w GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX oraz wiele innych formatów wymienionych w oficjalnej dokumentacji.

**Q: Jak mogę automatycznie obracać strony w partii dokumentów?**  
A: Umieść kod w pętli, która iteruje po kolekcji ścieżek plików, stosując tę samą logikę `rotatePage` dla każdego.

**Q: Jaka jest najlepsza praktyka obsługi błędów podczas obrotu?**  
A: Umieść użycie Viewer w bloku `try‑catch`, zaloguj wyjątek i opcjonalnie kontynuuj przetwarzanie kolejnego pliku.

## Zasoby
- **Dokumentacja**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Referencja API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Pobierz**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Zakup**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Darmowa wersja próbna**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Licencja tymczasowa**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Wsparcie**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Ostatnia aktualizacja:** 2026-03-29  
**Testowano z:** GroupDocs Viewer 25.2 for Java  
**Autor:** GroupDocs