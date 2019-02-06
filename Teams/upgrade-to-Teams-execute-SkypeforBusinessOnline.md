---
title: A atualização do Skype para negócios Online para equipes da Microsoft | Implantar
author: arachmanGitHub
ms.author: arachman
manager: serdars
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
ms.openlocfilehash: 668e44b66b08b16a04e730c43dbbe02a9edea4fe
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754627"
---
![Estágios da atualização jornada, com ênfase sobre a implantação e o estágio de implementação] (media/upgrade-banner-deployment.png "Estágios da atualização jornada, com ênfase sobre a implantação e o estágio de implementação")

Este artigo faz parte do estágio de implantação e a implementação da sua jornada de atualização. Antes de continuar, confirme que você tiver concluído as seguintes atividades:

- [Inscrito seus participantes do projeto](upgrade-enlist-stakeholders.md)
- [Definido o escopo do projeto](https://aka.ms/SkypetoTeams-Scope)
- [Compreendidos coexistência e interoperabilidade do Skype para equipes e de negócios](https://aka.ms/SkypeToTeams-Coexist)
- [Escolhido sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparado o seu ambiente](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Preparado sua organização](https://aka.ms/SkypeToTeams-UserReadiness)
- [Conduzido um piloto](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Atualização do Skype para negócios Online para equipes

Siga as orientações neste artigo se você implantou integralmente Skype para Business Online e deseja atualizar seus usuários do Skype for Business para equipes. Você pode atualizar usuários seletivamente ou tudo em, com base na atualização jornada que sua organização tenha escolhido, atribuindo-se o modo de atualização e coexistência apropriada para seus usuários.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Atribuir o modo de atualização e coexistência

Você pode atualizar seus usuários por equipes, atribuindo-se o modo de TeamsOnly de TeamsUpgradePolicy, que pode ser realizada usando o Centro de administração do Microsoft Teams ou um Skype para a sessão do Windows Powershell remoto de negócios.

Para obter mais informações, consulte [definindo sua coexistência e as configurações de atualização](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: Gerenciando a migração e coexistência](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Atualizar todos os usuários a equipes de uma só vez

Siga estas etapas para atualizar todos os seus usuários a equipes de uma só vez.

### <a name="step-1-notify-the-users-of-the-change"></a>Etapa 1: Notificar os usuários da alteração

1. No Centro de administração do Microsoft Teams, selecione **configurações de toda a organização** > **equipes de atualização**.
2. Em **modo de coexistência**, altere a opção de **Notificar Skype para usuários corporativos que uma atualização para equipes está disponível** para **ativado**.

### <a name="step-2-set-the-coexistence-mode-for-the-users"></a>Etapa 2: Definir o modo de coexistência para os usuários

1. No Centro de administração do Microsoft Teams, selecione **configurações de toda a organização**.
2. Selecione o modo de **Equipes somente** da lista suspensa **modo de coexistência** .

## <a name="upgrade-users-in-stages"></a>Atualizar os usuários em estágios

Se você quiser que seus usuários a atualização gradual para equipes, siga estas etapas.

### <a name="step-1-create-your-user-cohorts-for-the-upgrade"></a>Etapa 1: Criar seus colaboradores do usuário para a atualização

Colaboradores do usuário são grupos de usuários que serão movidos para o modo de equipes apenas ao mesmo tempo.

Para criar seus colaboradores (adicionar o link à página de seleção do usuário) do usuário

### <a name="step-2-set-the-user-mode-to-islands"></a>Etapa 2: Configurar o modo de usuário para ilhas

1. No Centro de administração do Microsoft Teams, selecione **usuários**e selecione um cohort do usuário.
2. Ao lado de **atualização de equipes**, selecione **Editar**.
3. No painel de **Atualização de equipes** , em **modo de coexistência**, selecione **Ilhas** da lista suspensa.

### <a name="step-3-set-notification-for-the-user-optional"></a>Etapa 3: Configurar a notificação para o usuário (opcional)

1. No Centro de administração do Microsoft Teams, selecione **usuários**e selecione um cohort do usuário.
2. Ao lado de **atualização de equipes**, selecione **Editar**.
3. No painel de **Atualização de equipes** , em **modo de coexistência**, altere opção **notificar o Skype para o usuário de negócios** para **ativado**.

### <a name="step-4-set-the-user-mode-to-teams-only"></a>Etapa 4: Configurar o modo de usuário para equipes somente

Quando estiver pronto para atualizar os usuários para usar equipes como seus aplicativos somente, defina o modo de coexistência para o usuário para equipes somente.

1. No Centro de administração do Microsoft Teams, selecione **usuários**e selecione um cohort do usuário.
2. Ao lado de **atualização de equipes**, selecione **Editar**.
3. No painel de **Atualização de equipes** , em **modo de coexistência**, selecione **Equipes somente** da lista suspensa.

## <a name="phone-system-and-teams-upgrade"></a>Atualização de sistema telefônico e equipes

Se seu Skype para implantação Business Online inclui o sistema telefônico com planos de chamada e a Microsoft tem o seu provedor de telefônica pública comutada (PSTN) de rede, atualizando seus usuários para equipes passará automaticamente PSTN de entrada chamando-se às equipes.

Se seu Skype para implantação Business Online inclui o sistema telefônico com nuvem conector Edition, consulte as [Considerações adicionais sobre roteamento direto de sistema do telefone](2-envision-make-my-service-decisions-direct-routing.md).