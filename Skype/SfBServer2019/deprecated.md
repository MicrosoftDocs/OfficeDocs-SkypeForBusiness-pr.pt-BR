---
title: O que é preterido do Skype for Business Server 2019
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: esses recursos foram removidos do Skype for Business Server 2019.'
ms.openlocfilehash: 43fa8bae64e65fcba1aaf21c75e06d396d3c47eee8df40cec0db0eb1d5d646eb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282464"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>O que é preterido do Skype for Business Server 2019

Saiba mais sobre os recursos e funcionalidades preterido no Skype for Business Server 2019. Para obter informações sobre novos recursos no Skype for Business Server 2019, consulte O que há [Skype for Business Server 2019](whats-new.md).

Alguns recursos não enfatizados estão incluídos no Skype for Business Server 2019 para compatibilidade com versões anteriores do produto.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Recursos preterido no Skype for Business Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Gateways XMPP para Skype for Business Server

Skype for Business Server 2015 e seus predecessores permitiram configurar um proxy XMPP (Extensible Messaging and Presence Protocol) no Servidor de Borda e um Gateway XMPP no servidor front-end ou pool de front-end. Essa funcionalidade não está mais disponível no Skype for Business Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Chat Persistente para Skype for Business Server

O Servidor de Chat Persistente é uma função opcional que permite que vários usuários em sua organização participem de conversas de sala de chat que persistem ao longo do tempo. O chat persistente não pode ser implantado com o Skype for Business Server 2019. Essa função de servidor é removida do Construtor de Topologias, bem como do código. 

A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL Espelhamento para Skype for Business Server

SQL O espelhamento não pode ser implantado com o Skype for Business Server 2019. Outras opções para fornecer Alta Disponibilidade e Recuperação de Desastres ainda são suportadas e você deve escolher entre elas. Consulte [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.

### <a name="in-place-upgrades"></a>Atualizações no local 

As atualizações in-locar estavam disponíveis no Skype for Business Server 2015, mas não são mais suportadas no Skype for Business Server 2019. Há suporte para atualização e coexistência lado a lado, consulte [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) para obter mais informações.

### <a name="mobility-service-mcx"></a>Serviço de Mobilidade (Mcx)

O suporte ao Serviço de Mobilidade usado por clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Isso foi anunciado anteriormente no Skype for Business Server 2015.

Todos os clientes Skype for Business móveis atuais já usam a UCWA (Unified Communications Web API) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herddos usando o Mcx precisarão atualizar para um cliente atual.

Para obter mais detalhes, [consulte Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and Mobile client feature comparison for [Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Ferramentas

As ferramentas a seguir não estarão disponíveis para uso na versão inicial do Skype for Business Server 2019:

- Calculadora de Planejamento de Capacidade do Skype for Business Server
- Skype for Business Server Ferramentas de depuração
- Skype for Business Server Ferramentas de Kit de Recursos (algumas ferramentas serão removidas)
    - Chamar Parkometer
    - Console do usuário de lookup
    - Migração de anúncio de número não atribuído

As seguintes ferramentas não são suportadas com Skype for Business Server 2019:

- Metodologia de Qualidade de Chamada (mas não Painel de Qualidade de Chamada)
- Scorecard da Metodologia de Qualidade de Chamada da Microsoft, v1.5
- Skype for Business Server Ferramenta de Planejamento 2015
- Skype for Business Server ferramenta de desempenho e estresse de 2015

### <a name="see-also"></a>Confira também

[Novidades no Skype for Business Server 2019](whats-new.md)

[Migrar a federação XMPP](migration/migrating-xmpp-federation.md)
