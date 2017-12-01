---
title: "Processamento de Espaço em branco em XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- East Asian characters [XAML Services]
- XAML [XAML Services], whitespace processing
- whitespace processing in XAML [XAML Services]
- characters [XAML Services], East Asian
ms.assetid: cc9cc377-7544-4fd0-b65b-117b90bb0b23
caps.latest.revision: "20"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 80b75897f54136849aa4b356c414145510d9cd3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="whitespace-processing-in-xaml"></a>Processamento de Espaço em branco em XAML
As regras de linguagem XAML de estado que espaço em branco significativo deve ser processado por um [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] implementação do processador. Este tópico documenta essas regras da linguagem XAML. Ele também documenta o tratamento de espaço em branco adicional que é definido pelo [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] implementação do processador XAML e o gravador XAML para serialização.  
  
<a name="whitespace_definition"></a>   
## <a name="whitespace-definition"></a>Definição de espaço em branco  
 Consistente com [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)], caracteres de espaço em branco no [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] são espaço, alimentação de linha e tab. Eles correspondem do [!INCLUDE[TLA#tla_unicode](../../../includes/tlasharptla-unicode-md.md)] valores 0020, 000A e 0009 respectivamente.  
  
<a name="whitespace_normalization"></a>   
## <a name="whitespace-normalization"></a>Normalização de espaço em branco  
 Por padrão a normalização de espaço em branco a seguir ocorre quando um [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processos de processador um [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] arquivo:  
  
1.  Caracteres de alimentação de linha entre caracteres do Leste Asiático são removidos. Consulte a seção "Caracteres do Leste Asiático" mais adiante neste tópico para obter uma definição do termo.  
  
2.  Todos os caracteres de espaço em branco (espaço, alimentação de linha, guia) são convertidos em espaços.  
  
3.  Todos os espaços consecutivos são excluídos e substituídos por um espaço.  
  
4.  Um espaço imediatamente após a marca de início é excluído.  
  
5.  Um espaço imediatamente antes da marca de fim é excluído.  
  
 "Default" corresponde ao estado denotado pelo valor padrão da [XML: space](../../../docs/framework/xaml-services/xml-space-handling-in-xaml.md) atributo.  
  
<a name="whitespace_in_inner_text_and_string_primitives"></a>   
## <a name="whitespace-in-inner-text-and-string-primitives"></a>Espaço em branco no texto interno e String primitivas  
 As regras de normalização anteriores se aplicam a texto interno encontrada dentro de elementos XAML. Após a normalização, um processador XAML Converte qualquer texto interno em um tipo apropriado, da seguinte maneira:  
  
-   Se o tipo da propriedade não é uma coleção, mas não é diretamente um <xref:System.Object> tipo, o processador XAML tenta converter para aquele tipo usando o conversor de tipos. Uma falha de conversão aqui causará um erro de tempo de compilação.  
  
-   Se o tipo da propriedade é uma coleção e o texto interno for contíguo (nenhuma intervenção elemento marcas), o texto interno é analisado como uma única <xref:System.String>. Se o tipo de coleção não pode aceitar <xref:System.String>, isso também faz com que um erro de tempo de compilação.  
  
-   Se o tipo da propriedade for <xref:System.Object>, o texto interno é analisado como uma única <xref:System.String>. Se existirem marcas de elemento intervenientes, isso causará um erro de tempo de compilação porque o <xref:System.Object> tipo implica um único objeto (<xref:System.String> ou de outra forma).  
  
-   Se o tipo da propriedade é uma coleção, e o texto interno não é contíguo, a primeira substring é convertida em um <xref:System.String> e adicionado como um item de coleção, o elemento intermediárias é adicionado como um item de coleção, e finalmente é a subcadeia de caracteres à direita (se houver) adicionado à coleção como um terceiro <xref:System.String> item.  
  
<a name="preserving_whitespace"></a>   
## <a name="preserving-whitespace"></a>Preservar espaço em branco  
 Há várias técnicas para preservar espaço em branco na fonte de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] para eventual apresentação que não são afetados por [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] normalização de espaço em branco do processador.  
  
 **XML: space = "preserve"**: especificar esse atributo no nível de elemento onde preservação de espaço em branco é desejada. Isso mantém todos os espaços, que inclui os espaços que podem ser adicionados por aplicativos de edição de código para "impressão bonita" em branco alinha elementos como um aninhamento visualmente intuitivo. No entanto, se esses espaços são renderizados é determinado pelo modelo de conteúdo para o elemento que contém. Evite especificar `xml:space="preserve"` no nível raiz porque a maioria dos modelos de objeto não considera o espaço em branco como significativas independentemente de como você definir o atributo. Configuração `xml:space` global pode ter consequências de desempenho de processamento (particularmente serialização) em algumas implementações de XAML. É uma melhor prática apenas definir o atributo especificamente no nível de elementos que renderiza espaço em branco em cadeias de caracteres, ou são coleções de espaço em branco significativo.  
  
 **Entidades e espaços não separáveis**: [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] oferece suporte para colocar qualquer [!INCLUDE[TLA#tla_unicode](../../../includes/tlasharptla-unicode-md.md)] entidade dentro de um modelo de objeto de texto. Você pode usar entidades dedicadas, como espaço incondicional (&\#160; em codificação UTF-8). Você também pode usar controles de rich text que oferecem suporte a caracteres de espaço incondicional. Você deve ter cuidado se você estiver usando entidades para simular características de layout, como identação, porque a saída de tempo de execução das entidades irão variar com base em um número maior de fatores que os recursos para produzir resultados de recuo em um típico sistema de layout, como uso adequado de painéis e margens. Por exemplo, as entidades são mapeadas para as fontes e podem alterar o tamanho em resposta a seleção de fonte do usuário.  
  
<a name="east_asian_characters"></a>   
## <a name="east-asian-characters"></a>Caracteres do Leste Asiático  
 "Caracteres do Leste Asiático" são definidos como um conjunto de [!INCLUDE[TLA2#tla_unicode](../../../includes/tla2sharptla-unicode-md.md)] varia de caractere U + 20000 a U + 2FFFD e U + 30000 até U + 3FFFD. Esse subconjunto às vezes também é conhecido como "Ideogramas CJK". Para obter mais informações, consulte [http://www.unicode.org](http://www.unicode.org/).  
  
<a name="whitespace_and_text_content_models"></a>   
## <a name="whitespace-and-text-content-models"></a>Modelos de conteúdo de texto e espaços em branco  
 Na prática, preservar espaço em branco é somente de interesse para um subconjunto de todos os modelos de conteúdo possíveis. Esse subconjunto é composto de modelos de conteúdo que podem levar a um singleton <xref:System.String> tipo de alguma forma, um dedicado <xref:System.String> coleção ou uma mistura de <xref:System.String> e outros tipos em uma <xref:System.Collections.IList> ou <xref:System.Collections.Generic.ICollection%601> coleção.  
  
### <a name="whitespace-and-text-content-models-in-wpf"></a>Modelos de conteúdo de espaço em branco e o texto no WPF  
 Para fins de ilustração, o restante desta seção faz referência a tipos específicos que são definidos pelo WPF. Os recursos de tratamento de espaço em branco são descritos neste tópico são geralmente relevantes para os serviços do .NET Framework XAML e WPF. Para ver esse comportamento em ação, você pode experimentar alguns marcação XAML WPF, exibir os resultados em um gráfico de objeto e serializar para marcação novamente.  
  
 Mesmo para modelos de conteúdo que pode receber cadeias de caracteres, o comportamento padrão dentro desses modelos de conteúdo é que qualquer espaço em branco que permanece não é tratado como significativo. Por exemplo, <xref:System.Windows.Controls.ListBox> leva um <xref:System.Collections.IList>, mas o espaço em branco (como alimentação de linha entre cada <xref:System.Windows.Controls.ListBoxItem>) não é preservado e não processado. Se você tentar usar alimentações de linha como separadores entre cadeias de caracteres para <xref:System.Windows.Controls.ListBoxItem> itens, ele não funciona em todos os; as cadeias de caracteres que são separadas por alimentação de linha são tratadas como uma cadeia de caracteres e um item.  
  
 As coleções que tratam o espaço em branco como significativas normalmente fazem parte do modelo de documento de fluxo. A coleção principal que oferece suporte ao comportamento preservação de espaço em branco é <xref:System.Windows.Documents.InlineCollection>. Essa classe de coleção é declarado com o <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>; quando esse atributo for encontrado, o [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processador tratará o espaço em branco dentro da coleção como significativo. A combinação de `xml:space="preserve"` e espaços em branco em uma <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> indicado coleção é que todos os espaços em branco é preservado e renderizados. A combinação de `xml:space="default"` e espaços em branco em uma <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> faz com que a normalização de espaço em branco inicial descrita anteriormente, que deixa um espaço em determinadas posições e esses espaços é preservadas e renderizados. Qual o comportamento é desejável cabe a você, e você deve usar `xml:space` seletivamente para habilitar o comportamento que você deseja.  
  
 Além disso, determinados elementos embutidos que denota um linebreak em um modelo de documento de fluxo devem deliberadamente não apresentar um espaço extra mesmo em uma coleção de espaço em branco significativo. Por exemplo, o <xref:System.Windows.Documents.LineBreak> elemento tem a mesma finalidade que o \<BR / > marca em [!INCLUDE[TLA2#tla_html](../../../includes/tla2sharptla-html-md.md)]e para facilitar a leitura na marcação, normalmente um <xref:System.Windows.Documents.LineBreak> é separado de qualquer texto subsequente por uma alimentação de linha. Esse avanço de linha não deve ser normalizado para se tornar um espaço à esquerda na linha subsequente. Para ativar esse comportamento, a definição de classe para o <xref:System.Windows.Documents.LineBreak> elemento se aplica a <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>, que depois é interpretado pelo [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processador significa que o espaço em branco ao redor <xref:System.Windows.Documents.LineBreak> sempre é cortado.  
  
## <a name="see-also"></a>Consulte também  
 [Visão geral de XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Entidades e XAML de caractere XML](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)  
 [Tratamento de xml:space em XAML](../../../docs/framework/xaml-services/xml-space-handling-in-xaml.md)