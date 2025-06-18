---
"date": "2025-04-25"
"description": "Aprenda como converter arquivos TXT em vários formatos como HTML, JPG, PNG e PDF usando o GroupDocs.Viewer para .NET com este guia abrangente."
"title": "Converta TXT para HTML, JPG, PNG, PDF usando GroupDocs.Viewer .NET - Um guia completo"
"url": "/pt/net/export-conversion/groupdocs-viewer-dotnet-txt-conversion-guide/"
"weight": 1
---

# Converta TXT para vários formatos com GroupDocs.Viewer .NET

## Introdução

Quer converter documentos de texto para vários formatos, como HTML, JPG, PNG ou PDF, sem esforço? Gerenciar conversões de documentos pode ser desafiador, especialmente quando se trata de várias páginas ou requisitos de formato específicos. **GroupDocs.Viewer para .NET** simplifica o processo de renderização de arquivos TXT em diversos formatos de saída, garantindo que seus dados sejam acessíveis e visualmente atraentes.

![Converta TXT para HTML, JPG, PNG, PDF com GroupDocs.Viewer para .NET](/viewer/export-conversion/convert-txt-to-html-jpg-png-pdf.png)

Neste guia, exploraremos como usar o GroupDocs.Viewer para .NET para transformar documentos TXT em HTML de várias páginas, HTML de uma única página, JPG, PNG e PDF. Ao final, você dominará:
- Convertendo arquivos TXT usando C# com GroupDocs.Viewer
- Implementando diferentes opções de renderização para suas necessidades
- Otimizando o desempenho durante conversões

Vamos nos aprofundar para resolver seus desafios de conversão de documentos.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte pronto:
- **Ambiente de Desenvolvimento**: Visual Studio 2019 ou posterior.
- **Estrutura .NET**: Versão 4.6.1 ou superior.
- **Biblioteca GroupDocs.Viewer para .NET**:
  - Por meio do console do gerenciador de pacotes NuGet: `Install-Package GroupDocs.Viewer -Version 25.3.0`
  - Usando o .NET CLI: `dotnet add package GroupDocs.Viewer --version 25.3.0`

É recomendável ter familiaridade com programação em C# e operações básicas de arquivo no .NET para acompanhar com facilidade.

## Configurando o GroupDocs.Viewer para .NET

### Instalação

Para começar, instale o **GroupDocs.Viewer** biblioteca usando seu gerenciador de pacotes preferido:

#### Console do gerenciador de pacotes NuGet
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

#### .NET CLI
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Licenciamento

