---
"description": "Aprimore seus aplicativos .NET com o GroupDocs.Viewer para uma visualização integrada de documentos. Integre facilmente funcionalidades de renderização de documentos aos seus projetos."
"linktitle": "Definir licença medida"
"second_title": "API .NET do GroupDocs.Viewer"
"title": "Definir licença medida"
"url": "/pt/net/getting-started/set-metered-license/"
"weight": 12
type: docs
---
# Definir licença medida

## Introdução
No mundo do desenvolvimento .NET, incorporar recursos avançados de visualização de documentos em seus aplicativos é essencial para aprimorar a experiência do usuário e a funcionalidade. O GroupDocs.Viewer para .NET oferece uma solução robusta para integrar perfeitamente funcionalidades de visualização de documentos em seus projetos .NET. Seja trabalhando com PDFs, documentos do Microsoft Office ou diversos formatos de imagem, o GroupDocs.Viewer simplifica o processo de renderização e exibição desses documentos em seus aplicativos.

![Defina a licença medida com o GroupDocs.Viewer para .NET](/viewer/getting-started/set-metered-license.png)

## Pré-requisitos
Antes de mergulhar na implementação do GroupDocs.Viewer para .NET, certifique-se de ter os seguintes pré-requisitos em vigor:
### 1. Instale o GroupDocs.Viewer para .NET
Para começar, você precisará baixar e instalar o GroupDocs.Viewer para .NET. Você pode encontrar o link para download [aqui](https://releases.groupdocs.com/viewer/net/). Siga as instruções de instalação fornecidas para configurar a biblioteca em seu ambiente de desenvolvimento.
### 2. Obtenha uma licença medida
Para utilizar o GroupDocs.Viewer para .NET, você precisa obter uma licença limitada. Esta licença permite controlar e monitorar o uso da sua API com base em cotas predefinidas. Siga os passos abaixo para configurar sua licença limitada:

## Importar namespaces
Primeiro, certifique-se de importar os namespaces necessários para acessar a funcionalidade fornecida pelo GroupDocs.Viewer para .NET:
```csharp
using System;
```

Agora, vamos dividir o código de exemplo fornecido em várias etapas:
## Etapa 1: Declarar chaves públicas e privadas
Declare variáveis para armazenar suas chaves públicas e privadas:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
Certifique-se de substituir `"YOUR_PUBLIC_KEY"` e `"YOUR_PRIVATE_KEY"` com suas chaves reais.
## Etapa 2: definir licença medida
Verifique se a chave pública foi fornecida. Caso contrário, solicite ao usuário que defina as chaves:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://purchase.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Etapa 3: Inicializar o objeto medido e definir a licença
Inicialize o objeto Metered e defina a licença medida usando suas chaves pública e privada:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Etapa 4: Mensagem de confirmação
Exibir uma mensagem de confirmação indicando que a licença foi definida com sucesso:
```csharp
Console.WriteLine("License set successfully.");
```

## Conclusão
Concluindo, o GroupDocs.Viewer para .NET oferece uma solução abrangente para incorporar funcionalidades de visualização de documentos em seus aplicativos .NET. Seguindo os passos descritos, você pode facilmente configurar uma licença limitada e começar a aproveitar os recursos do GroupDocs.Viewer em seus projetos.
## Perguntas frequentes
### P: Onde posso encontrar documentação do GroupDocs.Viewer para .NET?
Você pode encontrar a documentação [aqui](https://tutorials.groupdocs.com/viewer/net/).
### P: Existe uma avaliação gratuita disponível do GroupDocs.Viewer para .NET?
Sim, você pode acessar o teste gratuito [aqui](https://releases.groupdocs.com/).
### P: Como posso obter licenças temporárias para fins de testes?
Licenças temporárias podem ser obtidas [aqui](https://purchase.groupdocs.com/temporary-license/).
### P: Onde posso buscar suporte ou fazer perguntas relacionadas ao GroupDocs.Viewer para .NET?
Você pode buscar suporte e fazer perguntas no fórum GroupDocs.Viewer [aqui](https://forum.groupdocs.com/c/viewer/9).
### P: Onde posso comprar uma licença para o GroupDocs.Viewer para .NET?
Você pode comprar uma licença [aqui](https://purchase.groupdocs.com/buy).