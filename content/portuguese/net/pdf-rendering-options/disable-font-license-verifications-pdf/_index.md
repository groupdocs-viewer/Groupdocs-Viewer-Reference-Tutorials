---
"description": "Desbloqueie recursos de visualização de documentos integrados no seu .NET com o GroupDocs.Viewer para .NET. Integre e personalize facilmente a renderização de documentos com o mínimo de dependências."
"linktitle": "Desativar verificações de licença de fonte em PDF"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Desativar verificações de licença de fonte em PDF"
"url": "/pt/net/pdf-rendering-options/disable-font-license-verifications-pdf/"
"weight": 12
---

# Desativar verificações de licença de fonte em PDF

## Introdução
No âmbito do desenvolvimento .NET, gerenciar e manipular documentos costuma ser um aspecto crucial de muitas aplicações. Seja para visualizar PDFs, documentos do Word ou outros tipos de arquivo, ter ferramentas robustas para lidar com essas tarefas com eficiência é essencial. É aqui que o GroupDocs.Viewer para .NET entra em ação. Esta poderosa biblioteca oferece aos desenvolvedores a capacidade de integrar perfeitamente a funcionalidade de visualização de documentos em suas aplicações .NET.

![Desabilitar verificações de licença de fonte em PDF com GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/disable-font-license-verifications-in-pdf.png)

## Pré-requisitos
Antes de começar a usar o GroupDocs.Viewer para .NET, há alguns pré-requisitos que você precisa ter:
### 1. Instale o Visual Studio
Antes de mais nada, certifique-se de ter o Visual Studio instalado no seu sistema. Você pode baixá-lo do site da Microsoft, caso ainda não o tenha feito.
### 2. Baixe o GroupDocs.Viewer para .NET
Vá até o [link para download](https://releases.groupdocs.com/viewer/net/) para adquirir a versão mais recente do GroupDocs.Viewer para .NET. Siga as instruções de instalação fornecidas para configurá-lo em seu ambiente de desenvolvimento.
### 3. Obtenha uma licença temporária
Para liberar todo o potencial do GroupDocs.Viewer para .NET durante o desenvolvimento e os testes, é recomendável obter uma licença temporária. Você pode solicitá-la em [aqui](https://purchase.groupdocs.com/temporary-license/).

## Importar namespaces
Após concluir os pré-requisitos, você estará pronto para começar a utilizar o GroupDocs.Viewer para .NET em seus projetos. Comece importando os namespaces necessários para sua base de código.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Vamos dividir o exemplo fornecido em várias etapas para uma compreensão mais clara:
## Etapa 1: definir diretório de saída
Comece definindo o diretório onde você deseja que as páginas do documento renderizado sejam armazenadas.
```csharp
string outputDirectory = "Your Document Directory";
```
## Etapa 2: Definir o formato do caminho do arquivo de página
Defina o formato para os caminhos de arquivo de páginas individuais do documento.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
## Etapa 3: Inicializar objeto do visualizador
Crie uma instância da classe Viewer, passando o caminho para o documento que você deseja visualizar.
```csharp
using (Viewer viewer = new Viewer(TestFiles.OXPS_EMBEDDED_FONT))
```
## Etapa 4: Configurar opções de visualização HTML
Defina as opções para visualizar o documento como HTML, especificando o formato para recursos incorporados (por exemplo, imagens).
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Etapa 5: Desabilitar Verificações de Licença de Fonte
Ative a opção para desabilitar as verificações de licença de fonte para garantir uma renderização suave.
```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
## Etapa 6: Visualizar documento
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
O GroupDocs.Viewer para .NET oferece aos desenvolvedores uma solução abrangente para integrar recursos de visualização de documentos em seus aplicativos .NET sem esforço. Seguindo os passos descritos neste tutorial, você poderá utilizar esta poderosa biblioteca com eficiência para aprimorar seus fluxos de trabalho de gerenciamento de documentos.
## Perguntas frequentes
### O GroupDocs.Viewer para .NET pode manipular vários formatos de documentos?
Sim, o GroupDocs.Viewer suporta uma ampla variedade de formatos de documentos, incluindo PDF, Microsoft Word, Excel, PowerPoint e muito mais.
### GroupDocs.Viewer para .NET é adequado para aplicativos web?
Com certeza, o GroupDocs.Viewer pode ser perfeitamente integrado a aplicativos de desktop e web desenvolvidos usando tecnologias .NET.
### O GroupDocs.Viewer requer alguma dependência adicional?
Não, o GroupDocs.Viewer para .NET tem dependências mínimas e pode ser facilmente integrado aos seus projetos existentes.
### Posso personalizar a aparência dos documentos renderizados?
Sim, o GroupDocs.Viewer oferece várias opções para personalizar a aparência e o comportamento dos documentos renderizados para atender às suas necessidades específicas.
### Há suporte técnico disponível para o GroupDocs.Viewer para .NET?
Sim, você pode buscar assistência e orientação da equipe de suporte dedicada por meio do [fórum](https://forum.groupdocs.com/c/viewer/9).