---
date: '2026-01-08'
description: Aprenda como renderizar desenhos CAD em imagens PNG de alta qualidade
  usando dimensões personalizadas e cores de fundo com o GroupDocs.Viewer para Java.
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: Como Renderizar Desenhos CAD como PNG com Tamanho Personalizado e Cor de Fundo
  Usando o GroupDocs.Viewer para Java
type: docs
url: /pt/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Como Renderizar Desenhos CAD como PNG com Tamanho Personalizado e Cor de Fundo Usando GroupDocs.Viewer para Java

Está com dificuldade para converter seus desenhos CAD em imagens de alta qualidade enquanto mantém dimensões e estética específicas? Neste tutorial, mostraremos **como renderizar CAD** em arquivos PNG com tamanho e cor de fundo personalizados, para que você obtenha exatamente a aparência necessária para relatórios, apresentações ou visualizações na web.

## Respostas Rápidas
- **O que significa “how to render CAD”?** Refere‑se à conversão de arquivos CAD (por exemplo, DWG) em formatos de imagem como PNG usando código.  
- **Posso definir uma largura personalizada?** Sim – use `CadOptions.forRenderingByWidth(int width)`.  
- **Como altero o fundo?** Chame `cadOptions.setBackgroundColor(Color.YOUR_COLOR)`.  
- **Qual biblioteca é necessária?** GroupDocs.Viewer para Java (versão 25.2 ou posterior).  
- **Preciso de licença?** Uma licença temporária ou comprada remove as limitações de avaliação.

![Renderizar Desenhos CAD como PNG com Tamanho Personalizado e Cor de Fundo com GroupDocs.Viewer para Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Como Renderizar Desenhos CAD – Visão Geral
Esta seção expande o objetivo principal: **como renderizar CAD** em arquivos PNG controlando tamanho e fundo. Vamos percorrer a configuração completa, trechos de código e dicas práticas.

## O Que Você Vai Aprender
- Configurar o GroupDocs.Viewer para Java em seu projeto  
- **Converter DWG para PNG** com dimensões personalizadas  
- **Definir cor de fundo PNG** durante a renderização para um visual refinado  
- Cenários reais onde a renderização personalizada agrega valor  

## Pré‑requisitos

### Bibliotecas e Dependências Necessárias
- Java Development Kit (JDK) 8+  
- Maven para gerenciamento de dependências  

### Requisitos de Configuração do Ambiente
- IDE como IntelliJ IDEA ou Eclipse  
- Conhecimento básico de Java  

### Pré‑requisitos de Conhecimento
- Familiaridade com manipulação de arquivos em Java  

## Configurando o GroupDocs.Viewer para Java
Adicione o repositório GroupDocs e a dependência ao seu `pom.xml` do Maven:

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
Obtenha uma licença temporária ou completa para remover as restrições de avaliação.

### Inicialização e Configuração Básicas
Crie uma instância `Viewer` que aponte para seu arquivo CAD:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Guia de Implementação

### Recurso 1: Renderizar Desenhos CAD com Tamanho de Imagem Personalizado e Cor de Fundo

#### Visão Geral
Este recurso permite **converter DWG para PNG** especificando a largura da imagem e a tonalidade do fundo.

#### Implementação Passo a Passo

##### Importar Pacotes Necessários
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Configurar o Diretório de Saída e o Formato do Caminho do Arquivo
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### Inicializar Viewer com Opções de Renderização Personalizadas
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

**Explicação dos Parâmetros**  
- `PngViewOptions` – define o formato de saída e a nomenclatura.  
- `forRenderingByWidth(int width)` – define a largura personalizada da imagem.  
- `setBackgroundColor(Color color)` – **aplica a cor de fundo** ao PNG.

#### Dicas de Solução de Problemas
- Verifique se a pasta de saída existe; crie‑a se necessário.  
- Verifique novamente o caminho do arquivo de entrada e as permissões.  

### Recurso 2: Definir Cor de Fundo nas Opções de Renderização

#### Visão Geral
Aqui focamos em **definir cor de fundo PNG** para melhorar a consistência visual.

#### Implementação Passo a Passo

##### Importar Pacotes Necessários
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Configurar Opções de Renderização com Cor de Fundo
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

**Opções de Configuração Principais**  
- Ajuste `forRenderingByWidth(int width)` para diferentes dimensões.  
- Use qualquer constante `Color` ou `new Color(r,g,b)` personalizado para fundos sob medida.  

## Aplicações Práticas

### 1. Documentação de Engenharia
A renderização personalizada garante que os desenhos de engenharia atendam aos guias de estilo corporativo.

### 2. Visualização Arquitetônica
Apresente plantas com um fundo limpo que combine com os decks de apresentação.

### 3. Prototipagem de Fabricação
Gere PNGs precisos para fluxos de trabalho de prototipagem rápida.

### Possibilidades de Integração
Combine este pipeline de renderização com sistemas de gerenciamento de documentos para automatizar a geração de ativos visuais.

## Considerações de Desempenho

### Otimizando o Desempenho
- **Processamento em Lote:** Renderize vários arquivos CAD em um loop.  
- **Gerenciamento de Recursos:** Ajuste o tamanho do heap da JVM para desenhos grandes.

### Diretrizes de Uso de Recursos
Monitore CPU e memória; libere as instâncias `Viewer` prontamente.

### Melhores Práticas para Gerenciamento de Memória Java
- Use try‑with‑resources (como mostrado) para fechar automaticamente o `Viewer`.  
- Evite manter objetos `Path` grandes por mais tempo que o necessário.

## Problemas Comuns e Soluções

| Problema | Solução |
|----------|---------|
| **Pasta de saída não encontrada** | Crie o diretório antecipadamente ou adicione `Files.createDirectories(outputDirectory);` |
| **Imagem em branco** | Certifique‑se de que `cadOptions.setBackgroundColor` seja definido após `forRenderingByWidth`. |
| **Erros de falta de memória** | Aumente a opção JVM `-Xmx` ou processe arquivos em lotes menores. |

## Perguntas Frequentes

**Q: Posso renderizar outros formatos CAD além de DWG?**  
A: Sim, o GroupDocs.Viewer suporta DXF, DWF e vários outros tipos de arquivos CAD.

**Q: Como uso uma cor RGB personalizada em vez de uma constante predefinida?**  
A: Crie uma nova instância `Color`, por exemplo, `new Color(123, 45, 67)` e passe‑a para `setBackgroundColor`.

**Q: É possível renderizar apenas um layout ou camada específicos?**  
A: Você pode especificar opções de layout ou camada via `CadOptions` antes de chamar `viewer.view`.

**Q: A biblioteca suporta fundos transparentes?**  
A: Defina a cor de fundo para `new Color(0,0,0,0)` para transparência total se o formato de destino suportar.

**Q: Qual versão do GroupDocs.Viewer é necessária?**  
A: O tutorial usa a versão 25.2, mas versões mais recentes mantêm a mesma API.

## Conclusão
Agora você sabe **como renderizar CAD** em arquivos PNG com dimensões e cores de fundo personalizadas usando o GroupDocs.Viewer para Java. Aplique essas técnicas para criar ativos visuais de aparência profissional para fluxos de trabalho de engenharia, arquitetura ou fabricação.

### Próximos Passos
- Experimente diferentes larguras de imagem e cores.  
- Integre o código de renderização em um serviço de processamento em lote.  
- Explore opções adicionais do Viewer, como conversão para PDF ou renderização de múltiplas páginas.

---

**Última Atualização:** 2026-01-08  
**Testado com:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs