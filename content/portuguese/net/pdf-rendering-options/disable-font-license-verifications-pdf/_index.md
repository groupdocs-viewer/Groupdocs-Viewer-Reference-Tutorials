---
title: Desativar verificações de licença de fonte em PDF
linktitle: Desativar verificações de licença de fonte em PDF
second_title: API GroupDocs.Viewer .NET
description: Desbloqueie recursos integrados de visualização de documentos em seu .NET com GroupDocs.Viewer for .NET. Integre e personalize facilmente a renderização de documentos com dependências mínimas.
weight: 12
url: /pt/net/pdf-rendering-options/disable-font-license-verifications-pdf/
---
## Introdução
No domínio do desenvolvimento .NET, o gerenciamento e a manipulação de documentos costumam ser um aspecto crucial de muitos aplicativos. Seja para visualizar PDFs, documentos do Word ou outros tipos de arquivo, é essencial ter ferramentas robustas para lidar com essas tarefas com eficiência. É aqui que o GroupDocs.Viewer for .NET entra em ação. Esta poderosa biblioteca oferece aos desenvolvedores a capacidade de integrar perfeitamente a funcionalidade de visualização de documentos em seus aplicativos .NET.
## Pré-requisitos
Antes de começar a usar o GroupDocs.Viewer for .NET, existem alguns pré-requisitos que você precisa ter em vigor:
### 1. Instale o Visual Studio
Em primeiro lugar, certifique-se de ter o Visual Studio instalado em seu sistema. Você pode baixá-lo do site da Microsoft, caso ainda não o tenha feito.
### 2. Baixe GroupDocs.Viewer para .NET
 Vá para o[Link para Download](https://releases.groupdocs.com/viewer/net/) para adquirir a versão mais recente do GroupDocs.Viewer for .NET. Siga as instruções de instalação fornecidas para configurá-lo em seu ambiente de desenvolvimento.
### 3. Obtenha uma licença temporária
 Para desbloquear todo o potencial do GroupDocs.Viewer for .NET durante o desenvolvimento e teste, é recomendável obter uma licença temporária. Você pode solicitar um de[aqui](https://purchase.groupdocs.com/temporary-license/).

## Importar namespaces
Depois de concluir os pré-requisitos, você estará pronto para começar a utilizar o GroupDocs.Viewer for .NET em seus projetos. Comece importando os namespaces necessários para sua base de código.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Vamos dividir o exemplo fornecido em várias etapas para uma compreensão mais clara:
## Etapa 1: definir o diretório de saída
Comece definindo o diretório onde deseja que as páginas do documento renderizado sejam armazenadas.
```csharp
string outputDirectory = "Your Document Directory";
```
## Etapa 2: definir o formato do caminho do arquivo de página
Defina o formato dos caminhos de arquivo de páginas individuais do documento.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
## Etapa 3: inicializar o objeto visualizador
Crie uma instância da classe Viewer, passando o caminho do documento que deseja visualizar.
```csharp
using (Viewer viewer = new Viewer(TestFiles.OXPS_EMBEDDED_FONT))
```
## Etapa 4: configurar opções de visualização HTML
Defina as opções de visualização do documento como HTML, especificando o formato dos recursos incorporados (ex.: imagens).
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Etapa 5: desative as verificações de licença de fonte
Ative a opção de desativar as verificações de licença de fonte para garantir uma renderização suave.
```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
## Etapa 6: visualizar o documento
Invoque o método View do objeto Viewer, passando as opções configuradas.
```csharp
viewer.View(options);
```
## Etapa 7: Exibir diretório de saída
Informe o usuário sobre o local onde as páginas do documento renderizado estão armazenadas.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusão
GroupDocs.Viewer for .NET oferece aos desenvolvedores uma solução abrangente para integrar recursos de visualização de documentos em seus aplicativos .NET sem esforço. Seguindo as etapas descritas neste tutorial, você pode utilizar com eficácia esta poderosa biblioteca para aprimorar seus fluxos de trabalho de gerenciamento de documentos.
## Perguntas frequentes
### O GroupDocs.Viewer for .NET pode lidar com vários formatos de documentos?
Sim, o GroupDocs.Viewer oferece suporte a uma ampla variedade de formatos de documentos, incluindo PDF, Microsoft Word, Excel, PowerPoint e muito mais.
### O GroupDocs.Viewer for .NET é adequado para aplicativos da web?
Com certeza, o GroupDocs.Viewer pode ser perfeitamente integrado em aplicativos desktop e web desenvolvidos com tecnologias .NET.
### O GroupDocs.Viewer requer alguma dependência adicional?
Não, o GroupDocs.Viewer for .NET tem dependências mínimas e pode ser facilmente integrado aos seus projetos existentes.
### Posso personalizar a aparência dos documentos renderizados?
Sim, o GroupDocs.Viewer oferece várias opções para personalizar a aparência e o comportamento dos documentos renderizados para atender às suas necessidades específicas.
### O suporte técnico está disponível para GroupDocs.Viewer for .NET?
 Sim, você pode buscar assistência e orientação da equipe de suporte dedicada por meio do[fórum](https://forum.groupdocs.com/c/viewer/9).