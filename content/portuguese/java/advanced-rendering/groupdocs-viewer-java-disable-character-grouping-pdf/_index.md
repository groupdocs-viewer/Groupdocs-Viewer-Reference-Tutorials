---
date: '2025-12-21'
description: Aprenda como desativar o agrupamento em PDFs com o GroupDocs.Viewer para
  Java, usando java html nas opções de renderização de PDF para garantir uma representação
  precisa do texto.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: Como desativar o agrupamento em PDFs com o GroupDocs.Viewer para Java
type: docs
url: /pt/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# Como Desativar o Agrupamento em PDFs com GroupDocs.Viewer para Java

Quando você precisa **desativar o agrupamento** ao renderizar PDFs, especialmente para scripts complexos ou línguas antigas, o posicionamento preciso dos caracteres torna‑se essencial. O recurso padrão *Character Grouping* pode mesclar caracteres incorretamente, causando interpretação errônea do conteúdo. Neste guia, mostraremos passo a passo como desativar o agrupamento usando o GroupDocs.Viewer para Java, para que cada glifo permaneça exatamente onde deve estar.

![Técnicas de Renderização Precisa com GroupDocs.Viewer para Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Respostas Rápidas
- **O que “desativar o agrupamento” faz?** Ele força o renderizador a tratar cada caractere como um elemento independente, preservando o layout exato.  
- **Qual opção de API controla isso?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Preciso de uma licença?** Um teste funciona para avaliação, mas uma licença completa é necessária para produção.  
- **Posso gerar HTML Java a partir do PDF ao mesmo tempo?** Sim—use `HtmlViewOptions` para criar saída HTML enquanto desativa o agrupamento.  
- **Esse recurso é limitado a PDFs?** É principalmente para PDFs, mas o visualizador suporta muitos outros formatos.

## Introdução

Ao trabalhar com documentos PDF, a precisão na renderização é crucial—especialmente ao lidar com estruturas de texto complexas como hieróglifos ou línguas que exigem representação precisa dos caracteres. O recurso "Character Grouping" frequentemente causa problemas ao agrupar caracteres incorretamente, levando à interpretação errônea do conteúdo do documento. Isso pode ser particularmente problemático para usuários que precisam de replicação exata do layout de texto de seus documentos.

### Pré‑requisitos
- **Bibliotecas e Dependências**: Você precisará do GroupDocs.Viewer para Java versão 25.2 ou superior.  
- **Configuração do Ambiente**: Certifique‑se de que o Java Development Kit (JDK) esteja instalado e que sua IDE esteja configurada para trabalhar com projetos Maven.  
- **Pré‑requisitos de Conhecimento**: Compreensão básica de programação Java, especialmente manipulação de caminhos de arquivos e uso de bibliotecas externas.

## Como Desativar o Agrupamento na Renderização de PDF

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

Para utilizar totalmente o GroupDocs.Viewer, considere adquirir uma licença:
- **Teste Gratuito**: Comece com o teste gratuito para experimentar os recursos.  
- **Licença Temporária**: Solicite uma licença temporária se precisar de mais tempo.  
- **Compra**: Para projetos de longo prazo, a compra de uma licença é recomendada.

#### Inicialização e Configuração Básicas

Comece configurando o ambiente do seu projeto:

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

#### Recurso: Desativar o Agrupamento de Caracteres

##### Etapa 1: Definir o Diretório de Saída

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Por quê?** Isso garante que sua saída esteja organizada e facilmente acessível.

##### Etapa 2: Configurar o Formato do Caminho de Arquivo

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Por quê?** Ajuda a organizar sistematicamente as páginas do documento PDF.

##### Etapa 3: Inicializar as Opções de Visualização HTML

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Por quê?** Recursos incorporados garantem que todos os ativos necessários estejam incluídos no arquivo HTML de cada página.

##### Etapa 4: Desativar o Agrupamento de Caracteres

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Por quê?** Isso garante que os caracteres sejam renderizados individualmente, preservando seu layout e significado pretendidos.

##### Etapa 5: Renderizar o Documento

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Por quê?** Isso garante que todos os recursos sejam fechados adequadamente, evitando vazamentos de memória.

### Gerando HTML Java a partir de PDF sem Agrupamento

A classe `HtmlViewOptions` permite que você produza **html java a partir de pdf** mantendo cada caractere separado. Isso é especialmente útil quando você precisa incorporar as páginas renderizadas em um portal web ou em uma plataforma de e‑learning onde a colocação exata dos glifos é importante.

### Dicas de Solução de Problemas
- Certifique‑se de que o caminho do documento esteja correto para evitar `FileNotFoundException`.  
- Verifique se o diretório de saída tem permissões de gravação.  
- Verifique novamente se está usando uma versão compatível do GroupDocs.Viewer para Java.

## Aplicações Práticas
1. **Preservação de Línguas**: Ideal para renderizar documentos em idiomas como Chinês, Japonês ou scripts antigos onde a precisão dos caracteres é importante.  
2. **Documentos Legais e Financeiros**: Garante a exatidão em documentos que exigem representação precisa do texto para conformidade.  
3. **Recursos Educacionais**: Perfeito para livros didáticos e artigos acadêmicos que incluem diagramas ou anotações complexas.

## Considerações de Desempenho
- **Otimizar o Uso de Recursos**: Certifique‑se de que seu servidor possua recursos adequados para lidar com arquivos PDF grandes.  
- **Gerenciamento de Memória Java**: Use estruturas de dados eficientes e práticas de coleta de lixo para gerenciar a memória de forma eficaz.  
- **Processamento em Lote**: Ao renderizar vários documentos, processe-os em lotes para melhorar o rendimento.

## Conclusão

Agora você dominou **como desativar o agrupamento** durante a renderização de PDF com o GroupDocs.Viewer para Java. Essa capacidade é crucial para aplicações que exigem representação precisa do texto. Para explorar mais, tente integrar esse recurso com outros sistemas de gerenciamento de documentos ou experimente opções de renderização adicionais.

Os próximos passos incluem explorar recursos mais avançados do GroupDocs.Viewer e ajustar o desempenho para implantações em grande escala.

## Perguntas Frequentes

**Q:** *Por que eu precisaria desativar o agrupamento de caracteres?*  
**A:** Desativar o agrupamento impede que o renderizador mescle caracteres que pertencem a glifos distintos, o que é essencial para scripts onde o espaçamento e a ordem transmitem significado.

**Q:** *A configuração `setDisableCharsGrouping` se aplica apenas à saída HTML?*  
**A:** Não, ela afeta o mecanismo subjacente de renderização de PDF, portanto qualquer formato de saída (HTML, PNG, etc.) refletirá a alteração.

**Q:** *Posso combinar essa configuração com fontes personalizadas?*  
**A:** Sim—basta carregar suas fontes personalizadas antes de inicializar o `Viewer`, e a regra de agrupamento ainda será aplicada.

**Q:** *Desativar o agrupamento impacta o desempenho?*  
**A:** Um pouco, pois o mecanismo processa cada caractere individualmente, mas o impacto é mínimo para a maioria dos documentos.

**Q:** *Existe uma forma de alternar o agrupamento por página?*  
**A:** Atualmente a opção é global por instância de `PdfOptions`; seria necessário criar instâncias separadas de `Viewer` para páginas diferentes.

## Recursos
- [Documentação do GroupDocs](https://docs.groupdocs.com/viewer/java/)
- [Referência da API](https://reference.groupdocs.com/viewer/java/)
- [Baixar GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Comprar Licença](https://purchase.groupdocs.com/buy)
- [Versão de Teste Gratuita](https://releases.groupdocs.com/viewer/java/)
- [Aplicação de Licença Temporária](https://purchase.groupdocs.com/temporary-license/)
- [Fórum de Suporte do GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Última Atualização:** 2025-12-21  
**Testado com:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs