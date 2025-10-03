---
"date": "2025-04-25"
"description": "Aprenda a converter páginas PDF em imagens PNG, preservando as dimensões originais, usando o GroupDocs.Viewer para .NET. Este guia aborda a instalação, configuração e práticas recomendadas."
"title": "Converta PDFs para PNG com tamanho original usando o GroupDocs.Viewer para .NET"
"url": "/pt/net/export-conversion/convert-pdfs-to-png-groupdocs-viewer-net/"
"weight": 1
type: docs
---
# Converta PDFs para PNG com tamanho original usando o GroupDocs.Viewer para .NET

## Introdução

Converter arquivos PDF em imagens PNG, mantendo o tamanho original da página, é essencial para a digitalização de documentos de alta qualidade ou para a preparação de conteúdo para a web. Este tutorial o guiará pelo uso do GroupDocs.Viewer para .NET para renderizar páginas PDF como arquivos PNG, preservando suas dimensões originais.

![Converta PDFs para PNG com tamanho original com GroupDocs.Viewer para .NET](/viewer/export-conversion/convert-pdfs-to-png-with-original-size.png)

**O que você aprenderá:**
- Como configurar e configurar o GroupDocs.Viewer para .NET em seu projeto
- Processo passo a passo de renderização de PDFs em imagens PNG, mantendo o tamanho das páginas
- Principais opções de configuração e práticas recomendadas para desempenho ideal

Ao final deste tutorial, você será capaz de integrar essa funcionalidade aos seus aplicativos perfeitamente. Vamos começar com os pré-requisitos necessários para começar.

## Pré-requisitos

Antes de implementar o GroupDocs.Viewer para .NET em seu projeto, certifique-se de ter os seguintes requisitos:

### Bibliotecas e versões necessárias
- **GroupDocs.Viewer para .NET**: Versão 25.3.0 ou posterior.

### Requisitos de configuração do ambiente
- Um ambiente de desenvolvimento compatível, como o Visual Studio.
- Noções básicas de programação em C#.

### Pré-requisitos de conhecimento
- Familiaridade com o gerenciamento de pacotes NuGet.
- Alguma experiência trabalhando com PDFs e processamento de imagens em aplicativos .NET.

Depois de atender a esses pré-requisitos, podemos prosseguir com a configuração do GroupDocs.Viewer para .NET.

## Configurando o GroupDocs.Viewer para .NET

Para começar a usar o GroupDocs.Viewer para .NET, siga as etapas de instalação abaixo:

### Instalação via console do gerenciador de pacotes NuGet
Abra seu projeto no Visual Studio e use o seguinte comando:
```plaintext
Install-Package GroupDocs.Viewer -Version 25.3.0
```

