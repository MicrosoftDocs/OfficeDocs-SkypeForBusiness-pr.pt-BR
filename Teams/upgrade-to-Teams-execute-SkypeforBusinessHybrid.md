---
title: Atualizar Skype for Business implantação híbrida para o Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba como atualizar sua organização para o Microsoft Teams de uma implantação Skype for Business híbrida.
ms.localizationpriority: medium
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
ms.openlocfilehash: 4ea8db9f53b891002cf7fbe1f5282051e7aca7ea
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615597"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Atualizar de uma implantação Skype for Business híbrida para o Teams

![Estágios do percurso de atualização, com ênfase no estágio implantação e implementação.](media/upgrade-banner-deployment.png "Estágios do percurso de atualização, com ênfase no estágio implantação e implementação")

Este artigo faz parte do estágio implantação e implementação do seu percurso de atualização. Antes de continuar, confirme se você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](./upgrade-define-project-scope.md)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparou seu ambiente](./upgrade-prepare-environment.md)
- [Preparou sua organização](./upgrade-prepare-organization.md)
- [Conduz um piloto](./pilot-essentials.md)

Siga as diretrizes neste artigo se você implantou o Skype for Business ou o Microsoft Lync localmente e o configurou em uma implantação híbrida com sua organização do Microsoft 365 ou Office 365, e sua organização deseja atualizar para o Teams seletivamente, usando vários modos de coexistência ou tudo. Para qualquer um dos percursos de atualização, você precisa mover seus usuários para o Skype for Business Online (se eles ainda não estiverem hospedados online) e atribuir a eles o modo de coexistência e atualização apropriados.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Etapa 1: Mover usuários para o Skype for Business Online

Esta etapa se aplica aos usuários que estão hospedados no local no momento. Para obter mais informações sobre como mover esses usuários para o Skype for Business Online, consulte Mover usuários do local para o [Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Etapa 2: Atribuir um modo de coexistência e atualização

Depois de migrar seus usuários para o Skype for Business Online, você pode atribuir a eles o modo de coexistência apropriado com base no percurso de atualização escolhido pela sua organização. Para obter mais informações, consulte [Definindo suas configurações de coexistência](./setting-your-coexistence-and-upgrade-settings.md) e atualização [e TeamsUpgradePolicy: gerenciando a migração e a coexistência](upgrade-to-teams-on-prem-tools.md).

> [!NOTE]
> Com o Skype for Business Server 2019 e uma atualização cumulativa futura do Skype for Business Server 2015, você poderá executar a Etapa 1 (mover usuários para o Skype for Business Online) e a Etapa 2 (atualizar usuários para o Teams) em uma única etapa. Mais informações serão fornecidas após o lançamento Skype for Business Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Atualização do Sistema de Telefonia e do Teams

Se você estiver fazendo a transição de sua implantação híbrida do Skype for Business para o Sistema de Telefonia com Planos de Chamadas e a Microsoft será seu provedor PSTN (rede telefônica pública comutadas) e supondo que você concluiu a portabilidade do número de telefone, atualizar os usuários para o Teams fará a transição automática de chamadas PSTN de entrada para o Teams.

Se os Planos de Chamadas não estão disponíveis ou se você pretende usar seu provedor de conectividade PSTN existente, você precisa fazer a transição da implantação de voz corporativa ou implantação de voz híbrida que usa a implantação local existente ou o Cloud Connector Edition para o Roteamento Direto do Sistema de Telefonia da Microsoft. Para atualizar seus usuários para o Teams, confira as [considerações adicionais sobre o Roteamento Direto do Sistema de Telefonia](./direct-routing-landing-page.md).