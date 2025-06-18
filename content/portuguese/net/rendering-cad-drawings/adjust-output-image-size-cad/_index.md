---
"description": "Aprenda a ajustar o tamanho da imagem de saída para desenhos CAD usando o GroupDocs.Viewer para .NET. Melhore a visibilidade e a usabilidade sem esforço."
"linktitle": "Ajustar o tamanho da imagem de saída para desenhos CAD"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Ajustar o tamanho da imagem de saída para desenhos CAD"
"url": "/pt/net/rendering-cad-drawings/adjust-output-image-size-cad/"
"weight": 15
---

# Ajustar o tamanho da imagem de saída para desenhos CAD

## Introdução
Desenhos CAD frequentemente exigem ajustes específicos para visualização e apresentação ideais. O GroupDocs.Viewer para .NET oferece um conjunto de ferramentas poderoso para gerenciar e personalizar a saída de desenhos CAD. Neste tutorial, guiaremos você pelo processo de ajuste do tamanho da imagem de saída para desenhos CAD, passo a passo.
## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes pré-requisitos:
1. GroupDocs.Viewer para .NET: Baixe e instale o GroupDocs.Viewer para .NET em [aqui](https://releases.groupdocs.com/viewer/net/).
2. Diretório de documentos: prepare o diretório onde seu documento está localizado.
3. Noções básicas: familiarize-se com os conceitos básicos de programação .NET.

## Importar namespaces
Primeiro, certifique-se de importar os namespaces necessários para acessar as funcionalidades do GroupDocs.Viewer:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Etapa 1: definir diretório de saída
Defina o diretório onde você deseja armazenar as imagens de saída dos desenhos CAD:
```csharp
string outputDirectory = "Your Document Directory";
```
## Etapa 2: Definir o formato do caminho do arquivo de página
Defina o formato dos caminhos dos arquivos de página. Este formato será usado para nomear e salvar páginas individuais como arquivos HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Etapa 3: ajuste o tamanho da imagem
Dentro de um bloco using para o objeto Viewer, ajuste o tamanho da imagem para desenhos CAD definindo opções apropriadas:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Etapa 4: Exibir diretório de saída
Após renderizar o documento, exiba uma mensagem indicando a renderização bem-sucedida e forneça o local do diretório de saída:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusão
Ajustar o tamanho da imagem de saída para desenhos CAD é crucial para melhorar sua visibilidade e usabilidade. Com o GroupDocs.Viewer para .NET, esse processo se torna simplificado e eficiente, permitindo que você personalize a saída de acordo com suas necessidades específicas.
## Perguntas frequentes
### Posso ajustar o tamanho da imagem de saída para outros tipos de documentos além de desenhos CAD?
Sim, o GroupDocs.Viewer para .NET suporta vários tipos de documentos, e você pode ajustar o tamanho da imagem de saída para a maioria dos formatos de documento.
### GroupDocs.Viewer para .NET é compatível com diferentes versões do .NET Framework?
Sim, o GroupDocs.Viewer para .NET é compatível com diversas versões do .NET Framework, garantindo flexibilidade e usabilidade em diferentes ambientes.
### Há alguma opção de licenciamento disponível para o GroupDocs.Viewer para .NET?
Sim, você pode explorar diferentes opções de licenciamento, incluindo licenças temporárias e licenças comerciais, para atender às suas necessidades.
### Posso personalizar o formato de saída dos documentos renderizados?
Com certeza, o GroupDocs.Viewer para .NET oferece diversas opções de personalização, permitindo que você adapte o formato de saída de acordo com seus tutoriais.
### Onde posso encontrar suporte ou assistência adicional com o GroupDocs.Viewer para .NET?
Você pode visitar o fórum GroupDocs.Viewer [aqui](https://forum.groupdocs.com/c/viewer/9) para obter suporte, fazer perguntas e se envolver com a comunidade.