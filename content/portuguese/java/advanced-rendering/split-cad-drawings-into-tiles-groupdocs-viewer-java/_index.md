---
date: '2026-04-01'
description: Aprenda a dividir desenhos CAD em blocos usando o GroupDocs Viewer para
  Java, aumentando o desempenho de renderização e simplificando o manuseio de arquivos
  grandes.
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: Como dividir desenhos CAD em blocos com o GroupDocs Viewer
type: docs
url: /pt/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# Como dividir desenhos CAD em blocos com o GroupDocs Viewer

Se você está se perguntando **como dividir CAD** em arquivos menores e mais manejáveis, você está no lugar certo. Neste tutorial, vamos percorrer os passos exatos necessários para dividir grandes desenhos CAD em blocos usando **GroupDocs Viewer for Java**. Ao final, você terá uma solução pronta‑para‑usar que melhora a velocidade de renderização, reduz o consumo de memória e facilita a exibição dos desenhos em aplicações web ou móveis.

![Split CAD Drawings with GroupDocs.Viewer for Java](/viewer/advanced-rendering/split-cad-drawings-java.png)

## Respostas Rápidas
- **O que “dividir CAD” realiza?** Ele divide um desenho massivo em imagens menores (blocos) que carregam mais rápido e consomem menos memória.  
- **Qual formato é usado para os blocos?** Arquivos PNG são gerados por padrão, mas outros formatos são suportados via opções do Viewer.  
- **Preciso de uma licença?** Um teste gratuito funciona para desenvolvimento; uma licença paga é necessária para produção.  
- **Posso mudar o tamanho do bloco?** Sim – ajuste os cálculos `tileWidth` e `tileHeight` conforme suas necessidades.  
- **Esta abordagem é thread‑safe?** Renderizar cada bloco em sua própria instância `Viewer` com try‑with‑resources é seguro para execução concorrente.

## O que é “dividir CAD”?
Dividir CAD refere-se a dividir um único desenho CAD, frequentemente enorme, em múltiplas seções retangulares (blocos). Cada bloco é renderizado independentemente, permitindo que você carregue apenas as partes que o usuário realmente precisa — perfeito para mapas web, portais de documentos e visualizadores móveis.

## Por que usar o GroupDocs Viewer para Java?
O GroupDocs Viewer oferece suporte pronto‑para‑uso a mais de 100 formatos de arquivo, incluindo DWG, DXF e DWF. Sua API de blocos permite especificar coordenadas exatas, para que você possa renderizar exatamente a área de interesse sem processar todo o arquivo primeiro. Isso economiza ciclos de CPU, reduz a largura de banda e oferece uma experiência de usuário mais fluida.

## Pré‑requisitos
- **Bibliotecas**: GroupDocs.Viewer for Java ≥ 25.2.  
- **JDK**: Qualquer JDK recente (Java 8+).  
- **IDE**: IntelliJ IDEA, Eclipse ou outra IDE compatível com Java.  
- **Ferramenta de Build**: Maven (outras ferramentas de build funcionam desde que a dependência seja adicionada).  

## Configurando o GroupDocs.Viewer para Java
Add the GroupDocs repository and dependency to your `pom.xml`:

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
GroupDocs.Viewer offers a free trial license for evaluation:

- **Teste Gratuito**: Visite [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) para baixar a biblioteca.  
- **Licença Temporária**: Solicite em [Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Licença Completa**: Compre uma licença de produção na [Purchase Page](https://purchase.groupdocs.com/buy).

### Inicialização Básica
Create a simple `Viewer` instance to verify that the library loads correctly:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## Guia Passo a Passo para Dividir Desenhos CAD em Blocos

### Etapa 1: Definir o Diretório de Saída
We’ll store each tile as a separate PNG file. Using a utility method keeps the path logic clean and reusable.

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### Etapa 2: Configurar Opções de Visualização
Set the rendering format to PNG and tell the viewer not to preload every page (which saves memory).

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### Etapa 3: Calcular Dimensões dos Blocos
First we obtain the drawing’s original width and height, then split it into four equal quadrants.

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### Etapa 4: Renderizar e Salvar os Blocos
Add the calculated tiles to the rendering options and let the `Viewer` generate the PNG files.

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### Dicas de Solução de Problemas
- **Caminho de compilação** – Certifique-se de que os arquivos JAR do GroupDocs estejam no classpath.  
- **Permissões** – A pasta de saída deve ser gravável pelo processo Java.  
- **Exceções** – Se você vir `ViewerException`, verifique se o arquivo DWG não está corrompido e se a licença correta foi aplicada.

## Casos de Uso Comuns para Dividir Blocos CAD
1. **Mapeamento Web** – Carregue apenas a parte visível de um plano de piso conforme o usuário navega/zooma.  
2. **Gerenciamento de Documentos** – Armazene cada bloco separadamente para geração de pré‑visualizações mais rápidas.  
3. **Visualização Móvel** – Reduza a largura de banda baixando apenas os blocos necessários para a tela atual.

## Considerações de Desempenho
- **Tamanho do Bloco** – Blocos maiores significam menos arquivos, mas renderização mais lenta; encontre um equilíbrio com base nas necessidades da sua UI.  
- **Monitoramento de Memória** – Use as ferramentas de profiling do Java (por exemplo, VisualVM) para observar o uso de heap ao processar desenhos muito grandes.  
- **Limpeza de Recursos** – O padrão try‑with‑resources mostrado acima libera automaticamente recursos nativos.

## Perguntas Frequentes

**Q: Posso dividir outros tipos de arquivo (PDF, imagens) em blocos usando a mesma abordagem?**  
A: Sim. O GroupDocs Viewer suporta muitos formatos; você só precisa usar a classe de opções correspondente (por exemplo, `PdfViewOptions`).

**Q: Como altero a qualidade da imagem de saída?**  
A: Ajuste `viewOptions.setResolution(int dpi)` ou configure as opções de compressão no objeto `PngOptions`.

**Q: Minha aplicação fica sem memória em arquivos DWG muito grandes — o que posso fazer?**  
A: Reduza as dimensões dos blocos, aumente o heap da JVM (`-Xmx`) ou renderize os blocos sequencialmente em instâncias `Viewer` separadas.

**Q: É possível renderizar blocos de forma assíncrona?**  
A: Absolutamente. Envolva cada chamada de renderização de bloco em um `CompletableFuture` ou use um serviço executor para paralelizar a carga de trabalho.

**Q: Preciso de uma licença separada para cada bloco?**  
A: Não. Uma única licença válida do GroupDocs Viewer cobre todas as operações de renderização dentro da sua aplicação.

## Recursos
- [Documentação](https://docs.groupdocs.com/viewer/java/)
- [Referência da API](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Comprar uma Licença](https://purchase.groupdocs.com/buy)
- [Teste Gratuito](https://releases.groupdocs.com/viewer/java/)
- [Licença Temporária](https://purchase.groupdocs.com/temporary-license/)
- [Fórum de Suporte](https://forum.groupdocs.com/c/viewer/9)

---

**Última Atualização:** 2026-04-01  
**Testado com:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs