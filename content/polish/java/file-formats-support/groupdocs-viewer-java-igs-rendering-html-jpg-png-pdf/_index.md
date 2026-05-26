---
date: '2026-02-23'
description: Dowiedz się, jak konwertować pliki IGS na PDF, HTML, JPG i PNG za pomocą
  GroupDocs.Viewer dla Javy. Postępuj zgodnie z tym przewodnikiem krok po kroku, zawierającym
  gotowe do uruchomienia przykłady kodu.
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: Konwertuj IGS na PDF, HTML, JPG i PNG przy użyciu GroupDocs.Viewer Java
type: docs
url: /pl/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

**Author:** -> "**Autor:**". Keep same.

Now ensure all markdown formatting preserved.

Check for any other elements: There's a note about "For Polish, ensure proper RTL formatting if needed" but not needed.

Now produce final content.# Konwertuj IGS do PDF, HTML, JPG i PNG przy użyciu GroupDocs.Viewer Java

Jeśli potrzebujesz **konwertować IGS do PDF** (lub do HTML, JPG, PNG) bezpośrednio z aplikacji Java, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię przez wszystko, czego potrzebujesz — od konfiguracji biblioteki po renderowanie modelu 3‑D w formacie pasującym do Twojego projektu. Zobaczysz, dlaczego GroupDocs.Viewer jest solidnym wyborem dla szybkich, niezawodnych konwersji i otrzymasz praktyczny kod, który możesz wstawić do własnego rozwiązania.

