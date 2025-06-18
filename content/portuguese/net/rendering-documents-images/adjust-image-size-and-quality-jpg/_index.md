---
"description": "Aprenda a otimizar o tamanho e a qualidade de imagens no formato JPEG usando o Groupdocs.Viewer para .NET. Aprimore sua experiência de visualização de documentos."
"linktitle": "Ajustar tamanho e qualidade da imagem (JPG)"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Ajustar tamanho e qualidade da imagem (JPG)"
"url": "/pt/net/rendering-documents-images/adjust-image-size-and-quality-jpg/"
"weight": 11
---

# Ajustar tamanho e qualidade da imagem (JPG)

## Introdução
O Groupdocs.Viewer para .NET é uma biblioteca poderosa que permite aos desenvolvedores integrar perfeitamente a funcionalidade de visualização de documentos em seus aplicativos .NET. Um requisito comum em aplicativos de visualização de documentos é a capacidade de ajustar o tamanho e a qualidade das imagens, especialmente quando se trata de imagens JPEG (JPG). Neste tutorial, mostraremos o processo de ajuste do tamanho e da qualidade das imagens usando o Groupdocs.Viewer para .NET.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
1. Noções básicas de linguagem de programação C#.
2. Visual Studio instalado no seu sistema.
3. Biblioteca Groupdocs.Viewer para .NET instalada. Você pode baixá-la em [aqui](https://releases.groupdocs.com/viewer/net/).

## Importar namespaces
Primeiro, você precisa importar os namespaces necessários para o seu código C#. Esses namespaces fornecem acesso às classes e métodos necessários para trabalhar com Groupdocs.Viewer.
## Etapa 1: Importar namespaces
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Agora, vamos dividir o código de exemplo fornecido em várias etapas para uma melhor compreensão.
## Etapa 2: definir o diretório de saída e o formato do caminho do arquivo de paginação
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
Nesta etapa, especificamos o diretório de saída onde as imagens renderizadas serão salvas e definimos o formato para o caminho do arquivo de cada imagem de página.
## Etapa 3: inicializar o visualizador e configurar as opções de visualização JPG
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Aqui, inicializamos o objeto Viewer com o caminho para o documento a ser visualizado. Em seguida, criamos uma instância de JpgViewOptions e definimos a largura e a altura desejadas para as imagens JPEG.
## Etapa 4: renderizar o documento de origem
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Por fim, imprimimos uma mensagem indicando a renderização bem-sucedida do documento de origem e o local onde as imagens de saída são salvas.

## Conclusão
Neste tutorial, aprendemos como ajustar o tamanho e a qualidade de imagens JPEG usando o Groupdocs.Viewer para .NET. Seguindo os passos descritos acima, você pode incorporar facilmente essa funcionalidade aos seus aplicativos .NET, proporcionando aos usuários uma experiência otimizada de visualização de imagens.
## Perguntas frequentes
### Posso ajustar a qualidade da imagem também?
Sim, você pode ajustar a qualidade da imagem definindo a propriedade Qualidade em JpgViewOptions.
### Quais formatos de documento são suportados pelo Groupdocs.Viewer para .NET?
O Groupdocs.Viewer para .NET suporta uma ampla variedade de formatos de documentos, incluindo DOCX, PDF, PPTX, XLSX e muito mais.
### O Groupdocs.Viewer para .NET é compatível com o .NET Core?
Sim, o Groupdocs.Viewer para .NET é compatível com o .NET Core e também com o .NET Framework tradicional.
### Posso personalizar o formato de nomenclatura do arquivo de saída?
Sim, você pode personalizar o formato de nomenclatura do arquivo de saída modificando a variável pageFilePathFormat no código.
### Groupdocs.Viewer para .NET suporta anotações em documentos?
Sim, o Groupdocs.Viewer para .NET fornece suporte abrangente para anotações em documentos, incluindo destaque de texto, sublinhado e comentários.