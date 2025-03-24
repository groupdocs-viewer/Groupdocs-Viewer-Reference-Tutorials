---
title: Renderizar alterações rastreadas
linktitle: Renderizar alterações rastreadas
second_title: API GroupDocs.Viewer .NET
description: Descubra como renderizar alterações controladas em documentos sem esforço usando GroupDocs.Viewer for .NET. Aumente a eficiência do gerenciamento de documentos.
weight: 10
url: /pt/net/rendering-word-processing-documents/render-tracked-changes/
---

# Renderizar alterações rastreadas

## Introdução
Na era digital de hoje, a gestão e visualização eficiente de documentos é crucial tanto para empresas como para indivíduos. Com o advento de tecnologias avançadas, soluções como GroupDocs.Viewer for .NET revolucionaram a forma como interagimos com vários formatos de documentos, incluindo documentos Word, PDFs e muito mais. Neste guia abrangente, nos aprofundaremos em como aproveitar o GroupDocs.Viewer for .NET para renderizar alterações controladas em seus documentos de maneira integrada.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:
1. Instalação do GroupDocs.Viewer for .NET: Baixe e instale o GroupDocs.Viewer for .NET a partir do[local na rede Internet](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: certifique-se de ter o .NET Framework instalado em seu sistema.
3. Diretório de documentos: Prepare um diretório onde seus documentos serão armazenados.

## Importar namespaces
Para começar, importe os namespaces necessários para o seu projeto. Esses namespaces são essenciais para a utilização eficaz das funcionalidades do GroupDocs.Viewer.
## Passos:
1. Abra seu IDE: Inicie seu ambiente de desenvolvimento integrado (IDE) preferido, como o Visual Studio.
2. Crie ou abra seu projeto: Inicie um novo projeto ou abra um existente onde você pretende usar o GroupDocs.Viewer.
3. Importar namespaces: em seu arquivo de projeto ou arquivo de código, adicione os seguintes namespaces:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Agora, vamos dividir o exemplo fornecido em várias etapas para orientá-lo na renderização de alterações controladas usando GroupDocs.Viewer for .NET.
## Etapa 1: definir o diretório de saída
Em primeiro lugar, defina o diretório onde deseja que a saída renderizada seja salva.
```csharp
string outputDirectory = "Your Document Directory";
```
 Substituir`"Your Document Directory"`com o caminho para o diretório desejado.
## Etapa 2: definir o formato do caminho do arquivo de página
Especifique o formato dos caminhos do arquivo de paginação. Este formato determinará como as páginas renderizadas serão nomeadas e armazenadas.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Aqui,`"page_{0}.html"` indica que as páginas serão nomeadas como`page_1.html`, `page_2.html`, e assim por diante.
## Etapa 3: inicializar o objeto visualizador
 Inicialize um`Viewer` objeto passando o caminho do documento como argumento.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES))
{
    // O código continua na próxima etapa...
}
```
 Certifique-se de substituir`TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES` com o caminho para o seu documento.
## Etapa 4: configurar opções de visualização HTML
Configure as opções de visualização HTML para personalizar as configurações de renderização, como a renderização de alterações controladas.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.WordProcessingOptions.RenderTrackedChanges = true;
```
Esta etapa permite a renderização de alterações controladas no HTML de saída.
## Etapa 5: renderizar documento
Renderize o documento usando as opções configuradas.
```csharp
viewer.View(options);
```
Este comando inicia o processo de renderização com base nas configurações fornecidas.
## Etapa 6: Exibir diretório de saída
Informe o usuário sobre o local onde a saída renderizada está armazenada.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Esta mensagem notifica o usuário sobre a renderização bem-sucedida e onde encontrar os arquivos de saída.

## Conclusão
Concluindo, GroupDocs.Viewer for .NET oferece uma solução poderosa para renderizar alterações rastreadas em documentos sem esforço. Seguindo o guia passo a passo descrito neste artigo, você pode integrar perfeitamente essa funcionalidade aos seus aplicativos .NET, aumentando a eficiência do gerenciamento de documentos.
## Perguntas frequentes
### Posso renderizar alterações controladas em vários formatos de documentos usando GroupDocs.Viewer for .NET?
Sim, o GroupDocs.Viewer oferece suporte à renderização de alterações rastreadas em vários formatos, incluindo DOCX, PDF e muito mais.
### O GroupDocs.Viewer for .NET é compatível com todas as versões do .NET Framework?
Sim, o GroupDocs.Viewer for .NET é compatível com várias versões do .NET Framework, garantindo ampla compatibilidade.
### O GroupDocs.Viewer oferece algum teste gratuito para fins de teste?
Sim, você pode aproveitar uma avaliação gratuita do GroupDocs.Viewer para explorar seus recursos antes de tomar uma decisão de compra.
### Posso personalizar as configurações de renderização para atender a requisitos específicos?
Com certeza, GroupDocs.Viewer oferece amplas opções de personalização, permitindo adaptar o processo de renderização de acordo com suas necessidades.
### Onde posso procurar assistência se encontrar algum problema ou tiver dúvidas sobre o GroupDocs.Viewer?
 Para suporte e assistência da comunidade, você pode visitar o fórum GroupDocs.Viewer em[esse link](https://forum.groupdocs.com/c/viewer/9).