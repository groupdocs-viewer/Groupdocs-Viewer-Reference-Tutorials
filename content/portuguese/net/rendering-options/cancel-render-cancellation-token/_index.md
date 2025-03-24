---
title: Cancelar renderização com token de cancelamento
linktitle: Cancelar renderização com token de cancelamento
second_title: API GroupDocs.Viewer .NET
description: Integre o Groupdocs.Viewer for .NET perfeitamente em seus projetos .NET para uma visualização eficiente de documentos.
weight: 11
url: /pt/net/rendering-options/cancel-render-cancellation-token/
---
## Introdução
Groupdocs.Viewer for .NET é uma ferramenta poderosa projetada para simplificar a visualização e o processamento de documentos em aplicativos .NET. Esteja você lidando com PDFs, documentos do Microsoft Office ou outros formatos comuns, esta biblioteca oferece funcionalidade robusta para integrar perfeitamente recursos de visualização de documentos em seus projetos .NET.
## Pré-requisitos
Antes de mergulhar na integração do Groupdocs.Viewer for .NET, certifique-se de ter os seguintes pré-requisitos em vigor:
1.  Instalação: Baixe e instale a biblioteca Groupdocs.Viewer for .NET do site fornecido[Link para Download](https://releases.groupdocs.com/viewer/net/).
   
2.  Licença: Obtenha uma licença de[Documentos de grupo](https://purchase.groupdocs.com/buy) para desbloquear todo o potencial da biblioteca. Como alternativa, você pode começar com uma avaliação gratuita usando o[licença temporária](https://purchase.groupdocs.com/temporary-license/).
   
3. Ambiente de desenvolvimento: certifique-se de ter um ambiente de desenvolvimento compatível configurado, incluindo Visual Studio ou qualquer outro IDE .NET de sua escolha.

## Importar namespaces
Para utilizar o Groupdocs.Viewer for .NET de maneira eficaz, você precisa importar os namespaces necessários para o seu projeto. Siga esses passos:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Agora, vamos dividir o exemplo fornecido em várias etapas para melhor compreensão e implementação:
## Etapa 1: definir o diretório de saída
```csharp
string outputDirectory = "Your Document Directory";
```
Esta etapa define o diretório onde as páginas do documento renderizado serão armazenadas.
## Etapa 2: definir o formato do caminho do arquivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Aqui, definimos o formato dos caminhos de arquivo das páginas individuais do documento.
## Etapa 3: inicializar CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource é usado para gerar instâncias CancellationToken que podem ser usadas para cancelar operações assíncronas.
## Etapa 4: Obtenha o CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Esta etapa recupera o token do CancellationTokenSource, que será usado para cancelar a operação de renderização.
## Etapa 5: renderizar páginas do documento
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
Aqui, iniciamos a renderização das páginas do documento de forma assíncrona usando Task.Run(). A instância do Viewer é criada com o arquivo de documento especificado (SAMPLE_DOCX) e as opções de renderização são configuradas. O processo de renderização é então iniciado usando o método View da classe Viewer.
## Etapa 6: definir o tempo limite de renderização
```csharp
cancellationTokenSource.CancelAfter(10);
```
Esta etapa define um tempo limite de 10 milissegundos para a operação de renderização. Se a operação ultrapassar esse tempo limite, ela será automaticamente cancelada.
## Etapa 7: exibir mensagem de sucesso
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Finalmente, uma mensagem de sucesso é exibida indicando que o documento foi renderizado com sucesso.

## Conclusão
Neste tutorial, cobrimos os fundamentos da integração do Groupdocs.Viewer for .NET em seus projetos. Seguindo as etapas descritas acima, você pode incorporar perfeitamente recursos de visualização de documentos em seus aplicativos .NET, melhorando a experiência do usuário e a produtividade.
## Perguntas frequentes
### O Groupdocs.Viewer for .NET é compatível com todos os formatos de documentos?
Groupdocs.Viewer for .NET oferece suporte a uma ampla variedade de formatos de documentos, incluindo PDF, documentos do Microsoft Office, imagens e muito mais.
### Posso personalizar a aparência das páginas do documento renderizado?
Sim, você pode personalizar vários aspectos do processo de renderização, incluindo tamanho da página, qualidade, marca d'água e muito mais.
### O Groupdocs.Viewer for .NET requer conectividade com a Internet?
Não, o Groupdocs.Viewer for .NET opera localmente em seu ambiente .NET e não requer conectividade com a Internet para visualização de documentos.
### O suporte técnico está disponível para Groupdocs.Viewer for .NET?
 Sim, o suporte técnico está disponível através do[Fórum de documentos de grupo](https://forum.groupdocs.com/c/viewer/9), onde você pode fazer perguntas, relatar problemas e interagir com a comunidade.
### Posso experimentar o Groupdocs.Viewer for .NET antes de comprar?
 Sim, você pode começar com uma avaliação gratuita usando o fornecido[versão de teste](https://releases.groupdocs.com/).