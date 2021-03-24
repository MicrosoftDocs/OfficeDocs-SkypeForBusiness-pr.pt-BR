---
title: Atualizar a implantação híbrida do Skype for Business para o Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba como atualizar sua organização para o Microsoft Teams a partir de uma implantação híbrida do Skype for Business.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97725e7a9790f47f9789366567981f0167fdd806
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104017"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Atualizar de uma implantação híbrida do Skype for Business para o Teams

![Estágios da jornada de atualização, com ênfase no estágio implantação e implementação](media/upgrade-banner-deployment.png "Estágios da jornada de atualização, com ênfase no estágio implantação e implementação")

Este artigo faz parte do estágio implantação e implementação da sua jornada de atualização. Antes de prosseguir, confirme se você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](./upgrade-define-project-scope.md)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparou seu ambiente](./upgrade-prepare-environment.md)
- [Preparou sua organização](./upgrade-prepare-organization.md)
- [Conduzido um piloto](./pilot-essentials.md)

Siga as diretrizes neste artigo se você implantou o Skype for Business ou o Microsoft Lync local e configurou-o em uma implantação híbrida com sua organização do Microsoft 365 ou office 365, e sua organização deseja atualizar para o Teams seletivamente, usando vários modos de coexistência ou tudo. Para uma jornada de atualização, você precisa mover seus usuários para o Skype for Business Online (se eles ainda não estão online) e atribuir a eles o modo de coexistência e atualização apropriados.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Etapa 1: mover usuários para o Skype for Business Online

Esta etapa se aplica aos usuários que estão atualmente no local. Para obter mais informações sobre como mover esses usuários para o Skype for Business Online, consulte [Move users from on-premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Etapa 2: Atribuir um modo de coexistência e atualização

Depois de ter movido seus usuários para o Skype for Business Online, você pode atribuir a eles o modo de coexistência apropriado com base na jornada de atualização escolhida pela sua organização. Para obter mais informações, consulte [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).

> [!NOTE]
> Com o Skype for Business Server 2019 e uma atualização cumulativa futura do Skype for Business Server 2015, você poderá executar a Etapa 1 (mover usuários para o Skype for Business Online) e a Etapa 2 (atualizar usuários para o Teams) em uma única etapa. Mais informações serão fornecidas depois que o Skype for Business Server 2019 for lançado.

## <a name="phone-system-and-teams-upgrade"></a>Atualização do Sistema de Telefonia e do Teams

Se você estiver fazendo a transição da implantação híbrida do Skype for Business para o Sistema de Telefonia com Planos de Chamadas e a Microsoft será o provedor PSTN (rede telefônica pública comutado) e supondo que você concluiu a portação de número de telefone, atualizar seus usuários para o Teams fará a transição automática de chamadas PSTN de entrada para o Teams.

Se Os Planos de Chamadas não estão disponíveis ou você pretende usar seu provedor de conectividade PSTN existente, você precisará fazer a transição da implantação de voz corporativa ou a implantação de voz híbrida que usa a implantação local ou o Cloud Connector Edition existente para o Roteamento Direto do Sistema de Telefonia do Microsoft Phone. Para atualizar seus usuários para o Teams, consulte as [considerações adicionais para Roteamento Direto do Sistema de Telefonia.](./direct-routing-landing-page.md)