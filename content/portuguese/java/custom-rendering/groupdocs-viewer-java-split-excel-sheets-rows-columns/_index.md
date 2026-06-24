---
date: '2026-06-15'
description: Aprenda como converter Excel para PDF Java e dividir planilhas Excel
  por linhas e colunas usando o GroupDocs Viewer. Inclui configuração, código e boas
  práticas.
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
schemas:
- author: GroupDocs
  dateModified: '2026-06-15'
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  type: TechArticle
- description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  steps:
  - name: Set Up Paths and Initialize the Viewer
    text: First, define where the split pages will be saved and create a `Viewer`
      instance for the source workbook.
  - name: Configure Rows Per Page
    text: Tell the viewer how many rows each page should contain.
  - name: Render the Document
    text: Finally, render the workbook using the options you defined.
  - name: Set Up Paths and Initialize the Viewer
    text: The setup mirrors the row‑only example, only the file name changes.
  - name: Configure Rows and Columns Per Page
    text: Specify both dimensions to create a grid‑style split.
  - name: Render the Document
    text: Render using the same `view` call.
  type: HowTo
- questions:
  - answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
    question: Can I generate a PDF instead of HTML?
  - answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
    question: Is it possible to split based on cell content rather than fixed rows/columns?
  - answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
    question: Does GroupDocs Viewer support older Excel formats (XLS)?
  - answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
    question: How do I embed the generated HTML into a Spring MVC view?
  - answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
    question: What license do I need for commercial deployment?
  type: FAQPage
title: Converter Excel para PDF Java e dividir planilhas por linhas e colunas
type: docs
url: /pt/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# Converter Excel para PDF Java e Dividir Planilhas por Linhas e Colunas (Java)

Grandes pastas de Excel frequentemente contêm mais dados do que podem ser exibidos confortavelmente em uma única tela ou página impressa. **convert excel to pdf java** é um requisito comum quando você precisa de um formato estático e compartilhável, enquanto **splitting Excel sheets by rows and columns** facilita o consumo dos dados em layouts web ou de impressão. Neste guia, percorreremos ambas as tarefas usando **GroupDocs Viewer for Java**, mostraremos como configurar a paginação e explicaremos dicas de boas práticas para desempenho e solução de problemas.

