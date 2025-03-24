---
title: Substituir fonte ausente
linktitle: Substituir fonte ausente
second_title: API GroupDocs.Viewer .NET
description: Aprenda como substituir fontes ausentes em documentos .NET sem esforço usando GroupDocs.Viewer. Garanta uma renderização precisa com etapas simples.
weight: 20
url: /pt/net/rendering-options/replace-missing-font/
---

# Substituir fonte ausente

## Introdução
No mundo do desenvolvimento .NET, o manuseio eficiente de documentos é crucial. GroupDocs.Viewer for .NET fornece uma solução poderosa para visualizar vários formatos de documentos em seus aplicativos .NET. Neste tutorial, exploraremos como usar GroupDocs.Viewer for .NET para substituir fontes ausentes em documentos. Esteja você lidando com PDFs, apresentações em PowerPoint ou documentos do Word, o GroupDocs.Viewer simplifica o processo, garantindo que seus documentos sejam renderizados com precisão, mesmo quando faltam fontes.
## Pré-requisitos
Antes de mergulhar neste tutorial, certifique-se de ter o seguinte:
1. GroupDocs.Viewer para .NET: Baixe e instale a biblioteca GroupDocs.Viewer do site](https://releases.groupdocs.com/viewer/net/).
2. Ambiente de desenvolvimento: configure um ambiente de desenvolvimento .NET, como o Visual Studio.
3. Conhecimento básico de C#: Familiaridade com a linguagem de programação C# e o framework .NET.

## Importar namespaces
Em seu código C#, importe os namespaces necessários para acessar as funcionalidades do GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Agora, vamos percorrer o processo de substituição de fontes ausentes em documentos usando GroupDocs.Viewer for .NET.
## Etapa 1: definir o diretório de saída
```csharp
string outputDirectory = "Your Document Directory";
```
Defina o diretório onde as páginas do documento renderizado serão salvas.
## Etapa 2: definir o formato do caminho do arquivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Especifique o formato para nomear os arquivos HTML de saída. Neste exemplo, cada página será salva como um arquivo HTML com a convenção de nomenclatura "página_{page_number}.html".
## Etapa 3: inicializar o objeto visualizador
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Inicialize uma nova instância da classe Viewer, passando o caminho para o arquivo do documento (neste caso, uma apresentação do PowerPoint sem fontes) como parâmetro.
## Etapa 4: definir opções de visualização HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
Crie uma instância de HtmlViewOptions e configure-a para incorporar recursos na saída HTML. Especifique um nome de fonte padrão para usar como substituto de fontes ausentes.
## Etapa 5: renderizar documento
```csharp
viewer.View(options);
```
Invoque o método View do objeto Viewer, passando as opções de visualização HTML. Isso renderizará as páginas do documento usando as opções especificadas.
## Etapa 6: Exibir caminho de saída
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Imprima uma mensagem indicando a renderização bem-sucedida do documento e forneça o caminho onde os arquivos HTML de saída são salvos.

## Conclusão
Neste tutorial, aprendemos como usar GroupDocs.Viewer for .NET para substituir fontes ausentes em documentos. Seguindo essas etapas, você pode garantir que seus documentos sejam renderizados com precisão, mesmo quando determinadas fontes não estiverem disponíveis. GroupDocs.Viewer simplifica o processo, permitindo que você se concentre na construção de aplicativos .NET robustos sem se preocupar com problemas de compatibilidade de fontes.
## Perguntas frequentes
### O GroupDocs.Viewer pode lidar com outros tipos de problemas relacionados a fontes?
Sim, o GroupDocs.Viewer fornece várias funcionalidades relacionadas a fontes, incluindo substituição e detecção de fontes.
### O GroupDocs.Viewer é compatível com todos os frameworks .NET?
GroupDocs.Viewer oferece suporte a uma ampla variedade de estruturas .NET, incluindo .NET Core e .NET Standard.
### Posso personalizar a substituição de fonte padrão no GroupDocs.Viewer?
Com certeza, você pode especificar qualquer fonte de sua escolha como substituto padrão para fontes ausentes.
### O GroupDocs.Viewer oferece suporte ao processamento em lote de documentos?
Sim, o GroupDocs.Viewer permite processar vários documentos simultaneamente, tornando-o ideal para cenários de processamento em lote.
### Onde posso encontrar mais assistência ou suporte para GroupDocs.Viewer?
 Você pode visitar o fórum GroupDocs.Viewer[aqui](https://forum.groupdocs.com/c/viewer/9) para qualquer assistência ou dúvida de suporte.