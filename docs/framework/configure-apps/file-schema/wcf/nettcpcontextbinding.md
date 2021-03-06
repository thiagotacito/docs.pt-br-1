---
title: '&lt;netTcpContextBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d4715e1-5fff-4c3d-a226-18f21d0b30c4
caps.latest.revision: 13
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e4da2dadfb1a3995edff9836f5a2bbedde1e156d
ms.contentlocale: pt-br
ms.lasthandoff: 09/25/2017

---
# <a name="ltnettcpcontextbindinggt"></a>&lt;netTcpContextBinding&gt;
Especifica um contexto para o <xref:System.ServiceModel.NetTcpBinding> que requer que o nível de proteção seja assinado. O contextExchangeMechanism para NetTcpContextBinding é SOAPHeader.  
  
 \<sistema. ServiceModel >  
\<associações >  
\<netTcpContextBinding >  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<netTcpContextBinding>  
   <binding   
      closeTimeout="TimeSpan"  
            contextProtectionLevel="EncryptAndSign/None/Sign"  
      hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
      listenBacklog="Integer"  
      maxBufferPoolSize="integer"  
      maxBufferSize="Integer"  
      maxConnections="Integer"   
      maxReceivedMessageSize="Integer"  
            name="string"  
      openTimeout="TimeSpan"  
      portSharingEnabled="Boolean"  
      receiveTimeout="TimeSpan"  
      sendTimeout="TimeSpan"  
      transactionFlow="Boolean"   
      transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"   
            transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"  
  
      <reliableSession ordered="Boolean"  
            inactivityTimeout="TimeSpan"  
            enabled="Boolean" />  
      <security mode="Message/None/Transport/TransportWithCredential">  
           <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
                proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                realm="string"   
                defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
                defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                defaultRealm="string" />  
          <message clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
           algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
           establishSecurityContext="Boolean"   
           negotiateServiceCredential="Boolean"/>  
       </security>  
       <readerQuotas             maxArrayLength="Integer"            maxBytesPerRead="Integer"            maxDepth="Integer"             maxNameTableCharCount="Integer"                     maxStringContentLength="Integer" />   </binding>  