![Dividir Planilhas Excel por Linhas e Colunas com GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[Dividir Planilhas Excel por Linhas e Colunas com GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## Respostas Rápidas
- **Qual biblioteca é usada?** GroupDocs Viewer for Java.  
- **Posso dividir por linhas e colunas?** Sim – você pode definir rows‑per‑page e columns‑per‑page juntos.  
- **Preciso de licença?** Uma licença de avaliação ou temporária funciona para desenvolvimento; uma licença completa é necessária para produção.  
- **Quais formatos de saída são suportados?** HTML (recursos incorporados) é mostrado; PDF pode ser gerado com as mesmas opções.  
- **Maven é obrigatório?** Maven é a forma recomendada de gerenciar dependências.  
- **Posso também converter Excel para PDF?** Absolutamente – basta trocar `HtmlViewOptions` por `PdfViewOptions` e reutilizar as mesmas configurações de paginação.

## O que é “How to Split Excel”?
Dividir uma planilha Excel significa separar uma única planilha em várias páginas ou arquivos com base em um número fixo de linhas, colunas ou ambos. Essa técnica é útil quando você precisa criar relatórios paginados, incorporar dados em páginas web ou gerar seções imprimíveis sem carregar toda a pasta de trabalho de uma vez.

## Por que usar GroupDocs Viewer for Java?
GroupDocs Viewer processa planilhas em uma única passagem e paginá‑las automaticamente, eliminando cálculos manuais. **Processamento rápido renderiza uma pasta de trabalho XLSX de 250 páginas em menos de 2 segundos em um servidor típico de 2 núcleos**, e **a biblioteca suporta mais de 50 formatos de entrada e saída**, incluindo XLS, XLSX, CSV, PDF e HTML. Funciona em qualquer plataforma compatível com JVM — Windows, Linux, macOS, contêineres Docker ou runtimes serverless baseados em nuvem — para que você possa integrá‑la onde sua aplicação Java estiver.

## Pré-requisitos
- Java 17 ou posterior instalado.  
- Uma IDE como IntelliJ IDEA ou Eclipse.  
- Maven para gerenciamento de dependências.  
- Conhecimento básico de Java e familiaridade com manipulação de arquivos Excel.

### Bibliotecas Necessárias, Versões e Dependências
Adicione o repositório GroupDocs e a dependência do viewer ao seu `pom.xml`:

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

### Aquisição de Licença
Obtenha uma licença de avaliação, temporária ou compre uma licença completa em [GroupDocs](https://purchase.groupdocs.com/buy).

## Como Converter Excel para PDF Java?

A classe `Viewer` é o componente central do GroupDocs Viewer que carrega um documento e fornece métodos de renderização para vários formatos de saída. `SpreadsheetOptions` permite controlar configurações de paginação, como rows‑per‑page e columns‑per‑page para renderização de planilhas.

Carregue seu arquivo Excel com `new Viewer("source.xlsx")`, configure `SpreadsheetOptions` para paginação e chame `viewer.view(pdfOptions, stream)` – essa única chamada converte a pasta de trabalho em PDF respeitando os limites de linhas/colunas definidos. A conversão preserva fórmulas, imagens e estilos de célula, entregando uma réplica fiel em PDF pronta para distribuição.

## Como Dividir Planilhas Excel por Linhas

Dividir por linhas cria uma série de páginas HTML, cada uma contendo um número fixo de linhas (por exemplo, 15). Essa abordagem é ideal para dashboards que exibem um número limitado de registros por visualização. O viewer gerará arquivos HTML separados como `page_0.html`, `page_1.html`, etc., cada um contendo o número especificado de linhas. Isso simplifica o carregamento apenas da parte necessária em uma interface web, reduzindo largura de banda e tempo de renderização.

### Âncora de Definição
`Viewer` é a classe central do GroupDocs Viewer que carrega um documento e orquestra a renderização para o formato de saída escolhido.

### Implementação Passo a Passo

#### Etapa 1: Configurar Caminhos e Inicializar o Viewer
Primeiro, defina onde as páginas divididas serão salvas e crie uma instância `Viewer` para a pasta de trabalho de origem.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### Etapa 2: Configurar Linhas Por Página
Informe ao viewer quantas linhas cada página deve conter.

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### Etapa 3: Renderizar o Documento
Finalmente, renderize a pasta de trabalho usando as opções definidas.

```java
viewer.view(viewOptions);
```

## Como Dividir Planilhas Excel por Linhas e Colunas

Às vezes, uma única página precisa mostrar uma matriz de linhas **e** colunas (por exemplo, 15 linhas × 7 colunas). Isso oferece controle total sobre o layout de cada página HTML. As páginas resultantes exibem um bloco retangular de células, por exemplo linhas 1‑15 e colunas A‑G na primeira página, linhas 16‑30 e colunas H‑N na próxima. Essa paginação em estilo grade é útil para criar relatórios imprimíveis que se ajustam a tamanhos de papel padrão.

### Âncora de Definição
`SpreadsheetOptions` configura quantas linhas e colunas aparecem em cada página gerada.

### Implementação Passo a Passo

#### Etapa 1: Configurar Caminhos e Inicializar o Viewer
A configuração espelha o exemplo apenas‑linhas, apenas o nome do arquivo muda.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### Etapa 2: Configurar Linhas e Colunas Por Página
Especifique ambas as dimensões para criar uma divisão em estilo grade.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### Etapa 3: Renderizar o Documento
Renderize usando a mesma chamada `view`.

```java
viewer.view(options);
```

## Aplicações Práticas
- **Generate Excel report Java**: Transforme grandes modelos financeiros em uma série de relatórios HTML paginados.  
- **GroupDocs Viewer Excel**: Incorpore páginas divididas diretamente em um portal web para exploração interativa de dados.  
- **Render Excel HTML Java**: Sirva as páginas HTML geradas via um servlet ou controlador Spring para renderização rápida no cliente.  

## Considerações de Desempenho
- **Uso de memória** – Grandes pastas podem consumir heap significativo; considere aumentar a configuração JVM `-Xmx`.  
- **Tamanho do bloco** – Escolha contagens de linhas/colunas que equilibrem tamanho da página e velocidade de renderização.  
- **Atualizações de versão** – Mantenha o GroupDocs Viewer atualizado para aproveitar melhorias de desempenho; a versão mais recente 25.2 melhora a velocidade de renderização em até 30 % comparado com 24.x.

## Problemas Comuns & Solução de Problemas
| Sintoma | Causa Provável | Correção |
|---------|----------------|----------|
| `OutOfMemoryError` | Renderizando uma planilha muito grande com muitas linhas por página | Reduza `countRowsPerPage` ou aumente o heap da JVM |
| Arquivos de saída em branco | Caminho de arquivo incorreto ou permissões de gravação ausentes | Verifique se `outputDirectory` existe e tem permissão de escrita |
| Recursos HTML não carregando | Usando `forEmbeddedResources` mas servindo arquivos de uma URL base diferente | Sirva toda a pasta de saída ou troque para `forExternalResources` |

## Perguntas Frequentes

**P: Posso gerar um PDF em vez de HTML?**  
A: Sim. Substitua `HtmlViewOptions` por `PdfViewOptions` e mantenha a mesma configuração de `SpreadsheetOptions`.

**P: É possível dividir com base no conteúdo da célula em vez de linhas/colunas fixas?**  
A: Divisão direta baseada em conteúdo não está incorporada ao GroupDocs Viewer, mas você pode pré‑processar a pasta de trabalho com Apache POI para criar planilhas separadas antes da renderização.

**P: O GroupDocs Viewer suporta formatos antigos do Excel (XLS)?**  
A: Absolutamente. O visualizador lida com XLS, XLSX, CSV e outros formatos de planilha.

**P: Como incorporo o HTML gerado em uma visualização Spring MVC?**  
A: Sirva a pasta de saída como recurso estático e referencie os `page_0.html`, `page_1.html`, etc., gerados em seus templates Thymeleaf ou JSP.

**P: Qual licença preciso para implantação comercial?**  
A: É necessária uma licença completa de produção da GroupDocs; licenças de avaliação são apenas para avaliação.

## Recursos
- **Documentação**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Referência de API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Viewer Java Releases](https://releases.groupdocs.com/viewer/java/)
- **Compra**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Teste Gratuito**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Licença Temporária**: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Suporte**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-06-15  
**Tested With:** GroupDocs Viewer 25.2 for Java  
**Author:** GroupDocs  

---

## Tutoriais Relacionados

- [Renderizar Linhas e Colunas Ocultas em Planilhas Java Usando GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Pular Renderização de Linhas Vazias em Java Usando GroupDocs.Viewer: Guia de Desempenho](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [Guia Abrangente: Converter Excel 2003 XML para HTML/JPG/PNG/PDF com GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)