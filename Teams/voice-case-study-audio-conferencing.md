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
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785948"
---
# <a name="contoso-case-study-audio-conferencing"></a>Estudo de caso da Contoso: Conferência de áudio

Para ter noções básicas sobre a videoconferência, &mdash; o que é, o que é custo, disponibilidade e como funciona a &mdash; contoso analisou a [conferência de áudio no Office 365](deploy-audio-conferencing-teams-landing-page.md). 

## <a name="overview"></a>Visão geral 

Para videoconferência, a contoso usou números de telefone bem conhecidos na organização, e externamente. Como a contoso queria manter esses números onde possível, eles revisaram as informações sobre a atribuição de números de telefone dedicados e compartilhados à ponte de audioconferência. 

Com base na pesquisa, a contoso tomou as seguintes decisões: 

- Apenas um segmento da população que hospeda regularmente chamadas de conferência de áudio receberia licenças de audioconferência. 

- A contoso usaria números de telefone dedicados e portaria os números existentes para usá-la com a conferência de áudio.   

Como os usuários da Contoso estavam usando o Skype for Business e todas as caixas de correio dos usuários residem online, muitos usuários têm reuniões existentes agendadas. A contoso leu [usando o MMS (serviço de migração de reunião)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) para saber que reuniões existentes são atualizadas automaticamente para contoso quando alteram o usuário final para o modo TeamsOnly.  


## <a name="configuration"></a>Configuração

Os números de telefone associados à videoconferência são chamados de números de serviço no sistema telefônico. 

- Para locais que usam planos de chamada, para portar seus números de telefone existentes de sua operadora de telefonia para o Office 365, a contoso seguiu as etapas para [obter números de telefone de serviço](getting-service-phone-numbers.md).

- Para atribuir a licença de audioconferência ao usuário final no piloto técnico, o administrador da Contoso seguiu as etapas em [gerenciar as configurações de audioconferência de áudio para sua organização](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md). 

- Para o piloto e a migração para empresas, a contoso usou o licenciamento baseado em grupos seguindo as etapas em [atribuir licenças a usuários por associação a um grupo no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).  

 

 