---
title: Atualização do Skype para negócios Online para equipes - equipes da Microsoft
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considerações para a atualização para equipes do Skype para negócios Online
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: fabcd88a0444a01f950064ade0c49dfef50400e1
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013567"
---
![Estágios da atualização jornada, com ênfase sobre a implantação e o estágio de implementação] (media/upgrade-banner-deployment.png "Estágios da atualização jornada, com ênfase sobre a implantação e o estágio de implementação")

Este artigo faz parte do estágio de implantação e a implementação da sua jornada de atualização. Antes de continuar, confirme que você tiver concluído as seguintes atividades:

-   [Inscrito seus participantes do projeto](upgrade-enlist-stakeholders.md)
-   [Definido o escopo do projeto](https://aka.ms/SkypetoTeams-Scope)
-   [Compreendidos coexistência e interoperabilidade do Skype para equipes e de negócios](https://aka.ms/SkypeToTeams-Coexist)
-   [Escolhido sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Preparado o seu ambiente](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Preparado sua organização](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Conduzido um piloto](https://aka.ms/SkypeToTeams-Pilot)


# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Atualização do Skype para negócios Online para equipes

Siga as orientações neste artigo se você implantou integralmente Skype para Business Online e deseja atualizar seus usuários do Skype for Business para equipes. Você pode atualizar usuários seletivamente ou tudo em, com base na atualização jornada que sua organização tenha escolhido, atribuindo-se o modo de atualização e coexistência apropriada para seus usuários.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Atribuir o modo de atualização e coexistência

Atualizando para as equipes pode ser realizada, atribuindo-se o modo de TeamsOnly de TeamsUpgradePolicy, que pode ser realizada usando Microsoft Teams & Skype para o Centro de administração de empresa ou um Skype para sessão do Windows Powershell remoto de negócios.

Para obter mais informações, consulte [definindo sua coexistência e as configurações de atualização](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: Gerenciando a migração e coexistência](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

## <a name="phone-system-and-teams-upgrade"></a>Atualização de sistema telefônico e equipes

Se seu Skype para implantação Business Online inclui o sistema telefônico com planos de chamada e a Microsoft tem o seu provedor de telefônica pública comutada (PSTN) de rede, atualizando seus usuários para equipes passará automaticamente PSTN de entrada chamando-se às equipes.

Se seu Skype para implantação Business Online inclui o sistema telefônico com nuvem conector Edition, consulte as [Considerações adicionais sobre roteamento direto de sistema do telefone](2-envision-make-my-service-decisions-direct-routing.md).