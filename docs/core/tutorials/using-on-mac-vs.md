---
title: "Introdução ao .NET Core em macOS usando o Visual Studio para Mac"
description: "Este tópico explica como compilar um aplicativo de console simples usando o Visual Studio para Mac e o .NET Core."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.topic: get-started-article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8902e849-dd17-42c0-8264-cc7ae3927a0c
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e11515031716a66ead866e52504137cb4e1df137
ms.contentlocale: pt-br
ms.lasthandoff: 07/28/2017

---

# <a name="getting-started-with-net-core-on-macos-using-visual-studio-for-mac"></a>Introdução ao .NET Core em macOS usando o Visual Studio para Mac

O Visual Studio para Mac fornece um IDE (Ambiente de desenvolvimento integrado) completo para desenvolver aplicativos .NET Core. Este tópico explica como compilar um aplicativo de console simples usando o Visual Studio para Mac e o .NET Core.

> [!NOTE]
> Seus comentários são muito importantes. Há duas maneiras de enviar comentários à equipe de desenvolvimento no Visual Studio para Mac:
> * No Visual Studio para Mac, escolha **Ajuda** > **Relatar um Problema** no menu, ou **Relatar um Problema** na tela de boas-vindas. Isso abrirá uma janela para registrar um relatório de bugs. Você pode acompanhar seus comentários no portal [Developer Community (Comunidade do Desenvolvedor)](https://developercommunity.visualstudio.com/spaces/8/index.html).
> * Para fazer uma sugestão, escolha **Ajuda** > **Forneça uma Sugestão** no menu, ou **Forneça uma Sugestão** na tela de boas-vindas. Isso levará você até a página de [UserVoice do Visual Studio para Mac](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac).

## <a name="prerequisites"></a>Pré-requisitos

Confira o tópico [Pré-requisitos para .NET Core no Mac](../../core/macos-prerequisites.md).

## <a name="getting-started"></a>Introdução

Se você já tiver instalado os pré-requisitos e o Visual Studio para Mac, ignore esta seção e vá até [Criar um projeto](#creating-a-project). Execute estas etapas para instalar os pré-requisitos e o Visual Studio para Mac:

Baixe o [Instalador do Visual Studio para Mac](https://www.visualstudio.com/vs/visual-studio-mac/). Execute o instalador. Leia e aceite o contrato de licença. Durante a instalação, você tem a oportunidade de instalar o Xamarin, uma tecnologia de desenvolvimento de aplicativo móvel multiplataforma. A instalação do Xamarin e de seus componentes relacionados é opcional para o desenvolvimento em .NET Core. Para conferir um passo a passo do processo de instalação do Visual Studio para Mac, veja [Introdução ao Visual Studio para Mac](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/). Após a conclusão da instalação, inicie o IDE do Visual Studio para Mac.

## <a name="creating-a-project"></a>Criar um projeto

1. Escolha **Novo Projeto** na tela de Boas-vindas.

   ![Botão Novo Projeto na tela de Boas-vindas do Visual Studio para Mac](./media/using-on-mac-vs/vsmac1.png)

1. Na caixa de diálogo **Novo Projeto**, selecione **Aplicativo** sob o nó **.NET Core**. Selecione o modelo **Aplicativo de Console** e logo depois **Avançar**.

   ![Lista de modelos de novo projeto](./media/using-on-mac-vs/vsmac2.png)

1. Digite "HelloWorld" para o **Nome do Projeto**. Selecione **Criar**.

   ![Configurar a caixa de diálogo Novo Aplicativo de Console](./media/using-on-mac-vs/vsmac3.png)

1. Aguarde enquanto as dependências do projeto são restauradas. O projeto tem um único arquivo em C#, *Program.cs*, que contém uma classe `Program` com um método `Main`. A instrução `Console.WriteLine` produzirá "Hello World!" no console quando o aplicativo for executado.

   ![Janela principal com o arquivo Program.cs aberto](./media/using-on-mac-vs/vsmac4.png)

## <a name="run-the-application"></a>Executar o aplicativo

Execute o aplicativo no modo Depuração usando <kbd>F5</kbd> ou no modo Versão usando <kbd>CTRL</kbd>+<kbd>F5</kbd>.

![O painel Saída do Aplicativo mostra Hello World!](./media/using-on-mac-vs/vsmac5.png)

## <a name="next-step"></a>Próximas etapas

O tópico [Compilar uma solução completa do .NET Core no macOS usando o Visual Studio para Mac](using-on-mac-vs-full-solution.md) mostra como compilar uma solução completa do .NET Core que inclui uma biblioteca reutilizável e testes de unidade.

