---
date: '2026-08-19'
description: Aprenda como converter cdr para html, bem como jpg, png e pdf, usando
  o GroupDocs.Viewer para Java. Inclui configuração, exemplos de código e dicas de
  desempenho.
keywords:
- convert cdr to html
- convert cdr to pdf
- convert cdr to jpg
- convert cdr to png
- java convert coreldraw
lastmod: '2026-08-19'
og_description: Aprenda como converter cdr para html, jpg, png e pdf usando o GroupDocs.Viewer
  para Java. Guia passo a passo com configuração, trechos de código e melhores práticas
  de desempenho.
og_image_alt: Guide showing conversion of CorelDRAW CDR files to HTML, JPG, PNG, and
  PDF using GroupDocs.Viewer for Java
og_title: Converter cdr para html, jpg, png, pdf com GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-19'
  description: Learn how to convert cdr to html, as well as jpg, png, and pdf, using
    GroupDocs.Viewer for Java. Includes setup, code examples, and performance tips.
  headline: Convert cdr to html, jpg, png, pdf with GroupDocs.Viewer Java
  type: TechArticle
- description: Learn how to convert cdr to html, as well as jpg, png, and pdf, using
    GroupDocs.Viewer for Java. Includes setup, code examples, and performance tips.
  name: Convert cdr to html, jpg, png, pdf with GroupDocs.Viewer Java
  steps:
  - name: '**Libraries and dependencies** – GroupDocs.Viewer added to your Maven project.'
    text: '**Libraries and dependencies** – GroupDocs.Viewer added to your Maven project.'
  - name: '**Java Development Kit (JDK)** – version 8 or newer installed.'
    text: '**Java Development Kit (JDK)** – version 8 or newer installed.'
  - name: '**Basic Java knowledge** – to understand the code snippets.'
    text: '**Basic Java knowledge** – to understand the code snippets.'
  type: HowTo
- questions:
  - answer: Yes. Load the file with a `Viewer` instance that accepts a password parameter
      (see the API docs).
    question: Can I convert password‑protected CDR files?
  - answer: No hard limit, but very large files may require more memory; consider
      processing page‑by‑page.
    question: Is there a limit on the number of pages that can be converted at once?
  - answer: When using `HtmlViewOptions.forEmbeddedResources`, fonts are embedded
      as Base64, ensuring consistent rendering across browsers.
    question: Does the HTML output include embedded fonts?
  - answer: '`JpgViewOptions` provides a `setQuality(int)` method where you can specify
      a value from 1‑100.'
    question: How do I control JPEG quality?
  - answer: Absolutely—GroupDocs.Viewer is platform‑agnostic as long as the JDK is
      installed.
    question: Can I convert CDR files on a Linux server?
  type: FAQPage
tags:
- convert cdr
- groupdocs.viewer
- java file conversion
- coreldraw cdr
- document rendering
title: Converter cdr para html, jpg, png, pdf com GroupDocs.Viewer Java
type: docs
url: /pt/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/
weight: 1
---

# Converter cdr para html, jpg, png, pdf com GroupDocs.Viewer Java

Se você precisa **converter cdr para html** (ou para JPG, PNG e PDF) de forma rápida e confiável, chegou ao tutorial certo. Neste guia, percorreremos tudo o que você precisa — desde a instalação do GroupDocs.Viewer para Java até a renderização de arquivos CorelDRAW (CDR) em páginas HTML amigáveis para a web, imagens de alta qualidade e PDFs universalmente legíveis. Ao final, você poderá integrar essas conversões em qualquer aplicação Java com apenas algumas linhas de código.

![Renderizar arquivos CDR com GroupDocs.Viewer para Java](/viewer/file-formats-support/render-cdr-files.png)

[Renderizar arquivos CDR com GroupDocs.Viewer para Java](/viewer/file-formats-support/render-cdr-files.png)

## Respostas rápidas
- **Qual biblioteca converte CDR para HTML?** GroupDocs.Viewer for Java.  
- **Posso também converter CDR para JPG, PNG e PDF?** Sim — use a mesma Viewer API com diferentes opções de visualização.  
- **Preciso de uma licença?** Uma licença de teste ou temporária funciona para testes; uma licença completa é necessária para produção.  
- **Qual versão do Java é necessária?** JDK 8 ou superior.  
- **A conversão em lote é suportada?** Absolutamente — basta percorrer os arquivos com a mesma instância do Viewer.

## O que é “converter cdr para html”?
Converter cdr para html significa transformar um arquivo vetorial CorelDRAW em marcação HTML padrão, opcionalmente incorporando imagens e estilos para que o design possa ser visualizado diretamente em um navegador web sem a necessidade do software de design original. O processo preserva o layout original, cores e formas vetoriais ao convertê‑las em elementos SVG escaláveis ou imagens raster incorporadas ao HTML, permitindo uma representação visual precisa em diferentes navegadores enquanto mantém o tamanho do arquivo baixo.

