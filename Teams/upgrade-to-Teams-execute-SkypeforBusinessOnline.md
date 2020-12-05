---
title: Atualizar do Skype for Business online para o Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba como atualizar sua organização para o Microsoft Teams a partir de uma implantação do Skype for Business online.
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
ms.openlocfilehash: ca99c193a17547943018eba75004f0ec0a1a92f3
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578254"
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

Para obter mais informações, consulte [definindo suas configurações de coexistência e atualização](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: Gerenciando a migração e a coexistência](upgrade-to-teams-on-prem-tools.md).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Atualizar todos os usuários para o Teams ao mesmo tempo

Siga estas etapas para atualizar todos os usuários para o Teams ao mesmo tempo.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Etapa 1: notifique os usuários sobre a alteração (opcional)

1. No centro de administração do Microsoft Teams, selecione atualização **de equipes de configurações de toda a organização**  >  **Teams upgrade**.
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
1. No centro de administração do Microsoft Teams, selecione **usuários** e localize e selecione várias caixas de seleção para até 20 usuários que devem ser atualizados. 
2. Selecione **Editar configurações** no canto superior esquerdo da ListView. 
3. No painel **Editar configurações** à direita, em atualização do Microsoft **Teams**, altere **Notifique a opção usuário do Skype for Business** para **ligar**. Observação: se o valor do modo de coexistência for "usar configurações de toda a organização", você precisará primeiro definir explicitamente o modo de coexistência para esses usuários, seja qual for o valor padrão para a organização.

Como alternativa, talvez seja mais fácil habilitar notificações para grupos de usuários de uma vez usando o PowerShell. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Etapa 3: definir o modo de coexistência de usuários somente para equipes

Quando estiver pronto para atualizar os usuários da onda atual para usar o Microsoft Teams como o único aplicativo, defina o modo de coexistência para os usuários somente para equipes.

Se estiver usando o centro de administração do Microsoft Teams, você pode configurar o TeamsUpgradePolicy para até 20 usuários de uma só vez:
1. No centro de administração do Microsoft Teams, selecione **usuários** e marque a caixa de seleção de até 20 usuários.
2. Selecione **Editar configurações** no canto superior esquerdo da ListView.
3. No painel **Editar configurações** à direita, em seção **atualização do teams** , defina o modo de coexistência com o Microsoft **Teams somente** na lista suspensa.

Você também pode achar mais fácil atualizar os grupos de usuários de uma vez usando o PowerShell. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Etapa 4: Repita as etapas 1-3 para ondas sucessivas de usuários

Ao validar a atualização para o modo somente Teams e estiver pronto para expandir, repita as etapas anteriores para aplicar o TeamsOnly a mais usuários.  


## <a name="phone-system-and-pstn-connectivity-options"></a>Opções de conectividade PSTN e do sistema telefônico

O sistema telefônico com Teams tem suporte depois que o usuário está no modo TeamsOnly. (Se o usuário estiver no modo de ilhas, o sistema telefônico só tem suporte no Skype for Business.)  

### <a name="pstn-connectivity-options"></a>Opções de conectividade PSTN

Ao considerar as opções de conectividade PSTN (rede telefônica pública comutada), há dois cenários possíveis ao migrar do Skype for Business online para o modo TeamsOnly:

- Um usuário no Skype for Business Online, com um plano de chamadas da Microsoft. Após a atualização, este usuário continuará a ter um plano de chamadas da Microsoft. Esse é o cenário mais simples que requer apenas algumas etapas. Para obter mais informações, consulte [o Skype for Business online com planos de chamada da Microsoft](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).

- Um usuário no Skype for Business Online, com funcionalidade de voz local por meio do Skype for Business local ou da edição do Cloud Connector. A atualização do usuário para o Teams precisa ser coordenada com a migração do usuário para o roteamento direto para garantir que o usuário do TeamsOnly tenha funcionalidade PSTN.  Para obter mais informações, consulte o [Skype for Business online com voz local](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).


