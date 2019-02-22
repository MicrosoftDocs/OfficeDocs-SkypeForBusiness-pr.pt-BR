---
title: Planejar Aparência de linha compartilhada no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: Leia este tópico para saber como planejar para Shared linha aparência (SLA) no Skype 2015 do servidor de negócios, novembro de 2015 atualizações cumulativas.
ms.openlocfilehash: b65d637426b0a8533089b21021bce566373ca9f1
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "23884505"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>Planejar Aparência de linha compartilhada no Skype for Business Server 2015
 
Leia este tópico para saber como planejar para Shared linha aparência (SLA) no Skype 2015 do servidor de negócios, novembro de 2015 atualizações cumulativas. 
  
Aparência da linha compartilhado é um recurso do Skype for Business para lidar com várias chamadas em um número específico de um número compartilhado chamado. SLA pode configurar qualquer enterprise voice habilitado Skype para comercial do usuário como um número compartilhado com várias linhas para responder a várias chamadas. As chamadas não serão realmente recebidas no número compartilhado, em vez disso, elas serão encaminhadas para os usuários que atuam como representantes para o número compartilhado. Qualquer um dos representantes pode atender a chamada enquanto o restante dos representantes recebe uma notificação no telefone sobre quem obteve o convite e que linha ficou ocupada como resultado. Tanto o número de linhas quanto os representantes são configuráveis para um número compartilhado no SLA. Além disso, as opções avançadas, como BusyOption (o que acontece em uma situação quando todas as linhas estão ocupadas) e MissedCallOption (caso em que nenhum dos representantes atende uma chamada), também podem ser configuradas para um número compartilhado.
  
SLA tem suporte apenas nos seguintes dispositivos telefônicos (ele não há suporte para Skype para clientes corporativos nos computadores, telefones celulares ou outros dispositivos): 
  
- Polycom VVX300 com atualização de firmware 5.4.1
    
- Polycom VVX400 com atualização de firmware 5.4.1
    
- Polycom VVX500 com atualização de firmware 5.4.1
    
- Polycom VVX600 com atualização de firmware 5.4.1
    
SLA é um novo recurso do Skype para Business Server, novembro de 2015 atualizações cumulativas. 
  
Para obter informações sobre como implantar o SLA, consulte [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).
  
## <a name="feature-list"></a>Lista de recursos

Configuração de um grupo de SLA permite o seguinte:
  
- Todos os representantes do grupo podem atender chamadas de entrada para o mesmo número compartilhado. As chamadas podem ser baseadas em PSTN ou em SIP.
    
- Os representantes podem reter e atender chamadas.
    
- Os representantes podem transferir chamadas para um número externo do grupo SLA.
    
- Os representantes podem ver quantas chamadas estão atualmente no número compartilhado e ver o estado de cada uma delas.
    
- Você pode configurar um número máximo de chamadas simultâneas para o número compartilhado. Você também pode definir como deseja que as chamadas adicionais sejam manipuladas depois que esse máximo for atingido. As chamadas em excesso podem ser rejeitadas com um sinal de ocupado, encaminhadas para um número alternativo ou encaminhadas para o correio de voz.
    
- Você pode configurar como você deseja que as chamadas não atendidas (chamadas não atendidas após um determinado período de tempo) sejam tratadas. Se você ativar o correio de voz para a identidade do grupo, as chamadas não atendidas automaticamente irão para o correio de voz. Se você não tiver correio de voz habilitado para a identidade do grupo (número compartilhado), você poderá escolher que as chamadas perdidas sejam rejeitadas com um sinal de ocupado, encaminhadas para um número alternativo ou desconectadas.
    

