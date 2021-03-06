---
title: marshaling de interoperabilidade
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
- marshaling, COM interop
- interop marshaling
- interop marshaling, about interop marshaling
ms.assetid: 115f7a2f-d422-4605-ab36-13a8dd28142a
caps.latest.revision: 22
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ebe7d3aa48fa77287f20781938a0b9863f60de5f
ms.contentlocale: pt-br
ms.lasthandoff: 08/21/2017

---
# <a name="interop-marshaling"></a>marshaling de interoperabilidade
<a name="top"></a> O marshaling de interoperabilidade controla como os dados são passados em argumentos de método e valores retornados entre memória gerenciada e não gerenciada e durante chamadas. O marshaling de interoperabilidade é uma atividade de tempo de execução executada pelo serviço de marshaling do Common Language Runtime.  
  
 A maioria dos tipos de dados têm representações comuns tanto na memória gerenciada quanto na não gerenciada. O marshaler de interoperabilidade manipula esses tipos para você. Outros tipos podem ser ambíguos ou não representados em absoluto na memória gerenciada.  
  
 Um tipo ambíguo pode ter várias representações não gerenciadas que são mapeadas para um único tipo gerenciado ou ter informações de tipo ausentes, tais como o tamanho de uma matriz. Para tipos ambíguos, o marshaler fornece uma representação padrão e representações alternativas em que existem várias representações. Você pode fornecer instruções explícitas para o marshaler sobre como ele deve realizar marshaling de um tipo ambíguo.  
  
 Esta visão geral contém as seguintes seções:  
  
