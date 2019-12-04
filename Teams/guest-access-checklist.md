---
title: Lista de verificação de acesso de convidados do Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Use esta lista de verificação para ajudar a configurar o acesso de convidado no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bcba883166e01bd8a18d6d76b4622df0740500c8
ms.sourcegitcommit: 000fdb3bc1a0d4dda63fb00bab6a9a9ab0c85ab0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2019
ms.locfileid: "39813771"
---
<a name="microsoft-teams-guest-access-checklist"></a>Lista de verificação de acesso de convidados do Microsoft Teams
==========================================

Use esta lista de verificação para ajudar você a ativar e configurar o acesso de convidados no Microsoft Teams. Você precisa ser um administrador global ou administrador do teams para fazer essas alterações.

> [!IMPORTANT]
> Talvez seja necessário aguardar até 24 horas para que as alterações entrem em vigor. 

Assista a este vídeo curto (5:31 minutos) para ver como ativar o acesso de convidados durante o Microsoft 365, incluindo o Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a>Etapa 1: ativar o acesso de convidado no nível Teams de toda a organização

Para ativar o acesso de convidado, vá para o **centro de administração do Microsoft Teams**. 

1. No centro de administração do Teams, selecione o > **acesso de convidados**às **configurações de toda a organização**.
2. Defina a opção **permitir acesso de convidado no Microsoft Teams** como **ativado**.

    ![A captura de tela mostra um exemplo de alternância de configurações de equipes](media/guest-access-checklist-set-up-guests-image1.png)

3. Na mesma página, ative ou desative as configurações de **chamada**, **reunião**e **mensagens** para convidados.
4. Clique em **Salvar**.

> [!TIP]
> Se você estiver usando as configurações padrão nos grupos do Azure Active Directory, do SharePoint Online e do Office 365, pode ser que você tenha concluído a configuração do acesso de convidado. Nesse caso, você pode ignorar o restante das etapas. Se você não tiver certeza ou se estiver usando configurações personalizadas para grupos do AAD, SharePoint Online ou Office 365, continue com o restante das etapas desta lista de verificação.


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a>Etapa 2: configurar as configurações do Azure AD Business para empresas

1. Entre no [portal do Azure](https://portal.azure.com) como um administrador de locatários.
2. Selecione**as configurações de usuário** **do Azure Active Directory** > **Users** > .
3. Em **usuários externos**, selecione **gerenciar configurações de colaboração externa**.
   > [!NOTE]
   > As **configurações de colaboração externa** também estão disponíveis na página **relações organizacionais** . No Azure Active Directory, em **gerenciar**, acesse > **configurações**de **relações organizacionais**.
4. Na página **configurações de colaboração externas** , escolha as políticas que você deseja habilitar.

    - **As permissões de usuários convidados são limitadas**: esta política determina permissões para convidados em seu diretório. Selecione **Sim** para bloquear convidados de determinadas tarefas de diretório, como enumerar usuários, grupos ou outros recursos de diretório. Selecione **não** para dar aos convidados o mesmo acesso aos dados do diretório como usuários regulares em seu diretório.
     - **Administradores e usuários na função de convite de convidado podem convidar**: para permitir que administradores e usuários na função "convidador de convidado" possam convidar convidados, defina essa política como **Sim**.
     - **Os membros podem convidar**: para permitir que membros que não sejam administradores do seu diretório convidem convidados, defina essa política como **Sim**.

         > [!NOTE]
         > Se você definir que **os membros podem convidar** para **não** e, em seguida, habilitar o acesso de convidado nos grupos do Office 365 e no Microsoft Teams, os administradores poderão controlar os convites convidados para seu diretório. Depois que os convidados estiverem no diretório, eles poderão ser adicionados às equipes por membros não-administradores que sejam proprietários da equipe. Para obter mais informações, consulte [Autorizar acesso de convidados no Microsoft Teams](Teams-dependencies.md).
         > [!IMPORTANT]
         > Para que o acesso de convidados funcione completamente no Teams, você deve definir o recurso**Membros podem convidar** para **Sim**.   
     - **Convidados podem convidar**: para permitir que os convidados convidem outros convidados, defina essa política como **Sim**.
         > [!IMPORTANT]
         > Atualmente, o Teams não oferece suporte à função de emissor de convites, portanto, mesmo se você definir **Convidados possam convidar** para **Sim**, os convidados não conseguirão convidar outros convidados no Teams.
     - **Habilitar a senha de senha única para convidados (visualização)**: para obter mais informações sobre o recurso de senha de uso único, consulte [autenticação de senha única (visualização) de email](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).
     - **Restrições de colaboração**: para obter mais informações sobre como permitir ou bloquear convites para domínios específicos, consulte [permitir ou bloquear convites para usuários B2B de organizações específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).
        > [!NOTE]
        > Para obter restrições de colaboração, consulte [habilitar a colaboração externa B2B e gerenciar quem pode convidar convidados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).
      
 
    Para obter mais informações sobre como controlar quem pode convidar pessoas, consulte [Delegar convites para colaboração B2B do Active Directory do Azure](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).


## <a name="step-3-configure-office-365-groups"></a>Etapa 3: configurar grupos do Office 365

1. No centro de administração do Microsoft 365, vá para **configurações** > de**Serviços & suplementos** > **do Office 365 grupos**.
2. Verifique se **deixar que os membros do grupo fora do conteúdo do grupo de acesso à organização** estejam definidos como **ativado**. Se essa configuração estiver desativada, os convidados não poderão acessar qualquer conteúdo do grupo.
3. Certifique-se de **que o recurso proprietários de grupos Adicione pessoas de fora da organização a grupos** esteja definido como **ativado**. Se essa configuração estiver desativada, os proprietários da equipe não poderão adicionar novos convidados. No mínimo, essa configuração deve estar ativada para dar suporte ao acesso de convidado.

     ![A captura de tela mostra as alternâncias dos grupos do Office 365](media/guest-access-checklist-office365.png)

Para obter instruções detalhadas sobre como definir essas configurações, consulte [gerenciar o acesso de convidados nos grupos do Office 365](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) e [controlar o acesso de convidados a grupos do Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).
 

## <a name="step-4-configure-sharing-in-office-365"></a>Etapa 4: configurar o compartilhamento no Office 365 

Certifique-se de que os usuários possam adicionar convidados. Veja como:

1. No centro de administração do Microsoft 365, vá para **configurações** > **segurança & privacidade**.

     ![A captura de tela mostra um exemplo de configurações de serviços](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. Em **compartilhamento**, selecione **Editar**.

     ![A captura de tela mostra um exemplo de alternância de configurações de compartilhamento](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. Defina **permitir que os usuários adicionem novos convidados a essa organização** para serem **ativados**e, em seguida, clique em **salvar**.

     ![A captura de tela mostra um exemplo de alternância de configurações de compartilhamento](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
    > [!NOTE]
    > Essa configuração é equivalente à configuração os **Membros podem convidar** em **configurações** > do usuário**usuários externos** do Azure AD.  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a>Etapa 5: verificar a configuração de compartilhamento no SharePoint

Isso é um pouco de uma outra. O acesso de convidado no Microsoft Teams não funciona se a configuração **não permitir o compartilhamento fora da organização** estiver selecionada no centro de administração do SharePoint.

1. Entre no centro de administração do Microsoft 365.
2. Clique em **centro de administração**e selecione **SharePoint**.
3. No centro de administração do SharePoint, selecione **compartilhamento**.
4. Certifique-se de que a opção **não permitir o compartilhamento fora da sua organização** *não* esteja selecionada.
 
     ![A captura de tela mostra um exemplo de uma alternância de configurações online do SparePoint.](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a>Etapa 6: configurar permissões de usuário convidado

No aplicativo Teams, no nível individual da equipe, configure as permissões de convidado que controlam se os convidados podem criar, atualizar ou excluir canais. Os administradores do Team e os proprietários da equipe podem definir essas configurações.

![A captura de tela mostra um exemplo de alternância de configurações de equipe/canal](media/guest-access-checklist-TeamsSettings2.png)

Para saber mais sobre o acesso de convidado, consulte [acesso de convidado em equipes](guest-access.md) e [ative ou desative o acesso de convidado ao Microsoft Teams](set-up-guests.md).


## <a name="troubleshooting"></a>Solução de problemas

Se você tiver problemas para configurar o acesso de convidado ou adicionar convidados ao Microsoft Teams, use estes recursos para ajudá-lo:

[Solucionar problemas de acesso de convidado no Microsoft Teams](troubleshoot-guest-access.md)

[Solução de problemas do Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



