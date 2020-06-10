---
title: Atualizar do Skype for Business local para o Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba como migrar sua organização para o Microsoft Teams a partir de uma implantação local do Skype for Business.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34502fe9883c98179a6b2e23cd8360ae823c1853
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666013"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Atualizar de uma implantação local do Skype for Business para o Microsoft Teams

![Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação](media/upgrade-banner-deployment.png "Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação")

Este artigo faz parte do estágio de implantação e implementação de sua jornada de atualização. Antes de prosseguir, confirme que você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](https://aka.ms/SkypetoTeams-Scope)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Seu ambiente foi preparado](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Preparou sua organização](https://aka.ms/SkypeToTeams-UserReadiness)
- [Conduziu um piloto](https://aka.ms/SkypeToTeams-Pilot)

Siga as orientações neste artigo se você tiver implantado o Skype for Business ou o Microsoft Lync local e sua organização quiser atualizar para o Microsoft Teams seletivamente — usando vários modos de coexistência ou todos. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Etapa 1: implantar a conectividade híbrida

O principal pré-requisito para atualizar os usuários para o Microsoft Teams é implantar a conectividade híbrida.

Para obter mais informações, consulte [implantar conectividade híbrida entre o Skype for Business Server e o Skype for Business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Etapa 2: implementar a viagem de atualização escolhida para a sua organização

Depois de concluir a configuração híbrida, você poderá planejar a transferência dos usuários para o Microsoft 365 ou o Office 365.

Para obter mais informações, consulte:

- [TeamsUpgradePolicy: Gerenciando a migração e a coexistência](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

- [Mover usuários do local para o Skype for Business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="phone-system-and-teams-upgrade"></a>Atualização do sistema de telefonia e do teams

A transição de sistemas telefônicos locais para o Microsoft Teams permitirá que você aproveite o roteamento direto do sistema de telefonia ("roteamento direto") ou os planos de chamada fornecidos pela Microsoft para o Microsoft 365 ou o Office 365.

Se você não estiver usando planos de chamada, será necessário fazer a transição de sua implantação do Enterprise Voice para o roteamento direto do sistema telefônico como parte de sua atualização para o Microsoft Teams.

Para obter mais informações, consulte [considerações adicionais sobre o roteamento direto do sistema telefônico](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing). Se estiver planejando usar planos de chamada, consulte nossas diretrizes para [transferir seus números de telefone para o Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).