![Konwertuj pliki IGS do HTML, JPG, PNG i PDF przy użyciu GroupDocs.Viewer dla Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Szybkie odpowiedzi
- **Czy mogę konwertować IGS do PDF w Javie?** Tak, używając `PdfViewOptions` z GroupDocs.Viewer.  
- **Jakie formaty wyjściowe są obsługiwane?** HTML, JPG, PNG i PDF.  
- **Czy potrzebuję licencji do produkcji?** Wymagana jest licencja komercyjna; dostępna jest darmowa wersja próbna do testów.  
- **Jaka wersja Javy jest wymagana?** JDK 8 or higher.  
- **Czy Maven jest jedynym sposobem dodania biblioteki?** Nie, możesz również użyć Gradle lub ręcznego dołączenia pliku JAR.  

## Co to jest „konwertować IGS do PDF”?
Konwersja IGS (neutralnego formatu plików dla danych CAD 3‑D) do PDF oznacza przekształcenie złożonego modelu 3‑D w statyczny, powszechnie wyświetlany dokument. Jest to przydatne do udostępniania projektów interesariuszom, którzy nie posiadają narzędzi CAD.

## Dlaczego używać GroupDocs.Viewer do konwersji IGS?
- **Zero‑code CAD rendering** – biblioteka zajmuje się ciężką pracą parsowania formatu IGS.  
- **Multiple output options** – jedno wywołanie API może wygenerować HTML, JPG, PNG lub PDF.  
- **Cross‑platform** – działa na każdym systemie operacyjnym obsługującym Javę.  
- **Performance‑focused** – szybkie renderowanie nawet dużych zespołów.  

## Wymagania wstępne
- **GroupDocs.Viewer for Java** ≥ 25.2  
- **JDK 8+** zainstalowany i skonfigurowany w Twoim IDE (IntelliJ IDEA, Eclipse, NetBeans, itp.)  
- Podstawowa znajomość Maven (opcjonalna, ale zalecana)  

## Konfiguracja GroupDocs.Viewer dla Java

### Zależność Maven
Dodaj repozytorium GroupDocs oraz zależność Viewer do swojego `pom.xml`:

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
GroupDocs.Viewer offers:
- **Free trial** – bezpłatna wersja próbna – ograniczone użycie, świetna do szybkich testów.  
- **Temporary license** – licencja tymczasowa – pełny zestaw funkcji na krótki okres oceny.  
- **Commercial license** – licencja komercyjna – nieograniczone użycie w produkcji.  

### Podstawowa inicjalizacja Viewer
Poniższy fragment kodu pokazuje, jak utworzyć instancję `Viewer`, która wskazuje na Twój plik IGS:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## Renderowanie IGS do HTML

### Jak konwertować IGS do HTML?
Wyjście HTML zapewnia interaktywny, przyjazny przeglądarce widok modelu 3‑D.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

**Kluczowy punkt:** `HtmlViewOptions.forEmbeddedResources()` osadza wszystkie wymagane zasoby (CSS, obrazy) bezpośrednio w pliku HTML, co czyni go przenośnym.

## Renderowanie IGS do JPG

### Jak konwertować IGS do JPG?
Obrazy JPG są idealne do miniatur lub szybkich podglądów.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

Możesz dostosować `JpgViewOptions`, aby kontrolować rozdzielczość i jakość kompresji.

## Renderowanie IGS do PNG

### Jak konwertować IGS do PNG?
PNG obsługuje przezroczystość, co jest przydatne przy nakładaniu modelu na różne tła.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

Eksperymentuj z `PngViewOptions`, aby uzyskać najlepszy balans między rozmiarem pliku a jakością wizualną.

## Renderowanie IGS do PDF

### Jak konwertować IGS do PDF?
PDF jest podstawowym formatem do udostępniania szczegółowej dokumentacji projektowej. Ta sekcja bezpośrednio odnosi się do głównego słowa kluczowego **convert IGS to PDF**.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

`PdfViewOptions` pozwala kontrolować układ strony, jakość obrazu oraz czy osadzać czcionki.

## Praktyczne zastosowania
- **Web portals** – osadzaj modele renderowane w HTML bezpośrednio w konfiguratorach produktów.  
- **Marketing assets** – generuj obrazy JPG/PNG wysokiej rozdzielczości do broszur.  
- **Technical documentation** – dołącz renderowane PDF modele CAD w podręcznikach użytkownika.  
- **Quality assurance** – automatyzuj generowanie miniatur dla dużych partii plików IGS.  

## Częste problemy i rozwiązania

| Problem | Rozwiązanie |
|---------|-------------|
| **Folder wyjściowy nie znaleziony** | Sprawdź ścieżkę przekazaną do `Path outputDirectory` i upewnij się, że proces Java ma uprawnienia do zapisu. |
| **Puste strony w PDF** | Upewnij się, że plik IGS nie jest uszkodzony; najpierw spróbuj otworzyć go w przeglądarce CAD. |
| **Wolne renderowanie dużych zespołów** | Zwiększ pamięć JVM (`-Xmx2g` lub więcej) i rozważ renderowanie strona po stronie przy użyciu `viewer.getPageCount()`, jeśli to konieczne. |
| **Brakujące czcionki w PDF** | Użyj `PdfViewOptions`, aby osadzić wymagane czcionki lub zainstaluj brakujące czcionki na serwerze. |

## Najczęściej zadawane pytania

**Q: Czy mogę konwertować wiele plików IGS w jednym uruchomieniu?**  
A: Tak. Przejdź pętlą przez listę ścieżek plików i wywołaj odpowiednią metodę `view` dla każdego.

**Q: Czy można dostosować rozmiar strony PDF?**  
A: Oczywiście. `PdfViewOptions` udostępnia metodę `setPageSize(PageSize.A4)` i podobne.

**Q: Czy potrzebuję osobnej licencji dla każdego formatu wyjściowego?**  
A: Nie. Jedna licencja GroupDocs.Viewer obejmuje wszystkie obsługiwane formaty.

**Q: Jak duży może być plik IGS, zanim wydajność spadnie?**  
A: Biblioteka obsługuje pliki do kilku setek megabajtów, ale może być konieczne przydzielenie większej pamięci JVM dla bardzo dużych modeli.

**Q: Czy mogę renderować tylko określony widok lub orientację?**  
A: GroupDocs.Viewer renderuje domyślny widok. Aby uzyskać niestandardowe orientacje, przed konwersją przetwórz plik IGS w narzędziu CAD.

---

**Ostatnia aktualizacja:** 2026-02-23  
**Testowano z:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs