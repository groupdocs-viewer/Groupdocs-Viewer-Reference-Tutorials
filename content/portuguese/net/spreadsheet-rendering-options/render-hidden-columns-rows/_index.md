---
"description": "Desvende dados ocultos em planilhas sem esforço usando o GroupDocs.Viewer para .NET. Siga nosso guia passo a passo para revelar colunas e linhas ocultas."
"linktitle": "Renderizar colunas e linhas ocultas"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Renderizar colunas e linhas ocultas"
"url": "/pt/net/spreadsheet-rendering-options/render-hidden-columns-rows/"
"weight": 13
type: docs
---
# Renderizar colunas e linhas ocultas

## Introdução
No âmbito da visualização de documentos, o GroupDocs.Viewer para .NET se destaca como uma ferramenta robusta que facilita a renderização perfeita de vários formatos de documentos. Um recurso interessante é a capacidade de revelar colunas e linhas ocultas em planilhas. Neste tutorial, vamos nos aprofundar nas etapas para desbloquear esse recurso e liberar o potencial dos seus dados.
## Pré-requisitos
Antes de embarcar nesta jornada, certifique-se de ter os seguintes pré-requisitos em vigor:
- GroupDocs.Viewer para .NET: Certifique-se de ter a versão mais recente instalada. Caso contrário, você pode baixá-la do site [site oficial](https://releases.groupdocs.com/viewer/net/).
- Arquivo de documento: prepare um documento de amostra em formato de planilha (por exemplo, SAMPLE.XLSX) para experimentar colunas e linhas ocultas.
- Ambiente de desenvolvimento: configure um ambiente de trabalho, de preferência usando o Visual Studio ou qualquer outro IDE adequado para desenvolvimento .NET.
## Importar namespaces
No seu projeto .NET, importe os namespaces necessários para aproveitar as funcionalidades do GroupDocs.Viewer de forma eficaz:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Etapa 1: Configurar diretório de saída
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Defina o diretório de saída onde as páginas HTML renderizadas serão armazenadas. Ajuste o formato do caminho do arquivo de acordo.
## Etapa 2: inicializar o visualizador e configurar as opções
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
```
Crie uma instância do Visualizador fornecendo o caminho para o seu documento de planilha. Configure as opções de visualização HTML para incorporar recursos e habilitar a renderização de colunas e linhas ocultas.
## Etapa 3: Executar o processo de renderização
```csharp
    viewer.View(options);
}
```
Invoque o método View no objeto visualizador, passando as opções configuradas. Isso inicia o processo de renderização.
## Etapa 4: Verifique a saída
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Verifique a renderização bem-sucedida do documento de origem e localize a saída no diretório especificado.
## Conclusão
Desbloquear colunas e linhas ocultas em suas planilhas se torna muito fácil com o GroupDocs.Viewer para .NET. Este tutorial forneceu os passos essenciais para revelar dados ocultos, proporcionando uma visão mais abrangente dos seus documentos.
## Perguntas frequentes
### Posso renderizar colunas e linhas ocultas em outros formatos de documento além de planilhas?
Sim, o GroupDocs.Viewer suporta vários formatos de documentos, incluindo Word, PDF e PowerPoint, além de planilhas.
### Existe um limite para o número de colunas e linhas ocultas que podem ser renderizadas?
GroupDocs.Viewer processa com eficiência a renderização de uma ampla gama de colunas e linhas ocultas. No entanto, casos extremos com uma grande quantidade de dados ocultos podem afetar o desempenho.
### Posso personalizar o formato de saída dos dados renderizados?
Com certeza! O GroupDocs.Viewer oferece opções flexíveis para personalizar a saída, permitindo que você adapte os dados renderizados às suas necessidades específicas.
### Há alguma consideração de licenciamento para usar o GroupDocs.Viewer?
Sim, certifique-se de ter a licença apropriada para o seu uso. Explore as opções de licenciamento em [Compra do GroupDocs](https://purchase.groupdocs.com/buy) ou obter um [licença temporária](https://purchase.groupdocs.com/temporary-license/) para testes.
### Onde posso buscar assistência ou entrar em contato com a comunidade do GroupDocs para obter suporte?
Visite o [Fórum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) para suporte, discussões e interação com a comunidade.