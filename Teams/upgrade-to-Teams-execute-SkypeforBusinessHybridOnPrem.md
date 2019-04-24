---
title: Atualizar para o Microsoft Teams de uma implantação híbrida ou local do Skype for Business ‒ Microsoft Teams
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considerações para atualizar a equipes de um Skype para implantação de híbrido ou local de negócios.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38a9c3bd2e9649ea657a559f1c6d41aab86edd56
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32218720"
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

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a>Atualizar a equipes de um Skype para implantação de híbrido ou local de negócios

Siga as orientações neste artigo se você implantou Skype para negócios ou Microsoft Lync no local e sua organização deseja atualizar para equipes ou seletivamente — usando vários modos de coexistência — ou tudo em. A primeira etapa é configurar a conectividade híbrida com seu locatário do Office 365 e mova os usuários para Skype para Business Online e atribuí-las a coexistência apropriada e modo de atualização. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Etapa 1: Implantar a conectividade híbrida 

O pré-requisito principal para atualizar seus usuários para equipes é implantar conectividade híbrida. Isso pode envolver Implantando nova conectividade externa para sua Skype existente para a implantação do Lync ou de negócios ou simplesmente como configurar uma relação de híbrido com seu locatário do Office 365. 

Para obter mais informações, consulte [Deploy a conectividade de híbrido entre Skype para Business Server e do Skype para negócios Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).

## <a name="step-2-move-users-to-skype-for-business-online"></a>Etapa 2: Mover usuários para Skype para negócios Online 

Depois de concluir sua configuração híbrida, mova usuários para Skype para negócios Online. 

Para obter mais informações, consulte [mover os usuários no local para Skype para negócios Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online). 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a>Etapa 3: Atribuir uma coexistência e modo de atualização

Depois que você moveu os usuários para Skype para Business Online, você pode atribuir a eles o modo de coexistência apropriada com base em uma atualização jornada que sua organização tenha escolhido. Para obter mais informações, consulte [definindo sua coexistência e as configurações de atualização](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: Gerenciando a migração e coexistência](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

> [!NOTE]
> Com o Skype para Business Server 2019 e uma atualização cumulativa futura do Skype para Business Server 2015, você poderá executar a etapa 2 (mover usuários para Skype para Business Online) e a etapa 3 (atualização usuários às equipes) em uma única etapa. Mais informações serão fornecidas após o lançamento do Skype para Business Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Atualização de sistema telefônico e equipes

Se você estiver fazendo a transição de seu Skype para implantação híbrida de negócios para o sistema telefônico com planos de chamada e Microsoft será seu provedor de (PSTN) da rede telefônica pública comutada — e assumindo que você tiver concluído o número de telefone portando — atualizando os usuários As equipes passará automaticamente PSTN de entrada chamando-se às equipes.

Se os planos de chamada não estiver disponível, você precisará fazer a transição de sua implantação do enterprise voice roteamento direto do Microsoft Phone System. Para atualizar seus usuários para equipes, consulte as [Considerações adicionais sobre roteamento direto de sistema do telefone](2-envision-make-my-service-decisions-direct-routing.md).
