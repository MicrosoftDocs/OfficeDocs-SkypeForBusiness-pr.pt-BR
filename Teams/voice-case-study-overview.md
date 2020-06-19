---
title: Estudo de caso da Contoso Voice Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Estudo de caso de voz do teams para Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: 100889bacffdb9de722bd2e1e7295905876dab2e
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785941"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Estudo de caso da Contoso: visão geral da migração de voz do teams

Este artigo apresenta um estudo de caso sobre como uma empresa multinacional fictícia, contoso, implementou uma solução de voz de equipe para a sua organização.

A contoso implantou o Microsoft 365 Enterprise e corrigiu as principais decisões de design e os detalhes de implementação para o seguinte: rede, identidade, Windows 10 Enterprise, Office 365 ProPlus, gerenciamento de dispositivo móvel, proteção de informações, segurança, atualização do Skype for Business para equipes, sistemas telefônicos e conferência de áudio.  

Este artigo se concentra na maneira como a contoso migrou seus usuários locais para o Microsoft Teams para comunicação unificada, colaboração e voz. Para obter informações detalhadas sobre como a contoso acelera a transformação digital usando os serviços de nuvem da Microsoft, consulte todos os artigos principais começando com a [visão geral do estudo de caso da Contoso](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

Nos artigos principais, você encontrará informações sobre o seguinte:  

- Necessidades da infraestrutura de ti da contoso
- Sistema
- Identidade
- Windows 10 Enterprise
- Office 365 Pro Plus
- Gerenciamento de dispositivo móvel
- Proteção de informações
- Resumo da segurança do Microsoft 365 Enterprise
- Equipe para um projeto de melhor segredo
- Site do SharePoint Online para ativos digitais altamente confidenciais

Para obter informações sobre como planejar uma atualização, comece a começar a usar [a atualização do Microsoft Teams](upgrade-start-here.md).

## <a name="contoso-business-goals-for-teams"></a>Metas comerciais da Contoso para Teams

Para migrar seus usuários locais para o Microsoft Teams para comunicação unificada, colaboração e voz, a Contoso decidiu nas seguintes metas de negócios:

- Habilitação de equipes 

  A equipe de comunicação unificada de comunicação e colaboração da Contoso permitiu as políticas corretas para controlar e habilitar a colaboração interna e externa segura. 

- Atualização do Skype for Business para o Teams 

  O Skype for Business foi amplamente implantado dentro da contoso. Com a necessidade de sair dos sistemas herdados, a Contoso decidiu atualizar seus usuários do Skype for Business para o Teams. Para obter mais informações, consulte [estudo de caso da Contoso: plano de atualização do teams](voice-case-study-migration-plan.md).

- Sistema Telefônico  

  O Skype for Business com Enterprise Voice foi amplamente implantado dentro da contoso. Com a necessidade de remover sistemas herdados que foram o próximo nó para seus servidores de mediação, a contoso migrou os usuários do Skype for Business Enterprise Voice para o sistema telefônico. Os sites da Contoso usaram o plano de chamadas da Microsoft, o roteamento direto do sistema telefônico ou uma combinação dos dois. Para obter mais informações, consulte [estudo de caso da Contoso: sistema telefônico](voice-case-study-phone-system.md).

- Roteamento com Base no Local 

  Com os locais do Office em países regulamentados pela telefonia, a contoso precisou recriar o roteamento baseado em localização que estava presente no Skype for Business em sua implantação de sistema telefônico. Para obter mais informações, consulte [estudo de caso da Contoso: roteamento baseado em localização](voice-case-study-location-based-routing.md).

- Chamadas de emergência 

  Onde o roteamento direto foi implementado, a contoso configurou a chamada de emergência com terceiros aprovados. Para obter mais informações, consulte [estudo de caso da Contoso: chamadas de emergência](voice-case-study-emergency-calling.md).

- Audioconferência 

  A contoso configurou números de serviços de audioconferência que foram hospedados em seu tronco SIP para o provedor de PSTN. Para obter mais informações, consulte [estudo de caso da Contoso: videoconferência](voice-case-study-audio-conferencing.md). 

- Otimização de mídia local 

  A contoso aproveitou a otimização de mídia local em locais onde tinha um tronco de rota direta para o sistema de telefone da Microsoft que era aproveitado por sites remotos. Para obter mais informações, consulte [planejar a otimização de mídia local](direct-routing-media-optimization.md) e [Configurar a otimização de mídia local](direct-routing-media-optimization-configure.md).

- Atendedores automáticos e filas de chamadas

  Como resultado da Covid-19, a contoso queria oferecer suporte ao recepcionista enquanto a equipe estava trabalhando remotamente. A contoso usou atendedores automáticos e filas de chamadas para gerenciar as chamadas recebidas para o número de telefone da recepcionista. Para obter mais informações, consulte [estudo de caso da Contoso: atendedores automáticos e filas de chamadas](voice-case-study-call-queues.md).  


