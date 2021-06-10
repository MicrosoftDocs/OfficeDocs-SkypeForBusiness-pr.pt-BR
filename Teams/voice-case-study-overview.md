---
title: Teams de caso contoso de voz
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams de caso de voz para corporação multi-nacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19200ec5ab1556b0f2b4fda2f389e60bc236015b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097487"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Estudo de caso contoso: Teams de migração de voz

Este artigo apresenta um estudo de caso para como uma corporação multi-nacional fictícia, Contoso, implementou uma solução Teams voz para sua organização.

A Contoso implantou o Microsoft 365 Enterprise e abordou as principais decisões de design e detalhes de implementação para os seguintes: rede, identidade, Windows 10 Enterprise, Office 365 ProPlus, gerenciamento de dispositivo móvel, proteção de informações, segurança, atualização do Skype for Business para Teams, Sistema de Telefonia e Audioconferência.  

Este artigo se concentra em como a Contoso migrou seus usuários locais para Teams comunicação unificada, colaboração e voz. Para obter informações em segundo plano sobre como a Contoso acelerou sua transformação digital usando os serviços de nuvem da Microsoft, consulte todos os artigos principais começando com a visão geral do estudo de caso [contoso.](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

Nos artigos principais, você encontrará informações sobre o seguinte:  

- Necessidades de infraestrutura de TI da Contoso
- Rede
- Identidade
- Windows 10 Enterprise
- Office 365 Pro Plus
- Gerenciamento de dispositivos móveis
- Proteção de informações
- Resumo da Microsoft 365 Enterprise segurança
- Equipe para um projeto ultra-secreto
- SharePoint Site online para ativos digitais altamente confidenciais

Para obter informações sobre como planejar uma atualização, você vai querer começar com a atualização de Microsoft Teams [.](upgrade-start-here.md)

## <a name="contoso-business-goals-for-teams"></a>Metas de negócios da Contoso para Teams

Para migrar seus usuários locais para Teams comunicação unificada, colaboração e voz, a Contoso decidiu os seguintes objetivos comerciais:

- Teams habilitação 

  A equipe unificada de comunicação e colaboração da Contoso Teams com as políticas corretas para governar e habilitar a colaboração interna e externa segura. 

- Atualização do Skype for Business para o Teams 

  Skype for Business foi amplamente implantado dentro da Contoso. Com a necessidade de sair de sistemas herdado, a Contoso decidiu atualizar seus usuários Skype for Business para Teams. Para obter mais informações, consulte [Estudo de caso contoso: Teams plano de atualização](voice-case-study-migration-plan.md).

- Sistema de Telefonia  

  Skype for Business com voz corporativa foi amplamente implantado dentro da Contoso. Com a necessidade de mover os sistemas herdados que eram o próximo salto para seus servidores de mediação, a Contoso migrou seus usuários de voz Skype for Business corporativos para Sistema de Telefonia. Os sites da Contoso usavam o Plano de Chamadas da Microsoft, Sistema de Telefonia Roteamento Direto ou uma combinação de ambos. Para obter mais informações, consulte Estudo de caso [contoso: Sistema de Telefonia](voice-case-study-phone-system.md).

- Roteamento com Base no Local 

  Com locais de escritório em países regulamentados por telefonia, a Contoso precisava recriar o roteamento de Location-Based que estava presente no Skype for Business em sua implantação Sistema de Telefonia de telefonia. Para obter mais informações, consulte [Estudo de caso contoso: Location-Based Routing](voice-case-study-location-based-routing.md).

- Chamadas de emergência 

  Onde o Roteamento Direto foi implementado, a Contoso definiu chamadas de emergência com terceiros aprovados. Para obter mais informações, consulte [Estudo de caso contoso: Chamada de emergência](voice-case-study-emergency-calling.md).

- Audioconferência 

  A Contoso definiu números de serviço de Audioconferência hospedados no tronco SIP para o provedor PSTN. Para obter mais informações, consulte [Estudo de caso contoso: Audioconferência](voice-case-study-audio-conferencing.md). 

- Otimização de mídia local 

  A Contoso aproveitou a Otimização de Mídia Local em locais onde eles tinham um tronco de rota direta para Telefone Microsoft Sistema que foi aproveitado por sites remotos. Para obter mais informações, consulte [Plan for Local Media Optimization](direct-routing-media-optimization.md) and Configure Local Media [Optimization](direct-routing-media-optimization-configure.md).

- Atendimentos Automáticos e Filas de Chamada

  Como resultado do Covid-19, a Contoso queria oferecer suporte de recepcionista enquanto sua equipe estava trabalhando remotamente. A Contoso usou os atendimentos automáticos e filas de chamadas para gerenciar chamadas de entrada para o número de telefone da recepcionista. Para obter mais informações, consulte [Estudo de caso contoso: Atendimento Automático e Filas de Chamada.](voice-case-study-call-queues.md)