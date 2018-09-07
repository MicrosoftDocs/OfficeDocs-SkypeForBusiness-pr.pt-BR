---
title: Atualizar a partir de um Skype para implantação híbrida do Business às equipes - Teams da Microsoft
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considerações para atualizar a equipes de um Skype para implantação híbrida do Business.
localization_priority: Priority
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8519f9fd79d15e7b1ebc5cc3fc5aa05b7e9e9112
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23868169"
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

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Atualizar a partir de um Skype para implantação híbrida do Business às equipes

Siga as orientações neste artigo se você implantou Skype para negócios ou Microsoft Lync local configurado em uma implantação híbrida com seu locatário do Office 365 e sua organização deseja atualizar para equipes ou seletivamente — usando vários modos de coexistência — ou tudo em. Para qualquer um dos jornada de atualização, você precisa mover os usuários para Skype para Business Online (se eles já não são hospedados online) e atribuí-las a coexistência apropriada e o modo de atualização.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Etapa 1: Mover usuários para Skype para negócios Online

Esta etapa se aplica a usuários que estão atualmente hospedados no local. Para obter mais informações sobre como mover esses usuários para Skype para Business Online, consulte [mover usuários de em - local para Skype para negócios Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Etapa 2: Atribuir uma coexistência e modo de atualização

Depois que você moveu os usuários para Skype para Business Online, você pode atribuir a eles o modo de coexistência apropriada com base em uma atualização jornada que sua organização tenha escolhido. Para obter mais informações, consulte [definindo sua coexistência e as configurações de atualização](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: Gerenciando a migração e coexistência](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

> [!NOTE]
> Com o Skype para Business Server 2019 e uma atualização cumulativa futura do Skype para Business Server 2015, você poderá executar a etapa 1 (mover usuários para Skype para Business Online) e a etapa 2 (atualização usuários às equipes) em uma única etapa. Mais informações serão fornecidas após o lançamento do Skype para Business Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Atualização de sistema telefônico e equipes

Se você estiver fazendo a transição de seu Skype para implantação híbrida de negócios para o sistema telefônico com planos de chamada e Microsoft será seu provedor de (PSTN) da rede telefônica pública comutada — e assumindo que você tiver concluído o número de telefone portando — atualizando os usuários As equipes passará automaticamente PSTN de entrada chamando-se às equipes.

Se os planos de chamada não está disponível ou se você pretende usar seu provedor de conectividade PSTN existente, será necessário fazer a transição de sua implantação do enterprise voice — ou implantação de voz híbrida que usa as existentes no local implantação ou a edição de conector de nuvem — para Sistema telefônico Microsoft direcionar circulação. Para atualizar seus usuários para equipes, consulte as [Considerações adicionais sobre roteamento direto de sistema do telefone](2-envision-make-my-service-decisions-direct-routing.md).
