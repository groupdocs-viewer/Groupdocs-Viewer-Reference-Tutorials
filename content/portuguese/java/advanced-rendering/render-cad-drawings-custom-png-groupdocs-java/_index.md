---
date: '2026-08-30'
description: Aprenda como converter DWG para PNG, definir background color em Java
  e personalizar image size com GroupDocs.Viewer for Java.
keywords:
- convert dwg to png
- set background color java
- change cad background color
- java convert cad png
lastmod: '2026-08-30'
og_description: Converta DWG para PNG usando GroupDocs.Viewer for Java enquanto define
  um custom image width e background color. Este guia fornece step‑by‑step setup,
  code snippets e troubleshooting tips.
og_image_alt: 'Guide: converting DWG to PNG with custom size and background color
  using GroupDocs.Viewer for Java'
og_title: Converter DWG para PNG com custom size, background color em Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-30'
  description: Learn how to convert DWG to PNG, set background color Java, and customize
    image size with GroupDocs.Viewer for Java.
  headline: How to convert DWG to PNG with custom size & background color using GroupDocs.Viewer
    for Java
  type: TechArticle
- questions:
  - answer: Yes, GroupDocs.Viewer supports DXF, DWF, and several additional CAD formats.
    question: Can I render other CAD formats besides DWG?
  - answer: Instantiate a new `Color` with `new Color(123, 45, 67)` and pass it to
      `setBackgroundColor`.
    question: How do I use a custom RGB color instead of a predefined constant?
  - answer: You can specify layout or layer options via `CadOptions` before calling
      `viewer.view`.
    question: Is it possible to render only a specific layout or layer?
  - answer: Set the background color to `new Color(0,0,0,0)` for full transparency
      if the output format supports it.
    question: Does the library support transparent backgrounds?
  - answer: The tutorial uses version 25.2, but newer releases retain the same API
      surface.
    question: What version of GroupDocs.Viewer is required?
  type: FAQPage
tags:
- convert dwg
- GroupDocs.Viewer
- Java CAD rendering
- custom PNG output
title: Como converter DWG para PNG com custom size e background color usando GroupDocs.Viewer
  for Java
type: docs
url: /pt/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Como converter DWG para PNG com tamanho personalizado e cor de fundo usando GroupDocs.Viewer para Java

Neste tutorial você aprenderá **como converter DWG para PNG** controlando as dimensões de saída e a cor de fundo, usando GroupDocs.Viewer para Java. Seja para incorporar desenhos CAD em um relatório, gerar miniaturas para um portal web ou automatizar a renderização em lote, as etapas abaixo dão controle total sobre a aparência visual de cada arquivo PNG.

## Respostas rápidas
- **O que significa “converter DWG para PNG”?** É o processo de transformar um arquivo CAD DWG em uma imagem PNG por meio de código, preservando detalhes vetoriais como pixels raster.  
- **Posso definir uma largura personalizada?** Sim – chame `CadOptions.forRenderingByWidth(int width)` para definir a largura exata em pixels que você precisa.  
- **Como altero a cor de fundo?** Use `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` antes da renderização.  
- **Qual biblioteca é necessária?** GroupDocs.Viewer para Java (versão 25.2 ou mais recente).  
- **Preciso de licença?** Uma licença temporária ou completa remove limites de avaliação e habilita renderização ilimitada.

