---
title: Renderizar arquivos em páginas HTML únicas ou múltiplas
linktitle: Renderizar arquivos em páginas HTML únicas ou múltiplas
second_title: API GroupDocs.Viewer .NET
description: Aprenda como renderizar arquivos em páginas HTML usando GroupDocs.Viewer for .NET. Integre facilmente recursos de visualização de documentos aos seus aplicativos .NET.
weight: 12
url: /pt/net/rendering-archive-files/render-archives-html/
---

# Renderizar arquivos em páginas HTML únicas ou múltiplas

## Introdução
GroupDocs.Viewer for .NET é uma poderosa biblioteca de renderização de documentos que permite aos desenvolvedores integrar facilmente recursos de visualização de documentos em seus aplicativos .NET. Se você precisa renderizar arquivos em uma ou várias páginas HTML, este tutorial irá guiá-lo passo a passo pelo processo.
## Pré-requisitos
Antes de mergulhar neste tutorial, certifique-se de ter os seguintes pré-requisitos:
1.  GroupDocs.Viewer for .NET: Certifique-se de ter a biblioteca instalada em seu projeto. Você pode baixá-lo em[aqui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente de desenvolvimento: tenha um ambiente de desenvolvimento funcional configurado para desenvolvimento .NET.
3. Diretório de documentos: Prepare um diretório onde seus documentos serão armazenados.
4. Compreensão básica de C#: Familiarize-se com os fundamentos da linguagem de programação C#.

## Importar namespaces
No seu código C#, certifique-se de importar os namespaces necessários:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Siga estas etapas para renderizar arquivos em uma ou várias páginas HTML usando GroupDocs.Viewer for .NET:
## Etapa 1: definir o diretório de saída
Defina o diretório onde você deseja que as páginas HTML renderizadas sejam salvas:
```csharp
string outputDirectory = "Your Document Directory";
```
## Etapa 2: definir o formato do caminho do arquivo
Especifique o formato do caminho do arquivo para as páginas HTML. Para renderização de página única:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
Para renderização de várias páginas:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## Etapa 3: renderizar em HTML de página única
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## Etapa 4: renderizar HTML em várias páginas
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; // Definir itens por página
    viewer.View(options);
}
```
## Etapa 5: verificar o resultado
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusão
Renderizar arquivos em páginas HTML usando GroupDocs.Viewer for .NET é um processo simples. Seguindo as etapas descritas neste tutorial, você pode integrar perfeitamente recursos de visualização de documentos em seus aplicativos .NET.
## Perguntas frequentes
### Posso renderizar outros formatos de documentos além de arquivos?
Sim, GroupDocs.Viewer oferece suporte a uma ampla variedade de formatos de documentos, incluindo PDF, DOCX, XLSX, PPTX e muito mais.
### O GroupDocs.Viewer é adequado para aplicativos de desktop e web?
Com certeza, o GroupDocs.Viewer pode ser utilizado perfeitamente em aplicativos de desktop e da web.
### O GroupDocs.Viewer oferece opções de personalização para a interface do visualizador?
Sim, você pode personalizar a interface do visualizador de acordo com suas necessidades.
### Posso renderizar documentos de forma assíncrona com GroupDocs.Viewer?
Sim, o GroupDocs.Viewer fornece recursos de renderização assíncrona para melhorar o desempenho.
### O GroupDocs.Viewer oferece suporte a anotações de documentos?
Sim, GroupDocs.Viewer permite aos usuários visualizar e gerenciar anotações de documentos com eficiência.