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
ms.openlocfilehash: 67bb6c10bb8cc5f37d332459d8e147f4f626497d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802341"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Atualizar de uma implantação híbrida do Skype for Business para o Teams

![Estágios da jornada de atualização, com ênfase no estágio de Implantação e Implementação](media/upgrade-banner-deployment.png "Estágios da jornada de atualização, com ênfase no estágio de Implantação e Implementação")

Este artigo faz parte da etapa implantação e implementação da sua jornada de atualização. Antes de prosseguir, confirme que você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](https://aka.ms/SkypetoTeams-Scope)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparou seu ambiente](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Preparar sua organização](https://aka.ms/SkypeToTeams-UserReadiness)
- [Piloto conduzido](https://aka.ms/SkypeToTeams-Pilot)

Siga as orientações neste artigo se você implantou o Skype for Business ou o Microsoft Lync local e configurou-o em uma implantação híbrida com sua organização do Microsoft 365 ou do Office 365, e sua organização deseja atualizar para o Teams seletivamente, usando vários modos de coexistência ou tudo. Para uma viagem de atualização, você precisa mover os usuários para o Skype for Business Online (se eles ainda não estão online) e atribuir a eles a coexistência e o modo de atualização apropriados.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Etapa 1: mover usuários para o Skype for Business Online

Esta etapa se aplica aos usuários que estão atualmente no local. Para obter mais informações sobre como mover esses usuários para o Skype for Business Online, consulte Mover usuários locais para [o Skype for Business Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Etapa 2: Atribuir um modo de coexistência e atualização

Depois de mudar seus usuários para o Skype for Business Online, você pode atribuir a eles o modo de coexistência apropriado com base na jornada de atualização escolhida pela sua organização. Para obter mais informações, consulte [Definir suas configurações](https://aka.ms/SkypeToTeams-SetCoexistence) de coexistência e atualização e [TeamsUpgradePolicy: gerenciamento de migração e coexistência.](upgrade-to-teams-on-prem-tools.md)

> [!NOTE]
> Com o Skype for Business Server 2019 e uma futura atualização cumulativa do Skype for Business Server 2015, você poderá executar a Etapa 1 (mover usuários para o Skype for Business Online) e a Etapa 2 (atualizar usuários para o Teams) em uma única etapa. Mais informações serão fornecidas após o lançamento do Skype for Business Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Atualização do Sistema de Telefonia e do Teams

Se você estiver fazendo a transição da implantação híbrida do Skype for Business para o Sistema telefônico com Planos de Chamada e a Microsoft for seu provedor de PSTN (rede telefônica pública comutado) e supondo que você concluiu a portagem de número de telefone, atualizar os usuários para o Teams fará a transição de chamadas PSTN de entrada automaticamente para o Teams.

Se os Planos de Chamada não estão disponíveis ou se você pretende usar seu provedor de conectividade PSTN existente, será necessário fazer a transição da implantação de voz corporativa ou a implantação de voz híbrida que usa a implantação local ou o Cloud Connector Edition existente para o Roteamento Direto do Sistema de Telefonia do Microsoft Phone. Para atualizar seus usuários para o Teams, consulte as considerações [adicionais sobre o Roteamento Direto do Sistema de Telefonia.](2-envision-make-my-service-decisions-direct-routing.md)
