---
"description": "Aprenda a renderizar documentos do seu disco local com facilidade usando o Groupdocs.Viewer para .NET. Aprimore seus aplicativos .NET com documentos eficientes."
"linktitle": "Carregar documentos do disco local"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Carregar documentos do disco local"
"url": "/pt/net/loading-documents/loading-document-local-disk/"
"weight": 10
type: docs
---
# Carregar documentos do disco local

## Introdução
Na era digital atual, a renderização eficiente de documentos é essencial para diversas aplicações. O Groupdocs.Viewer para .NET oferece uma solução poderosa para renderizar documentos diretamente do seu disco local. Neste tutorial, guiaremos você pelo processo de carregamento de documentos do seu disco local usando o Groupdocs.Viewer para .NET. Seja você um desenvolvedor experiente ou iniciante, este guia passo a passo ajudará você a integrar perfeitamente a renderização de documentos aos seus aplicativos .NET.

![Carregar documentos do disco local com GroupDocs.Viewer .NET](/viewer/loading-documents/load-documents-from-local-disk.png)

## Pré-requisitos
Antes de começar o tutorial, certifique-se de ter os seguintes pré-requisitos:
1. Groupdocs.Viewer para .NET: Baixe e instale a versão mais recente de [aqui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente de desenvolvimento .NET: certifique-se de ter um ambiente de desenvolvimento .NET funcional configurado no seu sistema.
3. Documentos locais: tenha os documentos que você deseja renderizar armazenados localmente no seu disco.

## Importar namespaces
Primeiro, vamos importar os namespaces necessários para acessar as funcionalidades do Groupdocs.Viewer para .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Etapa 1: Carregar documentos do disco local
Comece configurando o diretório de saída onde as páginas HTML renderizadas serão salvas.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Etapa 2: Inicializar o Visualizador e Renderizar Documentos
Inicialize o objeto Viewer com o caminho do documento e renderize-o usando opções de visualização HTML.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Etapa 3: Exibir saída
Quando a renderização estiver concluída, exiba uma mensagem indicando a renderização bem-sucedida do documento de origem e o local dos arquivos de saída.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusão
Parabéns! Você aprendeu com sucesso a carregar documentos do seu disco local usando o Groupdocs.Viewer para .NET. Esta ferramenta poderosa abre um mundo de possibilidades para a renderização de documentos em seus aplicativos .NET.
## Perguntas frequentes
### Posso renderizar documentos de diferentes formatos usando o Groupdocs.Viewer para .NET?
Sim, o Groupdocs.Viewer para .NET suporta uma ampla variedade de formatos de documentos, incluindo DOCX, PDF, XLSX, PPTX e muito mais.
### O Groupdocs.Viewer para .NET é compatível com todos os frameworks .NET?
O Groupdocs.Viewer para .NET é compatível com a maioria das estruturas .NET, incluindo .NET Core, .NET Framework e .NET Standard.
### Posso personalizar as opções de renderização dos meus documentos?
Com certeza! O Groupdocs.Viewer para .NET oferece amplas opções de personalização, permitindo que você adapte o processo de renderização às suas necessidades específicas.
### Existe uma versão de teste disponível para o Groupdocs.Viewer para .NET?
Sim, você pode baixar uma versão de teste gratuita em [aqui](https://releases.groupdocs.com/).
### Onde posso encontrar suporte ou recursos adicionais para o Groupdocs.Viewer para .NET?
Para obter suporte e recursos adicionais, visite o Groupdocs.Viewer para .NET [fórum](https://forum.groupdocs.com/c/viewer/9).