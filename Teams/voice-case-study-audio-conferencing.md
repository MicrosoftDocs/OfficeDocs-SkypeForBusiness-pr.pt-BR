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
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Estudo de caso de voz do Teams para corporação multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785948"
---
# <a name="contoso-case-study-audio-conferencing"></a>Estudo de caso da Contoso: Audioconferência

Para obter uma compreensão do que é a audioconferência, o custo, a disponibilidade e a forma como ela funciona, a Contoso reviu a Audioconferência no &mdash; &mdash; Office [365.](deploy-audio-conferencing-teams-landing-page.md) 

## <a name="overview"></a>Visão Geral 

Para audioconferência, a Contoso usava números de telefone conhecidos dentro da organização e externamente. Como a Contoso queria manter esses números sempre que possível, eles revisaram as informações sobre a atribuição de números de telefone dedicados e compartilhados à ponte de audioconferência. 

Com base na pesquisa, a Contoso toma as seguintes decisões: 

- Somente um segmento da população que hospeda regularmente chamadas de audioconferência receberia licenças de Audioconferência. 

- A Contoso usaria números de telefone dedicados e portaria seus números existentes para uso com a Audioconferência.   

Como os usuários da Contoso estavam usando o Skype for Business e as caixas de correio de todos os usuários residem online, muitos usuários têm reuniões existentes agendadas. A Contoso leu Usando o [MMS (Meeting Migration Service)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) para saber que as reuniões existentes são atualizadas automaticamente para a Contoso quando eles alteram o usuário final para o modo TeamsOnly.  


## <a name="configuration"></a>Configuração

Os números de telefone associados à audioconferência são chamados de números de serviço no Sistema telefônico. 

- Para locais que usam Planos de Chamada, para portabilidade de seus números de telefone existentes de sua operadora de telefonia para o Office 365, a Contoso seguiu as etapas em Obter números de telefone [de serviço.](getting-service-phone-numbers.md)

- Para atribuir a licença de Audioconferência ao usuário final no piloto técnico, o administrador da Contoso seguiu as etapas em Gerenciar as configurações de [Audioconferência da sua organização.](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md) 

- Para o piloto comercial e a migração, a Contoso usou licenciamento baseado em grupo seguindo as etapas em Atribuir licenças aos usuários por associação ao grupo no [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)  

 

 