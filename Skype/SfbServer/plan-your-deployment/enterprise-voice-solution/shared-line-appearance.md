---
title: Planejar aparência de linha compartilhada no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: Leia este tópico para saber como planejar a Aparência de Linha Compartilhada (SLA) no Skype for Business Server 2015, atualização cumulativa de novembro de 2015.
ms.openlocfilehash: d7fa13b36c232e37c79e8509de71b4ac29ceff72
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813341"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>Planejar aparência de linha compartilhada no Skype for Business Server 2015
 
Leia este tópico para saber como planejar a Aparência de Linha Compartilhada (SLA) no Skype for Business Server 2015, atualização cumulativa de novembro de 2015. 
  
Aparência de linha compartilhada é um recurso no Skype for Business para lidar com várias chamadas em um número específico chamado número compartilhado. O SLA pode configurar qualquer usuário do Skype for Business habilitado para enterprise voice como um número compartilhado com várias linhas para responder a várias chamadas. As chamadas não são realmente recebidas no número compartilhado, em vez disso, são encaminhadas aos usuários que atuam como representantes do número compartilhado. Qualquer um dos representantes pode atender a chamada enquanto o restante dos representantes recebe uma notificação no telefone sobre quem a atende e qual linha está ocupada como resultado. Tanto o número de linhas quanto os representantes são configuráveis para um número compartilhado no SLA. Além disso, opções avançadas, como BusyOption (o que acontece em uma situação quando todas as linhas estão ocupadas) e MissedCallOption (o caso em que nenhum dos representantes atende uma chamada), também podem ser configuradas para um número compartilhado.
  
O SLA só tem suporte nos seguintes dispositivos telefônicos (não há suporte para clientes do Skype for Business em computadores, telefones celulares ou outros dispositivos): 
  
- Polycom VVX300 com atualização de firmware 5.4.1
    
- Polycom VVX400 com atualização de firmware 5.4.1
    
- Polycom VVX500 com atualização de firmware 5.4.1
    
- Polycom VVX600 com atualização de firmware 5.4.1
    
O SLA é um novo recurso do Skype for Business Server, atualização cumulativa de novembro de 2015. 
  
Para obter informações sobre como implantar o SLA, consulte [Deploy Shared Line Appearance in Skype for Business Server 2015.](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)
  
## <a name="feature-list"></a>Lista de Recursos

A configuração de um grupo SLA permite o seguinte:
  
- Todos os representantes do grupo podem atender chamadas de entrada para o mesmo número compartilhado. As chamadas podem ser baseadas em PSTN ou SIP.
    
- Os representantes podem segurar e atender chamadas.
    
- Os representantes podem transferir chamadas para um número fora do grupo SLA.
    
- Os representantes podem ver quantas chamadas estão atualmente no número compartilhado e exibir o status de cada uma dessas chamadas.
    
- Você pode configurar um número máximo de chamadas simultâneas para o número compartilhado. Você também pode definir como deseja que as chamadas adicionais sejam tratadas depois que esse máximo for atingido. Chamadas em excesso podem ser rejeitadas com um sinal de ocupado, encaminhadas para um número alternativo ou encaminhadas para a caixa postal.
    
- Você pode configurar como deseja que as chamadas perdidas (chamadas não a escolhidas após um determinado tempo) sejam tratadas. Se você habilitar a caixa postal para a identidade do grupo, as chamadas perdidas serão automaticamente para a caixa postal. Se você não tiver uma caixa postal habilitada para a identidade do grupo (número compartilhado), poderá optar por que as chamadas perdidas sejam rejeitadas com um sinal de ocupado, encaminhadas para um número alternativo ou desconectadas.
    

