---
title: Visão geral do estudo de caso da Contoso de voz do Teams
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
- highpri
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 'Estudo de caso de voz do Teams para empresas multinacionais: visão geral da migração de voz'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b77cffa9bfa56ad445e948a4688e18e35118fd7
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999476"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Estudo de caso da Contoso: visão geral da migração de voz do Teams

Este artigo apresenta um estudo de caso sobre como uma empresa multinacional fictícia, Contoso, implementou uma solução de voz do Teams para sua organização.

A Contoso implantou Microsoft 365 Enterprise e abordou as principais decisões de design e detalhes de implementação para os seguintes: rede, identidade, Windows 10 Enterprise, Office 365 ProPlus, gerenciamento de dispositivo móvel, proteção de informações, segurança, atualização de Skype for Business para Teams, Sistema de Telefonia e Audioconferência.  

Este artigo se concentra em como a Contoso migrou seus usuários locais para o Teams para comunicação unificada, colaboração e voz. Para obter informações básicas sobre como a Contoso acelerou sua transformação digital usando os serviços de nuvem da Microsoft, consulte todos os principais artigos que começam com a visão geral do estudo de caso da [Contoso](/microsoft-365/enterprise/contoso-case-study).

[https://learn.microsoft.com/microsoft-365/enterprise/contoso-case-study](/microsoft-365/enterprise/contoso-case-study) 

Nos artigos principais, você encontrará informações sobre o seguinte:  

- Necessidades de infraestrutura de TI da Contoso
- Rede
- Identidade
- Windows 10 Enterprise
- Office 365 Pro Plus
- Gerenciamento de dispositivo móvel
- Proteção de informações
- Resumo da Microsoft 365 Enterprise segurança
- Equipe para um projeto secreto
- Site do SharePoint Online para ativos digitais altamente confidenciais

Para obter informações sobre como planejar uma atualização, comece com a introdução [à atualização do Microsoft Teams](upgrade-start-here.md).

## <a name="contoso-business-goals-for-teams"></a>Metas de negócios da Contoso para o Teams

Para migrar seus usuários locais para o Teams para comunicação unificada, colaboração e voz, a Contoso decidiu os seguintes objetivos de negócios:

- Habilitação do Teams 

  A equipe unificada de comunicação e colaboração da Contoso habilitou o Teams com as políticas corretas para controlar e habilitar a colaboração interna e externa segura. 

- Atualização do Skype for Business para o Teams 

  Skype for Business foi amplamente implantado na Contoso. Com a necessidade de sair dos sistemas herdados, a Contoso decidiu atualizar seus Skype for Business para o Teams. Para obter mais informações, consulte o [estudo de caso da Contoso: plano de atualização do Teams](voice-case-study-migration-plan.md).

- Sistema de Telefonia  

  Skype for Business com o Enterprise Voice foi amplamente implantado na Contoso. Com a necessidade de mover sistemas herdados que eram o próximo salto para seus servidores de mediação, a Contoso migrou seus usuários de voz Skype for Business corporativos para o Sistema de Telefonia. Os sites da Contoso usaram o Plano de Chamadas da Microsoft, o Roteamento Direto do Sistema de Telefonia ou uma combinação de ambos. Para obter mais informações, consulte [o estudo de caso da Contoso: Sistema de Telefonia](voice-case-study-phone-system.md).

- Roteamento com Base no Local 

  Com os locais de escritório em países regulamentados por telefonia, a Contoso precisava recriar o roteamento de Location-Based que estava presente Skype for Business implantação do Sistema de Telefonia. Para obter mais informações, consulte [o estudo de caso da Contoso: Location-Based Roteamento](voice-case-study-location-based-routing.md).

- Chamadas de emergência 

  Onde o Roteamento Direto foi implementado, a Contoso configurou chamadas de emergência com terceiros aprovados. Para obter mais informações, consulte [o estudo de caso da Contoso: Chamada de Emergência](voice-case-study-emergency-calling.md).

- Audioconferência 

  A Contoso configurou números de serviço de Audioconferência hospedados em seu tronco SIP para seu provedor PSTN. Para obter mais informações, consulte [o estudo de caso da Contoso: Audioconferência](voice-case-study-audio-conferencing.md). 

- Otimização de mídia local 

  A Contoso aproveitou a Otimização de Mídia Local em locais em que tinham um tronco de rota direta para o Sistema de Telefonia da Microsoft que era utilizado por sites remotos. Para obter mais informações, consulte [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).

- Atendedores Automáticos e Filas de Chamadas

  Como resultado da Covid-19, a Contoso queria fornecer suporte de recepção enquanto sua equipe estava trabalhando remotamente. A Contoso usou atendedores automáticos e filas de chamadas para gerenciar chamadas de entrada para o número de telefone de sua recepção. Para obter mais informações, consulte [o estudo de caso da Contoso: Atendedores Automáticos e Filas de Chamadas](voice-case-study-call-queues.md).
