---
title: Obtenha informações de visualização do documento PDF
linktitle: Obtenha informações de visualização do documento PDF
second_title: API GroupDocs.Viewer .NET
description: Aprenda como extrair informações de visualização de documentos PDF usando GroupDocs.Viewer for .NET neste tutorial abrangente.
weight: 16
url: /pt/net/pdf-rendering-options/get-view-info-pdf-document/
---
## Introdução
GroupDocs.Viewer for .NET é uma ferramenta poderosa projetada para agilizar a visualização de documentos em aplicativos .NET. Esteja você lidando com PDFs, documentos do Word, planilhas do Excel ou apresentações do PowerPoint, esta biblioteca simplifica o processo de renderização e interação com vários formatos de arquivo. Neste tutorial, vamos nos concentrar em aproveitar os recursos do GroupDocs.Viewer especificamente para extrair informações de visualização de documentos PDF.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:
1.  Instalação do GroupDocs.Viewer para .NET: certifique-se de ter baixado e instalado a biblioteca GroupDocs.Viewer. Você pode obtê-lo no[Link para Download](https://releases.groupdocs.com/viewer/net/).   
2. Conhecimento básico de C#: Familiaridade com a linguagem de programação C# é essencial para compreender e implementar os exemplos de código fornecidos.
3. Acesso a um documento PDF: tenha um documento PDF pronto para usar para extrair informações da visualização.

## Importar namespaces
Em seu projeto C#, importe os namespaces necessários para utilizar as funcionalidades do GroupDocs.Viewer.

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```


Agora, vamos detalhar o processo de recuperação de informações de visualização de um documento PDF usando GroupDocs.Viewer for .NET.
## Etapa 1: inicializar o objeto visualizador
Crie um objeto Viewer e forneça o caminho para o documento PDF como parâmetro.
```csharp
using (Viewer viewer = new Viewer("path/to/your/sample.pdf"))
{
```
## Etapa 2: definir ViewInfoOptions
Especifique as opções de visualização, como visualização HTML, para recuperar informações de visualização.
```csharp
	ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
## Etapa 3: obter informações de visualização
Invoque o método GetViewInfo para extrair informações de visualização do documento PDF.
```csharp
	PdfViewInfo info = viewer.GetViewInfo(options) as PdfViewInfo;
```
## Etapa 4: informações de visualização de saída
Exiba as informações de visualização extraídas, como tipo de documento, contagem de páginas e permissões de impressão.
```csharp
	Console.WriteLine("Document type is: " + info.FileType);
	Console.WriteLine("Pages count: " + info.Pages.Count);
	Console.WriteLine("Printing allowed: " + info.PrintingAllowed);
}
```

## Conclusão
Neste tutorial, exploramos como utilizar o GroupDocs.Viewer for .NET para extrair informações de visualização de documentos PDF. Seguindo as etapas fornecidas, você pode integrar perfeitamente essa funcionalidade em seus aplicativos .NET, aprimorando o gerenciamento de documentos e os recursos de visualização.
## Perguntas frequentes
### O GroupDocs.Viewer é compatível com outros formatos de arquivo além de PDF?
Sim, GroupDocs.Viewer oferece suporte a uma ampla variedade de formatos de documentos, incluindo Word, Excel, PowerPoint e muito mais.
### Posso personalizar as opções de visualização de acordo com os requisitos da minha aplicação?
Com certeza, GroupDocs.Viewer oferece várias opções para personalizar a experiência de visualização com base em suas necessidades específicas.
### O GroupDocs.Viewer é adequado para aplicativos de desktop e web?
Sim, o GroupDocs.Viewer é versátil e pode ser integrado perfeitamente em aplicativos .NET de desktop e baseados na Web.
### O GroupDocs.Viewer fornece suporte e assistência caso eu encontre algum problema durante a implementação?
Certamente, você pode buscar ajuda no fórum da comunidade GroupDocs.Viewer ou acessar serviços de suporte profissional para resolução imediata de quaisquer problemas.
### Posso experimentar o GroupDocs.Viewer antes de fazer uma compra?
 Sim, você pode explorar os recursos do GroupDocs.Viewer acessando a versão de teste gratuita disponível no site.[local na rede Internet](https://purchase.groupdocs.com/buy).