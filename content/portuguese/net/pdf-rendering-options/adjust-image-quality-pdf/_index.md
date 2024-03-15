---
title: Ajustar a qualidade da imagem em PDF
linktitle: Ajustar a qualidade da imagem em PDF
second_title: API GroupDocs.Viewer .NET
description: Aprenda como ajustar a qualidade da imagem em documentos PDF usando GroupDocs.Viewer for .NET. Siga nosso tutorial passo a passo para uma integração perfeita.
type: docs
weight: 10
url: /pt/net/pdf-rendering-options/adjust-image-quality-pdf/
---
## Introdução
GroupDocs.Viewer for .NET é uma biblioteca poderosa que permite aos desenvolvedores integrar recursos de renderização de documentos em seus aplicativos .NET sem esforço. Um dos principais recursos desta biblioteca é a capacidade de ajustar a qualidade da imagem ao renderizar documentos PDF. Neste tutorial, orientaremos você no processo de ajuste da qualidade da imagem passo a passo usando GroupDocs.Viewer for .NET.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1. Conhecimento básico de programação C#.
2. Visual Studio instalado em seu sistema.
3. Biblioteca GroupDocs.Viewer para .NET baixada e instalada. Você pode baixá-lo em[aqui](https://releases.groupdocs.com/viewer/net/).

## Importar namespaces
Primeiro, você precisa importar os namespaces necessários para trabalhar com GroupDocs.Viewer for .NET:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Etapa 1: definir o diretório de saída
```csharp
string outputDirectory = "Your Document Directory";
```
 Substituir`"Your Document Directory"` com o caminho onde você deseja salvar as páginas HTML renderizadas.
## Etapa 2: definir o formato do caminho do arquivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Esta linha define o formato do caminho do arquivo de cada página HTML renderizada.`{0}` é um espaço reservado para o número da página.
## Etapa 3: ajustar a qualidade da imagem
```csharp
using (Viewer viewer = new Viewer("Your PDF File Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.ImageQuality = ImageQuality.Medium;
    viewer.View(options);
}
```
 Substituir`"Your PDF File Path"` com o caminho para o seu documento PDF.
## Etapa 4: Exibir caminho de saída
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Esta linha exibe o caminho onde as páginas HTML renderizadas são salvas.

## Conclusão
Neste tutorial, aprendemos como ajustar a qualidade da imagem ao renderizar documentos PDF usando GroupDocs.Viewer for .NET. Seguindo as etapas simples descritas acima, você pode personalizar facilmente a qualidade da imagem de acordo com suas necessidades.
## Perguntas frequentes
### Posso ajustar a qualidade da imagem para outros formatos de documento além do PDF?
Sim, o GroupDocs.Viewer for .NET oferece suporte a vários formatos de documento e você pode ajustar a qualidade da imagem para a maioria deles.
### Quais são as opções de qualidade de imagem disponíveis?
GroupDocs.Viewer for .NET oferece opções de qualidade de imagem Baixa, Média e Alta.
### Existe uma maneira de visualizar o documento antes de renderizá-lo com qualidade de imagem ajustada?
Sim, você pode usar o GroupDocs.Viewer for .NET para gerar visualizações de documentos com diferentes configurações de qualidade de imagem.
### O GroupDocs.Viewer for .NET requer uma licença para uso comercial?
 Sim, você precisa obter uma licença para uso comercial. Você pode comprar uma licença de[aqui](https://purchase.groupdocs.com/buy).
### Onde posso obter suporte para GroupDocs.Viewer for .NET?
 Você pode obter suporte no fórum GroupDocs.Viewer[aqui](https://forum.groupdocs.com/c/viewer/9).