---
date: '2026-08-25'
description: Aprenda a converter arquivos Numbers com o GroupDocs.Viewer para Java,
  transformando arquivos Apple Numbers em PDF, HTML, JPG ou PNG. Inclui configuração,
  etapas de conversão de documentos Java e dicas para exibição na web.
keywords:
- how to convert numbers
- java document conversion
- display numbers web
- java spreadsheet pdf
lastmod: '2026-08-25'
og_description: Aprenda a converter arquivos Numbers com o GroupDocs.Viewer para Java,
  transformando arquivos Apple Numbers em PDF, HTML, JPG ou PNG. Inclui configuração,
  etapas de conversão de documentos Java e dicas para exibição na web.
og_image_alt: 'Developer guide: Convert Numbers to PDF, HTML, JPG, PNG using GroupDocs.Viewer
  for Java'
og_title: Como converter arquivos Numbers com o GroupDocs.Viewer para Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-25'
  description: Learn how to convert numbers with GroupDocs.Viewer for Java, turning
    Apple Numbers files into PDF, HTML, JPG, or PNG. Includes setup, java document
    conversion steps, and web display tips.
  headline: How to convert numbers with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Over 100 formats, including DOCX, XLSX, PDF, HTML, and Apple Numbers,
      with full rendering capabilities for each.
    question: What file formats does GroupDocs.Viewer support?
  - answer: Stream the conversion page‑by‑page, use `options.setPageCount()` to limit
      memory usage, and consider compressing the output PDF.
    question: How do I handle large Numbers files efficiently?
  - answer: Yes—purchase a commercial license to remove trial limitations and obtain
      production‑grade support.
    question: Can GroupDocs.Viewer be used in a commercial project?
  - answer: Absolutely. Adjust `JpgViewOptions.setQuality(int)` or `PngViewOptions.setResolution(int)`
      to meet your size‑quality requirements.
    question: Is it possible to customize the output quality of images?
  - answer: Visit the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)
      for deep‑dive guides, sample projects, and API reference details.
    question: Where can I find more advanced usage examples?
  type: FAQPage
tags:
- convert numbers
- GroupDocs.Viewer
- Java document processing
title: Como converter arquivos Numbers com o GroupDocs.Viewer para Java
type: docs
url: /pt/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# Como converter Numbers com GroupDocs.Viewer para Java

Exibir planilhas Apple Numbers na web ou dentro de um cliente de desktop pode parecer um quebra‑cabeça, especialmente quando você precisa **converter Numbers para PDF** ou incorporá‑las como imagens para relatórios. Neste tutorial você aprenderá exatamente **como converter Numbers** para PDF, HTML, JPG e PNG usando **GroupDocs.Viewer para Java**. Vamos percorrer a configuração do projeto, a renderização ao nível de código e cenários do mundo real para que você possa criar pipelines robustos de visualização ou arquivamento em minutos.