![Renderizar desenhos CAD como PNG com tamanho personalizado e cor de fundo com GroupDocs.Viewer para Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## O que é o GroupDocs.Viewer para Java?
GroupDocs.Viewer para Java é uma API server‑side que renderiza mais de 150 formatos de arquivo — incluindo arquivos CAD — em imagens, PDFs ou HTML. Funciona sem exigir nenhum software de terceiros, como AutoCAD, tornando‑a ideal para pipelines automatizados.

## Como converter DWG para PNG com tamanho personalizado e cor de fundo?
Carregue o arquivo DWG com uma instância `Viewer`, configure `CadOptions` para a largura e cor de fundo desejadas e, finalmente, chame `viewer.view` com `PngViewOptions`. Esse fluxo de três etapas lida com I/O de arquivos, renderização e nomeação de saída em uma única operação eficiente em memória.

Viewer é a classe principal que carrega um documento e realiza a renderização.  
CadOptions configura opções específicas de CAD, como largura da imagem e cor de fundo.  
PngViewOptions define o formato de saída PNG e o padrão de nomenclatura das páginas renderizadas.

Agora você pode renderizar qualquer desenho DWG para um PNG exatamente com a largura que especificar e escolher qualquer cor sólida (ou transparente) de fundo para combinar com sua marca ou tema de UI.

## Por que definir uma cor de fundo personalizada?
Definir uma cor de fundo garante que o PNG renderizado se integre perfeitamente aos elementos de UI ao redor, evita margens brancas indesejadas e pode realçar detalhes do desenho que seriam perdidos em uma tela branca padrão. GroupDocs.Viewer suporta qualquer `java.awt.Color`, incluindo valores RGB personalizados, oferecendo controle pixel‑perfect.

java.awt.Color representa um valor de cor usado para renderizar fundos.

## Pré-requisitos

- **Java Development Kit (JDK) 8+** – a API tem como alvo o Java 8 e versões posteriores.  
- **Maven** – para gerenciamento de dependências.  
- **IDE** – IntelliJ IDEA, Eclipse ou qualquer editor de sua preferência.  
- **Conhecimento básico de manipulação de arquivos Java** – para ler arquivos DWG de origem e gravar saídas PNG.

## Configurando o GroupDocs.Viewer para Java
Adicione o repositório GroupDocs e a dependência Viewer ao seu `pom.xml` Maven:

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
Obtenha uma chave de licença temporária ou completa no portal GroupDocs e coloque o arquivo `license.lic` na pasta de recursos do seu projeto. Isso remove o limite de avaliação de 20 páginas e desbloqueia renderização em alta resolução.

### Inicialização e configuração básicas
Crie uma instância `Viewer` que aponte para a pasta contendo seus arquivos DWG:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Recurso 1: renderização de desenhos CAD com tamanho de imagem personalizado e cor de fundo

### Como alterar a cor de fundo do CAD
Para mudar a cor de fundo do CAD, configure o objeto CadOptions antes da renderização. Defina a largura desejada com `forRenderingByWidth` e aplique o novo fundo usando `setBackgroundColor`. O viewer então gera imagens PNG que refletem a cor especificada, garantindo estilo visual consistente em todos os arquivos de saída.

#### Implementação passo a passo

##### Importar pacotes necessários
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Configurar o diretório de saída e o formato do caminho do arquivo
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### Inicializar o viewer com opções de renderização personalizadas
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Specify the width for rendering
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);

    viewer.view(options);
}
```

**Explicação dos parâmetros**  
- `PngViewOptions` – define o formato de saída PNG e o padrão de nomenclatura.  
- `forRenderingByWidth(int width)` – força o renderizador a produzir uma imagem cuja largura corresponde ao valor de pixels fornecido; a altura é escalada proporcionalmente.  
- `setBackgroundColor(Color color)` – substitui a tela branca padrão pela cor que você escolher, melhorando a consistência visual nos ativos gerados.

#### Dicas de solução de problemas
- Certifique-se de que a pasta de saída exista; use `Files.createDirectories(outputDir)` se não existir.  
- Verifique se o caminho do arquivo de entrada está correto e se a aplicação tem permissões de leitura.  

## Recurso 2: definir cor de fundo nas opções de renderização

### Como definir a cor de fundo do PNG
Definir a cor de fundo do PNG envolve criar uma instância `Color` e atribuí‑la ao `CadOptions` antes da renderização. Isso garante que cada PNG gerado use o fundo especificado, correspondendo às diretrizes da sua marca ou tema de UI. Você pode usar constantes predefinidas ou definir valores RGB personalizados para controle preciso.

java.awt.Color representa um valor de cor usado para renderizar fundos.

#### Implementação passo a passo

##### Importar pacotes necessários
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Configurar opções de renderização com cor de fundo
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);
    
    viewer.view(options);
}
```

