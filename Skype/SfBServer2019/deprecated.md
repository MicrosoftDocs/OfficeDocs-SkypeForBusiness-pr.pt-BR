---
title: O que é reduzido do Skype para Business Server 2019
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/10/2018
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: Esses recursos foram removidos do Skype para Business Server 2019.'
ms.openlocfilehash: 926f5539a31dbcb37ff4ccb5494ccaa7be517d30
ms.sourcegitcommit: 112dc19075f9213207fde9e30bcde5681324b7c9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2018
ms.locfileid: "25696160"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>O que é reduzido do Skype para Business Server 2019 

Saiba mais sobre os recursos e funcionalidade são reduzidos no Skype para Business Server 2019. Para obter informações sobre novos recursos do Skype para Business Server 2019, consulte [What's in Skype para Business Server 2019](whats-new.md).

Alguns recursos desprovisionamento emphasised estão incluídos na Skype para Business Server 2019 para compatibilidade com versões anteriores do produto. 

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Recursos reduzidos no Skype para Business Server 2019 

        The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Gateways XMPP para Skype para Business Server

Skype para Business Server 2015 e seus predecessores permitia configurar um proxy de mensagens extensíveis e protocolo de presença (XMPP) no servidor de borda e um Gateway XMPP no pool de Front-End ou de servidor Front-End. Essa funcionalidade não está mais disponível no Skype para Business Server 2019.


### <a name="persistent-chat-for-skype-for-business-server"></a>Chat persistente para Skype para Business Server

Servidor de bate-papo persistente é uma função opcional que permite que vários usuários em sua organização participar de conversas de sala de chat que persistam ao longo do tempo. Chat persistente não pode ser implantado com Skype para Business Server 2019. Esta função de servidor é removida do construtor de topologia, bem como do código. 

A mesma funcionalidade está disponível em equipes. Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams).   

### <a name="sql-mirroring-for-skype-for-business-server"></a>Espelhamento de SQL para Skype para Business Server

Espelhamento de SQL não pode ser implantado com Skype para Business Server 2019. Outras opções para fornecer alta disponibilidade e recuperação de desastres ainda são suportadas e você deve escolher entre eles. Consulte o [plano de alta disponibilidade e recuperação de desastres em Skype para Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) revisar as opções.

### <a name="in-place-upgrades"></a>Atualizações in-loco 

Atualizações in-loco estavam disponíveis no Skype para Business Server 2015, mas não são mais suportadas no Skype para Business Server 2019. Lado a lado, atualização e coexistência é suportada, consulte [Migration to Skype para Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) para obter mais informações.

###  <a name="mobility-service-mcx"></a>Serviço de mobilidade (Mcx)

Suporte ao serviço de mobilidade usado pelos clientes móveis herdados não está mais disponível no Skype para Business Server 2019. Isso foi anunciado anteriormente no Skype para Business Server 2015.

Todos os Skype atual para clientes móveis do Business já use Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Usuários com clientes herdados usando Mcx serão necessário atualizar para um cliente atual.

Para obter mais detalhes, consulte [Planejar mobilidade para Skype para Business Server](../SfbServer/plan-your-deployment/mobility.md) e a [comparação de recursos do cliente móvel para Skype para negócios](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Ferramentas

As seguintes ferramentas não estarão disponíveis para uso em uma versão inicial do Skype para Business Server 2019:

- Skype para Calculadora de planejamento de capacidade do servidor de negócios
- Skype para Business Server as ferramentas de depuração
- Skype para ferramentas do Business Server Resource Kit (algumas ferramentas serão removidas)
    - Parquímetro de Chamada
    - Console do usuário de pesquisa
    - Migração de comunicado de número não atribuído

Não há suporte para as seguintes ferramentas com Skype para Business Server 2019:

- Painel de metodologia de qualidade de chamada
- Scorecard de metodologia de qualidade de chamada da Microsoft, v 1.5
- Skype for Business Server 2015 Planning Tool
- Skype for Business Server 2015 Stress and Performance Tool

### <a name="see-also"></a>Consulte também

[O que há de novo no Skype para Business Server 2019](whats-new.md)

[Migração da federação XMPP](migration/migrating-xmpp-federation.md)