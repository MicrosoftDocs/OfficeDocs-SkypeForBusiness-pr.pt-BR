---
title: O que foi preterido do Skype for Business Server 2019
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
description: 'Resumo: Esses recursos foram removidos do Skype for Business Server 2019.'
ms.openlocfilehash: 5c5914493d7e2f4da4fd72d6acf7ff2b979d8e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808721"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>O que foi preterido do Skype for Business Server 2019

Saiba mais sobre os recursos e funcionalidades preterido no Skype for Business Server 2019. Para saber mais sobre os novos recursos do Skype for Business Server 2019, confira o que há [no Skype for Business Server 2019.](whats-new.md)

Alguns recursos sem ênfase estão incluídos no Skype for Business Server 2019 para compatibilidade com versões anteriores do produto.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Recursos preterido no Skype for Business Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>XMPP Gateways for Skype for Business Server

O Skype for Business Server 2015 e seus predecessores permitiram configurar um proxy XMPP (Extensible Messaging and Presence Protocol) no Servidor de Borda e um Gateway XMPP no servidor front-end ou pool de front-end. Essa funcionalidade não está mais disponível no Skype for Business Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Chat Persistente para Skype for Business Server

O Servidor de Chat Persistente é uma função opcional que permite que vários usuários em sua organização participem de conversas de sala de chat que persistem ao longo do tempo. O chat persistente não pode ser implantado com o Skype for Business Server 2019. Essa função de servidor é removida do Construtor de Topologias, bem como do código. 

A mesma funcionalidade está disponível no Teams. Para saber mais, confira [Como começar a atualizar o Microsoft Teams.](/microsoftteams/upgrade-start-here)

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL Mirroring for Skype for Business Server

O espelhamento SQL não pode ser implantado com o Skype for Business Server 2019. Outras opções para fornecer alta disponibilidade e recuperação de desastres ainda são suportadas e você deve escolher entre elas. Consulte [Plano para alta disponibilidade e recuperação de desastres no Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) para revisar as opções.

### <a name="in-place-upgrades"></a>Atualizações no local 

As atualizações in-place estavam disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. Há suporte para atualização e coexistência lado a lado, confira Migração para [o Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) para obter mais informações.

### <a name="mobility-service-mcx"></a>Mobility Service (Mcx)

O suporte ao Mobility Service usado por clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Isso foi anunciado anteriormente no Skype for Business Server 2015.

Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herddos usando o Mcx precisarão atualizar para um cliente atual.

Para obter mais detalhes, [consulte Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and Mobile client feature comparison for Skype for [Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Ferramentas

As seguintes ferramentas não estarão disponíveis para uso na versão inicial do Skype for Business Server 2019:

- Calculadora de Planejamento de Capacidade do Skype for Business Server
- Ferramentas de depuração do Skype for Business Server
- Ferramentas do Kit de Recursos do Skype for Business Server (algumas ferramentas serão removidas)
    - Estacionamento de chamada
    - Lookup user console
    - Migração de comunicados de número não atribuído

As seguintes ferramentas não são suportadas com o Skype for Business Server 2019:

- Metodologia de Qualidade de Chamada (mas não Painel de Qualidade de Chamada)
- Scorecard da Metodologia de Qualidade de Chamada da Microsoft, v1.5
- Ferramenta de Planejamento do Skype for Business Server 2015
- Ferramenta de Stress and Performance do Skype for Business Server 2015

### <a name="see-also"></a>Confira também

[Novidades no Skype for Business Server 2019](whats-new.md)

[Migrar a federação XMPP](migration/migrating-xmpp-federation.md)
