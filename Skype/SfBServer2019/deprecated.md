---
title: O que foi preterido do Skype for Business Server 2019
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: esses recursos foram removidos do Skype for Business Server 2019.'
ms.openlocfilehash: f77ccecd0ab963c0707a7b1dc1d24083ed0c3729
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813979"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>O que foi preterido do Skype for Business Server 2019

Saiba mais sobre os recursos e as funcionalidades preteridos no Skype for Business Server 2019. Para obter informações sobre os novos recursos do Skype for Business Server 2019, consulte [o que há no Skype for Business server 2019](whats-new.md).

Alguns recursos desenfatizados estão incluídos no Skype for Business Server 2019 para fins de compatibilidade com versões anteriores do produto.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Recursos preteridos no Skype for Business Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Gateways XMPP para o Skype for Business Server

O Skype for Business Server 2015 e seus predecessores permitiam que você configure um proxy de protocolo de mensagens e de presença extensível (XMPP) no servidor de borda e um Gateway XMPP no servidor front-end ou no pool de front-ends. Esta funcionalidade não está mais disponível no Skype for Business Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Chat persistente para o Skype for Business Server

O servidor de chat persistente é uma função opcional que permite que vários usuários de sua organização participem de conversas da sala de chat que persistem ao longo do tempo. O chat persistente não pode ser implantado com o Skype for Business Server 2019. Esta função de servidor é removida do construtor de topologias, bem como do código. 

A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here).

### <a name="sql-mirroring-for-skype-for-business-server"></a>Espelhamento do SQL para o Skype for Business Server

O espelhamento do SQL não pode ser implantado com o Skype for Business Server 2019. Outras opções para fornecer alta disponibilidade e recuperação de desastres ainda têm suporte e você deve escolher entre elas. Consulte [planejar a alta disponibilidade e a recuperação de desastres no Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) para revisar as opções.

### <a name="in-place-upgrades"></a>Atualizações in-loco 

As atualizações in-loco estavam disponíveis no Skype for Business Server 2015, mas não são mais compatíveis com o Skype for Business Server 2019. A atualização lado a lado e a coexistência tem suporte, confira [migrar para o Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) para obter mais informações.

### <a name="mobility-service-mcx"></a>Serviço de mobilidade (MCX)

O suporte do serviço de mobilidade usado por clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Isso foi anunciado anteriormente no Skype for Business Server 2015.

Todos os clientes móveis atuais do Skype for Business já usam a API da Web de comunicação unificada (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.

Para obter mais detalhes, consulte comparação de recursos do [plano de mobilidade para o Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) e do [cliente móvel para o Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Tools

As seguintes ferramentas não estarão disponíveis para uso na versão inicial do Skype for Business Server 2019:

- Calculadora de planejamento de capacidade do Skype for Business Server
- Ferramentas de depuração do Skype for Business Server
- Ferramentas do kit de recursos do Skype for Business Server (algumas ferramentas serão removidas)
    - Parquímetro de Chamada
    - Console de usuário de pesquisa
    - Migração de anúncio de número não atribuído

As seguintes ferramentas não são compatíveis com o Skype for Business Server 2019:

- Metodologia de qualidade de chamada (mas não chama painel de qualidade)
- Scorecard de metodologia de qualidade de chamada da Microsoft, v 1.5
- Skype for Business Server 2015 Planning Tool
- Skype for Business Server 2015 Stress and Performance Tool

### <a name="see-also"></a>Confira também

[O que há de novo no Skype for Business Server 2019](whats-new.md)

[Migrar a federação XMPP](migration/migrating-xmpp-federation.md)
