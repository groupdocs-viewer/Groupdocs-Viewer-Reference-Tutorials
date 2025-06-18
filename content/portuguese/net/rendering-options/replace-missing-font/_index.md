---
"description": "Aprenda a substituir fontes ausentes em documentos .NET sem esforço usando o GroupDocs.Viewer. Garanta uma renderização precisa com etapas simples."
"linktitle": "Substituir fonte ausente"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Substituir fonte ausente"
"url": "/pt/net/rendering-options/replace-missing-font/"
"weight": 20
---

# Substituir fonte ausente

## Introdução
No mundo do desenvolvimento .NET, o manuseio eficiente de documentos é crucial. O GroupDocs.Viewer para .NET oferece uma solução poderosa para visualizar vários formatos de documentos em seus aplicativos .NET. Neste tutorial, exploraremos como usar o GroupDocs.Viewer para .NET para substituir fontes ausentes em documentos. Seja lidando com PDFs, apresentações do PowerPoint ou documentos do Word, o GroupDocs.Viewer simplifica o processo, garantindo que seus documentos sejam renderizados com precisão, mesmo quando as fontes estão ausentes.
## Pré-requisitos
Antes de começar este tutorial, certifique-se de ter o seguinte:
1. GroupDocs.Viewer para .NET: Baixe e instale a biblioteca GroupDocs.Viewer do site](https://releases.groupdocs.com/viewer/net/).
2. Ambiente de desenvolvimento: configure um ambiente de desenvolvimento .NET, como o Visual Studio.
3. Conhecimento básico de C#: Familiaridade com a linguagem de programação C# e o framework .NET.

## Importar namespaces
No seu código C#, importe os namespaces necessários para acessar as funcionalidades do GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Agora, vamos percorrer o processo de substituição de fontes ausentes em documentos usando o GroupDocs.Viewer para .NET.
## Etapa 1: definir diretório de saída
```csharp
string outputDirectory = "Your Document Directory";
```
Defina o diretório onde as páginas do documento renderizado serão salvas.
## Etapa 2: Definir o formato do caminho do arquivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Especifique o formato para nomear os arquivos HTML de saída. Neste exemplo, cada página será salva como um arquivo HTML com a convenção de nomenclatura "page_{page_number}.html".
## Etapa 3: Inicializar objeto do visualizador
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Inicialize uma nova instância da classe Viewer, passando o caminho para o arquivo do documento (neste caso, uma apresentação do PowerPoint com fontes ausentes) como parâmetro.
## Etapa 4: definir opções de visualização HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
Crie uma instância de HtmlViewOptions e configure-a para incorporar recursos na saída HTML. Especifique um nome de fonte padrão para substituir as fontes ausentes.
## Etapa 5: Renderizar documento
```csharp
viewer.View(options);
```
Invoque o método View do objeto Viewer, passando as opções de visualização HTML. Isso renderizará as páginas do documento usando as opções especificadas.
## Etapa 6: Exibir caminho de saída
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Imprima uma mensagem indicando a renderização bem-sucedida do documento e forneça o caminho onde os arquivos HTML de saída foram salvos.

## Conclusão
Neste tutorial, aprendemos como usar o GroupDocs.Viewer para .NET para substituir fontes ausentes em documentos. Seguindo esses passos, você garante que seus documentos sejam renderizados com precisão, mesmo quando determinadas fontes não estiverem disponíveis. O GroupDocs.Viewer simplifica o processo, permitindo que você se concentre na criação de aplicativos .NET robustos sem se preocupar com problemas de compatibilidade de fontes.
## Perguntas frequentes
### O GroupDocs.Viewer pode lidar com outros tipos de problemas relacionados a fontes?
Sim, o GroupDocs.Viewer fornece várias funcionalidades relacionadas a fontes, incluindo substituição e detecção de fontes.
### O GroupDocs.Viewer é compatível com todos os frameworks .NET?
GroupDocs.Viewer oferece suporte a uma ampla variedade de frameworks .NET, incluindo .NET Core e .NET Standard.
### Posso personalizar a substituição de fonte padrão no GroupDocs.Viewer?
Claro, você pode especificar qualquer fonte de sua escolha como a substituição padrão para fontes ausentes.
### O GroupDocs.Viewer suporta processamento em lote de documentos?
Sim, o GroupDocs.Viewer permite processar vários documentos simultaneamente, tornando-o ideal para cenários de processamento em lote.
### Onde posso encontrar mais assistência ou suporte para o GroupDocs.Viewer?
Você pode visitar o fórum GroupDocs.Viewer [aqui](https://forum.groupdocs.com/c/viewer/9) para qualquer assistência ou consulta de suporte.