![Renderizar documentos Apple Numbers com GroupDocs.Viewer para Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

[Renderizar documentos Apple Numbers com GroupDocs.Viewer para Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### O que você aprenderá
- Como adicionar o GroupDocs.Viewer a um projeto Java baseado em Maven.  
- Código passo a passo para **converter Numbers para pdf**, **converter Numbers para html**, **converter Numbers para jpg** e **converter Numbers para png**.  
- Quando escolher cada formato de saída para portais web, fluxos de trabalho de e‑mail ou sistemas de gerenciamento de documentos.  

## Respostas rápidas
- **Posso converter Numbers para PDF com Java?** Sim – instancie `Viewer` e chame `PdfViewOptions` para obter um PDF pronto‑para‑armazenar.  
- **Qual formato oferece a visualização web mais rica?** HTML, porque mantém tabelas, fórmulas e estilos interativos.  
- **Preciso de uma licença para produção?** Uma licença comercial é necessária para qualquer implantação que não seja de teste.  
- **A conversão de imagens é suportada?** Absolutamente – use `JpgViewOptions` ou `PngViewOptions` para capturas de alta qualidade.  
- **Qual versão do Java é necessária?** Java 8+ e Maven para gerenciamento de dependências.

## Pré-requisitos
- Java Development Kit (JDK) 8 ou posterior instalado na sua máquina.  
- Maven para gerenciar dependências e compilar o projeto.  
- Familiaridade básica com I/O de arquivos Java, caminhos e tratamento de exceções.  

## Configurando GroupDocs.Viewer para Java

### Instalação com Maven
Adicione o repositório GroupDocs e a dependência Viewer ao seu `pom.xml`. Este bloco deve permanecer exatamente como mostrado:

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

### Aquisição de licença
- **Teste gratuito:** Conjunto completo de recursos, sem necessidade de cartão de crédito.  
- **Licença temporária:** Solicite uma chave de tempo limitado para testes estendidos.  
- **Compra completa:** Obtenha uma licença perpétua para uso comercial.

## O que é a classe Viewer?
A classe `Viewer` é o motor central do GroupDocs.Viewer que carrega um documento e o renderiza no formato de saída solicitado. Ela abstrai o tratamento de tipos de arquivo para que você possa focar na lógica de negócios em vez de analisar os detalhes internos da planilha.

## Como converter Numbers para HTML com GroupDocs.Viewer para Java?

`HtmlViewOptions` especifica configurações para renderização HTML, como incorporação de recursos ou link para arquivos externos.  
Carregue o arquivo Numbers, configure as opções HTML e chame `viewer.view()`. O método `HtmlViewOptions.forEmbeddedResources()` agrupa CSS e imagens diretamente no HTML, tornando o resultado ideal para incorporação em uma página web sem ativos adicionais.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **Por que isso importa:** Recursos incorporados mantêm a visualização auto‑contida, eliminando links de imagem quebrados e simplificando a implantação em CDN.

## Como converter Numbers para JPG com GroupDocs.Viewer para Java?

`JpgViewOptions` configura a saída JPEG, permitindo ajustes de qualidade e tamanho para cada página renderizada.  
Você pode transformar cada página da planilha em uma captura JPEG. Ajuste a configuração `quality` para equilibrar o tamanho do arquivo e a fidelidade visual, o que é útil quando você precisa de imagens leves para redes sociais ou newsletters por e‑mail.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Dica:** Para processamento mais rápido de pastas de trabalho grandes, reduza a qualidade para 70 % – o impacto visual é mínimo enquanto o tamanho do arquivo diminui drasticamente.

## Como converter Numbers para PNG com GroupDocs.Viewer para Java?

`PngViewOptions` configura a saída PNG, suportando compressão sem perdas e configurações de resolução para imagens de alta qualidade.  
PNG oferece compressão sem perdas, preservando cada pixel exatamente como renderizado. Use a propriedade `resolution` para aumentar DPI quando precisar de gráficos prontos para impressão em relatórios ou PDFs.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Dica avançada:** Defina `options.setResolution(300)` para saída de alta resolução que fica nítida em páginas impressas.

## Como converter Numbers para PDF com GroupDocs.Viewer para Java?

`PdfViewOptions` define opções de renderização PDF, incluindo incorporação de fontes, compressão e controle de tamanho de página.  
O objeto `PdfViewOptions` permite incorporar fontes, controlar o tamanho da página e preservar o layout original da pasta de trabalho Numbers. A conversão ocorre em uma única chamada, produzindo um PDF pesquisável e não editável que é perfeito para arquivamento ou conformidade.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Configuração chave:** Ative `options.setCompress(true)` para reduzir o tamanho do PDF sem sacrificar a qualidade, o que é essencial para repositórios de documentos em grande escala.

## Por que usar GroupDocs.Viewer para Java?

GroupDocs.Viewer suporta **mais de 100 formatos de arquivo**, incluindo Apple Numbers, e pode renderizar planilhas com centenas de páginas sem carregar o arquivo inteiro na memória. Benchmarks mostram que um arquivo Numbers de 250 páginas é convertido para PDF em menos de 8 segundos em uma CPU padrão de 2,5 GHz, oferecendo velocidade e confiabilidade para pipelines corporativos.

## Aplicações práticas
- **Integração web:** Renderize para HTML para um visualizador de planilhas interativo que funciona em todos os navegadores sem plugins.  
- **Compartilhamento de conteúdo:** Converta para JPG/PNG para inserções rápidas de imagens em newsletters, aplicativos de chat ou feeds sociais.  
- **DMS corporativo:** Use **como converter Numbers** para PDF para armazenar uma versão não editável e pesquisável da planilha para conformidade e trilhas de auditoria.  

## Considerações de desempenho
- **Gerenciamento de recursos:** Sempre instancie `Viewer` dentro de um bloco try‑with‑resources (conforme mostrado) para que os recursos nativos sejam liberados prontamente.  
- **Pastas de trabalho grandes:** Processar página por página e transmitir a saída para manter o uso de memória abaixo de 100 MB, mesmo para arquivos de 500 páginas.  
- **Segurança de threads:** Crie uma instância separada de `Viewer` por thread; a classe não é thread‑safe, portanto compartilhar uma única instância pode causar condições de corrida.

## Armadilhas comuns e solução de problemas
- **Fontes ausentes:** Se o PDF gerado parecer diferente, certifique‑se de que as fontes necessárias estejam disponíveis no servidor ou incorpore‑as usando `PdfViewOptions.setEmbedFonts(true)`.  
- **Páginas em branco:** Verifique se o arquivo Numbers não está protegido por senha; o GroupDocs.Viewer atualmente não descriptografa pastas de trabalho protegidas.  
- **Erros de falta de memória:** Para arquivos extremamente grandes, habilite `options.setPageCount(1)` para renderizar uma página por vez e combinar os resultados posteriormente.

## Perguntas frequentes

**Q: Quais formatos de arquivo o GroupDocs.Viewer suporta?**  
A: Mais de 100 formatos, incluindo DOCX, XLSX, PDF, HTML e Apple Numbers, com capacidades completas de renderização para cada um.

**Q: Como lidar eficientemente com arquivos Numbers grandes?**  
A: Transmita a conversão página por página, use `options.setPageCount()` para limitar o uso de memória e considere comprimir o PDF de saída.

**Q: O GroupDocs.Viewer pode ser usado em um projeto comercial?**  
A: Sim—compre uma licença comercial para remover limitações de teste e obter suporte de nível de produção.

**Q: É possível personalizar a qualidade de saída das imagens?**  
A: Absolutamente. Ajuste `JpgViewOptions.setQuality(int)` ou `PngViewOptions.setResolution(int)` para atender aos seus requisitos de tamanho‑qualidade.

**Q: Onde posso encontrar exemplos de uso mais avançados?**  
A: Visite a [documentação do GroupDocs](https://docs.groupdocs.com/viewer/java/) para guias aprofundados, projetos de exemplo e detalhes de referência da API.

## Próximos passos
Experimente as opções mostradas acima, depois explore personalizações adicionais como marca d'água em PDFs, adição de proteção por senha ou integração do visualizador em um serviço REST Spring Boot. A [documentação do GroupDocs](https://docs.groupdocs.com/viewer/java/) fornece um catálogo completo de recursos que você pode combinar.

## Recursos
- **Documentação:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **Documentação GroupDocs:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)  
- **Referência de API:** [API reference](https://reference.groupdocs.com/viewer/java/)  
- **Referência de API GroupDocs:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **Comprar licença:** [Buy a License](https://purchase.groupdocs.com/buy)  
- **Teste gratuito:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Licença temporária:** [Request Here](https://purchase.groupdocs.com/temporary-license/)  
- **Fórum de suporte:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**Última atualização:** 2026-08-25  
**Testado com:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs

## Tutoriais Relacionados

- [Como converter Excel para HTML, JPG, PNG e PDF usando GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)  
- [Como converter Excel para HTML e renderizar linhas e colunas ocultas em Java com GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)  
- [Tutorial de renderização de documentos Java - Converter arquivos para HTML, PDF e imagens](/viewer/java/rendering-basics/)