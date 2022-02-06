---
title: Atualizar do Skype for Business local para o Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba como fazer a transição da sua organização para Microsoft Teams de uma implantação Skype for Business local.
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
---

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Atualizar de uma implantação Skype for Business local para Teams

![Estágios da jornada de atualização, com ênfase no estágio implantação e implementação.](media/upgrade-banner-deployment.png "Estágios da jornada de atualização, com ênfase no estágio implantação e implementação")

Este artigo faz parte do estágio implantação e implementação de sua jornada de atualização. Antes de prosseguir, confirme se você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](./upgrade-define-project-scope.md)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparou seu ambiente](./upgrade-prepare-environment.md)
- [Preparou sua organização](./upgrade-prepare-organization.md)
- [Conduzido um piloto](./pilot-essentials.md)

Siga as diretrizes deste artigo se você tiver implantado o Skype for Business ou o Microsoft Lync no local e sua organização quiser atualizar para o Microsoft Teams seletivamente, usando vários modos de coexistência ou todo o pacote. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Etapa 1: Implantar conectividade híbrida

O principal pré-requisito para atualizar seus usuários para Teams é implantar a conectividade híbrida.

Para obter mais informações, [consulte Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Etapa 2: Implementar sua jornada de atualização escolhida para sua organização

Depois de concluir sua configuração híbrida, você pode planejar mover seus usuários para Microsoft 365 ou Office 365.

Para obter mais informações, consulte:

- [TeamsUpgradePolicy: gerenciando migração e coexistência](upgrade-to-teams-on-prem-tools.md).

- [Mova os usuários do local para o Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="phone-system-and-teams-upgrade"></a>Sistema de Telefonia e Teams atualização

A transição de sistemas telefônicos locais para o Teams permitirá que você tire proveito do roteamento direto Sistema de Telefonia ("Roteamento Direto") ou dos Planos de Chamadas fornecidos pela Microsoft para Microsoft 365 ou Office 365.

Se você não estiver usando Planos de Chamadas, precisará fazer a transição da implantação de voz da empresa para Sistema de Telefonia Roteamento Direto como parte da atualização para Teams.

Para obter mais informações, [consulte considerações adicionais sobre Sistema de Telefonia Roteamento Direto](./direct-routing-landing-page.md). Se você estiver planejando usar Planos de Chamadas, consulte nossas diretrizes para transferir seus números de telefone [para](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) Teams.