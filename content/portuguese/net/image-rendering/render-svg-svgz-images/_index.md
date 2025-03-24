---
title: Renderizar imagens SVG e SVGZ
linktitle: Renderizar imagens SVG e SVGZ
second_title: API GroupDocs.Viewer .NET
description: Aprenda como renderizar imagens SVG e SVGZ usando GroupDocs.Viewer for .NET. Converta gráficos vetoriais em HTML, JPG, PNG e PDF sem esforço.
weight: 16
url: /pt/net/image-rendering/render-svg-svgz-images/
---
## Introdução
Neste tutorial, orientaremos você no processo de renderização de imagens SVG e SVGZ usando GroupDocs.Viewer for .NET. GroupDocs.Viewer for .NET é uma poderosa API de renderização de documentos que permite aos desenvolvedores renderizar vários formatos de documentos em seus aplicativos .NET. SVG e SVGZ são formatos de imagem populares usados para gráficos vetoriais e, com GroupDocs.Viewer for .NET, você pode facilmente renderizá-los em diferentes formatos de saída, como HTML, JPG, PNG e PDF.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos instalados e configurados:
1.  GroupDocs.Viewer for .NET: Baixe e instale o GroupDocs.Viewer for .NET em[aqui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente de desenvolvimento: certifique-se de ter um ambiente de desenvolvimento funcional para desenvolvimento .NET, como Visual Studio.
3. Arquivo SVGZ de amostra: tenha um arquivo SVGZ de amostra pronto para teste.

## Importar namespaces
Antes de mergulharmos no código, vamos importar os namespaces necessários:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Etapa 1: renderizar SVGZ para HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Etapa 2: renderizar SVGZ para JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Etapa 3: renderizar SVGZ para PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Etapa 4: renderizar SVGZ em PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Conclusão
Neste tutorial, aprendemos como renderizar imagens SVG e SVGZ usando GroupDocs.Viewer for .NET. Com apenas alguns passos simples, você pode converter imagens SVGZ em vários formatos de saída como HTML, JPG, PNG e PDF, tornando-as acessíveis e visualizáveis em diferentes ambientes.
## Perguntas frequentes
### O GroupDocs.Viewer pode renderizar outros formatos de imagem?
Sim, GroupDocs.Viewer oferece suporte à renderização de vários formatos de imagem, incluindo PNG, JPEG, BMP, TIFF, GIF e muito mais.
### O GroupDocs.Viewer é compatível com o .NET Core?
Sim, GroupDocs.Viewer é compatível com .NET Framework e .NET Core.
### Posso personalizar as opções de renderização?
Sim, o GroupDocs.Viewer oferece amplas opções de renderização, permitindo que você personalize a saída de acordo com seus requisitos.
### O GroupDocs.Viewer requer alguma dependência de terceiros?
Não, GroupDocs.Viewer é uma API independente e não requer dependências de terceiros para renderizar documentos.
### Existe uma versão de teste disponível para teste?
Sim, você pode baixar uma versão de teste gratuita do GroupDocs.Viewer em[aqui](https://releases.groupdocs.com/) para avaliar suas características antes de fazer uma compra.