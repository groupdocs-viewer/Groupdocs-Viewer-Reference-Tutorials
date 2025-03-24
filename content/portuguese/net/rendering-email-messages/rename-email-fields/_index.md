---
title: Renomear campos de e-mail durante a renderização
linktitle: Renomear campos de e-mail durante a renderização
second_title: API GroupDocs.Viewer .NET
description: Aprimore a experiência de visualização de documentos com GroupDocs.Viewer for .NET. Renderize e personalize e-mails perfeitamente.
weight: 12
url: /pt/net/rendering-email-messages/rename-email-fields/
---

# Renomear campos de e-mail durante a renderização

## Introdução

Na era digital de hoje, gerenciar e visualizar documentos de forma eficiente é fundamental para empresas e indivíduos. Quer se trate de contratos, relatórios ou e-mails, ter a capacidade de navegar perfeitamente por esses documentos pode aumentar muito a produtividade. É aqui que o GroupDocs.Viewer for .NET entra em ação. Esta poderosa biblioteca permite que os desenvolvedores integrem recursos de visualização de documentos diretamente em seus aplicativos .NET, oferecendo uma ampla gama de recursos para renderizar vários formatos de documentos.

## Pré-requisitos

Antes de mergulhar no tutorial sobre como renomear campos de e-mail durante a renderização usando GroupDocs.Viewer for .NET, certifique-se de ter os seguintes pré-requisitos:

1.  Biblioteca GroupDocs.Viewer for .NET: Baixe e instale a biblioteca GroupDocs.Viewer for .NET em[aqui](https://releases.groupdocs.com/viewer/net/).

2. Ambiente de desenvolvimento: certifique-se de ter um ambiente de desenvolvimento adequado configurado para desenvolvimento .NET, como Visual Studio.

3. Compreensão básica de C#: Familiarize-se com os fundamentos da linguagem de programação C#, pois o tutorial envolverá trechos de código C#.

4. Diretório de Documentos: Prepare um diretório onde sejam armazenados os documentos a serem renderizados.

## Importar namespaces

Para usar as funcionalidades do GroupDocs.Viewer em seu aplicativo .NET, você precisa importar os namespaces necessários.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Agora vamos dividir o processo de renomeação de campos de e-mail durante a renderização usando GroupDocs.Viewer for .NET em várias etapas:

## Etapa 1: definir o diretório de saída

Primeiramente, especifique o diretório onde as páginas HTML renderizadas serão salvas.

```csharp
string outputDirectory = "Your Document Directory";
```

## Etapa 2: definir o formato do caminho do arquivo de página

Defina o formato dos caminhos de arquivo das páginas HTML renderizadas. Cada página será salva como um arquivo HTML separado.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Etapa 3: inicializar o objeto visualizador

Crie uma instância da classe Viewer e passe como parâmetro o caminho do documento a ser visualizado.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## Etapa 4: configurar opções de visualização HTML

Configure as opções de visualização HTML, incluindo a especificação do formato do arquivo de saída e a configuração de mapeamentos de campos de e-mail.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## Etapa 5: renderizar documento

Invoque o método View do objeto Viewer, passando as opções de visualização HTML configuradas.

```csharp
viewer.View(options);
```

## Etapa 6: exibir mensagem de sucesso

Informe ao usuário que o documento foi renderizado com sucesso.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusão

Concluindo, GroupDocs.Viewer for .NET fornece uma solução perfeita para renderizar documentos em aplicativos .NET. Seguindo as etapas descritas neste tutorial, você pode renomear facilmente os campos de email durante a renderização, melhorando a legibilidade e a usabilidade dos documentos de email. Com sua API intuitiva e recursos abrangentes, GroupDocs.Viewer capacita os desenvolvedores a agilizar os processos de visualização de documentos de forma eficaz.

## Perguntas frequentes

### P: Posso renderizar documentos que não sejam e-mails usando GroupDocs.Viewer for .NET?

R: Sim, o GroupDocs.Viewer oferece suporte à renderização de vários formatos de documentos, incluindo PDF, documentos do Microsoft Office, imagens e muito mais.

### P: O GroupDocs.Viewer é compatível com o .NET Core?

R: Sim, o GroupDocs.Viewer oferece suporte ao .NET Core junto com o .NET Framework tradicional.

### P: Posso personalizar a aparência dos documentos renderizados?

R: Com certeza, o GroupDocs.Viewer oferece amplas opções de personalização para controlar a aparência e o comportamento dos documentos renderizados.

### P: O GroupDocs.Viewer oferece suporte ao streaming de documentos?

R: Sim, o GroupDocs.Viewer permite transmitir documentos diretamente para o navegador do cliente sem a necessidade de armazená-los no servidor.

### P: O GroupDocs.Viewer é adequado para aplicativos de nível empresarial?

R: Certamente, o GroupDocs.Viewer foi projetado para atender às demandas de aplicativos de nível empresarial com sua escalabilidade, confiabilidade e conjunto robusto de recursos.
