---
title: Atualize o Skype for Business online para o Microsoft Teams | Implementar
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Saiba como atualizar sua organização para o Microsoft Teams a partir de um deployement do Skype for Business online.
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
ms.openlocfilehash: 37deecdbff083718dcb5b8a16e77ac8da4b998ff
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905353"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Atualizar do Skype for Business Online para o Teams

![Atualize o diagrama de viagem, enfatizando implantação e implementação](media/upgrade-banner-deployment.png "Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação")

Este artigo faz parte do estágio de implantação e implementação da sua jornada de atualização. Antes de prosseguir, confirme que você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](https://aka.ms/SkypetoTeams-Scope)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Seu ambiente foi preparado](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Preparou sua organização](https://aka.ms/SkypeToTeams-UserReadiness)
- [Conduziu um piloto](https://aka.ms/SkypeToTeams-Pilot)

Siga as orientações neste artigo se você tiver implantado o Skype for Business online com total implementação e quiser atualizar os usuários do Skype for Business para o Microsoft Teams. Você pode atualizar usuários seletivamente ou todos os usuários, com base na jornada de atualização que a sua organização escolheu, atribuindo o modo de coexistência e atualização apropriado para seus usuários.

> [!IMPORTANT]
> O Skype for Business Online será desativado em 31 de julho de 2021, e depois disso não estará mais acessível nem terá suporte. Para maximizar a realização dos benefícios e garantir que sua organização tenha tempo adequado para implementar a atualização, recomendamos que você comece hoje sua jornada para o Microsoft Teams. Lembre-se de que uma atualização bem-sucedida alinha a prontidão técnica e do usuário, portanto, não deixe de aproveitar as diretrizes contidas ao navegar na jornada para o Microsoft Teams.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Atribuir a coexistência e o modo de atualização

Você pode atualizar os usuários para o modo TeamsOnly atribuindo a instância UpgradeToTeams do TeamsUpgradePolicy, que pode ser realizada usando o centro de administração do Microsoft Teams ou uma sessão do Windows PowerShell remota do Skype for Business. Você pode fazer isso por usuário ou com base em todo o locatário, se quiser atualizar o locatário inteiro em uma etapa. 

Para obter mais informações, consulte [definindo suas configurações de coexistência e atualização](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: Gerenciando a migração e a coexistência](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Atualizar todos os usuários para o Teams ao mesmo tempo

Siga estas etapas para atualizar todos os usuários para o Teams ao mesmo tempo.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Etapa 1: notifique os usuários sobre a alteração (opcional)

1. No centro de administração do Microsoft Teams, selecione**atualização de equipes** **de configurações** > de toda a organização.
2. Em **modo de coexistência**, **altere a opção** **notificar os usuários do Skype for Business que uma atualização para o Microsoft Teams está disponível** .

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Etapa 2: definir o modo de coexistência como TeamsOnly para a organização

1. No centro de administração do Microsoft Teams, selecione **configurações de toda a organização**.
2. Selecione modo **somente equipes** na lista suspensa **modo de coexistência** .

## <a name="upgrade-users-in-stages"></a>Atualizar usuários em estágios

Siga estas etapas se quiser atualizar gradualmente seus usuários para o TeamsOnly.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Etapa 1: identificar grupos de usuários para atualização

Muitas vezes, as organizações podem optar por atualizar suas organizações em ondas de sucesso de usuários.  Convém identificar esses usuários primeiro para que você possa procurá-los facilmente no centro de administração do Microsoft Teams. Você também pode querer usar o PowerShell para fazer isso com mais eficiência. Depois de identificar o conjunto de usuários para uma determinada onda de atualização, continue com as etapas restantes.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Etapa 2: definir notificação para os usuários na onda de atualização atual (opcional)

Se estiver usando o centro de administração do Microsoft Teams, você pode configurar o TeamsUpgradePolicy para até 20 usuários de uma só vez:
1. No centro de administração do Microsoft Teams, selecione **usuários**e localize e selecione várias caixas de seleção para até 20 usuários que devem ser atualizados. 
2. Selecione **Editar configurações** no canto superior esquerdo da ListView. 
3. No painel **Editar configurações** à direita, em atualização do Microsoft **Teams**, altere **Notifique a opção usuário do Skype for Business** para **ligar**. Observação: se o valor do modo de coexistência for "usar configurações de toda a organização", você precisará primeiro definir explicitamente o modo de coexistência para esses usuários, seja qual for o valor padrão para a organização.

Como alternativa, talvez seja mais fácil habilitar notificações para grupos de usuários de uma vez usando o PowerShell. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Etapa 3: definir o modo de coexistência de usuários somente para equipes

Quando estiver pronto para atualizar os usuários da onda atual para usar o Microsoft Teams como o único aplicativo, defina o modo de coexistência para os usuários somente para equipes.

Se estiver usando o centro de administração do Microsoft Teams, você pode configurar o TeamsUpgradePolicy para até 20 usuários de uma só vez:
1. No centro de administração do Microsoft Teams, selecione **usuários**e marque a caixa de seleção de até 20 usuários.
2. Selecione **Editar configurações** no canto superior esquerdo da ListView.
3. No painel **Editar configurações** à direita, em seção **atualização do teams** , defina o modo de coexistência com o Microsoft **Teams somente** na lista suspensa.

Você também pode achar mais fácil atualizar os grupos de usuários de uma vez usando o PowerShell. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Etapa 4: Repita as etapas 1-3 para ondas sucessivas de usuários

Ao validar a atualização para o modo somente Teams e estiver pronto para expandir, repita as etapas anteriores para aplicar o TeamsOnly a mais usuários.  


## <a name="phone-system-and-teams-upgrade"></a>Atualização do sistema de telefonia e do teams

Se a sua implantação do Skype for Business online incluir o sistema telefônico com planos de chamadas e a Microsoft for o seu provedor de rede telefônica pública comutada (PSTN), a atualização de seus usuários para o Microsoft Teams fará automaticamente a chamada PSTN de entrada para o Teams.

Se a sua implantação do Skype for Business Online inclui o sistema telefônico com o Cloud Connector Edition, consulte [considerações adicionais sobre o roteamento direto do sistema telefônico](2-envision-make-my-service-decisions-direct-routing.md).