### Instalação via .NET CLI
Como alternativa, você pode instalá-lo usando o .NET CLI com este comando:
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Etapas de aquisição de licença
1. **Teste grátis**: Baixe uma versão de teste em [Downloads do GroupDocs](https://releases.groupdocs.com/viewer/net/).
2. **Licença Temporária**: Obtenha uma licença temporária para explorar todos os recursos em [Página de Licença Temporária](https://purchase.groupdocs.com/temporary-license/).
3. **Comprar**:Para uso prolongado, adquira uma licença através do [Página de compra](https://purchase.groupdocs.com/buy).

### Inicialização e configuração básicas
Para inicializar o GroupDocs.Viewer para .NET no seu projeto C#, siga estas etapas:
1. Importe os namespaces necessários:
    ```csharp
    using System;
    using GroupDocs.Viewer;
    using GroupDocs.Viewer.Options;
    ```
2. Configure os caminhos para o seu PDF de entrada e diretório de saída.
3. Inicializar `Viewer` com o caminho para o seu documento de origem, conforme mostrado neste trecho:
   ```csharp
   string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
   string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
   string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";

   using (Viewer viewer = new Viewer(documentPath))
   {
       PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
       viewer.View(viewOptions);
   }
   ```

## Guia de Implementação
Esta seção aborda a implementação da renderização de páginas PDF como imagens PNG, mantendo seu tamanho original.

### Renderizando páginas PDF para PNG com tamanho de página original
#### Visão geral
Este recurso permite renderizar cada página de um documento PDF em uma imagem PNG, preservando suas dimensões originais. Isso é particularmente útil para aplicativos que exigem representação visual precisa de documentos.

##### Etapa 1: Configurar caminhos e inicializar o visualizador
Crie variáveis para o caminho de entrada do PDF e o diretório de saída:
```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";
```
Inicializar o `Viewer` classe com o caminho do seu documento de origem:
```csharp
using (Viewer viewer = new Viewer(documentPath))
{
    // O bloco de código continuará na próxima etapa
}
```
##### Etapa 2: Configurar PngViewOptions
Crie uma instância de `PngViewOptions`, especificando um padrão de nomenclatura de arquivo para as imagens de saída:
```csharp
PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
```
Configure as opções do visualizador para renderizar cada página em seu tamanho original:
```csharp
viewOptions.PdfOptions.RenderOriginalPageSize = true;
```
##### Etapa 3: renderizar páginas do documento
Ligue para o `View` método em seu `Viewer` por exemplo, passando as opções de visualização configuradas:
```csharp
viewer.View(viewOptions);
```
### Dicas para solução de problemas
- Certifique-se de que os caminhos estejam corretos e que os diretórios existam.
- Verifique se você tem as permissões necessárias para ler os diretórios de entrada e gravar nos diretórios de saída.

## Aplicações práticas
1. **Digitalização de documentos**: Converta documentos PDF arquivados em imagens digitais para facilitar acesso e distribuição.
2. **Portais da Web**: Exiba visualizações de documentos em sites sem precisar de leitores de PDF.
3. **Sistemas de gerenciamento de conteúdo (CMS)**: Integre-se com plataformas CMS para gerenciar e exibir grandes volumes de conteúdo PDF com eficiência.

## Considerações de desempenho
Para otimizar o desempenho do seu aplicativo usando o GroupDocs.Viewer para .NET:
- Limite o uso de memória processando documentos em blocos se estiver lidando com arquivos grandes.
- Use métodos assíncronos sempre que possível para evitar o bloqueio de threads durante a renderização.
- Descarte de `Viewer` instâncias imediatamente após o uso para liberar recursos.

## Conclusão
Neste tutorial, você aprendeu a renderizar páginas PDF como imagens PNG, mantendo seus tamanhos originais, usando o GroupDocs.Viewer para .NET. Abordamos a configuração do seu ambiente, a configuração das opções necessárias para obter os melhores resultados e exploramos aplicações práticas para essa funcionalidade.

As próximas etapas incluem experimentar outras opções de renderização disponíveis no GroupDocs.Viewer ou integrá-lo a projetos maiores para aprimorar os recursos de gerenciamento de documentos.

## Seção de perguntas frequentes
1. **Qual é a melhor maneira de lidar com arquivos PDF grandes com o GroupDocs.Viewer?**
   - Processe documentos em pedaços menores e use métodos assíncronos para manter o desempenho.
2. **Posso personalizar os nomes dos arquivos PNG de saída?**
   - Sim, especificando um padrão de nomenclatura em `PngViewOptions`.
3. **É possível renderizar apenas páginas específicas?**
   - Com certeza, você pode configurar `PageNumbers` em `PngViewOptions` para especificar quais páginas renderizar.
4. **Como faço para gerenciar o licenciamento do GroupDocs.Viewer?**
   - As opções incluem um teste gratuito, uma licença temporária ou a compra de uma licença completa.
5. **Esta configuração pode ser usada em aplicações web?**
   - Sim, ele é adequado para renderização de PDFs no lado do servidor no ASP.NET Core e outras estruturas da web baseadas em .NET.

## Recursos
- [Documentação](https://docs.groupdocs.com/viewer/net/)
- [Referência de API](https://reference.groupdocs.com/viewer/net/)
- [Baixar GroupDocs.Viewer](https://releases.groupdocs.com/viewer/net/)
- [Licença de compra](https://purchase.groupdocs.com/buy)
- [Teste grátis](https://releases.groupdocs.com/viewer/net/)
- [Licença Temporária](https://purchase.groupdocs.com/temporary-license/)
- [Fórum de Suporte](https://forum.groupdocs.com/c/viewer/9)