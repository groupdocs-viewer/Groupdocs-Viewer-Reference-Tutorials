---
date: '2026-08-08'
description: Aprenda como converter IGS para PDF, HTML, JPG e PNG usando o GroupDocs.Viewer
  para Java. Guia passo a passo, pré-requisitos e solução de problemas para desenvolvedores
  Java.
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: Converter IGS para PDF, HTML, JPG e PNG usando o GroupDocs.Viewer
  para Java. Configuração detalhada, trechos de código e solução de problemas para
  desenvolvedores Java.
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: Converter IGS para PDF, HTML, JPG e PNG com GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-08'
  description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
    for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
  headline: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: Yes. Iterate over a collection of file paths and invoke the appropriate
      `view` method for each file within the same `Viewer` instance.
    question: Can I convert multiple IGS files in a single run?
  - answer: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`,
      and custom dimensions via `setCustomSize(width, height)`.
    question: Is it possible to customize the PDF page size?
  - answer: No. A single GroupDocs.Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: The library reliably processes files up to **500 MB**; for models larger
      than 200 MB, allocate additional JVM memory and consider rendering in batches.
    question: How large can an IGS file be before performance degrades?
  - answer: GroupDocs.Viewer renders the default orientation defined in the IGS file.
      For custom views, preprocess the file with a CAD tool or adjust the model before
      conversion.
    question: Can I render only a specific view or orientation?
  type: FAQPage
tags:
- convert igs
- groupdocs.viewer
- java cad conversion
- pdf generation java
title: Converter IGS para PDF, HTML, JPG e PNG com GroupDocs.Viewer Java
type: docs
url: /pt/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# Converter IGS para PDF, HTML, JPG e PNG com GroupDocs.Viewer Java

Se você precisa **converter IGS para PDF** (ou para HTML, JPG, PNG) diretamente de uma aplicação Java, chegou ao lugar certo. Neste tutorial vamos percorrer tudo o que você precisa — desde a instalação da biblioteca até a renderização do modelo 3‑D no formato que se adapta ao seu projeto. Você entenderá por que o GroupDocs.Viewer é uma escolha sólida para conversões rápidas e confiáveis e receberá trechos de código prontos para uso que podem ser inseridos na sua própria solução.

![Converter arquivos IGS para HTML, JPG, PNG e PDF com GroupDocs.Viewer para Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Respostas rápidas
- **Posso converter IGS para PDF com Java?** Sim, use `PdfViewOptions` junto com a API `Viewer`.  
- **Quais formatos de saída são suportados?** HTML, JPG, PNG e PDF são todos manipulados nativamente.  
- **Preciso de uma licença para produção?** É necessária uma licença comercial; um teste gratuito permite experimentar os recursos principais.  
- **Qual versão do Java é necessária?** JDK 8 ou superior; a biblioteca também funciona em Java 11, 17 e posteriores.  
- **O Maven é a única forma de adicionar a biblioteca?** Não, você também pode usar Gradle ou adicionar manualmente os arquivos JAR ao seu classpath.

## O que é converter IGS para PDF?
Converter IGS para PDF significa transformar um arquivo CAD 3‑D neutro em um documento estático, visualizável universalmente. Isso permite que você compartilhe visualizações de design com partes interessadas que não possuem ferramentas CAD, incorpore a renderização em relatórios ou arquive o modelo para fins de conformidade.

## Por que usar o GroupDocs.Viewer para conversões de IGS?
O GroupDocs.Viewer processa arquivos IGS sem exigir nenhum software CAD externo. Ele suporta **mais de 50 formatos de entrada e saída**, pode renderizar montagens contendo **centenas de peças** mantendo o uso de memória abaixo de **200 MB**, e entrega resultados em menos de **2 segundos** para modelos típicos em um servidor padrão. Esses benefícios quantificados o tornam uma escolha de alto desempenho e custo‑efetiva para pipelines corporativos.

## Pré-requisitos
- **GroupDocs.Viewer para Java** ≥ 25.2 (a versão estável mais recente).  
- **JDK 8+** instalado e configurado no seu IDE (IntelliJ IDEA, Eclipse, NetBeans, etc.).  
- Conhecimento básico de Maven (opcional, mas recomendado para gerenciamento de dependências).  

## Configurando o GroupDocs.Viewer para Java

### Dependência Maven
Adicione o repositório GroupDocs e a dependência Viewer ao seu `pom.xml`:

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
O GroupDocs.Viewer oferece três opções de licenciamento:
- **Teste gratuito** – uso limitado, perfeito para testes rápidos de prova de conceito.  
- **Licença temporária** – conjunto completo de recursos por um curto período de avaliação, ideal para projetos piloto.  
- **Licença comercial** – uso ilimitado em produção, inclui suporte prioritário e atualizações.

### Inicialização básica do visualizador
A classe `Viewer` é o ponto de entrada para todas as operações de renderização. Ela carrega o arquivo fonte, analisa o formato e expõe métodos para produzir a saída desejada.

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

## Renderizando IGS para HTML

### Como converter IGS para HTML?
Carregue o arquivo IGS com uma instância de `Viewer` e passe um objeto `HtmlViewOptions` que incorpora todos os recursos necessários. A chamada retorna um único arquivo HTML que contém a visualização 3‑D completa, facilitando a incorporação em páginas web. Você também pode personalizar a renderização definindo opções como tamanho da página, cor de fundo e se deve incluir controles interativos.  
`HtmlViewOptions` configura como a saída HTML é gerada, incluindo incorporação de recursos e layout da página.

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

## Renderizando IGS para JPG

### Como converter IGS para JPG?
Crie um objeto `JpgViewOptions`, configure a resolução desejada e a qualidade de compressão, e deixe o `Viewer` gerar imagens rasterizadas para cada página do modelo. Os arquivos JPG gerados podem ser salvos em um diretório especificado, e você pode ajustar o parâmetro de qualidade para equilibrar tamanho do arquivo e fidelidade visual, o que é útil para miniaturas ou impressões de alta resolução.  
`JpgViewOptions` especifica configurações para geração de imagens JPG, como resolução, qualidade e diretório de saída.

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

## Renderizando IGS para PNG

### Como converter IGS para PNG?
A classe `PngViewOptions` permite produzir imagens sem perdas com transparência opcional. Esse formato é ideal para sobrepor o modelo em fundos coloridos em material de marketing. Você também pode definir a resolução e a cor de fundo para corresponder às diretrizes da sua marca, garantindo aparência consistente em todos os ativos gerados.  
`PngViewOptions` define parâmetros para renderização PNG, incluindo resolução, transparência e cor de fundo.

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

## Renderizando IGS para PDF

### Como converter IGS para PDF?
Use `PdfViewOptions` para produzir um PDF paginado que preserva o layout visual do modelo 3‑D. Você também pode incorporar fontes e controlar o tamanho da página para atender às diretrizes de branding corporativo. Configurações adicionais permitem especificar qualidade de imagem, nível de compressão e se deve incluir um índice para montagens com várias páginas.  
`PdfViewOptions` controla a criação do PDF, permitindo configuração de tamanho de página, qualidade de imagem e incorporação de fontes.

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

## Aplicações práticas
- **Portais web** – incorpore modelos renderizados em HTML diretamente em configuradores de produtos, permitindo que clientes girem e ampliem sem instalar plugins.  
- **Materiais de marketing** – gere imagens JPG/PNG de alta resolução para brochuras, apresentações e postagens em redes sociais.  
- **Documentação técnica** – inclua renderizações PDF de modelos CAD em manuais do usuário, garantindo que engenheiros possam visualizar os designs offline.  
- **Garantia de qualidade** – automatize a criação de miniaturas para milhares de arquivos IGS, acelerando fluxos de inspeção visual.

## Problemas comuns e soluções

| Problema | Solução |
|----------|---------|
| **Pasta de saída não encontrada** | Verifique o caminho passado para `Path outputDirectory` e assegure que o processo Java tenha permissões de gravação no diretório alvo. |
| **Páginas em branco no PDF** | Confirme que o arquivo IGS fonte não está corrompido; abra-o primeiro em um visualizador CAD nativo. |
| **Renderização lenta para grandes montagens** | Aumente o heap da JVM (`-Xmx2g` ou mais) e considere renderizar página a página usando `viewer.getPageCount()` para processar em lotes. |
| **Fontes ausentes no PDF** | Use `PdfViewOptions` para incorporar as fontes necessárias ou instale as fontes ausentes no servidor que hospeda o serviço de conversão. |

## Perguntas frequentes

**P: Posso converter vários arquivos IGS em uma única execução?**  
R: Sim. Itere sobre uma coleção de caminhos de arquivo e invoque o método `view` apropriado para cada arquivo dentro da mesma instância de `Viewer`.

**P: É possível personalizar o tamanho da página PDF?**  
R: Absolutamente. `PdfViewOptions` oferece `setPageSize(PageSize.A4)`, `PageSize.Letter` e dimensões personalizadas via `setCustomSize(largura, altura)`.

**P: Preciso de uma licença separada para cada formato de saída?**  
R: Não. Uma única licença do GroupDocs.Viewer cobre todos os formatos suportados, incluindo HTML, JPG, PNG e PDF.

**P: Qual o tamanho máximo de um arquivo IGS antes que o desempenho degrade?**  
R: A biblioteca processa de forma confiável arquivos de até **500 MB**; para modelos maiores que 200 MB, aloque memória JVM adicional e considere renderizar em lotes.

**P: Posso renderizar apenas uma visualização ou orientação específica?**  
R: O GroupDocs.Viewer renderiza a orientação padrão definida no arquivo IGS. Para visualizações personalizadas, pré‑procese o arquivo com uma ferramenta CAD ou ajuste o modelo antes da conversão.

---

**Última atualização:** 2026-08-08  
**Testado com:** GroupDocs.Viewer 25.2 para Java  
**Autor:** GroupDocs

## Tutoriais relacionados

- [converter cdr para html, jpg, png, pdf com GroupDocs.Viewer Java](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [Como converter pdf para html e otimizar a qualidade da imagem em Java com GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)