---
date: '2026-08-03'
description: Aprenda como converter zip para html usando GroupDocs.Viewer Java, definir
  itens por página, incorporar recursos html e converter lotes de arquivos compactados
  de forma eficiente.
keywords:
- convert zip to html
- how to batch convert
- embed resources html
- batch convert archives
- how to convert archives
lastmod: '2026-08-03'
og_description: Aprenda como converter zip para html usando GroupDocs.Viewer Java,
  definir itens por página, incorporar recursos html e converter lotes de arquivos
  compactados de forma eficiente. Siga o código passo a passo e dicas de desempenho.
og_image_alt: 'Guide: convert zip to html with GroupDocs.Viewer Java, showing pagination
  and embedded resources'
og_title: Converter zip para html e definir itens por página com GroupDocs.Viewer
  Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-03'
  description: Learn how to convert zip to html using GroupDocs.Viewer Java, set items
    per page, embed resources html, and batch convert archives efficiently.
  headline: Convert zip to html and set items per page with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: GroupDocs.Viewer Java is a server‑side library that renders over 50 document
      and archive formats—including ZIP and RAR—into HTML, PDF, or image files without
      requiring external applications.
    question: What is GroupDocs.Viewer Java?
  - answer: Visit the [free trial link](https://releases.groupdocs.com/viewer/java/)
      to download and test.
    question: How can I obtain a free trial of GroupDocs.Viewer?
  - answer: Yes, the viewer supports PDFs, Word, Excel, PowerPoint, and 35+ additional
      formats.
    question: Can I convert other document types besides archives?
  - answer: Reduce the number of items per page, enable streaming, or process archives
      in smaller batches to improve speed.
    question: What should I do if rendering is slow?
  - answer: Reach out via the [support forum](https://forum.groupdocs.com/c/viewer/9).
    question: Where can I get help or support?
  type: FAQPage
tags:
- convert zip
- GroupDocs.Viewer
- Java archive conversion
- html rendering
- batch conversion
title: Converter zip para html e definir itens por página com GroupDocs.Viewer Java
type: docs
url: /pt/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Converter zip para html e definir itens por página com GroupDocs.Viewer Java

Em muitas aplicações web, você precisa exibir o conteúdo de um arquivo ZIP ou RAR diretamente no navegador. Com o GroupDocs.Viewer para Java, você pode **converter zip para html** em uma única etapa, controlar quantas entradas do arquivo aparecem em cada página, incorporar todas as imagens e CSS de suporte e até processar em lote dezenas de arquivos. Este tutorial orienta você por todo o fluxo de trabalho, desde a configuração do Maven até a renderização de múltiplas páginas, e explica por que cada configuração é importante para desempenho e usabilidade.

![Convert Archives to HTML with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Respostas rápidas
- **O que controla “set items per page”?** Determina quantos arquivos ou pastas de um arquivo aparecem em cada página HTML gerada.  
- **Posso incorporar imagens e CSS diretamente no HTML?** Sim – use a opção `forEmbeddedResources` para incorporar recursos HTML.  
- **A conversão em lote é possível?** Absolutamente; você pode percorrer uma coleção de arquivos e renderizar cada um com as mesmas configurações.  
- **Preciso do Maven para usar o GroupDocs.Viewer?** Sim, adicione a dependência Maven `groupdocs-viewer` conforme mostrado abaixo.  
- **Quais formatos de saída são suportados?** HTML de página única e HTML de múltiplas páginas estão disponíveis, e a biblioteca suporta mais de 50 tipos de arquivos de entrada.

## O que é “set items per page” no GroupDocs.Viewer?
A configuração **set items per page** pertence às opções de renderização de arquivos. Ela informa ao visualizador quantas entradas do arquivo (arquivos ou pastas) devem ser exibidas em cada página HTML ao gerar um documento HTML de múltiplas páginas. Ajustar esse valor ajuda a equilibrar o tamanho da página e a velocidade de navegação, especialmente para arquivos grandes.

## Por que incorporar recursos html?
Incorporar recursos (imagens, CSS, fontes) diretamente dentro do arquivo HTML cria um documento único e portátil que pode ser aberto sem arquivos externos. Isso é ideal para anexos de e‑mail, visualização offline ou incorporação da saída em outras páginas da web. Essa abordagem também simplifica a implantação, pois não há necessidade de gerenciar caminhos de ativos externos.

## Pré-requisitos
- **Bibliotecas necessárias:** Inclua o GroupDocs.Viewer versão 25.2 ou posterior.  
- **Ambiente:** Java Development Kit (JDK) instalado e configurado.  
- **Conhecimento:** Java básico e gerenciamento de dependências Maven.  

## Configuração do Maven GroupDocs Viewer
Adicione o repositório GroupDocs e a dependência do visualizador ao seu `pom.xml`:

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
O GroupDocs.Viewer oferece um **link de teste gratuito**, uma licença temporária ou uma opção de compra completa. Escolha a que melhor se adequa ao cronograma do seu projeto.

### Inicialização básica
Após a configuração do Maven, traga o visualizador para o seu código:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Como renderizar arquivos para single‑page html
Viewer é a classe principal que carrega um documento ou arquivo para renderização.

Para gerar um único arquivo HTML que contenha todo o arquivo, crie uma instância `Viewer` para o arquivo ZIP e use `HtmlViewOptions.forEmbeddedResources()` para incorporar todas as imagens, CSS e fontes. Renderizar o arquivo com essas opções produz uma página autônoma adequada para e‑mail ou uso offline.

### Etapa 1: Definir diretório de saída
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Etapa 2: Definir nome de arquivo para saída de página única
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Etapa 3: Inicializar o visualizador
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Etapa 4: Configurar opções de renderização (incorporar recursos html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Etapa 5: Renderizar como página única
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Como renderizar arquivos para multi‑page html e definir itens por página
`HtmlViewOptions` configura como o visualizador renderiza a saída HTML, incluindo paginação e incorporação de recursos.

Para dividir um arquivo em várias páginas, crie `HtmlViewOptions.forEmbeddedResources()` e defina o tamanho de página desejado com `options.setItemsPerPage(20)`. O visualizador gerará arquivos HTML separados, cada um exibindo até o número especificado de entradas, o que melhora a navegação em arquivos grandes e garante carregamento mais rápido.

### Etapa 1: Reutilizar o diretório de saída
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Etapa 2: Definir formato de nome de arquivo para múltiplas páginas
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Etapa 3: Inicializar o visualizador novamente
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Etapa 4: Configurar opções de múltiplas páginas (incorporar recursos html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Etapa 5: Definir itens por página (palavra‑chave principal em ação)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Aplicações práticas
- **Sistemas de gerenciamento de documentos:** Adicione funcionalidade de visualização de arquivos sem instalar visualizadores adicionais.  
- **Portais web:** Ofereça aos usuários uma maneira rápida e sem download para explorar documentos agrupados.  
- **Ferramentas de colaboração:** Permita que equipes inspecionem arquivos compartilhados diretamente no navegador.

## Considerações de desempenho
- **Gerenciamento de recursos:** Mantenha o uso de memória baixo processando arquivos em streams; o visualizador pode lidar com arquivos de até 500 MB sem carregar todo o arquivo na memória.  
- **Conversão em lote de arquivos:** Percorra uma lista de arquivos de arquivo e chame a mesma lógica de renderização para maximizar o throughput.  
- **Estratégia de cache:** Armazene o HTML renderizado em cache se o mesmo arquivo for acessado com frequência, reduzindo o tempo de processamento repetido em até 70 %.

## Perguntas frequentes
**Q: O que é o GroupDocs.Viewer Java?**  
A: O GroupDocs.Viewer Java é uma biblioteca server‑side que renderiza mais de 50 formatos de documentos e arquivos — incluindo ZIP e RAR — em HTML, PDF ou arquivos de imagem sem exigir aplicativos externos.

**Q: Como posso obter um teste gratuito do GroupDocs.Viewer?**  
A: Visite o [link de teste gratuito](https://releases.groupdocs.com/viewer/java/) para baixar e testar.

**Q: Posso converter outros tipos de documentos além de arquivos?**  
A: Sim, o visualizador suporta PDFs, Word, Excel, PowerPoint e mais de 35 formatos adicionais.

**Q: O que devo fazer se a renderização estiver lenta?**  
A: Reduza o número de itens por página, habilite streaming ou processe arquivos em lotes menores para melhorar a velocidade.

**Q: Onde posso obter ajuda ou suporte?**  
A: Entre em contato através do [forum de suporte](https://forum.groupdocs.com/c/viewer/9).

**Q: É possível incorporar CSS e imagens diretamente no HTML?**  
A: Absolutamente — use `HtmlViewOptions.forEmbeddedResources` como mostrado nos exemplos.

**Q: Como faço para converter em lote uma pasta de arquivos?**  
A: Itere sobre cada arquivo com um loop `for`, aplicando a mesma configuração `Viewer` e `HtmlViewOptions` em cada iteração.

## Recursos
- **Documentação:** Aprofunde-se na funcionalidade com a [documentação do GroupDocs](https://docs.groupdocs.com/viewer/java/).  
- **Referência da API:** Explore a API completa na [API do GroupDocs](https://reference.groupdocs.com/viewer/java/).  
- **Download:** Obtenha os binários mais recentes na [página de download](https://releases.groupdocs.com/viewer/java/).  
- **Compra e licenciamento:** Revise as opções na [página de compra](https://purchase.groupdocs.com/buy).  
- **Suporte e comunidade:** Participe das discussões no [forum do GroupDocs](https://forum.groupdocs.com/c/viewer/9).

---

**Última atualização:** 2026-08-03  
**Testado com:** GroupDocs.Viewer 25.2  
**Autor:** GroupDocs

## Tutoriais Relacionados
- [Como converter zip para HTML e renderizar pastas zip em Java com GroupDocs.Viewer](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [converter zip para pdf com GroupDocs.Viewer Java - Nomes de Arquivo Personalizados](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [Como Converter DOCX para HTML Usando GroupDocs.Viewer para Java: Um Guia Passo a Passo](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)