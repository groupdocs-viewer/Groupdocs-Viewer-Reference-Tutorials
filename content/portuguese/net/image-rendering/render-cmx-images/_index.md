---
title: Renderizar imagens CMX
linktitle: Renderizar imagens CMX
second_title: API GroupDocs.Viewer .NET
description: Aprenda como renderizar facilmente imagens CMX em vários formatos usando GroupDocs.Viewer for .NET. Aprimore seu gerenciamento de documentos.
weight: 13
url: /pt/net/image-rendering/render-cmx-images/
---

# Renderizar imagens CMX

## Introdução
No domínio do gerenciamento e manipulação de documentos, a renderização de imagens de vários formatos é uma tarefa fundamental. GroupDocs.Viewer for .NET simplifica esse processo, fornecendo funcionalidades abrangentes para renderizar imagens CMX em diferentes formatos, como HTML, JPG, PNG e PDF. Este tutorial irá guiá-lo através do processo passo a passo de renderização de imagens CMX usando GroupDocs.Viewer for .NET.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
1.  Biblioteca GroupDocs.Viewer for .NET: Baixe e instale a biblioteca GroupDocs.Viewer for .NET em[aqui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente de desenvolvimento: Tenha um ambiente de desenvolvimento funcional configurado com o .NET framework.
3. Arquivo de imagem CMX: Obtenha um arquivo de imagem CMX que deseja renderizar.

## Importando Namespaces
Antes de continuar, certifique-se de importar os namespaces necessários para acessar as funcionalidades do GroupDocs.Viewer em seu aplicativo .NET:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## Renderizando para HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- Definir diretório de saída: Defina o diretório onde deseja armazenar os arquivos HTML renderizados.
- Especifique o formato do caminho do arquivo: defina o formato dos arquivos HTML de saída.
- Instancie o objeto Viewer: Crie uma instância da classe Viewer com o arquivo de imagem CMX.
- Opções de renderização de HTML: configure opções de renderização de HTML, como incorporação de recursos.
- Renderizar CMX em HTML: invoque o método View do objeto visualizador para renderizar a imagem CMX em HTML.
## Renderizando para JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Definir diretório de saída: Defina o diretório para armazenar os arquivos JPG renderizados.
- Especifique o formato do caminho do arquivo: defina o formato dos arquivos JPG de saída.
- Instancie o objeto Viewer: Crie uma instância da classe Viewer com o arquivo de imagem CMX.
- Opções de renderização de JPG: configure as opções de renderização de JPG.
- Renderizar CMX em JPG: invoque o método View do objeto visualizador para renderizar a imagem CMX em JPG.
## Renderizando para PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Definir diretório de saída: Defina o diretório para armazenar os arquivos PNG renderizados.
- Especifique o formato do caminho do arquivo: defina o formato dos arquivos PNG de saída.
- Instancie o objeto Viewer: Crie uma instância da classe Viewer com o arquivo de imagem CMX.
- Opções de renderização de PNG: configure as opções de renderização de PNG.
- Renderizar CMX em PNG: invoque o método View do objeto visualizador para renderizar a imagem CMX em PNG.
## Renderizando para PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Definir diretório de saída: Defina o diretório para armazenar o arquivo PDF renderizado.
- Especifique o formato do caminho do arquivo: defina o formato do arquivo PDF de saída.
- Instancie o objeto Viewer: Crie uma instância da classe Viewer com o arquivo de imagem CMX.
- Opções de renderização de PDF: configure as opções de renderização de PDF.
- Renderizar CMX em PDF: invoque o método View do objeto visualizador para renderizar a imagem CMX em PDF.

## Conclusão
Concluindo, GroupDocs.Viewer for .NET oferece uma solução robusta para renderizar imagens CMX em vários formatos de forma integrada. Seguindo as etapas descritas neste tutorial, você pode integrar facilmente recursos de renderização de imagens CMX em seus aplicativos .NET, aumentando a eficiência do gerenciamento de documentos.
## Perguntas frequentes
### Posso renderizar páginas específicas de uma imagem CMX?
Sim, você pode renderizar páginas específicas especificando o número da página nas opções de renderização.
### GroupDocs.Viewer for .NET é compatível com todas as estruturas .NET?
Sim, o GroupDocs.Viewer for .NET é compatível com vários frameworks .NET, incluindo .NET Core e .NET Framework.
### O GroupDocs.Viewer oferece suporte à renderização de imagens CMX criptografadas?
Sim, o GroupDocs.Viewer oferece suporte à renderização de imagens CMX criptografadas com chaves de descriptografia apropriadas.
### Posso personalizar as opções de renderização para diferentes formatos de saída?
Com certeza, GroupDocs.Viewer oferece amplas opções para personalizar parâmetros de renderização com base em seus requisitos.
### Existe um fórum da comunidade para suporte do GroupDocs.Viewer?
 Sim, você pode procurar assistência e interagir com a comunidade GroupDocs.Viewer no fórum de suporte[aqui](https://forum.groupdocs.com/c/viewer/9).