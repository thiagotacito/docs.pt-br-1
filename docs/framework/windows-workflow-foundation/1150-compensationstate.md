---
title: 1150 - CompensationState
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5debccf664768b84a7b213cd012b484df8fe3ef8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="1150---compensationstate"></a>1150 - CompensationState
## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|1150|  
|Palavras-chave|WFActivities|  
|Nível|Informações|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/depuração|  
  
## <a name="description"></a>Descrição  
 Indica uma alteração de estado em um CompensableActivity.  
  
## <a name="message"></a>Mensagem  
 CompensableActivity “%1 " está em “%2 " estado.  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|DisplayName|xs:string|O nome para exibição de atividade.|  
|Estado|xs:string|O estado da compensação.|  
|AppDomain|xs:string|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|