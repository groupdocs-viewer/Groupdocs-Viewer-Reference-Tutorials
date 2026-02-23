---
date: '2026-02-23'
description: Aprenda a definir itens por página, incorporar recursos HTML e converter
  em lote arquivos compactados para HTML de página única ou multipágina usando o GroupDocs.Viewer
  Java.
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 'Definir Itens Por Página: Converter Arquivos para HTML com GroupDocs.Viewer
  Java'
type: docs
url: /pt/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Definir itens por página: Converter arquivos compactados para HTML com GroupDocs.Viewer Java

Converter arquivos compactados como ZIP ou RAR em HTML compatível com a web é uma necessidade frequente quando você deseja compartilhar ou revisar documentos diretamente no navegador. Neste guia você aprenderá **como definir itens por página** ao renderizar arquivos compactados, como incorporar recursos HTML para uma saída autônoma e como converter arquivos compactados em lote de forma eficiente com GroupDocs.Viewer Java.

![Converter arquivos compactados para HTML com GroupDocs.Viewer para Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Respostas rápidas
- **O que controla “definir itens por página”?** Determina quantos arquivos ou pastas de um arquivo compactado aparecem em cada página HTML gerada.  
- **Posso incorporar imagens e CSS diretamente no HTML?** Sim – use a opção `forEmbeddedResources` para incorporar recursos HTML.  
- **A conversão em lote é possível?** Absolutamente; você pode percorrer uma coleção de arquivos compactados e renderizar cada um com as mesmas configurações.  
- **Preciso do Maven para usar o GroupDocs.Viewer?** Sim, adicione a dependência `maven groupdocs viewer` conforme mostrado abaixo.  
- **Quais formatos de saída são suportados?** HTML de página única Java e HTML de múltiplas páginas Java estão disponíveis.

## O que é “definir itens por página” no GroupDocs.Viewer?
A configuração **definir itens por página** pertence às opções de renderização de arquivos compactados. Ela informa ao visualizador quantas entradas do arquivo compactado (arquivos ou pastas) devem ser exibidas em cada página HTML ao gerar um documento HTML de múltiplas páginas. Ajustar esse valor ajuda a equilibrar o tamanho da página e a velocidade de navegação, especialmente para arquivos compactados grandes.

## Por que incorporar recursos HTML?
Incorporar recursos (imagens, CSS, fontes) diretamente dentro do arquivo HTML cria um documento único e portátil que pode ser aberto sem arquivos externos. Isso é ideal para anexos de e‑mail, visualização offline ou incorporação da saída em outras páginas da web.

## Pré‑requisitos

- **Bibliotecas necessárias:** Inclua GroupDocs.Viewer versão 25.2 ou posterior.  
- **Ambiente:** Java Development Kit (JDK) instalado e configurado.  
- **Conhecimento:** Noções básicas de Java e gerenciamento de dependências Maven.  

## Configuração do Maven para GroupDocs Viewer

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

### Aquisição de licença
O GroupDocs.Viewer oferece um **link de teste gratuito**, uma licença temporária ou uma opção de compra completa. Escolha a que melhor se adapta ao cronograma do seu projeto.

### Inicialização básica
Após a configuração do Maven, importe o viewer para o seu código:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Como renderizar arquivos compactados para HTML de página única

### Etapa 1: Definir diretório de saída
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Etapa 2: Definir nome de arquivo para saída de página única
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Etapa 3: Inicializar o Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Etapa 4: Configurar opções de renderização (incorporar recursos HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Etapa 5: Renderizar como uma única página
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Como renderizar arquivos compactados para HTML de múltiplas páginas e definir itens por página

### Etapa 1: Reutilizar o diretório de saída
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Etapa 2: Definir formato de nome de arquivo para várias páginas
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Etapa 3: Inicializar o Viewer novamente
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Etapa 4: Configurar opções de múltiplas páginas (incorporar recursos HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Etapa 5: Definir itens por página (palavra‑chave principal em ação)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Aplicações práticas

- **Sistemas de gerenciamento de documentos:** Adicione funcionalidade de pré‑visualização de arquivos compactados sem instalar visualizadores adicionais.  
- **Portais web:** Ofereça aos usuários uma forma rápida e sem download de explorar documentos agrupados.  
- **Ferramentas de colaboração:** Permita que equipes inspecionem arquivos compactados compartilhados diretamente no navegador.

## Considerações de desempenho

- **Gerenciamento de recursos:** Fique atento ao uso de memória; considere ajustar o coletor de lixo da JVM para lotes grandes.  
- **Conversão em lote de arquivos compactados:** Percorra uma lista de arquivos compactados e chame a mesma lógica de renderização para maximizar o throughput.  
- **Estratégia de cache:** Armazene o HTML renderizado em cache se o mesmo arquivo compactado for acessado com frequência.

## Perguntas frequentes

**P: O que é GroupDocs.Viewer Java?**  
R: Uma biblioteca versátil para renderizar documentos—including arquivos compactados—em formatos como HTML, PDF e imagens.

**P: Como posso obter um teste gratuito do GroupDocs.Viewer?**  
R: Visite o [link de teste gratuito](https://releases.groupdocs.com/viewer/java/) para baixar e testar.

**P: Posso converter outros tipos de documento além de arquivos compactados?**  
R: Sim, o viewer suporta PDFs, Word, Excel e muitos outros formatos.

**P: O que fazer se a renderização estiver lenta?**  
R: Reduza o número de itens por página, habilite streaming ou processe arquivos compactados em lotes menores.

**P: Onde posso obter ajuda ou suporte?**  
R: Entre em contato através do [fórum de suporte](https://forum.groupdocs.com/c/viewer/9).

**P: É possível incorporar CSS e imagens diretamente no HTML?**  
R: Absolutamente—use `HtmlViewOptions.forEmbeddedResources` como mostrado nos exemplos.

**P: Como faço a conversão em lote de uma pasta de arquivos compactados?**  
R: Itere sobre cada arquivo com um loop `for`, aplicando a mesma configuração de `Viewer` e `HtmlViewOptions` em cada iteração.

## Recursos

- **Documentação:** Aprofunde-se na funcionalidade com a [documentação do GroupDocs](https://docs.groupdocs.com/viewer/java/).  
- **Referência da API:** Explore a API completa em [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Download:** Obtenha os binários mais recentes na [página de download](https://releases.groupdocs.com/viewer/java/).  
- **Compra e licenciamento:** Revise as opções na [página de compra](https://purchase.groupdocs.com/buy).  
- **Suporte e comunidade:** Participe das discussões no [fórum GroupDocs](https://forum.groupdocs.com/c/viewer/9).

---

**Última atualização:** 2026-02-23  
**Testado com:** GroupDocs.Viewer 25.2  
**Autor:** GroupDocs