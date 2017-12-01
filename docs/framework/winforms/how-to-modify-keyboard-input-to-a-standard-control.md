---
title: "Como modificar a entrada do teclado para um controle padrão"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input [Windows Forms], modifying
- modifying keyboard input
- Windows Forms, modifying keyboard input
- keyboards [Windows Forms], keyboard input
ms.assetid: 626d3712-d866-4988-bcda-a2d5b36ec0ba
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2c95ba3ef1c590f5c7e5d5e89ed05cf28c7829d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-keyboard-input-to-a-standard-control"></a>Como modificar a entrada do teclado para um controle padrão
O Windows Forms fornece a capacidade de consumir e modificar as entradas do teclado. Consumir uma tecla significa tratá-la dentro de um método ou manipulador de eventos para que outros métodos e eventos mais adiante na fila de mensagens não recebam o valor da tecla. Modificar uma tecla significa modificar o valor de uma tecla para que os métodos e manipuladores de eventos mais adiante na fila de mensagens recebam um valor de tecla diferente. Este tópico mostra como realizar essas tarefas.  
  
### <a name="to-consume-a-key"></a>Consumir uma tecla  
  
-   Em um <xref:System.Windows.Forms.Control.KeyPress> manipulador de eventos, defina o <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> propriedade o <xref:System.Windows.Forms.KeyPressEventArgs> classe para `true`.  
  
     -ou-  
  
     Em um <xref:System.Windows.Forms.Control.KeyDown> manipulador de eventos, defina o <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> propriedade o <xref:System.Windows.Forms.KeyEventArgs> classe para `true`.  
  
    > [!NOTE]
    >  Definindo o <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> propriedade no <xref:System.Windows.Forms.Control.KeyDown> manipulador de eventos não impede que o <xref:System.Windows.Forms.Control.KeyPress> e <xref:System.Windows.Forms.Control.KeyUp> eventos sejam gerados para o pressionamento de tecla atual. Use o <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> propriedade para essa finalidade.  
  
     O exemplo a seguir é um trecho de um `switch` instrução que examina o <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> propriedade o <xref:System.Windows.Forms.KeyPressEventArgs> recebidas por um <xref:System.Windows.Forms.Control.KeyPress> manipulador de eventos. Esse código consome as teclas dos caracteres “A” e “a”.  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#6](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#6](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#6)]  
  
### <a name="to-modify-a-standard-character-key"></a>Modificar uma tecla de caractere padrão  
  
-   Em um <xref:System.Windows.Forms.Control.KeyPress> manipulador de eventos, defina o <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> propriedade do <xref:System.Windows.Forms.KeyPressEventArgs> classe para o valor da nova chave de caractere.  
  
     O exemplo a seguir é um trecho de uma instrução `switch` que modifica “B” para “A” e “b” para “a”. Observe que o <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> propriedade o <xref:System.Windows.Forms.KeyPressEventArgs> parâmetro está definido como `false`, para que o novo valor de chave é propagado para outros métodos e eventos na fila de mensagens.  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#7](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#7)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#7](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#7)]  
  
### <a name="to-modify-a-noncharacter-key"></a>Modificar uma tecla não caractere  
  
-   Substituir um <xref:System.Windows.Forms.Control> método que processa mensagens do Windows, detectar a mensagem WM_KEYDOWN ou WM_SYSKEYDOWN e defina o <xref:System.Windows.Forms.Message.WParam%2A> propriedade o <xref:System.Windows.Forms.Message> parâmetro para o <xref:System.Windows.Forms.Keys> valor que representa a nova chave não caractere.  
  
     O exemplo de código a seguir demonstra como substituir o <xref:System.Windows.Forms.Control.PreProcessMessage%2A> método de um controle para detectar as teclas F1 até F9 e modificar qualquer pressionamento de tecla F3 para F1. Para obter mais informações sobre <xref:System.Windows.Forms.Control> métodos que você pode substituir para interceptar mensagens de teclado, consulte [entrada do usuário em um aplicativo do Windows Forms](../../../docs/framework/winforms/user-input-in-a-windows-forms-application.md) e [como funciona a entrada do teclado](../../../docs/framework/winforms/how-keyboard-input-works.md).  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#12](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#12)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#12](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#12)]  
  
## <a name="example"></a>Exemplo  
 O exemplo de código a seguir é o aplicativo completo para os exemplos de código nas seções anteriores. O aplicativo usa um controle personalizado derivado de <xref:System.Windows.Forms.TextBox> classe para consumir e modificar a entrada do teclado.  
  
 [!code-csharp[System.Windows.Forms.KeyBoardInput#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInput#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Este exemplo requer:  
  
-   Referências aos assemblies System, System.Drawing e System.Windows.Forms.  
  
 Para obter informações sobre como criar este exemplo da linha de comando para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] ou [!INCLUDE[csprcs](../../../includes/csprcs-md.md)], consulte [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) (Compilação da linha de comando) ou [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) (Compilação da linha de comando com csc.exe). Também é possível compilar este exemplo em [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] colando o código em um novo projeto.  Consulte também [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)) (Como compilar e executar um exemplo completo de código dos Windows Forms usando o Visual Studio).  
  
## <a name="see-also"></a>Consulte também  
 [Entrada do teclado em um aplicativo dos Windows Forms](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [Entrada do usuário em um aplicativo dos Windows Forms](../../../docs/framework/winforms/user-input-in-a-windows-forms-application.md)  
 [Como a entrada do teclado funciona](../../../docs/framework/winforms/how-keyboard-input-works.md)