-   [Invocação de plataforma e modelos de interoperabilidade COM](#platform_invoke_and_com_interop_models)  
  
-   [Marshaling e apartments COM](#marshaling_and_com_apartments)  
  
-   [Marshaling de chamadas remotas](#marshaling_remote_calls)  
  
-   [Tópicos relacionados](#related_topics)  
  
-   [Referência](#reference)  
  
<a name="platform_invoke_and_com_interop_models"></a>   
## <a name="platform-invoke-and-com-interop-models"></a>Invocação de plataforma e modelos de interoperabilidade COM  
 O common language runtime fornece dois mecanismos para interoperação com código não gerenciado:  
  
-   Invocação de plataforma, que permite que o código gerenciado chame funções exportadas de uma biblioteca não gerenciada.  
  
-   Interoperabilidade COM, que permite que o código gerenciado interaja com objetos COM (Component Object Model) por meio de interfaces.  
  
 Tanto a invocação de plataforma quanto a interoperabilidade COM usam marshaling de interoperabilidade para mover com precisão os argumentos de método entre o chamador e o receptor e vice-versa, se necessário. Conforme mostra a ilustração a seguir, uma chamada de método de invocação de plataforma flui do código gerenciado para código não gerenciado e nunca na direção contrária, exceto quando [funções de retorno de chamada](../../../docs/framework/interop/callback-functions.md) estão envolvidas. Embora as chamadas de invocação de plataforma possam fluir somente de código gerenciado para código não gerenciado, os dados podem fluir em ambas as direções como parâmetros de entrada ou de saída. As chamadas de método de interoperabilidade COM podem fluir em ambas as direções.  
  
 ![Invocação de plataforma](../../../docs/framework/interop/media/interopmarshaling.png "interopmarshaling")  
Invocação de plataforma e fluxo de chamada de interoperabilidade COM  
  
 No nível mais baixo, ambos os mecanismos usam o mesmo serviço de marshaling de interoperabilidade; no entanto, alguns tipos de dados têm suporte apenas pela interoperabilidade COM ou pela invocação de plataforma. Para obter detalhes, consulte [Comportamento de marshaling padrão](../../../docs/framework/interop/default-marshaling-behavior.md).  
  
 [Voltar ao início](#top)  
  
<a name="marshaling_and_com_apartments"></a>   
## <a name="marshaling-and-com-apartments"></a>Marshaling e apartments COM  
 O marshaler de interoperabilidade realiza marshaling de dados entre o heap do Common Language Runtime e o heap não gerenciado. O marshaling ocorre sempre que o chamador e o receptor não podem operar na mesma instância dos dados. O marshaler de interoperabilidade torna possível que o chamador e o receptor pareçam estar funcionando nos mesmos dados, mesmo que eles tenham sua própria cópia dos dados.  
  
 O COM também tem um marshaler que realiza marshaling de dados entre apartments COM ou processos COM diferentes. Ao chamar entre código gerenciado e código não gerenciado dentro do mesmo apartment COM, o marshaler de interoperabilidade é o único marshaler envolvido. Ao chamar entre código gerenciado e o código não gerenciado em um apartment COM diferente ou um processo diferente, tanto o marshaler de interoperabilidade quanto o marshaler COM estão envolvidos.  
  
### <a name="com-clients-and-managed-servers"></a>Clientes COM e servidores gerenciados  
 Um servidor gerenciado exportado com uma biblioteca de tipos registrada pelo [Regasm.exe (Ferramenta de Registro de Assembly)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) tem uma `ThreadingModel` entrada do Registro definida como `Both`. Esse valor indica que o servidor pode ser ativado em um STA (Single-Threaded Apartment) ou um MTA (Multi-Threaded Apartment). O objeto de servidor é criado no mesmo apartment que o chamador dele, conforme mostrado na tabela a seguir.  
  
|Cliente COM|.NET Server|Requisitos de marshaling|  
|----------------|-----------------|-----------------------------|  
|STA|`Both` se torna isso STA.|Marshaling no mesmo apartment.|  
|MTA|`Both` se torna MTA.|Marshaling no mesmo apartment.|  
  
 Já que o cliente e o servidor estão no mesmo apartment, o serviço de marshaling de interoperabilidade manipula automaticamente todo o marshaling de dados. A ilustração a seguir mostra o serviço de marshaling de interoperabilidade funcionando entre heaps gerenciados e não gerenciados dentro do mesmo apartment de estilo COM.  
  
 ![Marshaling de interoperabilidade](../../../docs/framework/interop/media/interopheap.gif "interopheap")  
Processo de marshaling no mesmo apartment  
  
 Se você planeja exportar um servidor gerenciado, lembre-se de que o cliente COM determina o apartment do servidor. Um servidor gerenciado chamado por um cliente COM inicializado em um MTA deve assegurar acesso thread-safe.  
  
### <a name="managed-clients-and-com-servers"></a>Clientes gerenciados e servidores COM  
 A configuração padrão para apartments de cliente gerenciado é MTA; no entanto, o tipo de aplicativo do cliente .NET pode alterar a configuração padrão. Por exemplo, a configuração de apartment de um cliente [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] é STA. Você pode usar uma das propriedades <xref:System.STAThreadAttribute?displayProperty=fullName>, <xref:System.MTAThreadAttribute?displayProperty=fullName>, <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=fullName> ou <xref:System.Web.UI.Page.AspCompatMode%2A?displayProperty=fullName> para examinar e alterar a configuração de apartment de um cliente gerenciado.  
  
 O autor do componente define a afinidade do thread de um servidor COM. A tabela a seguir mostra as combinações de configurações de apartment de clientes .NET e servidores COM. Ele também mostra os requisitos de marshaling resultantes para as combinações.  
  
|Cliente .NET|Servidor COM|Requisitos de marshaling|  
|-----------------|----------------|-----------------------------|  
|MTA (padrão)|MTA<br /><br /> STA|Marshaling de interoperabilidade.<br /><br /> Marshaling COM e de interoperabilidade.|  
|STA|MTA<br /><br /> STA|Marshaling COM e de interoperabilidade.<br /><br /> Marshaling de interoperabilidade.|  
  
 Quando um cliente gerenciado e servidor não gerenciado estão no mesmo apartment, o serviço de marshaling de interoperabilidade manipula todo o marshaling de dados. No entanto, quando o cliente e servidor são inicializados em apartments diferentes, o marshaling de COM também é necessário. A ilustração a seguir mostra os elementos de uma chamada entre apartments.  
  
 ![Marshaling COM](../../../docs/framework/interop/media/singleprocessmultapt.gif "singleprocessmultapt")  
Chamada entre apartments entre um cliente .NET e um objeto COM  
  
 Para realizar marshaling entre apartments, você pode fazer o seguinte:  
  
-   Aceite a sobrecarga de marshaling de apartment cruzada, que é perceptível somente quando há muitas chamadas entre dos limites. Você deve registrar a biblioteca de tipos do componente COM para que chamadas cruzem o limite do apartment com êxito.  
  
-   Altere o thread principal, definindo o thread de cliente para STA ou MTA. Por exemplo, se o cliente C# chama muitos componentes COM STA, você pode evitar marshaling entre apartments definindo o thread principal para STA.  
  
    > [!NOTE]
    >  Depois que o thread de um cliente C# for definido para STA, chamadas para componentes COM MTA exigirão marshaling entre apartments.  
  
 Para obter instruções sobre como selecionar explicitamente um modelo de apartment, consulte [Threading gerenciado e não gerenciado](http://msdn.microsoft.com/en-us/db425c20-4b2f-4433-bf96-76071c7881e5).  
  
 [Voltar ao início](#top)  
  
<a name="marshaling_remote_calls"></a>   
## <a name="marshaling-remote-calls"></a>Marshaling de chamadas remotas  
 Assim como ocorre com marshaling entre apartments, o marshaling COM está envolvido em cada chamada entre código gerenciado e código não gerenciado e sempre que os objetos residem em processos separados. Por exemplo:  
  
-   Um cliente COM que invoca um servidor gerenciado em um host remoto usa COM distribuído (DCOM).  
  
-   Um cliente gerenciado que chama um servidor COM em um host remoto usa DCOM.  
  
 A ilustração a seguir mostra como o marshaling de interoperabilidade e o marshaling COM fornecem canais de comunicação entre os limites de processo e de host.  
  
 ![Marshaling COM](../../../docs/framework/interop/media/interophost.gif "interophost")  
Marshaling entre processos  
  
### <a name="preserving-identity"></a>Preservação de identidade  
 O Common Language Runtime preserva a identidade de referências gerenciadas e não gerenciados. A ilustração a seguir mostra o fluxo de referências diretas não gerenciadas (linha superior) e referências diretas gerenciadas (linha inferior) entre limites de processo e de host.  
  
 ![COM Callable Wrapper e Runtime Callable Wrapper](../../../docs/framework/interop/media/interopdirectref.gif "interopdirectref")  
Referência passando entre limites de processo e de host  
  
 Nessa ilustração:  
  
-   Um cliente não gerenciado obtém uma referência para um objeto COM de um objeto gerenciado que obtém essa referência de um host remoto. O mecanismo de comunicação remota é DCOM.  
  
-   Um cliente gerenciado obtém uma referência para um objeto gerenciado de um objeto COM que obtém essa referência de um host remoto. O mecanismo de comunicação remota é DCOM.  
  
    > [!NOTE]
    >  A biblioteca de tipos exportada do servidor gerenciado deve ser registrada.  
  
 O número de limites de processo entre o chamador e o receptor é irrelevante; a mesma referência direta ocorre para chamadas em processo e fora de processo.  
  
### <a name="managed-remoting"></a>Comunicação remota gerenciada  
 O tempo de execução também fornece comunicação remota gerenciada, que pode ser usada para estabelecer um canal de comunicação entre os objetos gerenciados entre limites de processo e de host. A comunicação remota gerenciada pode acomodar um firewall entre os componentes que estão se comunicando, conforme mostra a ilustração a seguir.  
  
 ![SOAP ou TcpChannel](../../../docs/framework/interop/media/interopremotesoap.gif "interopremotesoap")  
Chamadas remotas através de firewalls usando SOAP ou a classe TcpChannel  
  
 Algumas chamadas não gerenciadas podem ser canalizadas via SOAP, assim como as chamadas entre [componentes de serviço](http://msdn.microsoft.com/en-us/f109ee24-81ad-4d99-9892-51ac6f34978c) e COM.  
  
 [Voltar ao início](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>Tópicos relacionados  
  
|Título|Descrição|  
|-----------|-----------------|  
|[Comportamento de marshaling padrão](../../../docs/framework/interop/default-marshaling-behavior.md)|Descreve as regras que o serviço de marshaling de interoperabilidade usa para realizar marshaling de dados.|  
|[Marshaling de dados com a invocação de plataforma](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)|Descreve como declarar parâmetros de método e passar argumentos para funções exportadas por bibliotecas não gerenciadas.|  
|[Realizando marshaling em dados com interoperabilidade COM](../../../docs/framework/interop/marshaling-data-with-com-interop.md)|Descreve como personalizar os wrappers COM para alterar o comportamento de marshaling.|  
|[Como: migrar código DCOM gerenciado para o WCF](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)|Descreve como migrar do DCOM para o WCF.|  
|[Como mapear HRESULTs e exceções](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)|Descreve como mapear exceções personalizadas para HRESULTs e fornece o mapeamento completo de cada HRESULT para a respectiva classe de exceção comparável no .NET Framework.|  
|[Interoperação usando tipos genéricos](http://msdn.microsoft.com/en-us/26b88e03-085b-4b53-94ba-a5a9c709ce58)|Descreve quais ações têm suporte ao usar tipos genéricos para interoperabilidade COM.|  
|[Interoperação com código não gerenciado](../../../docs/framework/interop/index.md)|Descreve os serviços de interoperabilidade fornecidos pelo Common Language Runtime.|  
|[Interoperabilidade COM avançada](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)|Fornece links para obter mais informações sobre como incorporar componentes COM no aplicativo do .NET Framework.|  
|[Considerações sobre design para interoperação](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)|Fornece dicas para escrever componentes COM integrados.|  
  
 [Voltar ao início](#top)  
  
<a name="reference"></a>   
## <a name="reference"></a>Referência  
 <xref:System.Runtime.InteropServices?displayProperty=fullName>  
  
 [Voltar ao início](#top)

