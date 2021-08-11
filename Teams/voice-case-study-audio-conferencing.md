---
title: 'Teams caso contoso de voz: Audioconferência'
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
description: 'Teams de caso de voz para empresas multinacionais: Audioconferência'
appliesto:
- Microsoft Teams
ms.openlocfilehash: f25fa2e81244365d1c0c3dfcacf918f1b35a6fa71d2b619eaaa55c8aa219c310
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335791"
---
# <a name="contoso-case-study-audio-conferencing"></a>Estudo de caso contoso: Audioconferência

Para obter uma compreensão do que é a audioconferência, quanto custa, disponibilidade e como funciona a &mdash; Audioconferência revisada pela &mdash; Contoso [](deploy-audio-conferencing-teams-landing-page.md)em Office 365 . 

## <a name="overview"></a>Visão Geral 

Para a audioconferência, a Contoso usou números de telefone bem conhecidos dentro da organização e externamente. Como a Contoso queria manter esses números sempre que possível, eles revisaram as informações sobre a atribuição de números de telefone dedicados e compartilhados à ponte de audioconferência. 

Com base em suas pesquisas, a Contoso tomou as seguintes decisões: 

- Somente um segmento da população que hospeda regularmente chamadas de audioconferência receberia licenças de Audioconferência. 

- A Contoso usaria números de telefone dedicados e portaria seus números existentes para uso com Audioconferência.   

Como os usuários da Contoso estavam usando Skype for Business e todas as caixas de correio dos usuários residem online, muitos usuários têm reuniões existentes agendadas. Contoso leia Usando o Serviço de Migração de Reunião [(MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) para saber que as reuniões existentes são atualizadas automaticamente para a Contoso quando eles alteram o usuário final para o modo TeamsOnly.  


## <a name="configuration"></a>Configuração

Telefone números associados à audioconferência são chamados de números de serviço em Sistema de Telefonia. 

- Para locais que usam Planos de Chamadas, para por seus números de telefone existentes de sua operadora de telefonia para Office 365, a Contoso seguiu as etapas em Obter números [de telefone de serviço](getting-service-phone-numbers.md).

- Para atribuir a licença de Audioconferência ao usuário final no piloto técnico, o administrador da Contoso seguiu as etapas em Gerenciar as configurações de [Audioconferência para sua organização.](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md) 

- Para o piloto de negócios e a migração, a Contoso usou o licenciamento baseado em grupo seguindo as etapas em [Atribuir licenças](/azure/active-directory/users-groups-roles/licensing-groups-assign)aos usuários por associação ao grupo no Azure Active Directory .  

 

