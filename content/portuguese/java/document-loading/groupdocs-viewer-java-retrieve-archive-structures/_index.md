---
date: '2026-02-05'
description: Aprenda como obter viewinfo e recuperar estruturas de tipos de arquivos
  Java archive usando o GroupDocs.Viewer. Este guia cobre a configuração, exemplos
  de código e casos de uso do mundo real.
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: Como obter ViewInfo e recuperar estruturas de arquivo em Java
type: docs
url: /pt/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Como Obter ViewInfo e Recuperar Estruturas de Arquivo em Java

Gerenciar arquivos de arquivo de forma eficaz requer uma compreensão clara de sua estrutura. Neste tutorial, você aprenderá **como obter viewinfo** para qualquer arquivo e verá como isso ajuda a trabalhar com o **tipo de arquivo java archive**. Percorreremos a configuração do GroupDocs.Viewer, a extração de informações de visualização e a leitura recursiva das hierarquias de pastas para que você possa integrar a solução em projetos reais.

![Estruturas de Arquivo com GroupDocs.Viewer para Java](/viewer/document-loading/archive-structures-java.png)

**O que você aprenderá**
- Configurar e configurar o GroupDocs.Viewer para Java.  
- Métodos para **obter viewinfo** de arquivos.  
- Técnicas para ler e exibir a estrutura de pastas de um arquivo de arquivo.  
- Aplicações práticas e considerações de desempenho ao usar o GroupDocs.Viewer em projetos Java.

## Respostas Rápidas
- **O que o “viewinfo” fornece?** Ele retorna o tipo de arquivo, a contagem de páginas e a lista de pastas do arquivo.  
- **Quais arquivos são suportados?** ZIP, RAR, TAR e outros formatos comuns.  
- **Preciso de uma licença?** Uma avaliação gratuita funciona para teste; uma licença comercial é necessária para produção.  
- **Posso processar arquivos grandes?** Sim – use streaming e gerenciamento adequado de memória conforme mostrado mais adiante.  
- **O Maven é obrigatório?** O Maven é a forma recomendada de gerenciar a dependência do GroupDocs.Viewer.

## O que é “como obter viewinfo”?
`getViewInfo` é um método na API do GroupDocs.Viewer que extrai metadados sobre um documento ou arquivo sem renderizar o conteúdo completo. Para arquivos, ele revela a árvore de pastas interna, permitindo que você decida quais partes renderizar ou processar posteriormente.

## Por que Recuperar Estruturas de Tipo de Arquivo Java?
Entender o layout interno de um **java archive file type** (por exemplo, ZIP, RAR) permite que você:
- Localize rapidamente os arquivos necessários sem extrair tudo.  
- Construa pipelines automatizados que processam apenas sub‑pastas relevantes.  
- Integre a navegação de arquivos em sistemas de gerenciamento de conteúdo ou ingestão de dados.

## Pré-requisitos

- **Java Development Kit (JDK):** Versão 8 ou superior.  
- **Maven:** Para gerenciamento de dependências e builds.  
- **Conhecimento básico de Java:** Familiaridade com conceitos de POO ajuda, mas não é obrigatório.

Você também precisa de acesso à biblioteca GroupDocs.Viewer, que pode adicionar ao seu projeto Maven como mostrado abaixo.

## Configurando o GroupDocs.Viewer para Java

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

Esta seção mostra os passos exatos para chamar `getViewInfo` e ler a hierarquia de pastas.

#### Inicializar o Viewer

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Recuperar Informações de Visualização

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Exibir Estrutura de Pastas

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Leitura Recursiva de Pastas

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

Este recurso foca em imprimir a estrutura de pastas de um arquivo de arquivo. É semelhante ao primeiro recurso, mas enfatiza a exploração recursiva.

#### Configurar Opções de ViewInfo

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Exploração Recursiva

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Aplicações Práticas

1. **Gerenciamento de Dados:** Organize rapidamente grandes conjuntos de dados entendendo as estruturas de arquivos.  
2. **Processamento Automatizado de Arquivos:** Processar em lote arquivos arquivados sem extraí‑los completamente.  
3. **Integração CMS:** Aprimore sistemas de gerenciamento de conteúdo com navegação de arquivos em tempo real.

## Considerações de Desempenho

- **Otimizar Uso de Memória:** Processar pastas um nível de cada vez e fechar a instância `Viewer` prontamente.  
- **Manter Atualizado:** Use a versão mais recente do GroupDocs.Viewer e as releases do JDK para ganhos de desempenho.

## Problemas Comuns e Soluções

| Problema | Por que acontece | Correção |
|----------|------------------|----------|
| `NullPointerException` ao ler pastas | `viewInfo.getFolders()` retorna null para diretórios vazios | Verifique se é null ou lista vazia antes de iterar. |
| Processamento lento de arquivos ZIP enormes | Todo o arquivo é carregado na memória | Use opções de streaming disponíveis nas versões mais recentes do GroupDocs. |
| Licença não encontrada | Caminho do arquivo de licença está incorreto | Coloque o arquivo de licença na raiz da aplicação ou defina `License.setLicense("path/to/license.json")`. |

## Perguntas Frequentes

**Q: O que é o GroupDocs.Viewer?**  
A: É uma poderosa biblioteca Java para renderizar documentos, incluindo arquivos, em formatos como HTML, imagem e PDF.

**Q: Posso usar o GroupDocs.Viewer com outras linguagens de programação?**  
A: Sim, a GroupDocs oferece SDKs para várias plataformas, mas este tutorial foca na implementação Java.

**Q: Como lidar com arquivos de arquivo grandes?**  
A: Use práticas eficientes de gerenciamento de memória e considere dividir os arquivos se necessário.

**Q: Quais tipos de arquivos o GroupDocs.Viewer suporta?**  
A: Ele suporta uma variedade de formatos, incluindo ZIP, RAR, TAR, entre outros.

**Q: Existe um limite para o tamanho dos arquivos que posso processar?**  
A: Os limites dependem dos recursos do seu sistema. Teste no seu ambiente alvo para determinar limites práticos.

**Q: “Como obter viewinfo” funciona com arquivos protegidos por senha?**  
A: Sim, você pode fornecer a senha via `ArchiveOptions.setPassword("yourPassword")` antes de chamar `getViewInfo`.

## Conclusão

Seguindo este guia, você agora sabe **como obter viewinfo** para qualquer arquivo suportado e como percorrer sua hierarquia de pastas usando o GroupDocs.Viewer para Java. Essas técnicas permitem que você construa pipelines de processamento de dados mais inteligentes, melhore integrações CMS e manipule grandes coleções de arquivos arquivados com confiança. Em seguida, explore a renderização de arquivos individuais do arquivo ou a conversão para PDF/HTML usando outros recursos do Viewer.

---

**Última Atualização:** 2026-02-05  
**Testado com:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs  

**Recursos**
- **Documentação:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Referência da API:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **Download do GroupDocs.Viewer:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Comprar Licença:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Teste Gratuito e Licença Temporária:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)