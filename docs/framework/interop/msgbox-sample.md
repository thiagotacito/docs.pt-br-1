---
title: Exemplo de MsgBox
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- marshaling, MsgBox sample
- data marshaling, MsgBox sample
ms.assetid: 9e0edff6-cc0d-4d5c-a445-aecf283d9c3a
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0f6ef3407c5f06e04d7a8b882a6458f236886dea
ms.contentlocale: pt-br
ms.lasthandoff: 08/21/2017

---
# <a name="msgbox-sample"></a>Exemplo de MsgBox
Esta amostra demonstra como passar tipos de cadeia de caracteres por valor como parâmetros In e quando usar os campos <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> e <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>.  
  
 A amostra de MsgBox usa a seguinte função não gerenciada, mostrada com a respectiva declaração de função original:  
  
-   **MessageBox** exportada de User32.dll.  
  
    ```  
    int MessageBox(HWND hWnd, LPCTSTR lpText, LPCTSTR lpCaption,   
       UINT uType);  
    ```  
  
 Nesta amostra, a classe `LibWrap` contém um protótipo gerenciado para cada função não gerenciada chamado pela classe `MsgBoxSample`. Os métodos de protótipo gerenciado `MsgBox`, `MsgBox2` e `MsgBox3` têm declarações diferentes para a mesma função não gerenciada.  
  
 A declaração para `MsgBox2` produz uma saída incorreta na caixa de mensagem porque o tipo de caractere, especificado como ANSI, é incompatível com o ponto de entrada `MessageBoxW`, que é o nome da função Unicode. A declaração `MsgBox3` cria uma incompatibilidade entre os campos **EntryPoint**, **CharSet** e **ExactSpelling**. Quando chamado, `MsgBox3` gera uma exceção. Para obter informações detalhadas sobre a nomeação de cadeia de caracteres e marshaling de nome, consulte [Especificando um conjunto de caracteres](../../../docs/framework/interop/specifying-a-character-set.md).  
  
## <a name="declaring-prototypes"></a>Declarando Protótipos  
 [!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)] [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)] [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]  
  
## <a name="calling-functions"></a>Chamando Funções  
 [!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)] [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)] [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]  
  
## <a name="see-also"></a>Consulte também  
 [Marshaling em cadeias de caracteres](../../../docs/framework/interop/marshaling-strings.md)   
 [Tipos de Dados de Invocação de Plataforma](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f)   
 [Marshaling padrão para cadeias de caracteres](../../../docs/framework/interop/default-marshaling-for-strings.md)   
 [Criando protótipos em código gerenciado](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Especificando um conjunto de caracteres](../../../docs/framework/interop/specifying-a-character-set.md)

