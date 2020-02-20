---
title: O que foi preterido do Skype for Business Server 2019
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: esses recursos foram removidos do Skype for Business Server 2019.'
ms.openlocfilehash: 40a202f802ec8ac1a0f880f92ad9cf59ce68a627
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42125214"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>O que foi preterido do Skype for Business Server 2019

Saiba mais sobre os recursos e a funcionalidade preteridos no Skype for Business Server 2019. Para obter informações sobre os novos recursos no Skype for Business Server 2019, consulte [o que há no Skype for Business server 2019](whats-new.md).

Alguns recursos desenfatizados estão incluídos no Skype for Business Server 2019 para compatibilidade com versões anteriores do produto.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Recursos preteridos no Skype for Business Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Gateways do XMPP para o Skype for Business Server

O Skype for Business Server 2015 e seus predecessores permitiam que você configure um proxy Extensible Messaging and Presence Protocol (XMPP) no servidor de borda e um Gateway XMPP no servidor front-end ou no pool de front-ends. Essa funcionalidade não está mais disponível no Skype for Business Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Chat persistente para o Skype for Business Server

O servidor de chat persistente é uma função opcional que permite que vários usuários de sua organização participem de conversas de salas de chat que persistem ao longo do tempo. O chat persistente não pode ser implantado com o Skype for Business Server 2019. Essa função de servidor é removida do construtor de topologias, bem como do código. 

A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here).

### <a name="sql-mirroring-for-skype-for-business-server"></a>Espelhamento do SQL para o Skype for Business Server

O espelhamento do SQL não pode ser implantado com o Skype for Business Server 2019. Outras opções para fornecer alta disponibilidade e recuperação de desastres ainda têm suporte e você deve escolher entre elas. Consulte [Plan for High Availability and Disaster Recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) para revisar as opções.

### <a name="in-place-upgrades"></a>Atualizações in-loco 

As atualizações in-loco estavam disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. Há suporte para a atualização de lado a lado e a coexistência, consulte [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) para obter mais informações.

### <a name="mobility-service-mcx"></a>Serviço de mobilidade (MCX)

O suporte do serviço de mobilidade usado por clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Isso foi lançado anteriormente no Skype for Business Server 2015.

Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para suportar mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.

Para obter mais detalhes, consulte [plano de mobilidade para o Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) e [a comparação de recursos do cliente móvel para o Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Ferramentas

As seguintes ferramentas não estarão disponíveis para uso na versão inicial do Skype for Business Server 2019:

- Calculadora de planejamento de capacidade do Skype for Business Server
- Ferramentas de depuração do Skype for Business Server
- Ferramentas do kit de recursos do Skype for Business Server (algumas ferramentas serão removidas)
    - Chamar estacionador chamadas
    - Procurar console de usuário
    - Migração de anúncio de número não atribuído

As seguintes ferramentas não são suportadas com o Skype for Business Server 2019:

- Metodologia de qualidade de chamada (mas não chama painel de qualidade)
- Scorecard da metodologia de qualidade de chamada da Microsoft, v 1.5
- Ferramenta de planejamento do Skype for Business Server 2015
- Ferramenta de desempenho e stress do Skype for Business Server 2015

### <a name="see-also"></a>Confira também

[O que há de novo no Skype for Business Server 2019](whats-new.md)

[Migrando a Federação XMPP](migration/migrating-xmpp-federation.md)
