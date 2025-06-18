---
"description": "Integre perfeitamente o Groupdocs.Viewer para .NET aos seus projetos .NET para uma visualização eficiente de documentos."
"linktitle": "Cancelar renderização com token de cancelamento"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Cancelar renderização com token de cancelamento"
"url": "/pt/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
---

# Cancelar renderização com token de cancelamento

## Introdução
O Groupdocs.Viewer para .NET é uma ferramenta poderosa projetada para simplificar a visualização e o processamento de documentos em aplicativos .NET. Seja para PDFs, documentos do Microsoft Office ou outros formatos comuns, esta biblioteca oferece funcionalidades robustas para integrar perfeitamente os recursos de visualização de documentos aos seus projetos .NET.
## Pré-requisitos
Antes de mergulhar na integração do Groupdocs.Viewer para .NET, certifique-se de ter os seguintes pré-requisitos em vigor:
1. Instalação: Baixe e instale a biblioteca Groupdocs.Viewer para .NET fornecida [link para download](https://releases.groupdocs.com/viewer/net/).
   
2. Licença: Obtenha uma licença de [Groupdocs](https://purchase.groupdocs.com/buy) para desbloquear todo o potencial da biblioteca. Alternativamente, você pode começar com um teste gratuito usando o [licença temporária](https://purchase.groupdocs.com/temporary-license/).
   
3. Ambiente de desenvolvimento: certifique-se de ter um ambiente de desenvolvimento compatível configurado, incluindo o Visual Studio ou qualquer outro IDE .NET de sua escolha.

## Importar namespaces
Para utilizar o Groupdocs.Viewer para .NET de forma eficaz, você precisa importar os namespaces necessários para o seu projeto. Siga estes passos:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Agora, vamos dividir o exemplo fornecido em várias etapas para melhor compreensão e implementação:
## Etapa 1: definir diretório de saída
```csharp
string outputDirectory = "Your Document Directory";
```
Esta etapa define o diretório onde as páginas do documento renderizado serão armazenadas.
## Etapa 2: Definir o formato do caminho do arquivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Aqui, definimos o formato para os caminhos de arquivo das páginas individuais do documento.
## Etapa 3: Inicializar CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource é usado para gerar instâncias de CancellationToken que podem ser usadas para cancelar operações assíncronas.
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
Esta etapa define um tempo limite de 10 milissegundos para a operação de renderização. Se a operação exceder esse tempo limite, ela será cancelada automaticamente.
## Etapa 7: Exibir mensagem de sucesso
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Por fim, uma mensagem de sucesso é exibida indicando que o documento foi renderizado com sucesso.

## Conclusão
Neste tutorial, abordamos os princípios básicos da integração do Groupdocs.Viewer para .NET aos seus projetos. Seguindo os passos descritos acima, você pode incorporar recursos de visualização de documentos aos seus aplicativos .NET, aprimorando a experiência do usuário e a produtividade.
## Perguntas frequentes
### O Groupdocs.Viewer para .NET é compatível com todos os formatos de documento?
O Groupdocs.Viewer para .NET suporta uma ampla variedade de formatos de documentos, incluindo PDF, documentos do Microsoft Office, imagens e muito mais.
### Posso personalizar a aparência das páginas do documento renderizadas?
Sim, você pode personalizar vários aspectos do processo de renderização, incluindo tamanho da página, qualidade, marca d'água e muito mais.
### O Groupdocs.Viewer para .NET requer conectividade com a internet?
Não, o Groupdocs.Viewer para .NET opera localmente no seu ambiente .NET e não requer conectividade com a Internet para visualização de documentos.
### Há suporte técnico disponível para o Groupdocs.Viewer para .NET?
Sim, o suporte técnico está disponível através do [Fórum Groupdocs](https://forum.groupdocs.com/c/viewer/9), onde você pode fazer perguntas, relatar problemas e interagir com a comunidade.
### Posso testar o Groupdocs.Viewer para .NET antes de comprar?
Sim, você pode começar com um teste gratuito usando o fornecido [versão de teste](https://releases.groupdocs.com/).