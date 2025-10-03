---
"date": "2025-04-25"
"description": "Aprenda a extrair informações de arquivo com eficiência usando o GroupDocs.Viewer para .NET. Este guia aborda configuração, exemplos de código e aplicações práticas."
"title": "Como recuperar informações de arquivo usando o GroupDocs.Viewer para .NET - Um guia completo"
"url": "/pt/net/metadata-properties/groupdocs-viewer-net-retrieve-archive-info/"
"weight": 1
type: docs
---
# Como recuperar informações de arquivo usando o GroupDocs.Viewer para .NET: um guia completo

## Introdução

Você está procurando extrair informações detalhadas de arquivos compactados, como ZIPs, com eficiência? Entender a estrutura pode ser vital para o gerenciamento de documentos. Este guia mostrará como usar **GroupDocs.Viewer para .NET** para recuperar e exibir detalhes abrangentes sobre um arquivo compactado.

![Recuperar informações de arquivo com GroupDocs.Viewer para .NET](/viewer/metadata-properties/retrieve-archive-information.png)

Neste tutorial, abordaremos:
- Configurando GroupDocs.Viewer em seu aplicativo .NET
- Recuperando informações de visualização de arquivos compactados
- Exibindo estruturas de pastas dentro de arquivos

Ao final deste guia, você terá um sólido conhecimento sobre a implementação dessas funcionalidades. Vamos começar com o que você precisa antes de mergulhar no código.

### Pré-requisitos

Certifique-se de ter o seguinte pronto:

- **Bibliotecas e Versões**: Instale o GroupDocs.Viewer para .NET (versão 25.3.0).
- **Configuração do ambiente**: Use um ambiente de desenvolvimento .NET adequado, como o Visual Studio.
- **Pré-requisitos de conhecimento**: Noções básicas de C# e manipulação de arquivos em aplicativos .NET.

## Configurando o GroupDocs.Viewer para .NET

Para usar o GroupDocs.Viewer para .NET, instale-o por meio do Gerenciador de Pacotes NuGet:

### Instruções de instalação

**Console do gerenciador de pacotes NuGet**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**.NET CLI**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Obtenção de uma licença

O GroupDocs.Viewer oferece diversas opções de licenciamento:
- **Teste grátis**Explore funcionalidades básicas.
- **Licença Temporária**: Acesso a todos os recursos durante a avaliação.
- **Comprar**: Para uso a longo prazo, considere comprar uma licença.

Após a instalação e configuração da sua licença, inicialize o GroupDocs.Viewer no seu aplicativo. Veja um exemplo de configuração:

```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS"))
{
    // Use as funcionalidades do Visualizador aqui.
}
```

## Guia de Implementação

Dividiremos a implementação em recursos principais para uma abordagem estruturada.

### Recuperar informações de visualização para arquivos compactados

Entender a estrutura do seu arquivo é crucial. Veja como fazer isso:

#### Inicializar o objeto Viewer

Crie uma instância do `Viewer` classe com o caminho do seu arquivo compactado:

```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS";
using (Viewer viewer = new Viewer(documentPath))
{
    // Seu código para processamento irá aqui.
}
```

#### Obter informações de visualização

Recuperar informações de visualização, formatadas como imagens JPG:

```csharp
ViewInfo info = viewer.GetViewInfo(ViewInfoOptions.ForJpgView());
Console.WriteLine("File type: " + info.FileType);
Console.WriteLine("Pages count: " + info.Pages.Count);
```

#### Exibir informações da pasta raiz

Para uma visão geral abrangente, imprima os detalhes da pasta raiz:

```csharp
Console.WriteLine("Folders:");
Console.WriteLine(" - /");
```

#### Ler e imprimir recursivamente nomes de subpastas

Para explorar subpastas dentro do seu arquivo, use este método recursivo:

```csharp
string rootFolder = string.Empty;
ReadArchiveFolders(viewer, rootFolder);

private static void ReadArchiveFolders(Viewer viewer, string folder)
{
    ViewInfoOptions options = ViewInfoOptions.ForJpgView();
    options.ArchiveOptions.Folder = folder;

    ArchiveViewInfo viewInfo = viewer.GetViewInfo(options) as ArchiveViewInfo;
    foreach (string subFolder in viewInfo.Folders)
    {
        Console.WriteLine($" - {subFolder}");
        ReadArchiveFolders(viewer, subFolder);
    }
}
```

### Aplicações práticas

O GroupDocs.Viewer para .NET pode ser usado em vários cenários:
- **Sistemas de Gestão de Documentos**: Extraia e exiba automaticamente estruturas de arquivo.
- **Plataformas de entrega de conteúdo**: Fornecer visualizações de conteúdo arquivado aos usuários.
- **Ferramentas de análise de dados**: Analise hierarquias de pastas dentro de arquivos para obter insights de negócios.

A integração com outras estruturas como ASP.NET ou WPF é direta, permitindo incorporação perfeita em sistemas existentes.

## Considerações de desempenho

Para um desempenho ideal:
- **Otimize o uso de recursos**: Gerencie a memória com eficiência e lide com arquivos grandes.
- **Melhores práticas de gerenciamento de memória**: Descarte de `Viewer` objetos adequadamente para liberar recursos prontamente.

## Conclusão

Neste tutorial, você aprendeu a utilizar o GroupDocs.Viewer para .NET para recuperar informações detalhadas de arquivos compactados. A implementação desses recursos pode aprimorar significativamente suas capacidades de gerenciamento de documentos.

### Próximos passos

Considere explorar recursos mais avançados oferecidos pelo GroupDocs.Viewer ou integrá-lo a outros componentes do seu aplicativo. Experimente diferentes tipos de arquivo e estruturas de pastas complexas para aprofundar seu conhecimento.

## Seção de perguntas frequentes

1. **Qual é o propósito de `ViewInfoOptions`?**
   - Ele configura como você deseja visualizar um documento, como renderizar formatos específicos como JPG.

2. **Como lidar com arquivos grandes de forma eficiente?**
   - Use técnicas de gerenciamento de memória e descarte os recursos adequadamente.

3. **O GroupDocs.Viewer pode processar arquivos protegidos por senha?**
   - Sim, com a licença e configuração corretas, ele pode manipular documentos criptografados.

4. **Existe um limite para o tamanho do arquivo compactado que pode ser processado?**
   - limite depende da capacidade de memória do seu sistema; arquivos maiores exigem mais recursos.

5. **Como integro o GroupDocs.Viewer com aplicativos ASP.NET?**
   - Use a classe Viewer dentro das ações ou serviços do seu controlador, de forma semelhante a como você faria em um aplicativo de console.

## Recursos

- [Documentação](https://docs.groupdocs.com/viewer/net/)
- [Referência de API](https://reference.groupdocs.com/viewer/net/)
- [Baixe o GroupDocs.Viewer para .NET](https://releases.groupdocs.com/viewer/net/)
- [Comprar uma licença](https://purchase.groupdocs.com/buy)
- [Versão de teste gratuita](https://releases.groupdocs.com/viewer/net/)
- [Pedido de Licença Temporária](https://purchase.groupdocs.com/temporary-license/)
- [Fórum de Suporte](https://forum.groupdocs.com/c/viewer/9)