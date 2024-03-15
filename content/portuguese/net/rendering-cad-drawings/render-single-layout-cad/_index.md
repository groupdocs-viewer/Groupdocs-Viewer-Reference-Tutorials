---
title: Renderizar layout único em desenhos CAD
linktitle: Renderizar layout único em desenhos CAD
second_title: API GroupDocs.Viewer .NET
description: Aprenda como renderizar layout único em desenhos CAD usando GroupDocs.Viewer for .NET. Etapas fáceis para integração perfeita em seus aplicativos .NET.
type: docs
weight: 14
url: /pt/net/rendering-cad-drawings/render-single-layout-cad/
---
## Introdução
No domínio do desenvolvimento .NET, o manuseio e visualização de desenhos CAD é um requisito comum. GroupDocs.Viewer for .NET simplifica essa tarefa, fornecendo uma solução abrangente para renderização de desenhos CAD em aplicativos .NET. Neste tutorial, nos aprofundaremos na renderização de um único layout em desenhos CAD usando GroupDocs.Viewer for .NET.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:
- Compreensão básica da linguagem de programação C# e do framework .NET.
- Visual Studio instalado em seu sistema.
-  Biblioteca GroupDocs.Viewer para .NET baixada e referenciada em seu projeto. Você pode baixá-lo em[aqui](https://releases.groupdocs.com/viewer/net/).
- Familiaridade com formatos de arquivo CAD e suas estruturas.

## Importar namespaces
Em primeiro lugar, importe os namespaces necessários para o seu código C# para acessar as funcionalidades do GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Etapa 1: definir o diretório de saída
Especifique o diretório onde deseja que a saída renderizada seja salva.
```csharp
string outputDirectory = "Your Document Directory";
```
## Etapa 2: definir o formato do caminho do arquivo de página
Defina o formato do caminho do arquivo de cada página renderizada.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Etapa 3: instanciar o objeto visualizador
Crie uma instância da classe Viewer fornecida por GroupDocs.Viewer.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Etapa 4: configurar opções de visualização HTML
Configure opções para renderizar saída HTML com recursos incorporados.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Etapa 5: Especifique o nome do layout CAD
Especifique o nome do layout CAD que você deseja renderizar.
```csharp
options.CadOptions.LayoutName = "Model";
```
## Etapa 6: renderizar desenho CAD
Invoque o método View do objeto Viewer com as opções especificadas.
```csharp
viewer.View(options);
```
## Etapa 7: exibir mensagem de sucesso
Informe o usuário sobre a renderização bem-sucedida do documento de origem.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusão
Renderizar desenhos CAD, especialmente quando se trata de layouts, pode ser uma tarefa difícil. No entanto, com GroupDocs.Viewer for .NET, o processo torna-se contínuo e eficiente. Seguindo as etapas descritas neste tutorial, você pode renderizar facilmente um único layout em desenhos CAD em seus aplicativos .NET.
## Perguntas frequentes
### Posso renderizar vários layouts simultaneamente usando GroupDocs.Viewer for .NET?
Sim, o GroupDocs.Viewer for .NET oferece suporte à renderização de vários layouts a partir de desenhos CAD.
### O GroupDocs.Viewer é compatível com diferentes formatos de arquivo CAD?
Com certeza, GroupDocs.Viewer oferece suporte a uma ampla variedade de formatos de arquivo CAD, incluindo DWG, DXF, DGN e muito mais.
### Posso personalizar as opções de renderização de desenhos CAD?
Sim, o GroupDocs.Viewer oferece amplas opções para personalizar as configurações de renderização de acordo com suas necessidades.
### Existe uma avaliação gratuita disponível para GroupDocs.Viewer for .NET?
 Sim, você pode explorar os recursos do GroupDocs.Viewer com uma avaliação gratuita disponível[aqui](https://releases.groupdocs.com/).
### Onde posso obter suporte para GroupDocs.Viewer for .NET?
 Para qualquer dúvida ou assistência, você pode visitar o fórum GroupDocs.Viewer[aqui](https://forum.groupdocs.com/c/viewer/9).