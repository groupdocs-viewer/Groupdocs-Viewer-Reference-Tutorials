---
title: Renderizar imagens EMZ e EMF
linktitle: Renderizar imagens EMZ e EMF
second_title: API GroupDocs.Viewer .NET
description: Aprenda como renderizar imagens EMZ e EMF em vários formatos usando GroupDocs.Viewer for .NET. Tutorial fácil de seguir para desenvolvedores.
weight: 14
url: /pt/net/image-rendering/render-emz-emf-images/
---

# Renderizar imagens EMZ e EMF

## Introdução

GroupDocs.Viewer for .NET é uma poderosa API de renderização de documentos que permite aos desenvolvedores exibir vários tipos de documentos, incluindo imagens EMZ (Enhanced Windows Metafile) e EMF (Enhanced Metafile), em seus aplicativos .NET. Neste tutorial, exploraremos como renderizar imagens EMZ e EMF em diferentes formatos, como HTML, JPG, PNG e PDF usando GroupDocs.Viewer for .NET.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:

1.  GroupDocs.Viewer for .NET: você pode baixar a biblioteca em[aqui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente de desenvolvimento: certifique-se de ter um ambiente de desenvolvimento compatível configurado para desenvolvimento .NET.
3. Imagens EMZ/EMF de amostra: tenha imagens EMZ e EMF de amostra disponíveis para renderização.

## Importar namespaces

Antes de mergulhar no código, vamos importar os namespaces necessários:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Agora, vamos dividir cada exemplo em várias etapas em um formato de guia passo a passo:

## Renderizando imagens EMZ/EMF para HTML

### Etapa 1: definir o diretório de saída:
```csharp
string outputDirectory = "Your Document Directory";
```
 Substituir`"Your Document Directory"`com o caminho onde você deseja salvar o arquivo HTML renderizado.

### Etapa 2: Definir o formato do caminho do arquivo de página:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Isso especificará o formato do caminho do arquivo HTML renderizado.

### Etapa 3: renderizar para HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Este código inicializa o`Viewer` objeto com a imagem EMZ de amostra e o renderiza no formato HTML usando opções especificadas.

## Renderizando imagens EMZ/EMF para JPG, PNG e PDF

Repita as etapas a seguir para renderizar nos formatos JPG, PNG e PDF:

### Etapa 1: Definir o formato do caminho do arquivo de página:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Ajuste o nome e a extensão do arquivo de acordo com o formato de saída desejado (`jpg`, `png` , ou`pdf`).

### Etapa 2: Renderizar no respectivo formato:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Ajuste as opções de acordo com o formato de saída (Jpg, Png, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Substituir`JpgViewOptions` com`PngViewOptions` ou`PdfViewOptions` com base no formato de saída desejado.

## Conclusão

Concluindo, o GroupDocs.Viewer for .NET fornece uma solução perfeita para renderizar imagens EMZ e EMF em vários formatos em aplicativos .NET. Seguindo as etapas descritas neste tutorial, os desenvolvedores podem integrar facilmente recursos de renderização de documentos em seus aplicativos.

## Perguntas frequentes

### P: O GroupDocs.Viewer pode renderizar outros formatos de documentos além de imagens EMZ e EMF?
R: Sim, o GroupDocs.Viewer oferece suporte a uma ampla variedade de formatos de documentos, incluindo PDF, DOCX, PPTX, XLSX e muito mais.

### P: Existe uma avaliação gratuita disponível para GroupDocs.Viewer for .NET?
 R: Sim, você pode acessar o teste gratuito[aqui](https://releases.groupdocs.com/).

### P: O GroupDocs.Viewer oferece suporte para desenvolvedores?
 R: Sim, o GroupDocs fornece suporte por meio de seus[fórum](https://forum.groupdocs.com/c/viewer/9) onde os desenvolvedores podem fazer perguntas e buscar assistência.

### P: Posso adquirir uma licença temporária do GroupDocs.Viewer for .NET?
 R: Sim, licenças temporárias estão disponíveis para compra[aqui](https://purchase.groupdocs.com/temporary-license/).

### P: Onde posso encontrar documentação detalhada do GroupDocs.Viewer for .NET?
 R: Você pode consultar a documentação[aqui](https://tutorials.groupdocs.com/viewer/net/)para obter orientação abrangente sobre como usar a API.