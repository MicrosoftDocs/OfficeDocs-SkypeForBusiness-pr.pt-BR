---
title: Gerenciar a experiência do Microsoft Teams Exploratory
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Usuários do Office 365 que não possuem licenças para o Microsoft Teams podem iniciar uma licença do Teams Exploratory.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f2629f855485f0301f6a7fc576cd17a9e1c1f49d
ms.sourcegitcommit: bc2e0f6f2ed3802ecc67275594db221c61824458
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2020
ms.locfileid: "42398169"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a>Gerenciar a licença do Microsoft Teams Exploratory
=======================================================

A experiência do Microsoft Teams Exploratory permite aos usuários de sua organização que têm o Azure Active Directory (AAD) e não estejam licenciados para o Teams iniciem uma experiência exploratório do Teams. Os administradores podem ativar ou desativar esse recurso para os usuários em sua organização. O [Microsoft Commercial Cloud Trial](iw-trial-teams.md) anterior agora foi substituído pela experiência do Teams Exploratory.

## <a name="whats-in-the-teams-exploratory-experience"></a>O que há na experiência do Teams Exploratory?

Os planos de serviço que um administrador exibirá como parte da experiência de exploratório da equipe são:
 - Exchange Online (Plano 1)
 - Flow para Office 365
 - Insight por MyAnalytics
 - Microsoft Forms (Plano E1)
 - Microsoft Planner
 - Pesquisa da Microsoft
 - Microsoft StaffHub
 - Microsoft Stream para O365 E1 SKU
 - Microsoft Teams
 - Gerenciamento de Dispositivos Móveis para o Office 365
 - Aplicativos do Office Mobile para Office 365 
 - Office Online
 - PowerApps para o Office 365
 - SharePoint Online (Plano 1)
 - Sway
 - To-Do (Plano 1)
 - Quadro de Comunicações (Plano 1)
 - Yammer Enterprise


## <a name="whos-eligible"></a>Quem está qualificado?

Desde que o usuário tenha um endereço de e-mail de domínio gerenciado do AAD e atualmente não tenha / não tenha recebido uma licença do Teams, ele estará qualificado para esta experiência. Por exemplo, se um usuário tiver o Office 365 Business (que não inclui o Teams), eles estará qualificado para a experiência do Teams Exploratory.