Você pode começar com um **teste gratuito** ou obter um **licença temporária** para explorar todos os recursos do GroupDocs.Viewer para .NET sem limitações de avaliação:
- Teste gratuito: [Baixe aqui](https://releases.groupdocs.com/viewer/net/)
- Licença temporária: [Solicite aqui](https://purchase.groupdocs.com/temporary-license/)

Para uso contínuo, considere comprar uma licença diretamente de [Documentos do Grupo](https://purchase.groupdocs.com/buy).

### Inicialização básica

Para configurar o GroupDocs.Viewer no seu projeto:

```csharp
using System.IO;
using GroupDocs.Viewer;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");

// Inicialize o objeto Viewer com um caminho de arquivo TXT.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Seu código de renderização ficará aqui.
}
```

## Guia de Implementação

Agora, vamos nos aprofundar em cada recurso e ver como você pode implementá-los.

### Renderizar documento TXT para HTML de várias páginas

#### Visão geral
Este recurso demonstra a conversão de um documento TXT para o formato HTML de várias páginas. Cada página do arquivo de texto é renderizada como um arquivo HTML individual com recursos incorporados.

#### Etapa 1: Configurar o Visualizador

Criar um `Viewer` objeto para seu arquivo TXT de origem:

```csharp
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");

// Inicialize o Visualizador com um arquivo de texto de exemplo.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Continue para o passo 2...
```

#### Etapa 2: Configurar opções de visualização HTML

Configurar `HtmlViewOptions` para renderizar cada página separadamente:

```csharp
// Configure opções de visualização HTML para renderização de várias páginas.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);

// Renderize o documento como HTML de várias páginas.
viewer.View(options);
}
```

**Explicação**: O `ForEmbeddedResources()` O método garante que recursos como imagens e estilos sejam incorporados diretamente no arquivo HTML, facilitando o compartilhamento.

### Renderizar documento TXT em HTML de página única

#### Visão geral
Converta um documento TXT em uma única página HTML, ideal para documentos que precisam ser exibidos como uma página da web contínua.

#### Etapa 1: Configurar o Visualizador

Inicializar o `Viewer` objeto:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");

// Inicialize uma nova instância do Viewer para um arquivo de texto diferente.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample2.txt")))
{
    // Continue para o passo 2...
```

#### Etapa 2: Configurar opções de HTML de página única

Configurar `HtmlViewOptions` com a configuração de página única habilitada:

```csharp
// Configure opções para renderização em uma única página HTML.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
options.RenderToSinglePage = true;

// Renderizar como uma única página HTML.
viewer.View(options);
}
```

**Explicação**: O `RenderToSinglePage` propriedade garante que todo o conteúdo seja renderizado em uma página.

### Renderizar documento TXT para JPG

#### Visão geral
Este recurso permite converter um documento de texto em uma imagem JPEG, útil para apresentações visuais ou fins de arquivamento.

#### Etapa 1: Configurar o Visualizador

Prepare seu `Viewer` objeto:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");

// Inicialize o visualizador com um arquivo de amostra.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Continue para o passo 2...
```

#### Etapa 2: Configurar opções de visualização JPG

Configurar `JpgViewOptions` para renderização de imagem:

```csharp
// Configure opções para renderização como uma imagem JPG.
JpgViewOptions options = new JpgViewOptions(pageFileFullPath);

// Renderize o documento como um arquivo JPEG.
viewer.View(options);
}
```

**Explicação**: O `JpgViewOptions` A classe especifica como renderizar e salvar cada página do seu documento no formato JPEG.

### Renderizar documento TXT para PNG

#### Visão geral
Converta um documento de texto para o formato PNG, oferecendo saída de imagem de alta qualidade com suporte a transparência.

#### Etapa 1: Configurar o Visualizador

Inicializar o `Viewer` objeto:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");

// Crie uma instância do visualizador para seu arquivo TXT.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Continue para o passo 2...
```

#### Etapa 2: Configurar opções de visualização PNG

Configurar `PngViewOptions`:

```csharp
// Configure opções de visualização para renderização como uma imagem PNG.
PngViewOptions options = new PngViewOptions(pageFileFullPath);

// Renderize o documento no formato PNG.
viewer.View(options);
}
```

**Explicação**: O `PngViewOptions` A classe permite que cada página seja renderizada com transparência, tornando-a adequada para gráficos em camadas.

### Renderizar documento TXT para PDF

#### Visão geral
Este recurso é perfeito para converter documentos de texto em um formato PDF universalmente acessível.

#### Etapa 1: Configurar o Visualizador

Prepare seu `Viewer` objeto:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");

// Inicialize uma instância do visualizador para seu arquivo de texto de exemplo.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Continue para o passo 2...
```

#### Etapa 2: Configurar opções de visualização de PDF

Configurar `PdfViewOptions`:

```csharp
// Configure opções de visualização para renderização como um documento PDF.
PdfViewOptions options = new PdfViewOptions(pageFileFullPath);

// Renderize o documento em um arquivo PDF.
viewer.View(options);
}
```

**Explicação**: O `PdfViewOptions` A classe especifica como converter e salvar seus arquivos TXT como documentos PDF.

## Conclusão

Com o GroupDocs.Viewer para .NET, converter documentos de texto para vários formatos é simples. Este guia abordou a transformação de arquivos TXT em HTML de várias páginas, HTML de uma única página, JPG, PNG e PDF usando C#. Se você busca aprimorar a acessibilidade ou a compatibilidade de documentos, esses métodos oferecem soluções robustas.

Para obter mais assistência ou recursos mais avançados, consulte o [documentação oficial do GroupDocs.Viewer](https://docs.groupdocs.com/viewer/net/). Boa codificação!