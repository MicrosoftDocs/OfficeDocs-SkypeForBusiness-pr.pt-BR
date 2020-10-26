---
title: Gerenciar a experiência do Microsoft Teams Exploratory
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Usuários do Microsoft 365 ou do Office 365 que não possuem licenças para o Microsoft Teams podem começar com uma licença do Teams Exploratory.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 35ebe9f93321b67806b9fd777aba948f83954c04
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753576"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a>Gerenciar a licença do Microsoft Teams Exploratory
=======================================================

A experiência do Microsoft Teams Exploratory permite que os usuários em sua organização que têm o Azure Active Directory (Azure AD) e não estão licenciados para o Teams iniciem uma experiência exploratória do Teams. Os administradores podem ativar ou desativar esse recurso para os usuários em sua organização. O [Microsoft Commercial Cloud Trial](iw-trial-teams.md) anterior agora foi substituído pela experiência do Teams Exploratory.

## <a name="whats-in-the-teams-exploratory-experience"></a>O que há na experiência do Teams Exploratory?

Os planos de serviço que um administrador exibirá como parte da experiência de exploratório da equipe são:

- Exchange Online (Plano 1)
- Flow para o Microsoft 365 ou para o Office 365
- Insight por MyAnalytics
- Microsoft Forms (Plano E1)
- Microsoft Planner
- Pesquisa da Microsoft
- Microsoft StaffHub
- Microsoft Stream para Microsoft 365 e Office 365 E1 SKUs<sup>1</1>
- Microsoft Teams
- Gerenciamento de Dispositivo Móvel para o Microsoft 365 ou Office 365
- Aplicativos do Office Mobile para Office 365
- Office Online
- PowerApps para o Microsoft 365 ou para o Office 365
- SharePoint Online (Plano 1)
- Sway
- To-Do (Plano 1)
- Quadro de Comunicações (Plano 1)
- Yammer Enterprise

  <sup>1</sup> A mudança do Microsoft Stream para o [OneDrive for Business e o Microsoft Office SharePoint Online para gravações de reunião](tmr-meeting-recording-change.md) será uma abordagem em fases. No lançamento, você poderá optar por essa experiência. Em novembro, você terá que cancelar se quiser continuar usando o Stream. Em algum momento no início de 2021, exigiremos que todos os clientes usem o OneDrive for Business e o Microsoft Office SharePoint Online para novas gravações de reuniões.

## <a name="whos-eligible"></a>Quem é elegível

Os usuários atendem aos critérios para uma experiência Exploratória de Teams se:

- Tem um endereço de email de domínio gerenciado do Azure Active Directory.
- Pertence a um locatário com uma assinatura paga.