Habilite os usuários para se inscreverem em aplicativos e versões de avaliação (no centro de administração do Office 365). Para obter mais informações, confira [Gerenciar a experiência do Teams Exploratory](#manage-the-teams-exploratory-experience), mais adiante neste artigo. 


## <a name="who-isnt-eligible"></a>Quem não está qualificado

Sua organização não está qualificada para esta oferta se você for um Cliente Parceiro de Agregação ou se for um cliente do GCC, GCC High, DoD ou EDU.


## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>Como os usuários se inscrevem na experiência do Teams Exploratory

Os usuários qualificados podem inscrever-se para a experiência do Teams Exploratory fazendo logon no Teams ([teams.microsoft.com](https://teams.microsoft.com)). Eles receberão essa licença automaticamente e o administrador do locatário receberá uma notificação por e-mail na primeira vez que alguém em sua organização iniciar a experiência do Teams Exploratory.

## <a name="manage-the-teams-exploratory-experience"></a>Gerenciar a experiência do Teams Exploratory

A experiência do Teams Exploratory deve ser iniciada por usuários finais individuais, e você não pode iniciar essa oferta em nome de funcionários de usuários finais.

A experiência do Teams Exploratory vem com uma licença do Exchange Online, mas ela não será atribuída ao usuário até que o administrador a atribua. Se o usuário ainda não possui uma licença do Exchange e o administrador ainda não atribuiu a licença do Exchange Online, o usuário não poderá agendar reuniões no Teams e poderá estar perdendo outras funcionalidades do Teams.

Os administradores podem desabilitar a capacidade para que os usuários finais executem a experiência do Teams Exploratory em sua organização, usando a opção **Aplicativos e serviços de avaliação**.


### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Impedir que os usuários instalem serviços e aplicativos de avaliação

Você pode desativar a capacidade de um usuário de instalar aplicativos e serviços de avaliação, evitando que o usuário execute a experiência do Teams Exploratory.

1. No [Centro de administração do Microsoft 365](https://portal.office.com/adminportal/home), vá até **Configurações** > **Configurações**, selecione**Serviços**e, em seguida, selecione **Aplicativos e serviços de propriedade do usuário**.

    ![Captura de tela da página Serviços do centro de administração](media/iw-trial-services.png)

2. Desative a caixa de seleção **Permitir que os usuários instalem aplicativos e serviços de avaliação**.

    ![Captura de tela da página Aplicativos e serviços de propriedade do usuário no centro de administração](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > Se a sua organização não estiver qualificada para a experiência do Teams Exploratory, você não verá a opção **Permitir que os usuários instalem aplicativos e serviços de avaliação**.

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>Gerenciar a disponibilidade de um usuário com uma licença que inclua o Teams

Um usuário que recebe uma licença que inclui o Teams não está qualificado para a experiência do Teams Exploratory. Quando o plano de serviço do Teams está ativado, o usuário pode entrar e usar o Teams. Se o plano do serviço estiver desabilitado, o usuário não poderá entrar e a experiência do Teams Exploratory não estará disponível.

Para desativar o acesso ao Teams:

1. No Centro de administração do Microsoft 365, selecione **Usuários** > **Usuários ativos**.

2. Marque a caixa ao lado do nome do usuário.

3. À direita, na linha **Licenças de produto**, escolha **Editar**.

4. No painel **Licenças de produto**, troque o botão para **Desativar**.

    ![Captura de tela da página de licenças do produto do Centro de administração.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>Gerenciar a disponibilidade do Teams para os usuários que já estão usando a experiência do Teams Exploratory

Se um usuário estiver executando a experiência do Teams Exploratory, você poderá desativá-la removendo a licença ou o plano de serviço.

Para desabilitar a licença da experiência do Teams Exploratory:

1. No Centro de administração do Microsoft 365, selecione **Usuários** > **Usuários ativos**.

2. Marque a caixa ao lado do nome do usuário.

3. À direita, na linha **Licenças de produto**, escolha **Editar**.

4. No painel **Licenças de produto**, alterne a opção desta licença exploratória para **Desativar**.
   
    >[!Note]
    >A opção de alternância do Teams Exploratory será exibida após o primeiro usuário da organização iniciar a experiência do Teams Exploratory.

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a>Gerenciar o Teams para usuários que possuem a licença do Teams Exploratory

Você pode gerenciar usuários que possuem a licença do Teams Exploratory, assim como gerencia usuários que possuem uma licença paga regular. Para mais informações, confira [Gerenciar as configurações do Teams da sua organização](enable-features-office-365.md).

### <a name="upgrade-users-from-the-teams-exploratory-license"></a>Atualizar os usuários da licença do Teams Exploratory

Para atualizar os usuários da licença do Teams Exploratory, faça o seguinte:

1. Compre uma assinatura que inclua o Teams.

2. Remova a assinatura do Teams Exploratory do usuário.

3. Atribua as licenças adquiridas recentemente.

Para saber mais, confira [Licenças do Office 365 do Microsoft Teams](Office-365-licensing.md).

> [!NOTE]
> Se a licença do Teams Exploratory terminar e um usuário não for atualizado imediatamente para uma assinatura que inclua o Teams, os dados do usuário não serão removidos. O usuário ainda existe no Azure Active Directory e todos os dados no Teams ainda permanecem. Depois que uma nova licença for atribuída ao usuário para ativar a funcionalidade do Teams novamente, todo o conteúdo ainda existirá. 

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a>O que acontece com as licenças de Avaliação de Nuvem Comercial do Microsoft Teams herdadas?

A partir de fevereiro de 2020, os usuários qualificados podem começar a usar a experiência mais recente do Microsoft Teams Exploratory. Todos as licenças de Avaliação de Nuvem Comercial do Teams herdadas serão automaticamente convertidas para a nova oferta antes da expiração da avaliação.

### <a name="remove-a-teams-exploratory-license"></a>Remover uma licença do Teams Exploratory

- Se você deseja remover essa licença por meio do PowerShell, confira: [Remover licenças de contas de usuário com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

- Se você quiser remover essa licença por meio do portal de administração, confira: [remover licenças de usuários no Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide)

## <a name="how-long-does-the-teams-exploratory-experience-last"></a>Quanto tempo dura a experiência do Teams Exploratory?

A experiência Microsoft Teams Exploratory ficará disponível sem custo adicional até seu próximo aniversário empresarial ou renovação em ou após janeiro de 2021. Nesse momento, os usuários finais em uma licença do Microsoft Exploratory precisarão passar para uma licença paga que inclua o Teams. Quaisquer licenças de experiência do Microsoft Exploratory iniciadas depois disso permanecerão disponíveis sem custo adicional até o próximo aniversário ou ciclo de renovação. 

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-my-anniversary-or-renewal-date"></a>O que acontece se um usuário final iniciar a experiência do Microsoft Teams Exploratory imediatamente antes da data de renovação ou aniversário?

As licenças de experiência do Microsoft Teams Exploratory iniciadas dentro dos 90 dias após o aniversário ou a renovação do contrato da sua empresa não precisarão passar para uma licença paga até o aniversário ou ciclo de renovação subsequente. 
