---
title: Estudo de caso do Teams voice Contoso
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
description: Estudo de caso de voz do Teams para corporação multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a964075dfae514759309a81a7d7140cddd10220
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701219"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Estudo de caso da Contoso: Visão geral da migração de voz do Teams

Este artigo apresenta um estudo de caso sobre como uma corporação multinacional fictícia, a Contoso, implementou uma solução de voz do Teams para sua organização.

A Contoso implantou o Microsoft 365 Enterprise e abondou as principais decisões de design e detalhes de implementação para os seguintes: rede, identidade, Windows 10 Enterprise, Office 365 ProPlus, gerenciamento de dispositivo móvel, proteção de informações, segurança, atualização do Skype for Business para o Teams, Sistema de Telefonia e Audioconferência.  

Este artigo se concentra em como a Contoso migrou seus usuários locais para o Teams para comunicação unificada, colaboração e voz. Para obter informações sobre como a Contoso acelerou sua transformação digital usando os serviços de nuvem da Microsoft, consulte todos os artigos principais começando com a visão geral do estudo de caso [contoso.](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

Nos artigos principais, você encontrará informações sobre o seguinte:  

- Necessidades de infraestrutura de TI da Contoso
- Rede
- Identidade
- Windows 10 Enterprise
- Office 365 Pro Plus
- Gerenciamento de dispositivo móvel
- Proteção de informações
- Resumo da segurança do Microsoft 365 Enterprise
- Equipe para um projeto super-secreto
- Site do SharePoint Online para ativos digitais altamente confidenciais

Para obter informações sobre como planejar uma atualização, comece com a atualização do [Microsoft Teams.](upgrade-start-here.md)

## <a name="contoso-business-goals-for-teams"></a>Metas comerciais da Contoso para o Teams

Para migrar seus usuários locais para o Teams para comunicação unificada, colaboração e voz, a Contoso optou pelos seguintes objetivos comerciais:

- Habilitar o Teams 

  A equipe unificada de comunicação e colaboração da Contoso habilitaram o Teams com as políticas corretas para reger e habilitar a colaboração interna e externa segura. 

- Atualização do Skype for Business para o Teams 

  O Skype for Business foi amplamente implantado na Contoso. Com a necessidade de sair dos sistemas herdáveis, a Contoso decidiu atualizar os usuários do Skype for Business para o Teams. Para saber mais, confira o [estudo de caso da Contoso: Plano de atualização do Teams.](voice-case-study-migration-plan.md)

- Sistema de Telefonia  

  O Skype for Business com voz corporativa foi amplamente implantado na Contoso. Com a necessidade de migrar os sistemas herdados que eram o próximo salto para seus servidores de mediação, a Contoso migrou seus usuários de voz corporativa do Skype for Business para o Sistema de Telefonia. Os sites da Contoso usavam o Plano de Chamada da Microsoft, o Roteamento Direto do Sistema telefônico ou uma combinação de ambos. Para saber mais, confira [o estudo de caso da Contoso: Sistema telefônico.](voice-case-study-phone-system.md)

- Roteamento com Base no Local 

  Com locais de escritório em países regulamentados por telefonia, a Contoso precisava recriar o roteamento de Location-Based que estava presente no Skype for Business em sua implantação do Sistema de Telefonia. Para saber mais, confira o [estudo de caso contoso: Location-Based Roteamento.](voice-case-study-location-based-routing.md)

- Chamadas de emergência 

  Onde o Roteamento Direto foi implementado, a Contoso configura chamadas de emergência com terceiros aprovados. Para saber mais, confira [o estudo de caso da Contoso: Chamada de emergência.](voice-case-study-emergency-calling.md)

- Audioconferência 

  A Contoso configura números de serviço de Audioconferência hospedados no tronco SIP para o provedor de PSTN. Para saber mais, confira [o estudo de caso da Contoso: Audioconferência.](voice-case-study-audio-conferencing.md) 

- Otimização de mídia local 

  A Contoso tirou proveito da Otimização de Mídia Local em locais onde eles tinham um tronco de rota direta para o Microsoft Phone System que era aproveitado por sites remotos. Para obter mais informações, consulte [Plano de Otimização de Mídia Local](direct-routing-media-optimization.md) e Configurar [Otimização de Mídia Local.](direct-routing-media-optimization-configure.md)

- Assistentes Automáticos e Filas de Chamada

  Como resultado de Covid-19, a Contoso queria fornecer suporte para o recepcionista enquanto sua equipe estava trabalhando remotamente. A Contoso usava os atenderes automáticos e filas de chamadas para gerenciar chamadas de entrada para o número de telefone de seu recepcionista. Para obter mais informações, consulte o estudo de [caso da Contoso: Auto Attendants e Filas de Chamada.](voice-case-study-call-queues.md)  