Habilite os usuários para se inscreverem em aplicativos e versões de avaliação (no centro de administração do Office 365). Para obter mais informações, confira [Gerenciar a experiência do Teams Exploratory](#manage-the-teams-exploratory-experience), mais adiante neste artigo.

## <a name="who-isnt-eligible"></a>Quem não está qualificado

Os usuários não se enquadram nos critérios se:

- Tem uma licença do Teams ou anteriormente tinha uma licença Teams paga.
- Estão usando uma oferta de avaliação ou oferta de avaliação COVID.
- Estão em um locatário que tem pelo menos uma oferta especial de avaliação COVID.

Sua organização não está qualificada para esta oferta se você for um Cliente Parceiro de Agregação ou se for um cliente do GCC, GCC High, DoD ou EDU.

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>Como os usuários se inscrevem na experiência do Teams Exploratory

Os usuários qualificados podem inscrever-se para a experiência do Teams Exploratory fazendo logon no Teams ([teams.microsoft.com](https://teams.microsoft.com)). Essa licença será atribuída a eles automaticamente e o administrador do locatário receberá uma notificação por email na primeira vez que alguém em sua organização iniciar a experiência do Teams Exploratory.

## <a name="manage-the-teams-exploratory-experience"></a>Gerenciar a experiência do Teams Exploratory

A experiência Exploratória do Teams deve ser iniciada por usuários finais individuais e você não pode iniciar esta oferta em nome de funcionários usuários finais.

A experiência Exploratória do Teams vem com uma licença do Exchange Online, mas não será atribuída ao usuário até que o administrador a atribua. Se o usuário ainda não tiver uma licença do Exchange e o administrador ainda não tiver atribuído a licença do Exchange Online, o usuário não poderá agendar reuniões no Teams e pode estar perdendo outras funcionalidades do Teams.

Os administradores podem desabilitar a capacidade para que os usuários finais executem a experiência do Teams Exploratory em sua organização, usando a opção **Aplicativos e serviços de avaliação** .

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Impedir que os usuários instalem serviços e aplicativos de avaliação

Você pode desativar a capacidade de um usuário de instalar aplicativos e serviços de avaliação, o que impediria o usuário de executar a experiência Exploratória do Teams.

1. Do Centro de administração do Microsoft 365, vá até **Configurações** > **Configurações da Organização** , selecione **Serviços** e, em seguida, selecione **Aplicativos e serviços de propriedade do usuário** .

    ![a página de Serviços no centro de administração](media/iw-trial-services.png)

2. Desmarque a caixa de seleção **Permitir que os usuários instalem aplicativos e serviços de avaliação** .

    ![a página de aplicativos e serviços de propriedade do Usuário no centro de administração](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > Se a sua organização não estiver qualificada para a experiência do Teams Exploratory, você não verá a opção **Permitir que os usuários instalem aplicativos e serviços de avaliação** .

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>Gerenciar a disponibilidade de um usuário com uma licença que inclua o Teams

Um usuário que recebe uma licença que inclui o Teams não está qualificado para a experiência do Teams Exploratory. Quando o plano de serviço do Teams está ativado, o usuário pode entrar e usar o Teams. Se o plano do serviço estiver desabilitado, o usuário não poderá entrar e a experiência do Teams Exploratory não estará disponível. Você deve ter privilégios de administrador.

Para desativar o acesso ao Teams:

1. No Centro de administração do Microsoft 365, selecione **Usuários** > **Usuários ativos** .

2. Marque a caixa ao lado do nome do usuário.

3. Na linha **Licenças de produto** , escolha **Editar** .

4. No painel **​​Licenças do produto** , alterne a chave para **Desligado** .

    ![a página de licenças do Produto no centro de administração.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>Gerenciar a disponibilidade do Teams para os usuários que já estão usando a experiência do Teams Exploratory

Se um usuário estiver executando a experiência do Teams Exploratory, você poderá desativá-la removendo a licença ou o plano de serviço. Você deve ter privilégios de administrador.

Para desativar a licença de experiência do Teams Exploratory:

1. No Centro de administração do Microsoft 365, selecione **Usuários** > **Usuários ativos** .

2. Marque a caixa ao lado do nome do usuário.

3. Na linha **Licenças de produto** , escolha **Editar** .

4. No painel **Licenças de produto** , alterne a opção desta licença exploratória para **Desativar** .

    >[!Note]
    >A opção de alternância do Teams Exploratory será exibida após o primeiro usuário da organização iniciar a experiência do Teams Exploratory.

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a>Gerenciar o Teams para usuários que possuem a licença do Teams Exploratory

Você pode gerenciar usuários que possuem a licença do Teams Exploratory, assim como gerencia usuários que possuem uma licença paga regular. Para mais informações, confira [Gerenciar as configurações do Teams da sua organização](enable-features-office-365.md).

### <a name="upgrade-users-from-the-teams-exploratory-license"></a>Atualizar os usuários da licença do Teams Exploratory

Para atualizar os usuários da licença do Teams Exploratory (você deve ter privilégios de administrador), execute as seguintes tarefas:

1. Compre uma assinatura que inclua o Teams.

2. Remova a assinatura do Teams Exploratory do usuário.

3. Atribua as licenças adquiridas recentemente.

Para saber mais, confira [Descrição do serviço do Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

> [!NOTE]
> Se a licença Exploratória do Teams terminar e um usuário não fizer upgrade imediatamente para uma assinatura que inclua o Teams, ele terá 30 dias de período de carência e mais 30 dias após os quais os dados serão excluídos. O usuário ainda existe no Azure Active Directory. Assim que uma nova licença for atribuída ao usuário para habilitar a funcionalidade do Teams novamente, todo o conteúdo ainda existirá se o usuário for adicionado dentro do período de tempo de tolerância.

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a>O que acontece com as licenças do Microsoft Teams Commercial Cloud Trial

A partir de fevereiro de 2020, os usuários qualificados podem começar a usar a experiência mais recente do Microsoft Teams Exploratory. Todas as licenças do Teams Commercial Cloud Trial legado serão convertidas automaticamente para a nova oferta antes que o teste expire.

Quando os usuários se conectam no Teams Commercial Cloud Trial expirado pela primeira vez, atribuímos automaticamente uma licença de experiência do Teams Exploratory a esses usuários. Os usuários não serão convertidos antes de entrar.

### <a name="remove-a-teams-exploratory-license"></a>Remover uma licença do Teams Exploratory

- Se você deseja remover essa licença por meio do PowerShell, confira: [Remover licenças de contas de usuário com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

- Se você quiser remover essa licença por meio do portal de administração do, confira: [Excluir um usuário da sua organização](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)

## <a name="what-is-the-data-retention-policy"></a>Qual é a política de retenção de dados?

Confira as [Informações de assinatura do Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).

## <a name="how-long-does-the-teams-exploratory-experience-last"></a>Quanto tempo dura a experiência do Teams Exploratory?

A experiência Microsoft Teams Exploratory ficará disponível sem custo adicional até o próximo **aniversário** ou a **renovação de contrato** em ou após janeiro de 2021. Nesse momento, os usuários finais em uma licença do Microsoft Exploratory precisarão passar para uma licença paga que inclua o Teams. Quaisquer licenças da experiência do Microsoft Exploratory iniciadas depois disso permanecerão disponíveis sem custos adicionais, até o seu próximo ciclo de **aniversário** ou **renovação** .

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-the-anniversary-or-renewal-date"></a>O que acontece se um usuário final iniciar a experiência Microsoft Teams Exploratory pouco antes do aniversário ou data de renovação

Licenças de experiência do Microsoft Teams Exploratory iniciadas dentro de 90 dias de seu **aniversário de contrato** ou **renovação** não serão necessárias para mudar para uma licença paga até o aniversário subsequente ou ciclo de renovação.

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a>E se meu contrato não tiver um aniversário ou data de renovação anual (por exemplo, contratos mensais)

Para contratos sem aniversário ou data de renovação anual, o ano subsequente após o primeiro usuário final ativar as licenças de experiência Microsoft Teams Exploratory será tratado como aniversário ou data de renovação. Os usuários da licença do Microsoft Teams Exploratory devem ser convertidos em uma licença paga até essa data a cada ano, de acordo com as políticas descritas neste artigo.

Por exemplo, se o primeiro usuário final ativar o Microsoft Teams Exploratory em 19 de junho de 2020, ele e todos os outros usuários qualificados no locatário do cliente devem ser convertidos para uma licença paga com o Teams até 19 de junho de 2021.

> [!Note]
> Os clientes serão desabilitados e impedidos de iniciar uma nova licença de avaliação do Exploratory por 3 meses após a expiração de sua licença de avaliação do Exploratory anterior.
