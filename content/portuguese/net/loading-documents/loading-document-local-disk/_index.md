---
title: Carregar documentos do disco local
linktitle: Carregar documentos do disco local
second_title: API GroupDocs.Viewer .NET
description: Aprenda como renderizar documentos de seu disco local de maneira transparente usando Groupdocs.Viewer for .NET. Aprimore seus aplicativos .NET com documentos eficientes.
weight: 10
url: /pt/net/loading-documents/loading-document-local-disk/
---

# Carregar documentos do disco local

## Introdução
Na era digital de hoje, a renderização eficiente de documentos é essencial para diversas aplicações. Groupdocs.Viewer for .NET oferece uma solução poderosa para renderizar documentos diretamente de seu disco local. Neste tutorial, orientaremos você no processo de carregamento de documentos do disco local usando Groupdocs.Viewer for .NET. Quer você seja um desenvolvedor experiente ou esteja apenas começando, este guia passo a passo o ajudará a integrar perfeitamente a renderização de documentos em seus aplicativos .NET.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:
1.  Groupdocs.Viewer para .NET: Baixe e instale a versão mais recente em[aqui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente de desenvolvimento .NET: certifique-se de ter um ambiente de desenvolvimento .NET funcional configurado em seu sistema.
3. Documentos Locais: Tenha os documentos que você deseja renderizar armazenados localmente em seu disco.

## Importar namespaces
Primeiramente, vamos importar os namespaces necessários para acessar as funcionalidades do Groupdocs.Viewer for .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Etapa 1: carregar documentos do disco local
Comece configurando o diretório de saída onde as páginas HTML renderizadas serão salvas.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Etapa 2: inicializar o visualizador e renderizar documentos
Inicialize o objeto Viewer com o caminho do documento e renderize-o usando as opções de visualização HTML.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Etapa 3: Exibir saída
Assim que a renderização for concluída, exiba uma mensagem indicando a renderização bem-sucedida do documento de origem e a localização dos arquivos de saída.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusão
Parabéns! Você aprendeu com sucesso como carregar documentos do seu disco local usando Groupdocs.Viewer for .NET. Esta ferramenta poderosa abre um mundo de possibilidades para renderização de documentos em seus aplicativos .NET.
## Perguntas frequentes
### Posso renderizar documentos de diferentes formatos usando Groupdocs.Viewer for .NET?
Sim, o Groupdocs.Viewer for .NET oferece suporte a uma ampla variedade de formatos de documentos, incluindo DOCX, PDF, XLSX, PPTX e muito mais.
### O Groupdocs.Viewer for .NET é compatível com todas as estruturas .NET?
Groupdocs.Viewer for .NET é compatível com a maioria dos frameworks .NET, incluindo .NET Core, .NET Framework e .NET Standard.
### Posso personalizar as opções de renderização dos meus documentos?
Absolutamente! Groupdocs.Viewer for .NET oferece amplas opções de personalização, permitindo adaptar o processo de renderização aos seus requisitos específicos.
### Existe uma versão de teste disponível para Groupdocs.Viewer for .NET?
Sim, você pode baixar uma versão de avaliação gratuita em[aqui](https://releases.groupdocs.com/).
### Onde posso encontrar suporte ou recursos adicionais para Groupdocs.Viewer for .NET?
 Para suporte e recursos adicionais, visite Groupdocs.Viewer for .NET[fórum](https://forum.groupdocs.com/c/viewer/9).