---
title: "-debug (opções do compilador C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /debug
dev_langs:
- CSharp
helpviewer_keywords:
- debug compiler option [C#]
- -debug compiler option [C#]
- /debug compiler option [C#]
ms.assetid: e2b48c07-01bc-45cc-a52c-92e9085eb969
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 82656c8354288dd2f7e5b0dcb2905b6c050c0521
ms.contentlocale: pt-br
ms.lasthandoff: 07/28/2017

---
# <a name="debug-c-compiler-options"></a>/debug (opções do compilador C#)
A opção **/debug** faz o compilador gerar informações de depuração e colocá-las no(s) arquivo(s) de saída.  
  
## <a name="syntax"></a>Sintaxe  
  
```console  
/debug[+ | -]  
/debug:{full | pdbonly}  
```  
  
## <a name="arguments"></a>Arguments  
 `+` &#124; `-`  
 Especificar `+` ou apenas executar o **/debug** faz o compilador gerar informações de depuração e colocá-las em um de banco de dados do programa (arquivo .pdb). Especificar `-`, que será aplicado se **/debug** não for especificado, não cria nenhuma informação de depuração.  
  
 `full` &#124; `pdbonly`  
 Especifica o tipo de informações de depuração geradas pelo compilador. O argumento completo, que será aplicado se **/debug:pdbonly** não for especificado, habilita anexar um depurador ao programa em execução. Especificar pdbonly habilita a depuração do código-fonte quando o programa é iniciado no depurador, mas exibirá somente o assembler quando o programa em execução for anexado ao depurador.  
  
## <a name="remarks"></a>Comentários  
 Use essa opção para criar builds de depuração. Caso **/debug**, **/debug+** ou **/debug:full** não forem especificados, não será possível depurar o arquivo de saída do programa.  
  
 Caso **/debug:full** seja usado, lembre-se de que isso influenciará a velocidade e o tamanho do código otimizado JIT e haverá um pequeno impacto na qualidade do código com **/debug:full**. Recomenda-se **/debug:pdbonly** ou nenhum PDB para gerar código de versão.  
  
> [!NOTE]
>  Uma diferença entre **/debug:pdbonly** e **/debug:full** é que, com **/debug:full**, o compilador emite uma <xref:System.Diagnostics.DebuggableAttribute>, que é usada para avisar ao compilador JIT que as informações de depuração estão disponíveis. Portanto, haverá um erro se o código contiver <xref:System.Diagnostics.DebuggableAttribute> definido como false, caso **/debug:full** seja usado.  
  
 Para obter informações sobre como configurar o desempenho de depuração de um aplicativo, consulte [Facilitando a Depuração de uma Imagem](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).  
  
 Para alterar o local do arquivo .pdb, consulte [/pdb (Opções do Compilador C#)](../../../csharp/language-reference/compiler-options/pdb-compiler-option.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para definir esta opção do compilador no ambiente de desenvolvimento do Visual Studio  
  
1.  Abra a página **Propriedades** do projeto.  
  
2.  Clique na página de propriedades **Compilar**.  
  
3.  Clique no botão **Avançado**.  
  
4.  Modifique a propriedade **Informações de Depuração**.  
  
 Para obter informações sobre como definir essa opção do compilador programaticamente, consulte <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DebugSymbols%2A>.  
  
## <a name="example"></a>Exemplo  
 Coloque as informações de depuração no arquivo de saída `app.pdb`:  
  
```console  
csc /debug /pdb:app.pdb test.cs  
```  
  
## <a name="see-also"></a>Consulte também  
 [Opções do compilador do C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Gerenciando propriedades de solução e de projeto](/visualstudio/ide/managing-project-and-solution-properties)