## Por que converter cdr para html, jpg, png ou pdf?
Você pode renderizar uma única fonte CDR em quatro formatos amplamente suportados, cada um atendendo a um propósito distinto: HTML para visualização instantânea na web, JPG/PNG para imagens raster e PDF para documentos imprimíveis e arquiváveis. Essa flexibilidade permite oferecer o tipo de arquivo ideal a qualquer cliente, reduzir a duplicação de armazenamento e garantir a longevidade dos seus ativos.

## Pré‑requisitos

Antes de começarmos, certifique‑se de que você tem:

1. **Bibliotecas e dependências** – GroupDocs.Viewer adicionada ao seu projeto Maven.  
2. **Java Development Kit (JDK)** – versão 8 ou superior instalada.  
3. **Conhecimento básico de Java** – para entender os trechos de código.

### Bibliotecas necessárias, versões e dependências

Adicione a seguinte configuração Maven ao seu `pom.xml` (sem alterações em relação ao tutorial original):

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

### Etapas para aquisição de licença

GroupDocs.Viewer oferece um teste gratuito, licenças temporárias para testes ou opções de compra completa:

- **Teste gratuito** – Baixe na [GroupDocs Release Page](https://releases.groupdocs.com/viewer/java/).  
- **Licença temporária** – Solicite uma na [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Compra** – Obtenha uma licença permanente através da [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

## Configurando GroupDocs.Viewer para Java

Viewer é a classe principal que carrega um documento e fornece métodos de renderização para todos os formatos de saída suportados.

### Instalação com Maven
O snippet Maven acima buscará todos os JARs necessários automaticamente. Basta executar `mvn clean install` após salvar o arquivo.

### Inicialização da licença
`Viewer` é a classe principal que carrega um documento e fornece métodos de renderização para todos os formatos de saída suportados. Inicialize sua licença antes de renderizar quaisquer documentos:

```java
import com.groupdocs.viewer.License;

License lic = new License();
lic.setLicense("path/to/your/license/file.lic");
```

## Guia de implementação

A seguir, você encontrará exemplos passo a passo para cada formato de saída. Os blocos de código são idênticos ao tutorial original; adicionamos apenas texto explicativo ao redor deles.

### Como converter cdr para html com GroupDocs.Viewer

Carregue um arquivo CDR e chame a API de renderização HTML – isso é tudo que você precisa para gerar marcação pronta para a web. O processo requer a configuração dos caminhos de arquivos, a criação de uma instância `HtmlViewOptions` e a invocação de `viewer.view()`. Esse padrão de duas etapas funciona para qualquer tamanho de documento e preserva a fidelidade vetorial.

#### Renderizando documento cdr para HTML
**Visão geral:** Converta seus arquivos CDR em HTML amigável para a web para fácil compartilhamento.

**Etapa 1 – configure os caminhos dos arquivos**

```java
import java.nio.file.Path;

Path outputDirectory = TestFiles.getOutputDirectoryPath("RenderingCdr");
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.html");
```

**Etapa 2 – inicialize o viewer e renderize**

HtmlViewOptions configura a renderização HTML, permitindo incorporar recursos ou salvá‑los separadamente. O código a seguir renderiza cada página em um arquivo HTML separado, incorporando imagens como strings Base64.

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options); // Render the document into HTML format
}
```

### Como converter cdr para jpg com GroupDocs.Viewer

Você pode produzir imagens JPEG de alta qualidade a partir de uma fonte CDR em apenas duas linhas de código. Primeiro, configure `JpgViewOptions` com a qualidade desejada, depois chame `viewer.view()`. Essa abordagem é ideal para miniaturas, anexos de e‑mail ou qualquer cenário que necessite de uma imagem raster compacta.

#### Renderizando documento cdr para JPG
**Visão geral:** Produza imagens JPEG de alta qualidade a partir da sua fonte CDR.

**Etapa 1 – configure os caminhos dos arquivos**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.jpg");
```

**Etapa 2 – inicialize o viewer e renderize**

JpgViewOptions define as configurações de renderização JPEG, como qualidade de compressão e nomeação da saída. O exemplo abaixo salva cada página como um arquivo JPEG separado.

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into JPG format
}
```

### Como converter cdr para png com GroupDocs.Viewer

A saída PNG fornece imagens raster sem perdas, perfeitas para arquivamento ou processamento gráfico adicional. Use `PngViewOptions` para manter cada pixel intacto, então renderize o documento página por página.

#### Renderizando documento cdr para PNG
**Visão geral:** Gere imagens PNG sem perdas para fins de arquivamento ou design.

**Etapa 1 – configure os caminhos dos arquivos**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.png");
```

**Etapa 2 – inicialize o viewer e renderize**

