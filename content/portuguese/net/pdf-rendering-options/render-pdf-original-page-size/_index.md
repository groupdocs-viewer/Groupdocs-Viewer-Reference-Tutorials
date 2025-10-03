---
"description": "Aprenda a renderizar PDFs com tamanhos de página originais usando o GroupDocs.Viewer para .NET. Siga nosso guia passo a passo e integre essa funcionalidade perfeitamente."
"linktitle": "Renderizar PDF com tamanho de página original"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Renderizar PDF com tamanho de página original"
"url": "/pt/net/pdf-rendering-options/render-pdf-original-page-size/"
"weight": 17
type: docs
---
# Renderizar PDF com tamanho de página original

## Introdução
No âmbito do desenvolvimento .NET, o GroupDocs.Viewer se destaca como uma ferramenta poderosa para renderizar diversos formatos de documentos, incluindo PDFs. Um requisito comum no processamento de documentos é renderizar PDFs preservando seus tamanhos de página originais. Para realizar essa tarefa com perfeição, é necessário um conhecimento abrangente do GroupDocs.Viewer para .NET e suas funcionalidades.

![Renderizar PDF com tamanho de página original com GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/render-pdf-with-original-page-size.png)

## Pré-requisitos
Antes de começar a renderizar PDFs com tamanhos de página originais usando o GroupDocs.Viewer para .NET, certifique-se de ter os seguintes pré-requisitos:
### 1. Instale o GroupDocs.Viewer para .NET
Comece baixando a biblioteca GroupDocs.Viewer do site. Você pode obter a biblioteca no site fornecido [link para download](https://releases.groupdocs.com/viewer/net/). Siga as instruções de instalação fornecidas na documentação para integrá-lo ao seu projeto .NET de forma eficaz.
### 2. Configurar ambiente de desenvolvimento
Certifique-se de ter um ambiente de desenvolvimento configurado para desenvolvimento .NET. Isso inclui ter um IDE compatível instalado, como o Visual Studio, e um conhecimento básico de programação em C#.
### 3. Obtenha um documento PDF
Você precisará de um documento PDF de exemplo para renderizar com o GroupDocs.Viewer. Você pode usar qualquer documento PDF para fins de teste. Caso não tenha um, você pode baixar um PDF de exemplo de várias fontes online.

## Importar namespaces
Antes de prosseguir com a renderização de PDFs, é essencial importar os namespaces necessários para o seu projeto C#. Esta etapa permite que você acesse as classes e métodos necessários da biblioteca GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Agora que você tem os pré-requisitos definidos e os namespaces necessários importados, vamos dividir o processo de renderização de PDFs com tamanhos de página originais usando o GroupDocs.Viewer para .NET em etapas simples:
## Etapa 1: definir diretório de saída
```csharp
string outputDirectory = "Your Document Directory";
```
Certifique-se de especificar o diretório onde deseja que as páginas renderizadas sejam salvas. Substituir `"Your Document Directory"` com o caminho do diretório desejado.
## Etapa 2: Definir o formato do caminho do arquivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Configure o formato para nomear os arquivos de página renderizados. Neste exemplo, as páginas serão salvas como imagens PNG com nomes de arquivo no formato `"page_1.png"`, `"page_2.png"`, e assim por diante.
## Etapa 3: renderizar PDF com tamanho de página original
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
Instanciar um `Viewer` objeto com o caminho para o seu arquivo PDF. Em seguida, crie `PngViewOptions` com o formato de caminho de arquivo de página especificado. Definir `RenderOriginalPageSize` propriedade para `true` para preservar os tamanhos originais das páginas durante a renderização.
## Etapa 4: Exibir a localização do documento renderizado
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Imprima uma mensagem indicando a renderização bem-sucedida e forneça o diretório onde as páginas renderizadas foram salvas.

## Conclusão
Renderizar PDFs com os tamanhos de página originais usando o GroupDocs.Viewer para .NET é um processo simples se você seguir os passos descritos neste tutorial. Importando os namespaces necessários e seguindo o guia passo a passo, você pode integrar essa funcionalidade perfeitamente aos seus aplicativos .NET.
## Perguntas frequentes
### O GroupDocs.Viewer pode renderizar outros formatos de documento além de PDF?
Sim, o GroupDocs.Viewer suporta renderização de vários formatos de documentos, incluindo Word, Excel, PowerPoint e muito mais.
### O GroupDocs.Viewer é compatível com o .NET Core?
Sim, o GroupDocs.Viewer é compatível com ambientes .NET Framework e .NET Core.
### Posso personalizar o formato de saída das páginas renderizadas?
Sim, você pode personalizar o formato de saída ajustando as opções fornecidas pelo GroupDocs.Viewer, como definir diferentes formatos de imagem ou especificar opções de renderização personalizadas.
### O GroupDocs.Viewer oferece suporte para renderização de documentos baseada em nuvem?
Sim, o GroupDocs.Viewer fornece APIs para renderização de documentos baseada em nuvem, permitindo que você renderize documentos diretamente de provedores de armazenamento em nuvem.
### Existe um teste gratuito disponível para o GroupDocs.Viewer?
Sim, você pode explorar o GroupDocs.Viewer com um teste gratuito visitando o site fornecido [link](https://releases.groupdocs.com/).