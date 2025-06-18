---
"description": "Aprenda a renderizar formatos CAD específicos, como CF2, para HTML, JPG, PNG e PDF usando o Groupdocs.Viewer para .NET."
"linktitle": "Formatos CAD específicos de renderização (CF2)"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Formatos CAD específicos de renderização (CF2)"
"url": "/pt/net/rendering-cad-drawings/render-specific-cad-formats/"
"weight": 12
---

# Formatos CAD específicos de renderização (CF2)

## Introdução
Neste tutorial, exploraremos como renderizar formatos CAD específicos usando o Groupdocs.Viewer para .NET. O Groupdocs.Viewer é uma poderosa API de visualização de documentos que permite aos desenvolvedores exibir mais de 170 tipos de documentos em seus aplicativos sem a necessidade de instalação de software externo. Especificamente, vamos nos concentrar na renderização de formatos CAD, como CF2, para diversos formatos de saída, como HTML, JPG, PNG e PDF.
## Pré-requisitos
Antes de começarmos o tutorial, certifique-se de ter os seguintes pré-requisitos:
- Visual Studio instalado no seu sistema.
- Groupdocs.Viewer para .NET SDK. Você pode baixá-lo em [aqui](https://releases.groupdocs.com/viewer/net/).
- Conhecimento básico da linguagem de programação C#.
## Importar namespaces
Primeiro, vamos importar os namespaces necessários para renderizar formatos CAD.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Agora, vamos dividir cada exemplo em várias etapas:
## Renderizar CF2 para HTML
### Etapa 1: defina o diretório de saída onde o HTML renderizado será salvo.
```csharp
string outputDirectory = "Your Document Directory";
```
### Etapa 2: Defina o formato do caminho do arquivo para a saída HTML.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### Etapa 3: inicialize o objeto Viewer e especifique o arquivo CF2 de entrada.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Defina opções de renderização adicionais, se necessário
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Renderizar CF2 para JPG
### Etapa 1: defina o formato do caminho do arquivo para a saída JPG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### Etapa 2: inicialize o objeto Viewer e especifique o arquivo CF2 de entrada.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // Defina opções de renderização adicionais, se necessário
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Renderizar CF2 para PNG

### Etapa 1: defina o formato do caminho do arquivo para a saída PNG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### Etapa 2: inicialize o objeto Viewer e especifique o arquivo CF2 de entrada.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // Defina opções de renderização adicionais, se necessário
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Renderizar CF2 para PDF
### Etapa 1: defina o formato do caminho do arquivo para a saída PDF.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### Etapa 2: inicialize o objeto Viewer e especifique o arquivo CF2 de entrada.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // Defina opções de renderização adicionais, se necessário
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Conclusão
Neste tutorial, aprendemos como renderizar formatos CAD específicos, como CF2, usando o Groupdocs.Viewer para .NET. Seguindo o guia passo a passo, você poderá integrar facilmente recursos de renderização de documentos aos seus aplicativos .NET.
## Perguntas frequentes
### O Groupdocs.Viewer pode renderizar outros formatos CAD além do CF2?
Sim, o Groupdocs.Viewer suporta uma ampla variedade de formatos CAD, incluindo DWG, DXF, DGN e muito mais.
### O Groupdocs.Viewer é adequado para renderizar documentos em aplicativos web?
Com certeza, o Groupdocs.Viewer pode ser perfeitamente integrado a aplicativos web para renderizar documentos diretamente no navegador.
### O Groupdocs.Viewer requer alguma dependência externa para renderização?
Não, o Groupdocs.Viewer é uma API autônoma e não requer nenhuma dependência externa ou instalação de software.
### Posso personalizar as opções de renderização de acordo com minhas necessidades?
Sim, o Groupdocs.Viewer oferece várias opções de renderização que podem ser personalizadas para atender às suas necessidades específicas.
### Existe uma versão de teste disponível para o Groupdocs.Viewer?
Sim, você pode obter uma versão de teste gratuita do Groupdocs.Viewer em [aqui](https://releases.groupdocs.com/).