---
date: '2026-03-22'
description: Aprenda a gerar HTML a partir de PDF e desativar o agrupamento de caracteres
  usando o GroupDocs Viewer para Java para uma representação precisa do texto.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: Gerar HTML a partir de PDF e Desativar Agrupamento – GroupDocs Java
type: docs
url: /pt/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# Gerar HTML a partir de PDF e Desativar Agrupamento com GroupDocs Viewer para Java

Em muitos projetos, você precisa **gerar HTML a partir de PDF** mantendo cada glifo exatamente onde ele pertence. Isso é especialmente verdadeiro para scripts complexos, línguas antigas ou documentos legais, onde um único caractere fora de lugar pode mudar o significado. Neste tutorial, vamos guiá‑lo pelo processo completo de renderização de PDFs para HTML com GroupDocs Viewer para Java e mostrar **como desativar o agrupamento** para que cada caractere seja tratado como um elemento independente.

![Técnicas de Renderização Precisa com GroupDocs.Viewer para Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Respostas Rápidas
- **O que faz “desativar agrupamento”?** Ele força o renderizador a tratar cada caractere como um elemento independente, preservando o layout exato.  
- **Qual opção da API controla isso?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Preciso de uma licença?** Uma versão de avaliação funciona para testes, mas uma licença completa é necessária para produção.  
- **Posso gerar HTML a partir de PDF ao mesmo tempo?** Sim—use `HtmlViewOptions` para criar a saída HTML enquanto desativa o agrupamento.  
- **Esse recurso é limitado a PDFs?** É principalmente para PDFs, mas o visualizador suporta muitos outros formatos.

## Introdução

Ao trabalhar com documentos PDF, a precisão na renderização é crucial—especialmente ao lidar com estruturas de texto complexas como hieróglifos ou idiomas que exigem representação precisa de caracteres. O recurso “Character Grouping” frequentemente causa problemas ao agrupar caracteres incorretamente, levando à interpretação equivocada do conteúdo do documento. Isso pode ser particularmente problemático para usuários que precisam de replicação exata do layout de texto de seus documentos.

### Pré‑requisitos
- **Bibliotecas e Dependências**: Você precisará do GroupDocs.Viewer para Java versão 25.2 ou posterior.  
- **Configuração do Ambiente**: Certifique‑se de que o Java Development Kit (JDK) está instalado e que sua IDE está configurada para trabalhar com projetos Maven.  
- **Pré‑requisitos de Conhecimento**: Compreensão básica de programação Java, especialmente manipulação de caminhos de arquivos e uso de bibliotecas externas.

## Como gerar HTML a partir de PDF com GroupDocs Viewer

Gerar HTML a partir de PDF é um processo de duas etapas: configurar o visualizador e, em seguida, renderizar o documento. O ponto chave é desativar o agrupamento de caracteres antes da renderização, para que a saída HTML reflita o layout original do PDF caractere por caractere.

### Configurando o GroupDocs.Viewer para Java

#### Instalação via Maven

Primeiro, integre a biblioteca necessária ao seu projeto. Adicione a seguinte configuração no seu `pom.xml`:

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

#### Aquisição de Licença

Para utilizar plenamente o GroupDocs.Viewer, considere adquirir uma licença:
- **Teste Gratuito**: Comece com o teste gratuito para experimentar os recursos.  
- **Licença Temporária**: Solicite uma licença temporária se precisar de mais tempo.  
- **Compra**: Para projetos de longo prazo, é recomendável adquirir uma licença.

#### Inicialização e Configuração Básicas

Abaixo está um trecho pronto‑para‑executar que mostra o fluxo completo—desde a definição da pasta de saída até a renderização do PDF como HTML enquanto desativa o agrupamento de caracteres:

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### Guia de Implementação

#### Recurso: Desativar Agrupamento de Caracteres

A seguir, detalhamos cada linha do exemplo para que você entenda **por que** a fazemos e **como** ela contribui para gerar HTML a partir de PDF sem mesclagem indesejada de caracteres.

##### Etapa 1: Definir Diretório de Saída  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Por quê?** Isso garante que seus arquivos HTML renderizados sejam armazenados em uma pasta dedicada, facilitando a localização e o gerenciamento posteriores.

##### Etapa 2: Configurar Formato do Caminho de Arquivo  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Por quê?** Usar um placeholder (`{0}`) permite que o visualizador crie um arquivo HTML separado para cada página do PDF, mantendo a saída organizada.

##### Etapa 3: Inicializar Opções de Visualização HTML  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Por quê?** Recursos incorporados agrupam imagens, fontes e CSS diretamente em cada página HTML, o que é ideal para visualizadores baseados na web ou plataformas de e‑learning.

##### Etapa 4: Desativar Agrupamento de Caracteres  

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Por quê?** Esta é a linha crucial que indica ao motor de renderização **não** mesclar caracteres adjacentes, garantindo que o HTML gerado reflita a posição exata dos glifos do PDF de origem.

##### Etapa 5: Renderizar o Documento  

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Por quê?** Envolver o `Viewer` em um bloco try‑with‑resources garante que todos os recursos nativos sejam liberados automaticamente, evitando vazamentos de memória em aplicações de longa duração.

### Gerando HTML Java a partir de PDF sem Agrupamento

A classe `HtmlViewOptions` permite que você produza **gerar html a partir de pdf** mantendo cada caractere separado. Isso é especialmente útil quando você precisa incorporar as páginas renderizadas em um portal web ou em uma plataforma de e‑learning onde a colocação exata dos glifos é importante.

### Problemas Comuns e Soluções

- **FileNotFoundException** – Verifique novamente o caminho que você passa para `new Viewer(...)`. Use caminhos absolutos ou `Path.of(...)` para maior clareza.  
- **Permissões de Escrita** – Certifique‑se de que o diretório de saída seja gravável pelo processo Java; no Linux pode ser necessário ajustar as permissões da pasta (`chmod 775`).  
- **Incompatibilidade de Versão** – A opção `setDisableCharsGrouping` está disponível a partir da versão 25.2. Verifique se o seu `pom.xml` reflete a versão correta.  

### Aplicações Práticas

1. **Preservação de Idiomas** – Ideal para renderizar documentos em Chinês, Japonês, Árabe ou scripts antigos onde o espaçamento de caracteres tem significado.  
2. **Documentos Legais e Financeiros** – Garante a replicação exata do texto para documentos com alta exigência de conformidade.  
3. **Recursos Educacionais** – Perfeito para livros didáticos que incluem diagramas complexos, anotações ou conteúdo multilíngue.  

### Considerações de Desempenho

- **Otimizar Uso de Recursos** – PDFs grandes podem consumir muita memória. Considere processar páginas em lotes e descartar as instâncias de `Viewer` prontamente.  
- **Gerenciamento de Memória Java** – Ajuste o heap da JVM (`-Xmx2g` ou superior) se você prever o processamento de PDFs com várias centenas de páginas.  
- **Renderização Paralela** – Para conversões em massa, crie threads separadas, cada uma com sua própria instância de `Viewer`, para aproveitar CPUs multi‑core.  

## Perguntas Frequentes

**Q:** *Por que eu precisaria desativar o agrupamento de caracteres?*  
**A:** Desativar o agrupamento impede que o renderizador mescle caracteres que pertencem a glifos distintos, o que é essencial para scripts onde o espaçamento e a ordem transmitem significado.

**Q:** *A configuração `setDisableCharsGrouping` se aplica apenas à saída HTML?*  
**A:** Não, ela afeta o motor de renderização PDF subjacente, portanto qualquer formato de saída (HTML, PNG, JPEG, etc.) refletirá a alteração.

**Q:** *Posso combinar essa configuração com fontes personalizadas?*  
**A:** Sim—carregue suas fontes personalizadas antes de inicializar o `Viewer`, e a regra de agrupamento ainda será aplicada.

**Q:** *Desativar o agrupamento impacta o desempenho?*  
**A:** Um pouco, pois o motor processa cada caractere individualmente, mas o impacto é mínimo para a maioria dos documentos.

**Q:** *Existe uma maneira de alternar o agrupamento por página?*  
**A:** Atualmente a opção é global por instância de `PdfOptions`; você precisaria de instâncias separadas de `Viewer` para diferentes páginas se precisar de comportamento misto.

## Recursos

- [Documentação do GroupDocs](https://docs.groupdocs.com/viewer/java/)
- [Referência da API](https://reference.groupdocs.com/viewer/java/)
- [Download do GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Comprar Licença](https://purchase.groupdocs.com/buy)
- [Versão de Teste Gratuita](https://releases.groupdocs.com/viewer/java/)
- [Solicitação de Licença Temporária](https://purchase.groupdocs.com/temporary-license/)
- [Fórum de Suporte do GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Última Atualização:** 2026-03-22  
**Testado com:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs