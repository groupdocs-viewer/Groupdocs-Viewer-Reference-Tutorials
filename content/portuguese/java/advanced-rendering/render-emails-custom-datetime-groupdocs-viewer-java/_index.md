---
date: '2026-09-15'
description: Aprenda como converter eml para html com um formato de datetime personalizado
  e timezone offset usando GroupDocs.Viewer para Java — ideal para email archiving
  e support portals.
keywords:
- convert eml to html
- custom datetime format
- set timezone offset
- email rendering html
lastmod: '2026-09-15'
og_description: Converter eml para html com um formato de datetime personalizado e
  timezone offset usando GroupDocs.Viewer para Java. Siga este step‑by‑step guide
  para accurate email rendering.
og_image_alt: Screenshot of GroupDocs.Viewer rendering an email to HTML with custom
  datetime in Java
og_title: Converter eml para html com datetime personalizado em java usando GroupDocs.Viewer
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  headline: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  type: TechArticle
- description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  name: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  steps:
  - name: set up output directory and file path
    text: Define where the generated HTML will be saved. *Explanation:* `Path.of()`
      creates a reference to the folder where the HTML will be saved. `resolve()`
      appends the file name.
  - name: initialize viewer with email file
    text: Instantiate the `Viewer` class for the target EML file. *Explanation:* The
      `Viewer` instance points to the EML file you want to convert.
  - name: configure HtmlViewOptions
    text: Create an `HtmlViewOptions` object that bundles images and other resources
      directly into the HTML output. *Explanation:* `forEmbeddedResources()` bundles
      images and other resources directly into the HTML output.
  - name: set custom datetime format *(custom datetime java)*
    text: '`setDateTimeFormat` sets the date‑time pattern used when rendering email
      timestamps. Define the pattern that will be used for all timestamps in the rendered
      HTML. *Explanation:* This pattern displays the month, day, year, hour, minute,
      AM/PM marker, and the timezone offset (`zzz`).'
  - name: set timezone offset *(timezone offset java)*
    text: '`setTimeZoneOffset` specifies the time‑zone that will be applied to all
      email timestamps. Adjust timestamps to the desired time zone. *Explanation:*
      Adjusts the rendered timestamps to the desired time zone. Replace `"GMT+1"`
      with any valid zone identifier.'
  - name: render document
    text: Execute the conversion and produce the final HTML file. *Explanation:* Executes
      the conversion, producing an HTML file with your custom date‑time settings.
  type: HowTo
- questions:
  - answer: Attachments are automatically embedded when you use `HtmlViewOptions.forEmbeddedResources()`.
      You can also extract them via the Viewer API if you need separate files.
    question: How do I handle eml files with attachments?
  - answer: Yes, after rendering you can edit the generated HTML file or inject CSS
      programmatically before saving.
    question: Can I change the HTML template or add custom CSS?
  - answer: Wrap the rendering logic in a loop and reuse the same `HtmlViewOptions`
      instance for each file.
    question: Is it possible to render multiple eml files in a batch?
  - answer: GroupDocs.Viewer also supports MSG, PST, and other email containers—simply
      change the file extension in the `Viewer` constructor.
    question: What if I need to support other email formats like msg?
  - answer: Licensing is per deployment; consult the GroupDocs licensing guide for
      multi‑server scenarios.
    question: Do I need a separate license for each server?
  type: FAQPage
tags:
- convert eml
- GroupDocs Viewer
- java email conversion
- email to html
- custom datetime
title: Converter eml para html com datetime personalizado em java usando GroupDocs.Viewer
type: docs
url: /pt/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# Converter eml para html com datetime personalizado em java usando GroupDocs.Viewer

Em sistemas modernos de suporte e arquivamento, **converter eml para html** rapidamente enquanto preserva timestamps exatos é uma capacidade indispensável. Este tutorial mostra como renderizar um e‑mail EML para HTML, aplicar um **formato de datetime personalizado** e definir um **deslocamento de fuso horário** usando GroupDocs.Viewer para Java. Ao final, você terá um trecho reutilizável que produz visualizações de e‑mail precisas e prontas para a web para qualquer fluxo de **conversão de email para html**.

![Render Emails with Custom DateTime with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

## Respostas rápidas
- **GroupDocs.Viewer pode converter EML para HTML?** Sim – a API renderiza arquivos EML diretamente para HTML sem clientes de e‑mail externos.  
- **Preciso de uma licença para produção?** Um teste gratuito serve para testes; uma licença paga é necessária para implantações em produção.  
- **Qual versão do Java é suportada?** Java 8 ou superior é totalmente suportado.  
- **Como altero o formato de data exibido?** Chame `options.getEmailOptions().setDateTimeFormat("MMM dd, yyyy hh:mm a zzz")`.  
- **Posso ajustar o fuso horário?** Sim, use `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"))`.

## O que é “converter eml para html”?
`Convert eml to html` é o processo de transformar um arquivo de e‑mail EML em um documento HTML para renderização no navegador. Converter um arquivo EML para HTML transforma o e‑mail bruto (incluindo cabeçalhos, corpo e anexos) em um formato amigável à web que os navegadores podem exibir sem plugins adicionais. Isso facilita a incorporação de e‑mails em aplicações web, arquivos ou painéis de suporte.

## Por que usar o GroupDocs.Viewer para esta tarefa?
GroupDocs.Viewer suporta **mais de 50 formatos de entrada e saída**, incluindo EML, MSG, PST e PDF, e pode renderizar e‑mails com centenas de páginas sem carregar o arquivo inteiro na memória. Seu mecanismo sem dependências elimina a necessidade de Outlook ou analisadores de terceiros, dando a você controle total sobre **formato de datetime personalizado** e **deslocamento de fuso horário**, mantendo o uso de recursos baixo.

## Pré-requisitos
- GroupDocs.Viewer for Java ≥ 25.2  
- JDK 8+ e uma IDE Java (IntelliJ IDEA, Eclipse, VS Code)  
- Maven para gerenciamento de dependências  

## Configurando o GroupDocs.Viewer para Java

### Configuração do Maven
Adicione o repositório GroupDocs e a dependência Viewer ao seu arquivo `pom.xml`.

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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

### Aquisição de licença
Comece com um teste gratuito ou solicite uma licença temporária para testes prolongados. Adquira uma licença completa para uso em produção.

### Inicialização básica
Crie uma instância `Viewer` que aponta para o arquivo EML que você deseja converter.

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Converter eml para html com datetime personalizado em java

Os passos a seguir orientam você a renderizar um arquivo EML para HTML aplicando um formato de datetime personalizado e um deslocamento de fuso horário.

### Etapa 1: configurar diretório de saída e caminho do arquivo
Defina onde o HTML gerado será salvo.

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*Explicação:* `Path.of()` cria uma referência à pasta onde o HTML será salvo. `resolve()` adiciona o nome do arquivo.

### Etapa 2: inicializar o viewer com o arquivo de e‑mail
Instancie a classe `Viewer` para o arquivo EML alvo.

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*Explicação:* A instância `Viewer` aponta para o arquivo EML que você deseja converter.

### Etapa 3: configurar HtmlViewOptions
Crie um objeto `HtmlViewOptions` que incorpora imagens e outros recursos diretamente na saída HTML.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*Explicação:* `forEmbeddedResources()` incorpora imagens e outros recursos diretamente na saída HTML.

### Etapa 4: definir formato de datetime personalizado *(custom datetime java)*
`setDateTimeFormat` define o padrão de data‑hora usado ao renderizar timestamps de e‑mail.  
Defina o padrão que será usado para todos os timestamps no HTML renderizado.

```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*Explicação:* Este padrão exibe o mês, dia, ano, hora, minuto, marcador AM/PM e o deslocamento de fuso horário (`zzz`).

### Etapa 5: definir deslocamento de fuso horário *(timezone offset java)*
`setTimeZoneOffset` especifica o fuso horário que será aplicado a todos os timestamps de e‑mail.  
Ajuste os timestamps para o fuso horário desejado.

```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*Explicação:* Ajusta os timestamps renderizados para o fuso horário desejado. Substitua `"GMT+1"` por qualquer identificador de zona válido.

### Como ajustar o fuso horário do e‑mail em java
Se precisar **ajustar o fuso horário do e‑mail** além de deslocamentos simples — como lidar com mudanças de horário de verão — você pode obter o objeto `TimeZone` apropriado da API `java.util.TimeZone` usando IDs de região como `"Europe/Paris"` ou `"America/New_York"` e passá‑lo para `setTimeZoneOffset`. Isso garante que os timestamps dos e‑mails sempre reflitam o horário local correto.

### Etapa 6: renderizar o documento
Execute a conversão e produza o arquivo HTML final.

```java
viewer.view(options);
```
*Explicação:* Executa a conversão, produzindo um arquivo HTML com suas configurações de data‑hora personalizadas.

## Como o formato de datetime personalizado impacta o HTML renderizado?
O formato de datetime personalizado determina como cada timestamp de e‑mail aparece no HTML gerado, afetando a legibilidade e a conformidade com a localidade. Ao especificar um padrão como `"MMM dd, yyyy hh:mm a zzz"`, você garante que cada data seja exibida de forma consistente, incluindo a abreviação do mês, dia, ano, hora, minuto, marcador AM/PM e o deslocamento de fuso horário explícito, o que é crucial para equipes de suporte globais.

## Quais formatos de arquivo o GroupDocs.Viewer suporta para renderização de e‑mail?
GroupDocs.Viewer pode renderizar arquivos **EML, MSG, PST, MBOX e EMLX** para HTML, PDF, PNG e JPEG. Ele suporta mais de 50 formatos de documentos e imagens, permitindo converter e‑mails para qualquer dos formatos web‑friendly mais comuns sem conversores adicionais.

## Como posso converter em lote vários arquivos eml?
Coloque todos os arquivos EML em um único diretório, itere sobre cada arquivo com uma estrutura `for` ou `foreach`, reutilize a mesma instância `HtmlViewOptions` e chame `viewer.view` para cada arquivo. Essa abordagem minimiza a sobrecarga de criação de objetos e acelera conversões em massa.

## Dicas de solução de problemas
- **FileNotFoundException:** Verifique os caminhos usados em `Viewer` e `Path.of()`.  
- **Incorrect timestamps:** Certifique-se de que o ID `TimeZone` corresponde à sua região alvo.  
- **Missing images:** Confirme que você usou `HtmlViewOptions.forEmbeddedResources()`; caso contrário, recursos externos podem ser omitidos.  

## Aplicações práticas
1. **Arquivamento de e‑mail:** Armazene snapshots HTML pesquisáveis de e‑mails para auditorias de conformidade.  
2. **Portais de suporte ao cliente:** Exiba tickets recebidos com horários locais precisos para agentes em todo o mundo.  
3. **Documentação legal:** Produza registros de e‑mail prontos para o tribunal com timestamps padronizados.  

## Considerações de desempenho
- Implante em um servidor dedicado para conversões em lote.  
- Monitore o uso do heap Java; aumente `-Xmx` se encontrar `OutOfMemoryError`.  
- Cache o HTML renderizado quando o mesmo e‑mail for solicitado repetidamente para reduzir a carga da CPU.  

## Conclusão
Agora você tem um método completo e pronto para produção para **converter eml para html** com um formato de datetime personalizado e deslocamento de fuso horário usando GroupDocs.Viewer para Java. Esta solução melhora a legibilidade, garante a precisão dos timestamps e se integra perfeitamente a fluxos de trabalho de arquivamento, suporte ou jurídico.

**Próximos passos:** Explore opções adicionais do Viewer, como injeção de CSS personalizada, paginação ou conversão para PDF para adaptar ainda mais a saída às necessidades da sua aplicação.

## Perguntas frequentes

**Q: Como lido com arquivos eml com anexos?**  
A: Os anexos são incorporados automaticamente quando você usa `HtmlViewOptions.forEmbeddedResources()`. Você também pode extraí‑los via a API Viewer se precisar de arquivos separados.

**Q: Posso alterar o modelo HTML ou adicionar CSS personalizado?**  
A: Sim, após a renderização você pode editar o arquivo HTML gerado ou injetar CSS programaticamente antes de salvar.

**Q: É possível renderizar vários arquivos eml em lote?**  
A: Envolva a lógica de renderização em um loop e reutilize a mesma instância `HtmlViewOptions` para cada arquivo.

**Q: E se eu precisar suportar outros formatos de e‑mail como msg?**  
A: O GroupDocs.Viewer também suporta MSG, PST e outros contêineres de e‑mail — basta mudar a extensão do arquivo no construtor `Viewer`.

**Q: Preciso de uma licença separada para cada servidor?**  
A: A licença é por implantação; consulte o guia de licenciamento do GroupDocs para cenários multi‑servidor.

## Recursos

- [Documentação](https://docs.groupdocs.com/viewer/java/)
- [Referência da API](https://reference.groupdocs.com/viewer/java/)
- [Baixar](https://releases.groupdocs.com/viewer/java/)
- [Compra](https://purchase.groupdocs.com/buy)
- [Teste gratuito](https://releases.groupdocs.com/viewer/java/)
- [Licença temporária](https://purchase.groupdocs.com/temporary-license/)
- [Fórum de suporte](https://forum.groupdocs.com/c/viewer/9)

---

**Última atualização:** 2026-09-15  
**Testado com:** GroupDocs.Viewer 25.2 (Java)  
**Autor:** GroupDocs

## Tutoriais relacionados

- [Converter e‑mail para HTML e renomear campos – GroupDocs Viewer Java](/viewer/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/)
- [java converter msg para pdf – Otimizar renderização de Email‑para‑PDF com GroupDocs.Viewer](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)
- [GroupDocs Viewer Java Renderização HTML Responsiva](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
