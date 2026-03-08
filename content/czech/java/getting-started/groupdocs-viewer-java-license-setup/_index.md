---
date: '2026-03-08'
description: Naučte se, jak získat dočasnou licenci, nastavit GroupDocs.Viewer pro
  Javu pomocí lokálních souborů nebo URL a ověřit dostupnost cesty k licenci.
keywords:
- GroupDocs.Viewer Java license
- setting license in Java
- HTTP URL-based licenses
title: Jak získat dočasnou licenci a nastavit licence v GroupDocs.Viewer Java
type: docs
url: /cs/java/getting-started/groupdocs-viewer-java-license-setup/
weight: 1
---

# Jak získat dočasnou licenci a nastavit licence v GroupDocs.Viewer Java

Efektivní správa licencí je klíčová při integraci knihoven třetích stran, jako je **GroupDocs.Viewer for Java**, do vašich aplikací. Tento průvodce vám ukáže **jak získat dočasnou licenci**, nastavit ji z lokálního souboru nebo HTTP URL a ověřit, že cesta k licenci je správná. Na konci tohoto tutoriálu budete mít spolehlivé, připravené pro produkci nastavení licencí, které udrží vaši aplikaci v souladu a výkonnou.

![File and URL Setup with GroupDocs.Viewer for Java](/viewer/getting-started/file-and-url-setup-png.png)

## Rychlé odpovědi
- **Jak získám dočasnou licenci?** Požádejte o ni na stránce GroupDocs temporary‑license a stáhněte soubor *.lic*.  
- **Mohu načíst licenci z URL?** Ano – stačí nasměrovat `License.setLicense` na HTTP adresu, která vrací platný licenční soubor.  
- **Co se stane, pokud chybí cesta k licenci?** Implementujte kontrolu, která zobrazí návod a zabrání spuštění vieweru.  
- **Musím po změně licence restartovat aplikaci?** Ne, `License.setLicense` lze zavolat za běhu.  
- **Jaká verze Javy je vyžadována?** Doporučuje se JDK 8 nebo vyšší.

## Co je dočasná licence?
**Dočasná licence** je časově omezený klíč vydaný společností GroupDocs, který vám umožní vyzkoušet produkt bez zakoupení plné licence. Chová se přesně jako trvalá licence po dobu své platnosti, což vám umožní testovat všechny funkce v reálném prostředí.

## Proč získat dočasnou licenci?
- **Rychlé vyhodnocení:** Získejte plnou funkčnost okamžitě pro projekty proof‑of‑concept.  
- **Žádný finanční závazek:** Otestujte před zakoupením.  
- **Jednoduchá integrace:** Funguje se stejnými API voláními jako trvalá licence.

## Předpoklady
1. **Java Development Kit (JDK):** Verze 8 nebo vyšší.  
2. **IDE:** IntelliJ IDEA, Eclipse nebo jakékoli Java‑kompatibilní IDE.  
3. **GroupDocs.Viewer for Java knihovna:** Přidána do vašeho projektu (viz nastavení Maven níže).  
4. **Základní znalost Javy:** Znalost tříd, importů a zpracování výjimek.

## Nastavení GroupDocs.Viewer pro Java
Pro začátek zahrňte knihovnu do svého Maven projektu.

### Konfigurace Maven
Add the following configuration to your `pom.xml` file:
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

