---
title: Adicionar marca d'água no documento
linktitle: Adicionar marca d'água no documento
second_title: API GroupDocs.Viewer .NET
description: Aprenda como adicionar marcas d’água a documentos de maneira simples usando GroupDocs.Viewer for .NET. Melhore a segurança e a marca dos documentos com este tutorial fácil de seguir.
weight: 10
url: /pt/net/rendering-options/add-watermark/
---

# Adicionar marca d'água no documento

## Introdução
Na era digital de hoje, gerenciar e visualizar vários formatos de documentos de forma integrada é uma necessidade para muitas empresas e indivíduos. Felizmente, com ferramentas como GroupDocs.Viewer for .NET, o manuseio de documentos se torna muito fácil. Essa poderosa biblioteca .NET permite que os desenvolvedores integrem facilmente a funcionalidade de visualização de documentos em seus aplicativos, permitindo que os usuários visualizem documentos sem precisar do software original que os criou.
## Pré-requisitos
Antes de começar a usar o GroupDocs.Viewer for .NET para adicionar marcas d’água a documentos, certifique-se de ter o seguinte:
1. Configuração do ambiente: tenha um ambiente de desenvolvimento configurado com .NET Framework ou .NET Core instalado.
2.  GroupDocs.Viewer for .NET: Baixe e instale a biblioteca GroupDocs.Viewer for .NET do[página de download](https://releases.groupdocs.com/viewer/net/).
3. Arquivos de documentos: Prepare os arquivos de documentos com os quais deseja trabalhar, como DOCX, PDF ou outros.
4. Conhecimento básico de C#: É necessária familiaridade com a linguagem de programação C# para implementar os exemplos de código.

## Importar namespaces
Antes de começar a adicionar marcas d'água a documentos usando GroupDocs.Viewer for .NET, certifique-se de importar os namespaces necessários em seu código C#. Esta etapa permite que você acesse perfeitamente as classes e métodos fornecidos pela biblioteca.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Agora, vamos percorrer o processo de adição de uma marca d'água a um documento usando GroupDocs.Viewer for .NET. Siga estas etapas para integrar perfeitamente a funcionalidade de marca d'água ao seu aplicativo.
## Etapa 1: definir o diretório de saída
```csharp
string outputDirectory = "Your Document Directory";
```
Especifique o diretório onde deseja que os arquivos de saída sejam salvos após aplicar a marca d'água.
## Etapa 2: definir o formato do caminho do arquivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Defina o formato dos caminhos de arquivo das páginas renderizadas. Neste exemplo, serão gerados arquivos HTML com números de página.
## Etapa 3: instanciar o objeto visualizador
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // O código continua na próxima etapa...
}
```
Crie uma instância da classe Viewer, passando como parâmetro o caminho do arquivo do documento. Neste exemplo, estamos usando um arquivo DOCX de amostra.
## Etapa 4: configurar opções de visualização HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Configure as opções de visualização HTML, incluindo o texto da marca d'água que você deseja adicionar ao documento.
## Etapa 5: visualizar documento com marca d'água
```csharp
viewer.View(options);
```
Invoque o método View do objeto Viewer, passando as opções configuradas. Isso renderizará o documento com a marca d'água especificada.
## Etapa 6: Exibir caminho do diretório de saída
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informa o usuário sobre a renderização bem-sucedida do documento e indica o diretório onde os arquivos de saída são salvos.

## Conclusão
GroupDocs.Viewer for .NET fornece uma maneira conveniente de adicionar marcas d'água a documentos de forma programática. Seguindo as etapas descritas neste tutorial, você pode integrar perfeitamente a funcionalidade de marca d'água em seus aplicativos .NET, melhorando a segurança e a marca dos documentos.
## Perguntas frequentes
### Posso personalizar a aparência da marca d'água?
Sim, você pode personalizar várias propriedades da marca d’água, como texto, fonte, cor, tamanho e posição.
### O GroupDocs.Viewer oferece suporte à visualização de documentos de fontes remotas?
Sim, GroupDocs.Viewer oferece suporte à visualização de documentos de armazenamento local, bem como de URLs remotos.
### Existe uma versão de teste disponível para GroupDocs.Viewer for .NET?
Sim, você pode baixar uma versão de avaliação gratuita em[aqui](https://releases.groupdocs.com/).
### Posso adicionar marcas d'água a várias páginas de um documento?
Com certeza, GroupDocs.Viewer permite adicionar marcas d’água a páginas individuais ou a todas as páginas de um documento.
### Como posso obter suporte ou assistência se encontrar algum problema?
 Você pode buscar ajuda e suporte nos fóruns da comunidade GroupDocs[aqui](https://forum.groupdocs.com/c/viewer/9).