PngViewOptions especifica os parâmetros de renderização PNG, incluindo suporte a fundos transparentes. O código cria um PNG por página automaticamente.

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PNG format
}
```

### Como converter cdr para pdf com GroupDocs.Viewer

Converter um arquivo CDR em PDF fornece um documento universalmente legível e pronto para impressão. `PdfViewOptions` lida com a conversão de vetor para raster internamente, preservando o layout e as fontes sem a necessidade do Adobe Illustrator.

#### Renderizando documento cdr para PDF
**Visão geral:** Converta seus arquivos CDR em PDFs universalmente legíveis.

**Etapa 1 – configure os caminhos dos arquivos**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result.pdf");
```

**Etapa 2 – inicialize o viewer e renderize**

PdfViewOptions controla a geração de PDF, permitindo a incorporação de fontes e a personalização do layout das páginas. O trecho cria um único PDF contendo todas as páginas.

```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PDF format
}
```

## Aplicações práticas

- **Portais web:** Use a conversão para HTML para incorporar designs CDR diretamente em seu site.  
- **Galerias de imagens:** Utilize as saídas JPG/PNG para galerias de carregamento rápido ou catálogos de produtos.  
- **Compartilhamento de documentos:** Forneça PDFs para clientes que precisam de uma versão imprimível e somente leitura.  
- **Arquivamento:** Armazene múltiplos formatos para garantir acessibilidade futura independentemente de mudanças de software.  
- **Integração multiplataforma:** Alimente os arquivos gerados em serviços subsequentes como OCR, analytics ou sistemas de gerenciamento de ativos digitais.

## Considerações de desempenho

- **Descarte as instâncias do Viewer** prontamente (como mostrado com try‑with‑resources) para liberar memória.  
- **Processamento em lote:** Percorra uma coleção de arquivos CDR usando a mesma configuração do Viewer para reduzir a sobrecarga.  
- **Alocação de recursos:** GroupDocs.Viewer pode renderizar documentos de até 500 páginas sem carregar o arquivo inteiro na memória, mas desenhos muito complexos podem se beneficiar de um aumento no tamanho do heap. Monitore o uso de CPU e RAM durante conversões em grande escala.

## Armadilhas comuns e dicas de solução de problemas

- **Fontes ausentes:** Se a saída parecer diferente, certifique‑se de que as fontes necessárias estejam disponíveis no servidor ou incorpore‑as via `PdfViewOptions`.  
- **Arquivos grandes:** Para arquivos CDR superiores a 200 MB, considere processar página por página para evitar `OutOfMemoryError`.  
- **Qualidade de imagem incorreta:** Ajuste o valor `setQuality` em `JpgViewOptions` se os JPEGs parecerem muito comprimidos.  
- **Erros de licença:** Verifique se o caminho do arquivo de licença está correto e se a versão da licença corresponde à versão da sua biblioteca Viewer.

## Conclusão

Mostramos como **converter cdr para html**, bem como para JPG, PNG e PDF, usando o GroupDocs.Viewer para Java. Seguindo os trechos de código concisos e as dicas de boas práticas, você pode incorporar essas conversões em qualquer fluxo de trabalho baseado em Java, entregando saídas flexíveis e de alta qualidade aos seus usuários.

### Próximos passos
- Experimente opções avançadas de renderização, como tamanhos de página personalizados ou marcas d'água.  
- Combine o pipeline de conversão com uma API REST para oferecer transformação de arquivos sob demanda.  
- Participe da comunidade e faça perguntas no [GroupDocs Forum](https://forum.groupdocs.com/c/viewer).

## Perguntas frequentes

**P: Posso converter arquivos CDR protegidos por senha?**  
A: Sim. Carregue o arquivo com uma instância `Viewer` que aceita um parâmetro de senha (consulte a documentação da API).

**P: Existe um limite para o número de páginas que podem ser convertidas de uma vez?**  
A: Não há limite rígido, mas arquivos muito grandes podem exigir mais memória; considere processar página por página.

**P: A saída HTML inclui fontes incorporadas?**  
A: Ao usar `HtmlViewOptions.forEmbeddedResources`, as fontes são incorporadas como Base64, garantindo renderização consistente em diferentes navegadores.

**P: Como controlo a qualidade do JPEG?**  
A: `JpgViewOptions` fornece um método `setQuality(int)` onde você pode especificar um valor de 1‑100.

**P: Posso converter arquivos CDR em um servidor Linux?**  
A: Absolutamente — o GroupDocs.Viewer é independente de plataforma, desde que o JDK esteja instalado.

---

**Última atualização:** 2026-08-19  
**Testado com:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs

## Tutoriais relacionados

- [Como converter Excel para HTML, JPG, PNG e PDF usando GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)  
- [Como converter CF2 para PDF, HTML, JPG, PNG com GroupDocs.Viewer para Java](/viewer/java/rendering-basics/render-cf2-files-groupdocs-java/)  
- [Como converter pdf para html e otimizar a qualidade da imagem em Java com GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)