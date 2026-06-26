---
date: '2026-03-16'
description: Aprenda como converter DWG para PNG com tamanho e cor de fundo personalizados
  usando o GroupDocs.Viewer para Java.
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: Como converter DWG para PNG com tamanho personalizado e cor de fundo usando
  o GroupDocs.Viewer para Java
type: docs
url: /pt/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Como Converter DWG para PNG com Tamanho Personalizado e Cor de Fundo Usando GroupDocs.Viewer para Java

Se você está procurando **converter DWG para PNG** mantendo total controle sobre as dimensões da imagem e o estilo do fundo, você está no lugar certo. Neste tutorial, vamos guiá‑lo na renderização de arquivos CAD como PNGs, personalizando a largura e alterando a cor de fundo para que a saída corresponda aos requisitos do seu relatório, apresentação ou visualização na web.

## Respostas Rápidas
- **O que significa “converter DWG para PNG”?** É o processo de transformar um arquivo DWG CAD em uma imagem PNG usando código.  
- **Posso definir uma largura personalizada?** Sim – use `CadOptions.forRenderingByWidth(int width)`.  
- **Como altero a cor de fundo?** Chame `cadOptions.setBackgroundColor(Color.YOUR_COLOR)`.  
- **Qual biblioteca é necessária?** GroupDocs.Viewer para Java (versão 25.2 ou posterior).  
- **Preciso de uma licença?** Uma licença temporária ou comprada remove os limites de avaliação.

![Render CAD Drawings as PNG with Custom Size & Background Color with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Como Converter DWG para PNG – Visão Geral
Nesta seção, expandimos o objetivo principal: **como converter DWG para PNG** controlando tamanho e fundo. Você verá a configuração completa, o código exato que precisa e dicas práticas para evitar armadilhas comuns.

## O Que Você Vai Aprender
- Configurar o GroupDocs.Viewer para Java em um projeto Maven  
- **Converter DWG para PNG** com dimensões personalizadas  
- **Alterar a cor de fundo do CAD** durante a renderização para um visual refinado  
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
Adicione o repositório GroupDocs e a dependência ao seu `pom.xml` Maven:

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
Crie uma instância `Viewer` que aponta para o seu arquivo CAD:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Recurso 1: Renderizando Desenhos CAD com Tamanho de Imagem Personalizado e Cor de Fundo

### Como Alterar a Cor de Fundo do CAD
Este recurso permite **converter DWG para PNG** especificando uma largura personalizada e aplicando um novo tom de fundo.

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
- `setBackgroundColor(Color color)` – **define a cor de fundo do PNG** para melhorar a consistência visual.

#### Dicas de Solução de Problemas
- Verifique se a pasta de saída existe; crie-a se necessário.  
- Verifique novamente o caminho do arquivo de entrada e as permissões.  

## Recurso 2: Definindo a Cor de Fundo nas Opções de Renderização

### Como Definir a Cor de Fundo do PNG
Aqui nos concentramos na opção **set background color PNG** para garantir que cada imagem renderizada corresponda à paleta da sua marca.

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

**Opções Principais de Configuração**  
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
- Evite manter objetos `Path` grandes por mais tempo do que o necessário.

## Problemas Comuns e Soluções

| Problema | Solução |
|----------|---------|
| **Pasta de saída não encontrada** | Crie o diretório antecipadamente ou adicione `Files.createDirectories(outputDirectory);` |
| **Imagem em branco** | Certifique-se de que `cadOptions.setBackgroundColor` seja definido após `forRenderingByWidth`. |
| **Erros de falta de memória** | Aumente a opção JVM `-Xmx` ou processe os arquivos em lotes menores. |

## Perguntas Frequentes

**Q: Posso renderizar outros formatos CAD além de DWG?**  
A: Sim, o GroupDocs.Viewer suporta DXF, DWF e vários outros tipos de arquivos CAD.

**Q: Como uso uma cor RGB personalizada em vez de uma constante predefinida?**  
A: Crie uma nova instância `Color`, por exemplo, `new Color(123, 45, 67)` e passe-a para `setBackgroundColor`.

**Q: É possível renderizar apenas um layout ou camada específicos?**  
A: Você pode especificar opções de layout ou camada via `CadOptions` antes de chamar `viewer.view`.

**Q: A biblioteca suporta fundos transparentes?**  
A: Defina a cor de fundo como `new Color(0,0,0,0)` para transparência total se o formato de destino suportar.

**Q: Qual versão do GroupDocs.Viewer é necessária?**  
A: O tutorial usa a versão 25.2, mas versões mais recentes mantêm a mesma API.

---

**Última Atualização:** 2026-03-16  
**Testado com:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs