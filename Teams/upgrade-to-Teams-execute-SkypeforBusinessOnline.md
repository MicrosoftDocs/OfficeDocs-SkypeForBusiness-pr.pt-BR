---
title: Atualizar do Skype for Business Online para o Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba como atualizar sua organização para o Microsoft Teams a partir de uma implantação do Skype for Business Online.
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

![Diagrama de atualização da jornada, enfatizando Implantação e Implementação](media/upgrade-banner-deployment.png "Estágios da jornada de atualização, com ênfase no estágio de Implantação e Implementação")

Este artigo faz parte da etapa implantação e implementação da sua jornada de atualização. Antes de prosseguir, confirme que você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](https://aka.ms/SkypetoTeams-Scope)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparou seu ambiente](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Preparar sua organização](https://aka.ms/SkypeToTeams-UserReadiness)
- [Piloto conduzido](https://aka.ms/SkypeToTeams-Pilot)

Siga as orientações neste artigo se você implantou o Skype for Business Online e deseja atualizar seus usuários do Skype for Business para o Teams. Você pode atualizar os usuários seletivamente ou de forma total, com base na jornada de atualização escolhida pela sua organização, atribuindo a coexistência e o modo de atualização apropriados aos usuários.

> [!IMPORTANT]
> O Skype for Business Online será desativado em 31 de julho de 2021, e depois disso não estará mais acessível nem terá suporte. Para maximizar a realização dos benefícios e garantir que sua organização tenha tempo adequado para implementar a atualização, recomendamos que você comece hoje sua jornada para o Microsoft Teams. Lembre-se de que uma atualização bem-sucedida alinha a preparação técnica e do usuário, portanto, lembre-se de aproveitar as orientações aqui enquanto navega para o Microsoft Teams.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Atribuir a coexistência e o modo de atualização

Você pode atualizar seus usuários para o modo TeamsOnly atribuindo a instância UpgradeToTeams do TeamsUpgradePolicy, que pode ser executada usando o centro de administração do Microsoft Teams ou uma sessão remota do Windows PowerShell do Skype for Business. Você pode fazer isso por usuário ou em todo o locatário se quiser atualizar o locatário inteiro em uma etapa. 

Para obter mais informações, consulte [Definir suas configurações](https://aka.ms/SkypeToTeams-SetCoexistence) de coexistência e atualização e [TeamsUpgradePolicy: gerenciamento de migração e coexistência.](upgrade-to-teams-on-prem-tools.md)

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Atualizar todos os usuários para o Teams de uma só vez

Siga estas etapas para atualizar todos os usuários para o Teams de uma só vez.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Etapa 1: notificar os usuários sobre a alteração (opcional)

1. No Centro de administração do Microsoft Teams, selecione Atualização do Teams para configurações **em toda a**  >  **organização.**
2. Em **Modo de Coexistência,** altere a **notificação** dos usuários do Skype for Business de que uma atualização para o Teams está disponível para **a opção Para.**

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Etapa 2: Definir o modo de coexistência como TeamsOnly para a organização

1. No Centro de administração do Microsoft Teams, selecione **configurações de toda a organização.**
2. Selecione **o modo Somente** Equipes na listada do modo Coexistência. 

## <a name="upgrade-users-in-stages"></a>Atualizar usuários em estágios

Siga estas etapas se quiser atualizar gradualmente seus usuários para o TeamsOnly.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Etapa 1: identificar grupos de usuários para atualização

Muitas vezes, as organizações podem optar por atualizar suas organizações em ondas de sucesso dos usuários.  Primeiro, você deve identificar esses usuários para poder pesquisá-los facilmente no Centro de administração do Microsoft Teams. Como alternativa, talvez você queira usar o PowerShell para fazer isso com mais eficiência. Depois de identificar o conjunto de usuários para uma determinada onda de atualização, continue com as etapas restantes.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Etapa 2: Definir notificação para os usuários na onda de atualização atual (opcional)

Se estiver usando o Centro de administração do Microsoft Teams, você poderá configurar o TeamsUpgradePolicy para até 20 usuários ao mesmo tempo:
1. No Centro de administração do Microsoft Teams, selecione Usuários e localize e marque várias caixas de seleção para até 20 usuários que devem ser atualizados. 
2. Selecione **Editar configurações** no canto superior esquerdo da visualização de lista. 
3. No painel **Editar configurações à** direita, em Atualização do **Teams,** altere **Notificar** a opção do usuário do Skype for Business para **2010.** Observação: se o valor do modo de coexistência for "Usar configurações de toda a organização", você não verá essa opção, portanto, primeiro será necessário definir explicitamente o modo de Coexistência para esses usuários, seja qual for o valor padrão para a organização.

Como alternativa, talvez seja mais fácil habilitar notificações para grupos de usuários ao mesmo tempo usando o PowerShell. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Etapa 3: definir o modo de coexistência para os usuários como Somente Equipes

Quando você estiver pronto para atualizar os usuários na onda atual para usar o Teams como seu único aplicativo, de definir o modo de Coexistência para os usuários apenas para o Teams.

Se estiver usando o Centro de administração do Microsoft Teams, você poderá configurar o TeamsUpgradePolicy para até 20 usuários ao mesmo tempo:
1. No Centro de administração do Microsoft Teams, selecione **Usuários** e marque a caixa de seleção para até 20 usuários.
2. Selecione **Editar configurações** no canto superior esquerdo da visualização de lista.
3. No painel **Editar configurações** à direita, na seção de atualização do **Teams,** de definir o modo de coexistência como **Equipes** somente na lista listada.

Como alternativa, talvez seja mais fácil atualizar grupos de usuários de uma só vez usando o PowerShell. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Etapa 4: repetir as etapas de 1 a 3 para ondas sucessivas de usuários

Conforme validar sua atualização para o modo Somente do Teams e estiver pronto para expandir, repita as etapas anteriores para aplicar o TeamsOnly a mais usuários.  


## <a name="phone-system-and-pstn-connectivity-options"></a>Opções de conectividade PSTN e sistema telefônico

O Sistema telefônico com o Teams tem suporte depois que o usuário está no modo TeamsOnly. (Se o usuário estiver no modo Ilhas, o Sistema telefônico só tem suporte no Skype for Business.)  

### <a name="pstn-connectivity-options"></a>Opções de conectividade PSTN

Ao considerar as opções de conectividade PSTN (Rede Telefônica Pública Comutado), há dois cenários possíveis ao mudar do Skype for Business Online para o modo TeamsOnly:

- Um usuário no Skype for Business Online, com um Plano de Chamada da Microsoft. Após a atualização, esse usuário continuará a ter um plano de Chamada da Microsoft. Esse é o cenário mais simples que requer apenas algumas etapas. Para obter mais informações, [consulte Do Skype for Business Online com planos de Chamada da Microsoft.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)

- Um usuário no Skype for Business Online, com funcionalidade de voz local por meio do Skype for Business local ou do Cloud Connector Edition. A atualização do usuário para o Teams precisa ser coordenada com a migração do usuário para o Roteamento Direto para garantir que o usuário do TeamsOnly tenha funcionalidade PSTN.  Para obter mais informações, [consulte o Skype for Business Online com voz local.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)


