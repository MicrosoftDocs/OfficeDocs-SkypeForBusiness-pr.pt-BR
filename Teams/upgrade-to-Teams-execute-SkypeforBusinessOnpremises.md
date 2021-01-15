---
title: Atualizar do Skype for Business local para o Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba como fazer a transição da sua organização para o Microsoft Teams a partir de uma implantação local do Skype for Business.
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
ms.openlocfilehash: 90542f680c1d3992f5f318bfedad8a12470d282b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820941"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Atualizar de uma implantação local do Skype for Business para o Teams

![Estágios da jornada de atualização, com ênfase no estágio implantação e implementação](media/upgrade-banner-deployment.png "Estágios da jornada de atualização, com ênfase no estágio implantação e implementação")

Este artigo faz parte do estágio implantação e implementação da sua jornada de atualização. Antes de prosseguir, confirme se você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](https://aka.ms/SkypetoTeams-Scope)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparou seu ambiente](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Preparou sua organização](https://aka.ms/SkypeToTeams-UserReadiness)
- [Conduz um piloto](https://aka.ms/SkypeToTeams-Pilot)

Siga as orientações neste artigo se você implantou o Skype for Business ou o Microsoft Lync local e sua organização deseja atualizar para o Microsoft Teams seletivamente, usando vários modos de coexistência, ou todo o pacote. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Etapa 1: Implantar conectividade híbrida

O principal pré-requisito para atualizar seus usuários para o Teams é implantar a conectividade híbrida.

Para obter mais informações, [consulte Implantar conectividade híbrida entre o Skype for Business Server e o Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Etapa 2: Implementar sua jornada de atualização escolhida para sua organização

Depois de concluir a configuração híbrida, você pode planejar mover seus usuários para o Microsoft 365 ou o Office 365.

Para obter mais informações, consulte:

- [TeamsUpgradePolicy: gerenciando a migração e a coexistência.](upgrade-to-teams-on-prem-tools.md)

- [Mova os usuários do local para o Skype for Business Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="phone-system-and-teams-upgrade"></a>Atualização do Sistema de Telefonia e do Teams

A transição de sistemas telefônicos locais para o Teams permitirá que você aproveite o Roteamento Direto do Sistema de Telefonia ("Roteamento Direto") ou os Planos de Chamadas fornecidos pela Microsoft para o Microsoft 365 ou o Office 365.

Se você não estiver usando Planos de Chamadas, precisará fazer a transição da implantação de voz corporativa para o Roteamento Direto do Sistema de Telefonia como parte da atualização para o Teams.

Para obter mais informações, consulte [considerações adicionais sobre o Roteamento Direto do Sistema de Telefonia.](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing) Se você estiver planejando usar Planos de Chamadas, consulte nossa orientação para transferir seus números [de telefone para o Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)