## Získání licence
To use GroupDocs.Viewer, obtain a license:
- **Bezplatná zkušební verze:** Stáhněte z [GroupDocs site](https://releases.groupdocs.com/viewer/java/).  
- **Dočasná licence:** Požádejte o ni na [temporary-license page](https://purchase.groupdocs.com/temporary-license/).  
- **Nákup:** Pro trvalé řešení zvažte zakoupení licence na [GroupDocs purchase page](https://purchase.groupdocs.com/buy).

### Základní inicializace
Once the library is added, you can initialize the viewer:
```java
import com.groupdocs.viewer.License;

public class InitializeViewer {
    public static void main(String[] args) {
        License license = new License();
        // Set the path to your license file or URL here
        license.setLicense("YOUR_LICENSE_PATH");
        System.out.println("GroupDocs.Viewer initialized successfully.");
    }
}
```

## Jak získat dočasnou licenci a nastavit ji ze souboru
### Přehled
Nastavení licence z lokálního souboru je nejnáročnější přístup a funguje i když aplikace běží offline.

### Kroky implementace
1. **Definujte cestu k licenci** – nasměrujte na soubor *.lic*, který jste obdrželi po žádosti o dočasnou licenci:
```java
final String licensePath = "YOUR_DOCUMENT_DIRECTORY/your-license-file.lic";
```
2. **Aplikujte licenci** – použijte třídu `License` pro načtení:
```java
import com.groupdocs.viewer.License;

public class SetLicenseFromFile {
    public static void run() {
        if (licensePath != null && !licensePath.startsWith("http")) {
            License license = new License();
            license.setLicense(licensePath);
            System.out.println("License set successfully.");
        } else {
            // Handle cases where the path is not valid
            System.err.println(
                "We do not ship any license with this example.\n" +
                "Visit the GroupDocs site to obtain either a temporary or permanent license.\n" +
                "Learn more about licensing at https://purchase.groupdocs.com/faqs/licensing.\n" +
                "Lear how to request temporary license at https://purchase.groupdocs.com/temporary-license.");
        }
    }
}
```
**Tipy:**  
- Ověřte, že cesta k souboru je absolutní nebo relativní k pracovnímu adresáři.  
- Zajistěte, aby soubor měl oprávnění ke čtení pro uživatele, který spouští JVM.

## Jak zacházet s URL licence
### Přehled
Licence založená na URL je praktická pro cloudová nasazení, kde licenční soubor žije v zabezpečeném úložišti.

### Kroky implementace
1. **Definujte URL licence** – nahraďte zástupný text vaším skutečným koncovým bodem:
```java
final String licensePath = "http://example.com/license.lic";
```
2. **Detekujte a zaznamenejte použití URL** – níže uvedený příklad vás jednoduše informuje, že byla zadána URL:
```java
public class HandleLicenseURL {
    public static void run() {
        if (licensePath != null && licensePath.startsWith("http")) {
            System.err.println("License path was not provided, license URL is found instead!");
        }
    }
}
```
**Tipy:**  
- V produkci byste soubor stáhli (např. pomocí `java.net.HttpURLConnection`) a poté zavolali `license.setLicense(stream)`.  
- Přidejte logiku opakování a zpracování časových limitů, aby se vyrovnala s přechodnými síťovými problémy.

## Jak zkontrolovat dostupnost licence (ověřit cestu k licenci)
### Přehled
Před pokusem o načtení licence je dobrým zvykem **zkontrolovat dostupnost licence**, abyste mohli nasměrovat vývojáře nebo uživatele k získání dočasné licence, pokud je potřeba.

### Kroky implementace
1. **Simulujte chybějící cestu k licenci**:
```java
final String licensePath = null;
```
2. **Poskytněte jasné pokyny, pokud cesta chybí**:
```java
public class CheckLicensePathAvailability {
    public static void run() {
        if (licensePath == null) {
            System.out.println(
                "\nWe do not ship any license with this example.\n" +
                "Visit the GroupDocs site to obtain either a temporary or permanent license.\n" +
                "Learn more about licensing at https://purchase.groupdocs.com/faqs/licensing.\n" +
                "Lear how to request temporary license at https://purchase.groupdocs.com/temporary-license.");
        }
    }
}
```
**Tipy:**  
- Zaznamenejte tuto zprávu při spuštění, aby operační týmy věděly, že licence chybí.  
- Zvažte ukončení aplikace nebo zakázání funkcí vieweru, dokud nebude poskytnuta platná licence.

## Praktické aplikace
Pochopení, jak **získat dočasnou licenci**, nastavit ji ze souboru nebo URL a **ověřit dostupnost cesty k licenci**, odemyká několik reálných scénářů:
1. **Systémy pro správu dokumentů** – vložte viewer, který automaticky ověřuje licenci při každém spuštění.  
2. **Cloudové SaaS platformy** – uložte licenci v chráněném úložišti blob a načtěte ji přes URL pro aktualizace bez výpadku.  
3. **Enterprise nasazení** – použijte dočasnou licenci během pilotních fází před zakoupením plnohodnotné licence.

## Úvahy o výkonu
- **Využití zdrojů:** Načtěte licenci jednou při startu aplikace; opakované volání přidává zbytečný I/O.  
- **Správa paměti:** Objekt `License` drží minimální stav, ale vždy zavírejte streamy, pokud licenci stahujete ručně.

## Závěr
Podle výše uvedených kroků můžete **získat dočasnou licenci**, nakonfigurovat GroupDocs.Viewer pro Java pomocí lokálního souboru nebo HTTP URL a **zkontrolovat dostupnost licence**, aby vaše aplikace byla v souladu. Tento pevný základ licencování zabraňuje chybám za běhu a poskytuje vám flexibilitu přecházet mezi vývojovým, testovacím a produkčním prostředím s jistotou.

### Často kladené otázky
1. **Jak nastavit lokální licenční soubor v GroupDocs.Viewer Java?**  

   Použijte `license.setLicense("path/to/license.lic")` s správnou cestou k souboru pro aplikaci lokální licence.

2. **Mohu načíst licenci přímo z URL?**  

   Ano, ale ujistěte se, že váš kód zvládá přístup k URL, případně stáhne licenci za běhu nebo řeší síťové problémy.

3. **Co mám dělat, pokud je cesta k licenci neplatná nebo chybí?**  

   Implementujte kontroly na null nebo neplatné cesty a poskytněte návod nebo záložní výzvy k získání platné licence.

4. **Je možné dynamicky přepínat mezi licenčním souborem a URL?**  

   Ano, přidáním podmíněné logiky, která zvládne oba scénáře podle vašeho prostředí nebo parametrů za běhu.

5. **Jaké jsou osvědčené postupy pro správu licencí v produkci?**  

   Ukládejte licence bezpečně, pravidelně ověřujte jejich platnost a implementujte zpracování chyb souvisejících s licencí, aby byl zajištěn nepřerušený provoz.

## Často kladené otázky
**Q: Jak dlouho dočasná licence platí?**  
A: Obvykle 30 dnů, poté můžete požádat o obnovení nebo přejít na trvalou licenci.

**Q: Potřebuji internetové připojení pro použití licence založené na souboru?**  
A: Ne. Lokální soubor *.lic* funguje zcela offline po načtení.

**Q: Mohu licenční soubor šifrovat pro vyšší bezpečnost?**  
A: Licenční soubor je již podepsán společností GroupDocs; další šifrování je volitelné, ale není vyžadováno.

**Q: Co se stane, pokud licence vyprší během běhu aplikace?**  
A: Operace vieweru začnou házet výjimky související s licencí; doporučuje se kontrolovat expiraci při startu.

**Q: Je bezpečné ukládat URL licence ve zdrojovém kódu?**  
A: Vyhněte se ukládání citlivých URL; místo toho použijte proměnné prostředí nebo zabezpečené úložiště konfigurací.

---

**Poslední aktualizace:** 2026-03-08  
**Testováno s:** GroupDocs.Viewer 25.2 pro Java  
**Autor:** GroupDocs