</netTcpContextBinding>  
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|closeTimeout|Um <xref:System.TimeSpan> valor que especifica o intervalo de tempo fornecido para uma operação de fechamento concluir. Esse valor deve ser maior ou igual a <xref:System.TimeSpan.Zero>. O padrão é 00:01:00.|  
|contextProtectionLevel|Uma opção válida <xref:System.Net.Security.ProtectionLevel> valor que especifica o nível de proteção desejado do cabeçalho SOAP usado para propagar as informações de contexto.  O valor padrão é `Sign`.|  
|hostnameComparisonMode|Especifica o modo de comparação de nome de host HTTP usado para analisar URIs. Esse atributo é do tipo `System.ServiceModel.HostnameComparisonMode`, que indica se o nome do host é usado para acessar o serviço ao fazer correspondência no URI. O valor padrão é `StrongWildcard`, que ignora o nome do host na correspondência.|  
|listenBacklog|Um inteiro positivo que especifica o número máximo de canais esperando para serem aceitos no ouvinte. Conexões exceder esse limite são enfileiradas até que espaço abaixo do limite se torne disponível. O `connectionTimeout` atributo limita o tempo que um cliente aguardará antes de ser conectado antes de gerar uma exceção de conexão. O padrão é 10.|  
|maxBufferPoolSize|Um inteiro que especifica o tamanho do pool de buffer máximo para esta associação. O padrão é 512 * 1024 bytes. Muitas partes do Windows Communication Foundation (WCF) usam buffers. Criação e destruição de buffers de cada vez que elas são usadas são caro e coleta de lixo para buffers também é cara. Com os pools de buffer, usar um buffer do pool, usá-lo e retorná-lo ao pool quando terminar. Portanto, a sobrecarga na criação e destruição de buffers é evitada.|  
|maxBufferSize|Um inteiro positivo que especifica o tamanho máximo, em bytes, do buffer usado para armazenar mensagens na memória. Se o buffer estiver cheio, o excesso de dados permanece no soquete subjacente até que o buffer tem espaço novamente. Esse valor não pode ser menor que `maxReceivedMessageSize` atributo. O padrão é 65536. Para obter mais informações, consulte <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.|  
|maxConnections|Um inteiro que especifica o número máximo de conexões de entrada e saídas de serviço cria/aceitará. Conexões de entrada e saídas são contados em relação a um limite separado especificado por esse atributo.<br /><br /> Excedendo o limite de conexões de entrada são enfileiradas até que um espaço abaixo do limite se torne disponível.<br /><br /> Conexões de saída além do limite são enfileiradas até que um espaço abaixo do limite se torne disponível.<br /><br /> O padrão é 10.|  
|maxReceivedMessageSize|Um inteiro positivo que especifica o tamanho máximo, em bytes, incluindo os cabeçalhos, o que podem ser recebidos em um canal configurado com essa associação. O remetente de uma mensagem exceder esse limite recebem uma falha SOAP. O receptor descartará a mensagem e cria uma entrada do evento no log de rastreamento. O padrão é 65536.|  
|name|Uma cadeia de caracteres que contém o nome da configuração da associação. Esse valor deve ser exclusivo, porque ele é usado como uma identificação para a associação. Começando com [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], associações e comportamentos não precisam ter um nome. Para obter mais informações sobre a configuração padrão e associações de nomes e comportamentos, consulte [configuração simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) e [configuração simplificada para serviços WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|openTimeout|Um <xref:System.TimeSpan> valor que especifica o intervalo de tempo fornecido para uma operação de abertura concluir. Esse valor deve ser maior ou igual a <xref:System.TimeSpan.Zero>. O padrão é 00:01:00.|  
|portSharingEnabled|Um valor booleano que especifica se o compartilhamento de porta TCP está habilitado para esta conexão. Se isso for `false`, cada associação usa sua própria porta exclusiva. Essa configuração é relevante apenas para os serviços, porque os clientes não são afetados.|  
|receiveTimeout|Um <xref:System.TimeSpan> valor que especifica o intervalo de tempo fornecido para uma operação de recebimento concluir. Esse valor deve ser maior ou igual a <xref:System.TimeSpan.Zero>. O padrão é 00:10:00.|  
|sendTimeout|Um <xref:System.TimeSpan> valor que especifica o intervalo de tempo fornecido para uma operação de envio concluir. Esse valor deve ser maior ou igual a <xref:System.TimeSpan.Zero>. O padrão é 00:01:00.|  
|transactionFlow|Um valor booleano que especifica se a associação oferece suporte a fluxo de transações de WS. O padrão é `false`.|  
|transactionProtocol|Especifica o protocolo de transação a ser usado com essa associação. Os valores válidos são<br /><br /> -OleTransactions<br />-WSAtomicTransactionOctober2004<br /><br /> O padrão é OleTransactions. Esse atributo é do tipo <xref:System.ServiceModel.TransactionProtocol>.|  
|transferMode|Um <xref:System.ServiceModel.TransferMode> valor que especifica se as mensagens são armazenados em buffer ou transmitidas ou uma solicitação ou resposta.|  
  
### <a name="child-elements"></a>Elementos filho  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<segurança >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|Define as configurações de segurança para a associação. Esse elemento é do tipo <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.|  
|[\<readerQuotas >](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|Define as restrições na complexidade de mensagens SOAP que podem ser processadas por pontos de extremidade configurados com essa associação. Esse elemento é do tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[reliableSession](http://msdn.microsoft.com/en-us/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|Especifica se as sessões confiáveis são estabelecidas entre pontos de extremidade de canal.|  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<associações >](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Esse elemento contém uma coleção de associações padrão e personalizadas.|  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.ServiceModel.NetTcpBinding>   
 <xref:System.ServiceModel.NetTcpContextBinding>   
 <xref:System.ServiceModel.Configuration.NetTcpContextBindingElement>   
 <xref:System.ServiceModel.Channels.ContextBindingElement>   
 [\<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)   
 [Associações](../../../../../docs/framework/wcf/bindings.md)   
 [Configurando associações fornecidas pelo sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Usando associações para configurar clientes e serviços do Windows Communication Foundation](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<associação >](../../../../../docs/framework/misc/binding.md)

