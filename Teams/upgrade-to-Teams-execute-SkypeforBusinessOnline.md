---
title: A atualização do Skype para negócios Online para equipes da Microsoft | Implantar
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considerações para a atualização para equipes do Skype para negócios Online
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6748397c354f9238282f9646388993fc0e9f7b88
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902714"
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

# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Atualizar do Skype for Business Online para o Teams

Siga as orientações neste artigo se você implantou integralmente Skype para Business Online e deseja atualizar seus usuários do Skype for Business para equipes. Você pode atualizar usuários seletivamente ou tudo em, com base na atualização jornada que sua organização tenha escolhido, atribuindo-se o modo de atualização e coexistência apropriada para seus usuários.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Atribuir o modo de atualização e coexistência

Você pode atualizar seus usuários para o modo de TeamsOnly, atribuindo-se a instância de UpgradeToTeams do TeamsUpgradePolicy, que pode ser realizada usando o Centro de administração do Microsoft Teams ou um Skype para a sessão do Windows Powershell remoto de negócios. Você pode fazer isso em uma base por usuário, ou em uma base de todo o locatário de se desejar atualização inquilino inteiro em uma única etapa. 

Para obter mais informações, consulte [definindo sua coexistência e as configurações de atualização](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: Gerenciando a migração e coexistência](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Atualizar todos os usuários a equipes de uma só vez

Siga estas etapas para atualizar todos os seus usuários a equipes de uma só vez.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Etapa 1: Notificar os usuários da alteração (opcional)

1. No Centro de administração do Microsoft Teams, selecione **configurações de toda a organização** > **equipes de atualização**.
2. Em **modo de coexistência**, altere a opção de **Notificar Skype para usuários corporativos que uma atualização para equipes está disponível** para **ativado**.

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Etapa 2: Configurar o modo de coexistência para TeamsOnly para a organização

1. No Centro de administração do Microsoft Teams, selecione **configurações de toda a organização**.
2. Selecione o modo de **Equipes somente** da lista suspensa **modo de coexistência** .

## <a name="upgrade-users-in-stages"></a>Atualizar os usuários em estágios

Se você quiser que seus usuários a atualização gradual para TeamsOnly, siga estas etapas.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Etapa 1: Identificar os grupos de usuários para atualização

As organizações podem optar por atualizar suas organizações em ondas sucesso de usuários.  Você vai querer identificar esses usuários pela primeira vez, portanto, você pode facilmente procurar por elas no Centro de administração do Microsoft Teams. Como alternativa, convém usar o PowerShell para fazer isso de maneira mais eficiente. Depois de identificar o conjunto de usuários para uma determinada onda de atualização, continue com as etapas restantes.

### <a name="step-2-set-notification-for-the-users-in-the-current-ugprade-wave-optional"></a>Etapa 2: Definir uma notificação para os usuários na atualização onda atual (opcional)

Se estiver usando o Centro de administração do Microsoft Teams, você pode configurar TeamsUpgradePolicy para usuário até 20 ao mesmo tempo:
1. No Centro de administração do Microsoft Teams, selecione **os usuários**e find and seleção múltipla a caixa de seleção para até 20 usuários que deve ser atualizado. 
2. Selecione **Editar configurações** no canto superior esquerdo do automático. 
3. No painel à direita, em **atualização de equipes**, **Editar configurações** altere opção **notificar o Skype para o usuário de negócios** para **ativado**. Observação: Se o valor do modo de coexistência for "configurações de todo o uso Org", você não verá essa opção, portanto você precisará primeiro definir explicitamente o modo de coexistência para esses usuários ao vivo do que o valor padrão é de organograma.

Como alternativa, você talvez seja mais fácil habilitar as notificações para grupos de usuários ao mesmo tempo usando o PowerShell. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Etapa 3: Definir o modo de coexistência para que os usuários somente equipes

Quando estiver pronto para atualizar os usuários na onda atual para usar equipes como seus aplicativos somente, defina o modo de coexistência para os usuários para equipes apenas.

Se estiver usando o Centro de administração do Microsoft Teams, você pode configurar TeamsUpgradePolicy para usuário até 20 ao mesmo tempo:
1. No Centro de administração do Microsoft Teams, selecione **os usuários**e, em seguida, marque a caixa de seleção para até 20 usuários.
2. Selecione **Editar configurações** no canto superior esquerdo do automático.
3. No painel **Editar configurações** à direita, na seção **Atualizar equipes** , defina o modo de coexistência para **Equipes apenas** na lista suspensa.

Como alternativa, você talvez seja mais fácil para atualizar os grupos de usuários ao mesmo tempo usando o PowerShell. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Etapa 4: Repita as etapas 1 a 3 para fases sucessivas de usuários

Conforme você valida a atualização para o modo somente equipes e estiver pronto para expandir, repita as etapas anteriores para aplicar TeamsOnly a mais usuários.  


## <a name="phone-system-and-teams-upgrade"></a>Atualização de sistema telefônico e equipes

Se seu Skype para implantação Business Online inclui o sistema telefônico com planos de chamada e a Microsoft tem o seu provedor de telefônica pública comutada (PSTN) de rede, atualizando seus usuários para equipes passará automaticamente PSTN de entrada chamando-se às equipes.

Se seu Skype para implantação Business Online inclui o sistema telefônico com nuvem conector Edition, consulte as [Considerações adicionais sobre roteamento direto de sistema do telefone](2-envision-make-my-service-decisions-direct-routing.md).
