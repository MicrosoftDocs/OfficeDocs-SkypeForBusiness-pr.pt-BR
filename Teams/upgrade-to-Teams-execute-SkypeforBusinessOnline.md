---
title: Atualizar do Skype for Business Online para o Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba como atualizar sua organização para o Microsoft Teams de uma implantação Skype for Business Online.
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
ms.openlocfilehash: 5da45fcc5a9459b909e03f0d4e904b57d9a3f0fa
ms.sourcegitcommit: 9a9168d5c40bbb0cceaf3ffd11eb104c137f26b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67590208"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Atualizar do Skype for Business Online para o Teams

![Diagrama de jornada de atualização, enfatizando a implantação e a implementação.](media/upgrade-banner-deployment.png "Estágios do percurso de atualização, com ênfase no estágio implantação e implementação")

Este artigo faz parte do estágio implantação e implementação do seu percurso de atualização. Antes de continuar, confirme se você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](./upgrade-define-project-scope.md)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparou seu ambiente](./upgrade-prepare-environment.md)
- [Preparou sua organização](./upgrade-prepare-organization.md)
- [Conduz um piloto](./pilot-essentials.md)

Siga as diretrizes neste artigo se você implantou totalmente o Skype for Business Online e deseja atualizar seus usuários do Skype for Business para o Teams. Você pode atualizar os usuários seletivamente ou todos, com base no percurso de atualização escolhido pela sua organização, atribuindo a coexistência e o modo de atualização apropriados aos usuários.

> [!IMPORTANT]
> Skype for Business Online foi desativado em 31 de julho de 2021. Para maximizar a realização dos benefícios e garantir que sua organização tenha tempo adequado para implementar a atualização, recomendamos que você comece hoje sua jornada para o Microsoft Teams. Lembre-se de que uma atualização bem-sucedida alinha a preparação técnica e do usuário, portanto, certifique-se de aproveitar as diretrizes aqui enquanto navega sua jornada para o Microsoft Teams.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Atribuir o modo de coexistência e atualização

Você pode atualizar seus usuários para o modo TeamsOnly atribuindo a instância UpgradeToTeams do TeamsUpgradePolicy, que pode ser executada usando o centro de administração do Microsoft Teams ou uma sessão Skype for Business de Windows PowerShell remota. Você pode fazer isso por usuário ou em todo o locatário se quiser atualizar todo o locatário em uma etapa. 

Para obter mais informações, consulte [Definindo suas configurações de coexistência](./setting-your-coexistence-and-upgrade-settings.md) e atualização [e TeamsUpgradePolicy: gerenciando a migração e a coexistência](upgrade-to-teams-on-prem-tools.md).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Atualizar todos os usuários para o Teams ao mesmo tempo

Siga estas etapas para atualizar todos os usuários para o Teams ao mesmo tempo.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Etapa 1: Notificar os usuários sobre a alteração (opcional)

1. No centro de administração do Microsoft Teams, selecione as **configurações de****atualização do** Teams > .
2. No **modo coexistência**, altere a opção **Notificar Skype for Business usuários de que uma atualização para o Teams está disponível**, alterne para **Ativado**.

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Etapa 2: Definir o modo de coexistência como TeamsOnly para a organização

1. No centro de administração do Microsoft Teams, selecione as **configurações de****atualização do** Teams > .
2. Selecione **o modo Somente** Equipes **na lista** suspensa modo coexistência.

## <a name="upgrade-users-in-stages"></a>Atualizar usuários em estágios

Siga estas etapas se quiser atualizar gradualmente seus usuários para o TeamsOnly.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Etapa 1: Identificar grupos de usuários para atualização

Muitas vezes, as organizações podem optar por atualizar suas organizações em ondas de sucesso dos usuários.  Você desejará identificar esses usuários primeiro para poder pesquisá-los facilmente no centro de administração do Microsoft Teams. Como alternativa, talvez você queira usar o PowerShell para fazer isso com mais eficiência. Depois de identificar o conjunto de usuários para uma determinada onda de atualização, continue com as etapas restantes.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Etapa 2: Definir notificação para os usuários na onda de atualização atual (opcional)

Se estiver usando o centro de administração do Microsoft Teams, você poderá configurar o TeamsUpgradePolicy para até 20 usuários ao mesmo tempo:
1. No centro de administração do Microsoft Teams, selecione **Usuários e** localize e marque várias caixas de seleção para até 20 usuários que devem ser atualizados. 
2. Selecione **Editar configurações** no canto superior esquerdo do modo de exibição de lista. 
3. No painel **Editar configurações à** direita, em Atualização do **Teams**, altere Notificar Skype for Business **usuário** para **Ativado**. Observação: se o valor do modo de coexistência for "Usar configurações em toda a organização", você não verá essa opção, portanto, primeiro você precisará definir explicitamente o modo de coexistência para esses usuários como qualquer que seja o valor padrão para a organização.

Como alternativa, você pode achar mais fácil habilitar notificações para grupos de usuários de uma só vez usando o PowerShell. Para obter mais informações, [consulte Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Etapa 3: Definir o modo de coexistência somente para usuários no Teams

Quando você estiver pronto para atualizar os usuários na onda atual para usar o Teams como seu único aplicativo, defina o modo coexistência para os usuários apenas para o Teams.

Se estiver usando o centro de administração do Microsoft Teams, você poderá configurar o TeamsUpgradePolicy para até 20 usuários ao mesmo tempo:
1. No centro de administração do Microsoft Teams, selecione **Usuários** e marque a caixa de seleção para até 20 usuários.
2. Selecione **Editar configurações** no canto superior esquerdo do modo de exibição de lista.
3. No painel **Editar configurações** à direita, na seção atualização do **Teams** , defina o modo de coexistência como **Teams** somente na lista suspensa.

Como alternativa, você pode achar mais fácil atualizar grupos de usuários de uma só vez usando o PowerShell. Para obter mais informações, [consulte Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Etapa 4: Repita as etapas de 1 a 3 para ondas sucessivas de usuários

À medida que você validar sua atualização para o modo Somente Equipes e estiver pronto para expandir, repita as etapas anteriores para aplicar o TeamsOnly a mais usuários.  


## <a name="phone-system-and-pstn-connectivity-options"></a>Opções de conectividade PSTN e Sistema de Telefonia

Há suporte para o Sistema de Telefonia com o Teams depois que o usuário está no modo TeamsOnly. (Se o usuário estiver no modo Ilhas, o Sistema de Telefonia só será compatível com Skype for Business.)  

### <a name="pstn-connectivity-options"></a>Opções de conectividade PSTN

Ao considerar as opções de conectividade PSTN (Rede Telefônica Pública Comunada), há dois cenários possíveis ao migrar do Skype for Business Online para o modo TeamsOnly:

- Um usuário do Skype for Business Online, com um Plano de Chamadas da Microsoft. Após a atualização, esse usuário continuará a ter um plano de Chamada da Microsoft. Esse é o cenário mais simples que requer apenas algumas etapas. Para obter mais informações, [consulte Do Skype for Business Online com planos de chamadas da Microsoft](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).

- Um usuário do Skype for Business Online, com funcionalidade de voz local por meio Skype for Business local ou Cloud Connector Edition. A atualização do usuário para o Teams precisa ser coordenada com a migração do usuário para o Roteamento Direto para garantir que o usuário do TeamsOnly tenha funcionalidade PSTN.  Para obter mais informações, [consulte Skype for Business Online com voz local](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).
