---
title: Plano para implantações do servidor de borda no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Resumo: planeje o ambiente do Skype for Business Server Edge. Este tópico apresenta os conceitos de borda e permite que você se organize com nossos tópicos mais detalhados.'
ms.openlocfilehash: 536ab82ec6845c55a0ee067ad8c1a4f5d9b9e153
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277157"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Plano para implantações do servidor de borda no Skype for Business Server
 
**Resumo:** Planeje o ambiente do Skype for Business Server Edge. Este tópico apresenta os conceitos de borda e permite que você se organize com nossos tópicos mais detalhados.
  
Quando você tem um ambiente do Skype for Business Server que está funcionando bem internamente, a próxima etapa para você pode ser apresentar um servidor de borda ou um pool de bordas para o ambiente. Essa função seria vital se você quiser que os serviços fornecidos pelo Skype for Business Server sejam usados por pessoas que estão fora da sua rede interna. Isso pode incluir:
  
- Usuários remotos: funcionários remotos, temporariamente ou de modo contínuo.
    
- Usuários federados: os funcionários de sua organização parceira.
    
- Usuários móveis.
    
- Clientes em potencial, parceiros e até usuários anônimos que você quer convidar para reuniões e apresentações.
    
O acesso de usuários externos, que é o servidor de borda fornecido, permite que tudo isso aconteça. Seus usuários internos poderão aproveitar os seguintes serviços hospedados pela implantação do Skype for Business Server:
  
- Mensagens instantâneas e presença para comunicação: usuários externos autorizados podem participar em conversas de mensagens instantâneas e conferências. Eles obter as informações de presença de outros usuários (que também recebem suas informações de presença). Você não poderá fazer conferências com vários participantes se estiver usando um provedor de mensagens de chat público, que é estritamente de comunicação ponto a ponto. Mas os protocolos SIP e XMPP são aceitos.
    
- Conferência de áudio/vídeo (A/V): os usuários externos autorizados podem participar de conferências de áudio e vídeo do Skype for Business Server.
    
- Webconferência: seus usuários externos autorizados podem participar de conferências do Skype for Business. Você também pode habilitar a participação para usuários remotos, usuários federados e usuários anônimos, se quiser. Os usuários de mensagens de chat públicas não podem participar de conferências. Também existem opções para permitir que esses usuários participem do compartilhamento de área de trabalho e aplicativos, e até mesmo ajam como organizadores ou apresentadores da reunião.
    
O acesso ao dispositivo móvel tem suporte, como o Enterprise Voice. Você pode convidar usuários externos para as reuniões das quais eles devem participar, mesmo usuários anônimos, se você quiser dar permissões a eles.
  
Se isso atender às necessidades de sua organização, planejar um ambiente de Borda será de grande ajuda para a implementação. Para ler mais sobre o assunto, temos os tópicos listados abaixo.

> [!NOTE]
> Os gateways e proxies XMPP estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. Consulte [migrando a Federação do XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações. 
  
## <a name="planning-topics"></a>Tópicos de planejamento:

Os artigos de planejamento são:
  
- [Requisitos de sistema do Servidor de Borda no Skype for Business Server 2015](system-requirements.md)
    
- [Requisitos de ambiente do Servidor de Borda no Skype for Business Server 2015](edge-environmental-requirements.md)
    
- [Cenários do Servidor de Borda no Skype for Business Server 2015](scenarios.md)
    

