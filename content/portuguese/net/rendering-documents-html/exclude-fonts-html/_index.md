---
title: Excluir fontes do HTML renderizado
linktitle: Excluir fontes do HTML renderizado
second_title: API GroupDocs.Viewer .NET
description: Aprenda como excluir fontes de HTML renderizado usando GroupDocs.Viewer for .NET. Siga este guia passo a passo para uma exibição perfeita de documentos.
weight: 10
url: /pt/net/rendering-documents-html/exclude-fonts-html/
---
## Introdução
GroupDocs.Viewer for .NET é uma poderosa biblioteca de renderização de documentos que permite aos desenvolvedores exibir mais de 50 formatos de documentos em seus aplicativos .NET sem a necessidade de dependências externas. Neste tutorial, vamos nos concentrar em um recurso específico do GroupDocs.Viewer: excluir fontes da saída HTML renderizada. 
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
1. Compreensão básica do desenvolvimento em C# e .NET.
2.  GroupDocs.Viewer para .NET instalado. Você pode baixá-lo em[aqui](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio ou qualquer outro IDE para desenvolvimento em C#.

## Importar namespaces
No seu código C#, certifique-se de incluir os namespaces necessários:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Etapa 1: definir o diretório de saída
Configure o diretório onde deseja que os arquivos HTML renderizados sejam salvos.
```csharp
string outputDirectory = "Your Document Directory";
```
## Etapa 2: definir o formato do caminho do arquivo de página
Especifique o formato dos caminhos de arquivo de páginas individuais do documento renderizado.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Etapa 3: inicializar o objeto visualizador
Instancie o objeto Viewer com o documento que você deseja renderizar.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Seu código vai aqui
}
```
## Etapa 4: definir opções de visualização HTML
Defina as opções de renderização HTML, incluindo o formato dos recursos incorporados e das fontes a serem excluídas.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Etapa 5: renderizar documento
Passe as opções de visualização HTML para o objeto Viewer para renderizar o documento.
```csharp
viewer.View(options);
```
## Etapa 6: localização do documento renderizado de saída
Informe ao usuário o local onde os arquivos HTML renderizados são salvos.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusão
Neste tutorial, aprendemos como usar GroupDocs.Viewer for .NET para excluir fontes da saída HTML renderizada. Seguindo as etapas descritas acima, você pode personalizar o processo de renderização para atender às suas necessidades específicas, garantindo a exibição ideal dos documentos em seus aplicativos.
## Perguntas frequentes
### Posso excluir várias fontes do HTML renderizado?
 Sim, você pode adicionar vários nomes de fontes ao`FontsToExclude` lista nas opções de visualização HTML.
### O GroupDocs.Viewer é compatível com todos os frameworks .NET?
Sim, GroupDocs.Viewer oferece suporte a .NET Framework 4.6.1 e superior.
### Posso renderizar documentos de locais de armazenamento remotos?
Sim, GroupDocs.Viewer oferece suporte à renderização de documentos de armazenamento local, bem como de locais e fluxos de armazenamento remoto.
### O GroupDocs.Viewer oferece suporte a design responsivo para saída HTML?
Sim, você pode ativar a renderização responsiva ajustando as opções de visualização HTML de acordo.
### O suporte técnico está disponível para GroupDocs.Viewer?
 Sim, você pode procurar assistência e participar de discussões sobre o[Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).