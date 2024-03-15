---
title: Renderizar PDF com tamanho de página original
linktitle: Renderizar PDF com tamanho de página original
second_title: API GroupDocs.Viewer .NET
description: Aprenda como renderizar PDFs com tamanhos de página originais usando GroupDocs.Viewer for .NET. Siga nosso guia passo a passo e integre perfeitamente essa funcionalidade.
type: docs
weight: 17
url: /pt/net/pdf-rendering-options/render-pdf-original-page-size/
---
## Introdução
No domínio do desenvolvimento .NET, GroupDocs.Viewer se destaca como uma ferramenta poderosa para renderizar vários formatos de documentos, incluindo PDFs. Um requisito comum no manuseio de documentos é renderizar PDFs preservando seus tamanhos de página originais. Realizar essa tarefa perfeitamente requer uma compreensão abrangente do GroupDocs.Viewer for .NET e de suas funcionalidades.
## Pré-requisitos
Antes de mergulhar na renderização de PDFs com tamanhos de página originais usando GroupDocs.Viewer for .NET, certifique-se de ter os seguintes pré-requisitos em vigor:
### 1. Instale GroupDocs.Viewer para .NET
 Comece baixando a biblioteca GroupDocs.Viewer do site. Você pode obter a biblioteca no site fornecido[Link para Download](https://releases.groupdocs.com/viewer/net/). Siga as instruções de instalação fornecidas na documentação para integrá-lo de forma eficaz ao seu projeto .NET.
### 2. Configurar ambiente de desenvolvimento
Certifique-se de ter um ambiente de desenvolvimento configurado para desenvolvimento .NET. Isso inclui ter um IDE compatível instalado, como o Visual Studio, e um conhecimento básico de programação C#.
### 3. Obtenha um documento PDF
Você precisará de um documento PDF de amostra para renderizar com GroupDocs.Viewer. Você pode usar qualquer documento PDF para fins de teste. Se não tiver um, você pode baixar um PDF de amostra de várias fontes online.

## Importar namespaces
Antes de prosseguir com a renderização de PDFs, é essencial importar os namespaces necessários para o seu projeto C#. Esta etapa permite acessar as classes e métodos necessários da biblioteca GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Agora que você tem os pré-requisitos implementados e os namespaces necessários importados, vamos dividir o processo de renderização de PDFs com tamanhos de página originais usando GroupDocs.Viewer for .NET em etapas simples:
## Etapa 1: definir o diretório de saída
```csharp
string outputDirectory = "Your Document Directory";
```
 Certifique-se de especificar o diretório onde deseja que as páginas renderizadas sejam salvas. Substituir`"Your Document Directory"` com o caminho do diretório desejado.
## Etapa 2: definir o formato do caminho do arquivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Configure o formato para nomear os arquivos de página renderizados. Neste exemplo, as páginas serão salvas como imagens PNG com nomes de arquivos no formato`"page_1.png"`, `"page_2.png"`, e assim por diante.
## Passo 3: Renderizar PDF com tamanho de página original
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
 Instanciar um`Viewer` objeto com o caminho para o seu arquivo PDF. Então, crie`PngViewOptions` com o formato de caminho de arquivo de página especificado. Definir`RenderOriginalPageSize` propriedade para`true` para preservar os tamanhos de página originais durante a renderização.
## Etapa 4: Exibir localização do documento renderizado
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Imprima uma mensagem indicando a renderização bem-sucedida e forneça o diretório onde as páginas renderizadas são salvas.

## Conclusão
Renderizar PDFs com tamanhos de página originais usando GroupDocs.Viewer for .NET é um processo simples quando você segue as etapas descritas neste tutorial. Ao importar os namespaces necessários e seguir o guia passo a passo, você pode integrar perfeitamente essa funcionalidade aos seus aplicativos .NET.
## Perguntas frequentes
### O GroupDocs.Viewer pode renderizar outros formatos de documentos além do PDF?
Sim, GroupDocs.Viewer oferece suporte à renderização de vários formatos de documentos, incluindo Word, Excel, PowerPoint e muito mais.
### O GroupDocs.Viewer é compatível com o .NET Core?
Sim, GroupDocs.Viewer é compatível com ambientes .NET Framework e .NET Core.
### Posso personalizar o formato de saída das páginas renderizadas?
Sim, você pode personalizar o formato de saída ajustando as opções fornecidas pelo GroupDocs.Viewer, como definir diferentes formatos de imagem ou especificar opções de renderização personalizadas.
### O GroupDocs.Viewer oferece suporte para renderização de documentos baseada em nuvem?
Sim, o GroupDocs.Viewer fornece APIs para renderização de documentos baseada em nuvem, permitindo renderizar documentos diretamente de provedores de armazenamento em nuvem.
### Existe um teste gratuito disponível para GroupDocs.Viewer?
 Sim, você pode explorar o GroupDocs.Viewer com uma avaliação gratuita visitando o site fornecido[link](https://releases.groupdocs.com/).