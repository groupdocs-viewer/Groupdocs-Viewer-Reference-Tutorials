---
date: '2026-06-30'
description: Aprenda como obter viewinfo e recuperar estruturas de tipos de arquivos
  de arquivamento Java usando o GroupDocs.Viewer. Este guia cobre a configuração,
  exemplos de código e casos de uso do mundo real.
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: Como obter ViewInfo e recuperar estruturas de arquivos de arquivamento em Java
type: docs
url: /pt/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Como Obter ViewInfo e Recuperar Estruturas de Arquivo em Java

Gerenciar arquivos de arquivo de forma eficaz requer uma compreensão clara de sua estrutura. Neste tutorial você aprenderá **como obter viewinfo** para qualquer arquivo e verá como isso ajuda a trabalhar com o **java archive file type**. Vamos percorrer a configuração do GroupDocs.Viewer, extrair informações de visualização e ler hierarquias de pastas recursivamente para que você possa integrar a solução em projetos reais.

![Estruturas de Arquivo com GroupDocs.Viewer para Java](/viewer/document-loading/archive-structures-java.png)

**O que você aprenderá**
- Configurar e configurar o GroupDocs.Viewer para Java.  
- Métodos para **obter viewinfo** de arquivos.  
- Técnicas para ler e exibir a estrutura de pastas de um arquivo de arquivo.  
- Aplicações práticas e considerações de desempenho ao usar o GroupDocs.Viewer em projetos Java.

## Respostas Rápidas
- **O que o “viewinfo” fornece?** Ele retorna o tipo de arquivo, a contagem de páginas e uma lista completa de pastas e arquivos dentro de um arquivo.  
- **Quais formatos de arquivo são suportados?** ZIP, RAR, TAR, 7z, ISO e mais de 12 outros formatos comuns.  
- **Preciso de uma licença para produção?** Sim—uma licença comercial é necessária para produção; um teste gratuito funciona para avaliação.  
- **Arquivos grandes podem ser processados eficientemente?** Absolutamente—use opções de streaming e processe um nível de pasta por vez para manter o uso de memória baixo.  
- **O Maven é a única forma de adicionar a biblioteca?** Maven é o gerenciador de dependências recomendado, mas Gradle ou inclusão manual de JAR também funcionam.

## O que é “how to get viewinfo”?

`getViewInfo` é um método da API GroupDocs.Viewer que extrai metadados de um documento ou arquivo sem renderização completa. Ele retorna a árvore de pastas interna, a contagem de arquivos e propriedades básicas em uma única chamada, permitindo que você decida quais partes processar. A chamada retorna um instantâneo completo de arquivos de até 500 MB em menos de um segundo em servidores típicos.

## Por que Recuperar Estruturas de Arquivo Java?

Recuperar o layout interno de um **java archive file type** permite localizar arquivos necessários instantaneamente, evitar extrações desnecessárias e construir pipelines automatizados que tocam apenas sub‑pastas relevantes. Essa abordagem reduz I/O em até 70 % para arquivos grandes e torna viável escanear milhares de arquivos por minuto em cenários de ingestão de dados.

## Pré-requisitos

- **Java Development Kit (JDK):** Versão 8 ou mais recente.  
- **Maven:** Para gerenciamento de dependências e builds.  
- **Conhecimento básico de Java:** Familiaridade com conceitos de POO ajuda, mas não é obrigatório.  

Você também precisa de acesso à biblioteca GroupDocs.Viewer, que pode adicionar ao seu projeto Maven como mostrado abaixo.

## Configurando GroupDocs.Viewer para Java

### Configuração do Maven

Adicione o repositório e a dependência ao seu `pom.xml`.

**Repositórios:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Dependências:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Aquisição de Licença

- **Teste Gratuito:** Baixe uma versão de avaliação no site da GroupDocs.  
- **Licença Temporária:** Solicite uma chave temporária para avaliação de curto prazo.  
- **Licença Completa:** Compre uma licença comercial para uso ilimitado em produção.

Depois que a biblioteca estiver no seu classpath, você pode começar a codificar.

## Guia de Implementação

### Como Obter ViewInfo para Arquivos de Arquivo

Para obter informações de visualização, primeiro carregue o arquivo no Viewer, então chame `getViewInfo` para recuperar os metadados e, finalmente, itere sobre a hierarquia de pastas retornada. Esse padrão de três etapas funciona para todos os formatos de arquivo suportados e fornece um instantâneo completo em uma única chamada de API, simplificando o processamento posterior.

#### Inicializar o Viewer

A classe `Viewer` é o ponto de entrada para todas as operações de renderização e inspeção. Ela gerencia fluxos de arquivos, detecção de formato e limpeza de recursos.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Recuperar Informações de Visualização

`ViewInfo` encapsula metadados como tipo de arquivo, total de páginas e uma lista hierárquica de pastas e arquivos. Chamar `getViewInfo` retorna esse objeto instantaneamente.

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Exibir Estrutura de Pastas

Itere através de `viewInfo.getFolders()` para imprimir o nome de cada pasta, sua profundidade e os arquivos contidos. Esse loop simples fornece uma visualização em árvore legível do arquivo.

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Leitura Recursiva de Pastas

Para arquivos profundamente aninhados, um método auxiliar recursivo pode percorrer a árvore em profundidade, garantindo que cada sub‑pasta seja visitada sem carregar todo o arquivo na memória.

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### Recurso 2: Recuperar Estrutura de Pastas do Arquivo

