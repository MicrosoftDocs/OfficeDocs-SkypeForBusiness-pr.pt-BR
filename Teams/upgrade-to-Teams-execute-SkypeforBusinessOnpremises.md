---
title: Atualizar do Skype for Business local para o Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba como fazer a transição de sua organização para o Microsoft Teams Skype for Business implantação local.
ms.localizationpriority: medium
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
ms.openlocfilehash: 7b06134a0fe0f72e8dc9c01b4faa85c67a6063f3
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615437"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Atualizar de uma Skype for Business implantação local para o Teams

![Estágios do percurso de atualização, com ênfase no estágio implantação e implementação.](media/upgrade-banner-deployment.png "Estágios do percurso de atualização, com ênfase no estágio implantação e implementação")

Este artigo faz parte do estágio implantação e implementação do seu percurso de atualização. Antes de continuar, confirme se você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](./upgrade-define-project-scope.md)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparou seu ambiente](./upgrade-prepare-environment.md)
- [Preparou sua organização](./upgrade-prepare-organization.md)
- [Conduz um piloto](./pilot-essentials.md)

Siga as diretrizes neste artigo se você implantou o Skype for Business ou o Microsoft Lync localmente e sua organização deseja atualizar para o Microsoft Teams seletivamente, usando vários modos de coexistência ou tudo. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Etapa 1: Implantar conectividade híbrida

O principal pré-requisito para atualizar seus usuários para o Teams é implantar a conectividade híbrida.

Para obter mais informações, [consulte Implantar conectividade híbrida entre Skype for Business Server e Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Etapa 2: Implementar o percurso de atualização escolhido para sua organização

Depois de concluir a configuração híbrida, você pode planejar mover seus usuários para o Microsoft 365 ou Office 365.

Para obter mais informações, consulte:

- [TeamsUpgradePolicy: gerenciar a migração e a coexistência](upgrade-to-teams-on-prem-tools.md).

- [Mover usuários do local para o Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="phone-system-and-teams-upgrade"></a>Atualização do Sistema de Telefonia e do Teams

A transição de sistemas de telefonia locais para o Teams permitirá que você aproveite o Roteamento Direto do Sistema de Telefonia ("Roteamento Direto") ou os Planos de Chamadas fornecidos pela Microsoft para o Microsoft 365 ou Office 365.

Se você não estiver usando Planos de Chamadas, precisará fazer a transição da implantação de voz corporativa para o Roteamento Direto do Sistema de Telefonia como parte da atualização para o Teams.

Para obter mais informações, consulte [considerações adicionais sobre o Roteamento Direto do Sistema de Telefonia](./direct-routing-landing-page.md). Se você estiver planejando usar planos de chamadas, consulte nossas diretrizes para [transferir seus números de telefone para o Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).