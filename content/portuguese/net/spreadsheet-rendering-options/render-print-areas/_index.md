---
title: Renderize áreas de impressão com GroupDocs.Viewer para .NET
linktitle: Renderizar áreas de impressão
second_title: API GroupDocs.Viewer .NET
description: Explore o GroupDocs.Viewer for .NET e renderize facilmente áreas de impressão em vários formatos de documentos. Experimente o teste gratuito agora! #GroupDocs.Viewer
type: docs
weight: 17
url: /pt/net/spreadsheet-rendering-options/render-print-areas/
---
## Introdução
Bem-vindo a este guia completo sobre como aproveitar o GroupDocs.Viewer for .NET para renderizar áreas de impressão em seus documentos. Se você é um desenvolvedor .NET e busca uma solução robusta para renderização de documentos, você está no lugar certo. Neste tutorial, orientaremos você no processo de renderização de áreas de impressão usando GroupDocs.Viewer, garantindo uma experiência perfeita em seus aplicativos.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Conhecimento prático de desenvolvimento em C# e .NET.
-  GroupDocs.Viewer para .NET instalado. Você pode baixá-lo[aqui](https://releases.groupdocs.com/viewer/net/).
- Um documento de amostra (por exemplo, "SAMPLE.XLSX") no diretório de documentos especificado.
## Importar namespaces
Certifique-se de importar os namespaces necessários em seu código C# para uma implementação adequada:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Etapa 1: configurar o diretório de documentos
Comece especificando o diretório de saída das páginas HTML renderizadas:
```csharp
string outputDirectory = "Your Document Directory";
```
## Etapa 2: definir o formato do caminho do arquivo de página
Crie um formato para os caminhos do arquivo de página, combinando o diretório de saída e um espaço reservado para o número da página:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Etapa 3: inicializar GroupDocs.Viewer
Instancie a classe Viewer com o caminho para seu documento de amostra:
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
```
## Etapa 4: configurar opções de visualização HTML
Configure as opções de visualização HTML, especificando o formato do caminho do arquivo de página e habilitando opções para renderizar áreas de impressão:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.SpreadsheetOptions = SpreadsheetOptions.ForRenderingPrintArea();
```
## Etapa 5: renderizar o documento
 Invoque o`View` método para renderizar o documento com as opções especificadas:
```csharp
viewer.View(options);
```
## Etapa 6: exibir mensagem de sucesso
Imprima uma mensagem de sucesso, indicando que o documento de origem foi renderizado com sucesso:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
## Conclusão
Parabéns! Você aprendeu com sucesso como utilizar o GroupDocs.Viewer for .NET para renderizar áreas de impressão em seus documentos. Esta ferramenta poderosa abre novas possibilidades para renderização de documentos em seus aplicativos .NET.
## Perguntas frequentes
### O GroupDocs.Viewer é compatível com diferentes formatos de documentos?
 Sim, GroupDocs.Viewer oferece suporte a uma ampla variedade de formatos de documentos, incluindo PDF, DOCX, XLSX e muito mais. Consulte o[documentação](https://reference.groupdocs.com/viewer/net/) para obter uma lista completa.
### Posso experimentar o GroupDocs.Viewer antes de fazer uma compra?
 Absolutamente! Você pode explorar a ferramenta com uma avaliação gratuita disponível[aqui](https://releases.groupdocs.com/).
### Onde posso encontrar suporte ou procurar assistência para quaisquer problemas?
 Visite a[Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9)para se conectar com a comunidade e obter assistência.
### Existe uma opção de licença temporária disponível?
 Sim, você pode obter uma licença temporária[aqui](https://purchase.groupdocs.com/temporary-license/).
### Onde posso comprar o GroupDocs.Viewer para .NET?
 Você pode fazer sua compra[aqui](https://purchase.groupdocs.com/buy).