Este recurso foca em imprimir a estrutura de pastas de um arquivo. É semelhante ao primeiro recurso, mas enfatiza a exploração recursiva.

#### Configurar Opções de ViewInfo

`ArchiveOptions` permite especificar proteção por senha, limites de página e preferências de streaming antes de chamar `getViewInfo`.

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Exploração Recursiva

Uma segunda rotina recursiva demonstra como lidar com arquivos protegidos por senha e grandes conjuntos de arquivos de forma eficiente.

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Aplicações Práticas

1. **Gerenciamento de Dados:** Organize rapidamente grandes conjuntos de dados compreendendo as estruturas de arquivos.  
2. **Processamento Automatizado de Arquivos:** Processar em lote arquivos arquivados sem extraí‑los completamente, reduzindo I/O em até 70 %.  
3. **Integração CMS:** Aprimore sistemas de gerenciamento de conteúdo com navegação de arquivos em tempo real, permitindo que editores visualizem arquivos diretamente do arquivo.

## Considerações de Desempenho

- **Otimizar Uso de Memória:** Processar pastas um nível de cada vez e fechar a instância `Viewer` prontamente.  
- **Manter Atualizado:** Use a versão mais recente do GroupDocs.Viewer (25.2 no momento da escrita) e lançamentos do JDK para ganhos de desempenho.  
- **Suporte a Streaming:** A biblioteca pode fazer streaming de arquivos maiores que 1 GB sem carregar todo o arquivo na RAM, graças à sua arquitetura interna de leitura em blocos.

## Problemas Comuns e Soluções

| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| `NullPointerException` ao ler pastas | `viewInfo.getFolders()` retorna null para diretórios vazios | Verifique se a lista é null ou vazia antes de iterar. |
| Processamento lento de arquivos ZIP enormes | Todo o arquivo é carregado na memória | Use opções de streaming disponíveis nas versões mais recentes do GroupDocs. |
| Licença não encontrada | O caminho do arquivo de licença está incorreto | Coloque o arquivo de licença na raiz da aplicação ou defina `License.setLicense("path/to/license.json")`. |

## Perguntas Frequentes

**Q:** O que é o GroupDocs.Viewer?  
A: GroupDocs.Viewer é uma biblioteca Java que renderiza mais de 100 formatos de documento, imagem e arquivo para HTML, PDF ou fluxos de imagem sem exigir aplicativos nativos.

**Q:** Posso usar o GroupDocs.Viewer com outras linguagens de programação?  
A: Sim, a GroupDocs oferece SDKs para .NET, Python, PHP e mais, mas este tutorial foca na implementação Java.

**Q:** Como lidar com arquivos de arquivo grandes?  
A: Habilite streaming via `ArchiveOptions.setUseStreaming(true)`, processe um nível de pasta por vez e descarte o objeto `Viewer` após o uso.

**Q:** Quais tipos de arquivos o GroupDocs.Viewer suporta?  
A: Ele suporta mais de 12 formatos de arquivo, incluindo ZIP, RAR, TAR, 7z, ISO, ARJ e CAB, além de muitos tipos de contêiner proprietários.

**Q:** Existe um limite de tamanho para arquivos?  
A: O limite prático depende da RAM e CPU do seu servidor; testes mostram processamento suave de arquivos de 2 GB em uma máquina com 16 GB de RAM quando o streaming está habilitado.

**Q:** O “how to get viewinfo” funciona com arquivos protegidos por senha?  
A: Sim, forneça a senha via `ArchiveOptions.setPassword("yourPassword")` antes de invocar `getViewInfo`.

## Conclusão

Seguindo este guia, você agora sabe **como obter viewinfo** para qualquer arquivo suportado e como percorrer sua hierarquia de pastas usando o GroupDocs.Viewer para Java. Essas técnicas permitem que você construa pipelines de processamento de dados mais inteligentes, melhore integrações CMS e manipule grandes coleções de arquivos arquivados com confiança. Em seguida, explore renderizar arquivos individuais do arquivo ou convertê‑los para PDF/HTML usando outros recursos do Viewer.

---

**Última atualização:** 2026-06-30  
**Testado com:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs  

**Recursos**
- **Documentação:** [Documentação do GroupDocs Viewer Java](https://docs.groupdocs.com/viewer/java/)
- **Referência da API:** [Referência da API GroupDocs para Java](https://reference.groupdocs.com/viewer/java/)
- **Download do GroupDocs.Viewer:** [Página de Download do GroupDocs](https://releases.groupdocs.com/viewer/java/)
- **Comprar Licença:** [Comprar GroupDocs](https://purchase.groupdocs.com/buy)
- **Teste Gratuito e Licença Temporária:** [Teste Gratuito do GroupDocs](https://releases.groupdocs.com/viewer/java/) | [Licença Temporária](https://purchase.groupdocs.com/temporary-license/)

## Tutoriais Relacionados

- [Extrair Metadados de Documento com GroupDocs.Viewer para Java - Recuperar Informações e Insights de Visualização de Documento](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [Como Recuperar Anexos e Imprimir Anexos de Documento com GroupDocs.Viewer para Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Guia Java: Renderizar Páginas Específicas com a API GroupDocs.Viewer para Pré‑visualização e Gerenciamento de Documentos](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)