---
"description": "Aprenda a renderizar imagens CMX em vários formatos sem esforço usando o GroupDocs.Viewer para .NET. Aprimore seu gerenciamento de documentos."
"linktitle": "Renderizar imagens CMX"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Renderizar imagens CMX"
"url": "/pt/net/image-rendering/render-cmx-images/"
"weight": 13
type: docs
---
# Renderizar imagens CMX

## Introdução
No âmbito do gerenciamento e manipulação de documentos, renderizar imagens de vários formatos é uma tarefa fundamental. O GroupDocs.Viewer para .NET simplifica esse processo, fornecendo funcionalidades abrangentes para renderizar imagens CMX em diferentes formatos, como HTML, JPG, PNG e PDF. Este tutorial guiará você pelo processo passo a passo de renderização de imagens CMX usando o GroupDocs.Viewer para .NET.

![Renderizar imagens CMX com GroupDocs.Viewer para .NET](/viewer/image-rendering/render-cmx-images.png)

## Pré-requisitos
Antes de começar o tutorial, certifique-se de ter os seguintes pré-requisitos:
1. Biblioteca GroupDocs.Viewer para .NET: Baixe e instale a biblioteca GroupDocs.Viewer para .NET em [aqui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente de desenvolvimento: tenha um ambiente de desenvolvimento funcional configurado com o .NET Framework.
3. Arquivo de imagem CMX: obtenha um arquivo de imagem CMX que você deseja renderizar.

## Importando namespaces
Antes de prosseguir, certifique-se de importar os namespaces necessários para acessar as funcionalidades do GroupDocs.Viewer no seu aplicativo .NET:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## Renderização para HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- Definir diretório de saída: defina o diretório onde você deseja armazenar os arquivos HTML renderizados.
- Especificar formato do caminho do arquivo: defina o formato para os arquivos HTML de saída.
- Instanciar objeto Viewer: crie uma instância da classe Viewer com o arquivo de imagem CMX.
- Opções de renderização de HTML: configure opções de renderização de HTML, como incorporação de recursos.
- Renderizar CMX para HTML: invoque o método View do objeto visualizador para renderizar a imagem CMX para HTML.
## Renderização para JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Definir diretório de saída: define o diretório para armazenar os arquivos JPG renderizados.
- Especificar formato do caminho do arquivo: defina o formato para os arquivos JPG de saída.
- Instanciar objeto Viewer: crie uma instância da classe Viewer com o arquivo de imagem CMX.
- Opções de renderização de JPG: configure as opções de renderização de JPG.
- Renderizar CMX para JPG: invoque o método View do objeto visualizador para renderizar a imagem CMX para JPG.
## Renderizando para PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Definir diretório de saída: define o diretório para armazenar os arquivos PNG renderizados.
- Especificar formato do caminho do arquivo: defina o formato para os arquivos PNG de saída.
- Instanciar objeto Viewer: crie uma instância da classe Viewer com o arquivo de imagem CMX.
- Opções de renderização de PNG: configure as opções de renderização de PNG.
- Renderizar CMX para PNG: invoque o método View do objeto visualizador para renderizar a imagem CMX para PNG.
## Renderização para PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Definir diretório de saída: define o diretório para armazenar o arquivo PDF renderizado.
- Especificar formato do caminho do arquivo: defina o formato do arquivo PDF de saída.
- Instanciar objeto Viewer: crie uma instância da classe Viewer com o arquivo de imagem CMX.
- Opções de renderização de PDF: configure as opções de renderização de PDF.
- Renderizar CMX em PDF: invoque o método View do objeto visualizador para renderizar a imagem CMX em PDF.

## Conclusão
Concluindo, o GroupDocs.Viewer para .NET oferece uma solução robusta para renderizar imagens CMX em vários formatos de forma integrada. Seguindo os passos descritos neste tutorial, você poderá integrar facilmente os recursos de renderização de imagens CMX aos seus aplicativos .NET, aprimorando a eficiência do gerenciamento de documentos.
## Perguntas frequentes
### Posso renderizar páginas específicas de uma imagem CMX?
Sim, você pode renderizar páginas específicas especificando o número da página nas opções de renderização.
### O GroupDocs.Viewer para .NET é compatível com todas as estruturas .NET?
Sim, o GroupDocs.Viewer para .NET é compatível com vários frameworks .NET, incluindo .NET Core e .NET Framework.
### O GroupDocs.Viewer suporta renderização de imagens CMX criptografadas?
Sim, o GroupDocs.Viewer suporta a renderização de imagens CMX criptografadas com chaves de descriptografia apropriadas.
### Posso personalizar as opções de renderização para diferentes formatos de saída?
Com certeza, o GroupDocs.Viewer oferece amplas opções para personalizar parâmetros de renderização com base em suas necessidades.
### Existe um fórum da comunidade para suporte ao GroupDocs.Viewer?
Sim, você pode buscar assistência e interagir com a comunidade GroupDocs.Viewer no fórum de suporte [aqui](https://forum.groupdocs.com/c/viewer/9).