**Opções de configuração principais**  
- Ajuste `forRenderingByWidth(int width)` para diferentes dimensões, como 800 px para miniaturas web ou 1920 px para impressões de alta resolução.  
- Use qualquer constante `Color` predefinida (por exemplo, `Color.LIGHT_GRAY`) ou crie uma instância personalizada com `new Color(r, g, b)` para branding preciso.  

## Aplicações práticas

### 1. Documentação de engenharia
A renderização personalizada garante que cada desenho siga o guia de estilo da empresa, eliminando a edição manual de imagens após a exportação.

### 2. Visualização arquitetônica
Apresente plantas com um fundo que combine com apresentações ou portais voltados ao cliente, melhorando a coesão visual.

### 3. Prototipagem de fabricação
Gere PNGs para fluxos de trabalho de prototipagem rápida onde ferramentas subsequentes esperam um tamanho e fundo de imagem específicos.

### Possibilidades de integração
Combine este pipeline de renderização com um sistema de gerenciamento de documentos (por exemplo, SharePoint) para gerar automaticamente imagens de pré‑visualização sempre que um arquivo DWG for carregado.

## Considerações de desempenho

### Otimizando o desempenho
- **Processamento em lote:** Percorra um diretório de arquivos DWG e renderize cada um sequencialmente para amortizar os custos de inicialização da JVM.  
- **Gerenciamento de recursos:** Para desenhos grandes (500+ páginas), aumente o heap da JVM (`-Xmx2g`) ou processe arquivos em lotes menores para evitar erros de falta de memória.

### Diretrizes de uso de recursos
Monitore o uso de CPU e memória com ferramentas como VisualVM; libere instâncias `Viewer` prontamente usando try‑with‑resources.

### Melhores práticas para gerenciamento de memória Java
- Use try‑with‑resources (conforme mostrado) para fechar automaticamente o `Viewer`.  
- Evite reter objetos `Path` grandes além do uso imediato.  

## Problemas comuns e soluções

| Problema | Solução |
|----------|---------|
| Pasta de saída não encontrada | Crie o diretório antecipadamente ou adicione `Files.createDirectories(outputDirectory);` |
| Imagem em branco | Certifique-se de que `cadOptions.setBackgroundColor` seja chamado após `forRenderingByWidth`. |
| Erros de falta de memória | Aumente a opção JVM `-Xmx` ou processe os arquivos em lotes menores. |

## Perguntas frequentes

**Q: Posso renderizar outros formatos CAD além de DWG?**  
A: Sim, GroupDocs.Viewer suporta DXF, DWF e vários outros formatos CAD.

**Q: Como usar uma cor RGB personalizada em vez de uma constante predefinida?**  
A: Instancie um novo `Color` com `new Color(123, 45, 67)` e passe‑o para `setBackgroundColor`.

**Q: É possível renderizar apenas um layout ou camada específicos?**  
A: Você pode especificar opções de layout ou camada via `CadOptions` antes de chamar `viewer.view`.

**Q: A biblioteca suporta fundos transparentes?**  
A: Defina a cor de fundo para `new Color(0,0,0,0)` para transparência total se o formato de saída suportar.

**Q: Qual versão do GroupDocs.Viewer é necessária?**  
A: O tutorial usa a versão 25.2, mas lançamentos mais recentes mantêm a mesma superfície de API.

**Última atualização:** 2026-08-30  
**Testado com:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs

## Tutoriais relacionados

- [groupdocs viewer dwg – Como renderizar desenhos CAD específicos em Java usando GroupDocs.Viewer](/viewer/java/rendering-basics/render-cad-groupdocs-viewer-java/)
- [Renderizar camadas CAD Java com GroupDocs.Viewer – Um guia completo](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [Como converter pdf para html e otimizar a qualidade da imagem em Java com GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)