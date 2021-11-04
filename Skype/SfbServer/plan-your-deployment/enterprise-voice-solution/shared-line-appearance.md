---
title: Planejar a aparência de linha compartilhada no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: Leia este tópico para saber como planejar a Aparência de Linha Compartilhada (SLA) no Skype for Business Server 2015, Atualização Cumulativa de novembro de 2015.
ms.openlocfilehash: dbe90a1d506f8d90e66ae065b9f31d95897e8c9a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759483"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>Planejar a aparência de linha compartilhada no Skype for Business Server 2015
 
Leia este tópico para saber como planejar a Aparência de Linha Compartilhada (SLA) no Skype for Business Server 2015, Atualização Cumulativa de novembro de 2015. 
  
Aparência de Linha Compartilhada é um recurso no Skype for Business para lidar com várias chamadas em um número específico chamado um número compartilhado. O SLA pode configurar qualquer usuário habilitado para voz corporativa Skype for Business como um número compartilhado com várias linhas para responder a várias chamadas. As chamadas não são realmente recebidas no número compartilhado, em vez disso, elas são encaminhadas aos usuários que atuam como representantes do número compartilhado. Qualquer um dos representantes pode atender a chamada enquanto o restante dos representantes recebe uma notificação em seu telefone sobre quem a recebeu e qual linha ficou ocupada como resultado. O número de linhas e os representantes são configuráveis para um número compartilhado no SLA. Além disso, opções avançadas, como BusyOption (o que acontece em uma situação quando todas as linhas estão ocupadas) e MissedCallOption (caso em que nenhum dos representantes atende uma chamada), também pode ser configurada para um número compartilhado.
  
O SLA só tem suporte nos seguintes dispositivos telefônicos (não há suporte para clientes Skype for Business em computadores, telefones celulares ou outros dispositivos): 
  
- Polycom VVX300 com atualização de firmware 5.4.1
    
- Polycom VVX400 com atualização de firmware 5.4.1
    
- Polycom VVX500 com atualização de firmware 5.4.1
    
- Polycom VVX600 com atualização de firmware 5.4.1
    
O SLA é um novo recurso no Skype for Business Server, Atualização Cumulativa de novembro de 2015. 
  
Para obter informações sobre como implantar o SLA, consulte [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).
  
## <a name="feature-list"></a>Lista de Recursos

Configurar um grupo SLA habilita o seguinte:
  
- Todos os representantes do grupo podem responder chamadas de entrada para o mesmo número compartilhado. As chamadas podem ser baseadas em PSTN ou baseadas em SIP.
    
- Os representantes podem segurar e atender chamadas.
    
- Os representantes podem transferir chamadas para um número fora do grupo SLA.
    
- Os representantes podem ver quantas chamadas estão atualmente no número compartilhado e exibir o status de cada uma dessas chamadas.
    
- Você pode configurar um número máximo de chamadas simultâneas para o número compartilhado. Você também pode definir como deseja que as chamadas adicionais sejam manipuladas depois que esse máximo for atingido. Chamadas em excesso podem ser rejeitadas com um sinal de ocupado, encaminhadas para um número alternativo ou encaminhadas para a caixa postal.
    
- Você pode configurar como deseja que chamadas perdidas (chamadas não a atender após um determinado tempo) sejam manipuladas. Se você habilitar a caixa postal para a identidade do grupo, as chamadas perdidas automaticamente vão para a caixa postal. Se você não tiver a caixa postal habilitada para a identidade do grupo (número compartilhado), você poderá optar por chamadas perdidas a serem rejeitadas com um sinal de ocupado, encaminhadas para um número alternativo ou desconectadas.
    

