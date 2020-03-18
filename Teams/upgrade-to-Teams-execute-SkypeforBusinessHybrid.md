---
title: Atualizar a implantação híbrida do Skype for Business para o Microsoft Teams | PSTN
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Considerações para a atualização do teams a partir de uma implantação híbrida do Skype for Business.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ca9ebc7a28e07eec9b24c0628ade4941c0fd2fa2
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706691"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Atualizar de uma implantação híbrida do Skype for Business para o Teams

![Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação](media/upgrade-banner-deployment.png "Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação")

Este artigo faz parte do estágio de implantação e implementação da sua jornada de atualização. Antes de prosseguir, confirme que você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](https://aka.ms/SkypetoTeams-Scope)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Seu ambiente foi preparado](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Preparou sua organização](https://aka.ms/SkypeToTeams-UserReadiness)
- [Conduziu um piloto](https://aka.ms/SkypeToTeams-Pilot)

Siga as orientações neste artigo se você tiver implantado o Skype for Business ou o Microsoft Lync local e o configurou em uma implantação híbrida com o seu locatário do Office 365 e sua organização quiser atualizar para as equipes seletivamente — usando vários modos de coexistência — ou todos. Para a viagem de atualização, você precisa mover seus usuários para o Skype for Business online (se eles ainda não estiverem online) e atribuí-los ao modo de coexistência e à atualização apropriados.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Etapa 1: mover usuários para o Skype for Business Online

Esta etapa se aplica a usuários que estão hospedados no momento no local. Para obter mais informações sobre como mover esses usuários para o Skype for Business Online, consulte [mover usuários do local para o Skype for Business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Etapa 2: atribuir um modo de coexistência e atualização

Depois de mover os usuários para o Skype for Business Online, você pode atribuir a eles o modo de coexistência apropriado com base na jornada de atualização que a sua organização escolheu. Para obter mais informações, consulte [definindo suas configurações de coexistência e atualização](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: Gerenciando a migração e a coexistência](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

> [!NOTE]
> Com o Skype for Business Server 2019 e uma atualização cumulativa futura do Skype for Business Server 2015, você poderá executar a etapa 1 (movendo usuários para o Skype for Business online) e a etapa 2 (atualizar usuários para o Microsoft Teams) em uma única etapa. Mais informações serão fornecidas após o lançamento do Skype for Business Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Atualização do sistema de telefonia e do teams

Se você estiver fazendo a transição da sua implantação híbrida do Skype for Business para o sistema telefônico com planos de chamadas e a Microsoft for o seu provedor de rede telefônica pública comutada (PSTN) e presumir que você concluiu a portabilidade do número de telefone, a atualização dos usuários para O Microsoft Teams fará a transição de chamadas PSTN de entrada automaticamente para o Microsoft Teams.

Se os planos de chamada não estiverem disponíveis ou se você pretende usar seu provedor de conectividade PSTN existente, é preciso fazer a transição de sua implantação de voz empresarial ou a implantação de voz híbrida que usa a implantação local existente ou a edição do conector de nuvem, para Encaminhamento direto do sistema telefônico da Microsoft. Para atualizar os usuários para o Microsoft Teams, consulte [considerações adicionais sobre o roteamento direto do sistema telefônico](2-envision-make-my-service-decisions-direct-routing.md).
