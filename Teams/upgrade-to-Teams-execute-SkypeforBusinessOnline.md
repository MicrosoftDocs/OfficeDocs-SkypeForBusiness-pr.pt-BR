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
ms.openlocfilehash: 65b00f8e56792164ed2aa0b8240d0d131a7bdbcd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104007"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Atualizar do Skype for Business Online para o Teams

![Atualizar diagrama de jornada, enfatizando Implantação e Implementação](media/upgrade-banner-deployment.png "Estágios da jornada de atualização, com ênfase no estágio implantação e implementação")

Este artigo faz parte do estágio implantação e implementação da sua jornada de atualização. Antes de prosseguir, confirme se você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](./upgrade-define-project-scope.md)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparou seu ambiente](./upgrade-prepare-environment.md)
- [Preparou sua organização](./upgrade-prepare-organization.md)
- [Conduzido um piloto](./pilot-essentials.md)

Siga as diretrizes neste artigo se você tiver implantado totalmente o Skype for Business Online e quiser atualizar seus usuários do Skype for Business para o Teams. Você pode atualizar os usuários de forma seletiva ou all-in, com base na jornada de atualização escolhida pela sua organização, atribuindo a coexistência apropriada e o modo de atualização aos seus usuários.

> [!IMPORTANT]
> O Skype for Business Online será desativado em 31 de julho de 2021, e depois disso não estará mais acessível nem terá suporte. Para maximizar a realização dos benefícios e garantir que sua organização tenha tempo adequado para implementar a atualização, recomendamos que você comece hoje sua jornada para o Microsoft Teams. Lembre-se de que uma atualização bem-sucedida alinha a preparação técnica e do usuário, portanto, certifique-se de aproveitar as diretrizes aqui enquanto você navega sua jornada para o Microsoft Teams.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Atribuir o modo de coexistência e atualização

Você pode atualizar seus usuários para o modo TeamsOnly atribuindo a instância UpgradeToTeams do TeamsUpgradePolicy, que pode ser executada usando o centro de administração do Microsoft Teams ou uma sessão de Windows PowerShell remota do Skype for Business. Você pode fazer isso por usuário ou em toda a locatário se quiser atualizar o locatário inteiro em uma etapa. 

Para obter mais informações, consulte [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Atualizar todos os usuários para o Teams de uma só vez

Siga estas etapas para atualizar todos os seus usuários para o Teams ao mesmo tempo.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Etapa 1: Notificar os usuários sobre a alteração (opcional)

1. No centro de administração do Microsoft Teams, selecione **Configurações** em toda a organização  >  **Atualização do Teams**.
2. Em **Modo de Coexistência,** altere a **opção Notificar** usuários do Skype for Business de que uma atualização para o Teams está disponível para **On**.

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Etapa 2: Definir o modo de coexistência como TeamsOnly para a organização

1. No centro de administração do Microsoft Teams, selecione **Configurações em toda a organização.**
2. Selecione **o modo Somente** equipes na lista de listada no modo coexistência. 

## <a name="upgrade-users-in-stages"></a>Atualizar usuários em estágios

Siga estas etapas se quiser atualizar gradualmente seus usuários para o TeamsOnly.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Etapa 1: Identificar grupos de usuários para atualização

Muitas vezes, as organizações podem optar por atualizar suas organizações em ondas de sucesso de usuários.  Você vai querer identificar esses usuários primeiro para que você possa facilmente pesquisá-los no centro de administração do Microsoft Teams. Como alternativa, talvez você queira usar o PowerShell para fazer isso com mais eficiência. Depois de identificar o conjunto de usuários para uma determinada onda de atualização, continue com as etapas restantes.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Etapa 2: Definir notificação para os usuários na onda de atualização atual (opcional)

Se estiver usando o centro de administração do Microsoft Teams, você poderá configurar o TeamsUpgradePolicy para até 20 usuários ao mesmo tempo:
1. No Centro de administração do Microsoft Teams, selecione **Usuários** e localize e selecione a caixa de seleção para até 20 usuários que devem ser atualizados. 
2. Selecione **Editar configurações** no canto superior esquerdo da listview. 
3. No painel **Editar configurações** à direita, em Atualização do **Teams,** altere **Notificar** a opção de usuário do Skype for Business para **On**. Observação: se o valor do modo de coexistência for "Usar configurações em toda a organização", você não verá essa opção, portanto, primeiro você precisará definir explicitamente o modo coexistência para esses usuários como qualquer que seja o valor padrão para a organização.

Como alternativa, você pode encontrar mais fácil habilitar notificações para grupos de usuários ao mesmo tempo usando o PowerShell. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Etapa 3: Definir o modo de coexistência para usuários como Somente equipes

Quando você estiver pronto para atualizar os usuários na onda atual para usar o Teams como seu único aplicativo, de definir o modo coexistência para os usuários como Somente teams.

Se estiver usando o centro de administração do Microsoft Teams, você poderá configurar o TeamsUpgradePolicy para até 20 usuários ao mesmo tempo:
1. No centro de administração do Microsoft Teams, selecione **Usuários** e selecione a caixa de seleção para até 20 usuários.
2. Selecione **Editar configurações** no canto superior esquerdo da listview.
3. No painel **Editar configurações** à direita, na seção Atualização do **Teams,** de definir o modo de coexistência como **Teams Somente** na lista de menus.

Como alternativa, talvez seja mais fácil atualizar grupos de usuários ao mesmo tempo usando o PowerShell. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Etapa 4: Repita as etapas 1-3 para ondas sucessivas de usuários

À medida que você valida sua atualização para o modo Somente do Teams e está pronto para expandir, repita as etapas anteriores para aplicar o TeamsOnly a mais usuários.  


## <a name="phone-system-and-pstn-connectivity-options"></a>Opções de conectividade do Sistema de Telefonia e PSTN

O Sistema de Telefonia com o Teams é suportado depois que o usuário está no modo TeamsOnly. (Se o usuário estiver no modo Ilhas, o Sistema de Telefonia só será suportado com o Skype for Business.)  

### <a name="pstn-connectivity-options"></a>Opções de conectividade PSTN

Ao considerar as opções de conectividade PSTN (Rede Telefônica Pública Comucionada), há dois cenários possíveis ao mudar do Skype for Business Online para o modo TeamsOnly:

- Um usuário no Skype for Business Online, com um Plano de Chamadas da Microsoft. Após a atualização, esse usuário continuará a ter um plano de Chamada da Microsoft. Esse é o cenário mais simples que exige apenas algumas etapas. Para obter mais informações, consulte [From Skype for Business Online with Microsoft Calling Plans](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).

- Um usuário no Skype for Business Online, com funcionalidade de voz local por meio do Skype for Business local ou do Cloud Connector Edition. A atualização do usuário para o Teams precisa ser coordenada com a migração do usuário para Roteamento Direto para garantir que o usuário do TeamsOnly tenha funcionalidade PSTN.  Para obter mais informações, [consulte From Skype for Business Online with on-premises voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).