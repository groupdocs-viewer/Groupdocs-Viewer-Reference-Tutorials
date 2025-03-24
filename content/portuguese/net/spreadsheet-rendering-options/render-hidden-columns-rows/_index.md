---
title: Renderizar colunas e linhas ocultas
linktitle: Renderizar colunas e linhas ocultas
second_title: API GroupDocs.Viewer .NET
description: Desbloqueie dados ocultos em planilhas sem esforço usando GroupDocs.Viewer for .NET. Siga nosso guia passo a passo para revelar colunas e linhas ocultas.
weight: 13
url: /pt/net/spreadsheet-rendering-options/render-hidden-columns-rows/
---
## Introdução
No domínio da visualização de documentos, GroupDocs.Viewer for .NET se destaca como uma ferramenta robusta que facilita a renderização perfeita de vários formatos de documentos. Um recurso intrigante é a capacidade de revelar colunas e linhas ocultas em planilhas. Neste tutorial, nos aprofundaremos nas etapas para desbloquear esse recurso e liberar o potencial de seus dados.
## Pré-requisitos
Antes de embarcar nesta jornada, certifique-se de ter os seguintes pré-requisitos em vigor:
- GroupDocs.Viewer para .NET: certifique-se de ter a versão mais recente instalada. Caso contrário, você pode baixá-lo no[website oficial](https://releases.groupdocs.com/viewer/net/).
- Arquivo de documento: Prepare um documento de amostra em formato de planilha (por exemplo, SAMPLE.XLSX) para experimentar colunas e linhas ocultas.
- Ambiente de Desenvolvimento: Configure um ambiente de trabalho, de preferência usando Visual Studio ou qualquer outro IDE adequado para desenvolvimento .NET.
## Importar namespaces
Em seu projeto .NET, importe os namespaces necessários para aproveitar as funcionalidades do GroupDocs.Viewer de maneira eficaz:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Etapa 1: configurar o diretório de saída
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Defina o diretório de saída onde as páginas HTML renderizadas serão armazenadas. Ajuste o formato do caminho do arquivo de acordo.
## Etapa 2: inicializar o visualizador e configurar opções
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
```
Crie uma instância do Viewer fornecendo o caminho para o documento da planilha. Configure opções de visualização HTML para incorporar recursos e ativar a renderização de colunas e linhas ocultas.
## Etapa 3: executar o processo de renderização
```csharp
    viewer.View(options);
}
```
Invoque o método View no objeto visualizador, passando as opções configuradas. Isso inicia o processo de renderização.
## Etapa 4: verifique a saída
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Verifique a renderização bem-sucedida do documento de origem e localize a saída no diretório especificado.
## Conclusão
Desbloquear colunas e linhas ocultas em suas planilhas é muito fácil com GroupDocs.Viewer for .NET. Este tutorial equipou você com as etapas essenciais para revelar dados ocultos, proporcionando uma visão mais abrangente de seus documentos.
## perguntas frequentes
### Posso renderizar colunas e linhas ocultas em outros formatos de documento além de planilhas?
Sim, o GroupDocs.Viewer oferece suporte a vários formatos de documentos, incluindo Word, PDF e PowerPoint, além de planilhas.
### Existe um limite para o número de colunas e linhas ocultas que podem ser renderizadas?
GroupDocs.Viewer lida com eficiência com a renderização de uma ampla variedade de colunas e linhas ocultas. No entanto, casos extremos com uma grande quantidade de dados ocultos podem afetar o desempenho.
### Posso personalizar o formato de saída dos dados renderizados?
Absolutamente! GroupDocs.Viewer oferece opções flexíveis para personalizar a saída, permitindo adaptar os dados renderizados às suas necessidades específicas.
### Há alguma consideração de licenciamento para usar o GroupDocs.Viewer?
 Sim, certifique-se de ter a licença apropriada para seu uso. Explore as opções de licenciamento em[Compra de GroupDocs](https://purchase.groupdocs.com/buy) ou obter um[licença temporária](https://purchase.groupdocs.com/temporary-license/) para teste.
### Onde posso procurar assistência ou entrar em contato com a comunidade GroupDocs para obter suporte?
 Visite a[Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) para suporte, discussões e interação com a comunidade.