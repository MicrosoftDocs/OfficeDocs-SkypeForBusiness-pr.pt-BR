---
title: Lista de verificação de acesso de convidados do Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Use esta lista de verificação para ajudar a configurar o acesso de convidado no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b60b0e5f0972d862ec1b945f1b267b04faae9a8a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833251"
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

Estas são as configurações do Azure AD que dão suporte ao acesso de convidado no Teams. Depois que essas configurações forem configuradas, você poderá [Adicionar](add-guests.md) e [gerenciar convidados](manage-guests.md) no Microsoft Teams.

1. Entre no [portal do Azure](https://portal.azure.com) como um administrador de locatários.
2. Selecione**as configurações de usuário** **do Azure Active Directory** > **Users** > .
3. Em **usuários externos**, selecione **gerenciar configurações de colaboração externa**.
   > [!NOTE]
   > As **configurações de colaboração externa** também estão disponíveis na página **relações organizacionais** . No Azure Active Directory, em **gerenciar**, acesse > **configurações**de **relações organizacionais**.
4. Na página **configurações de colaboração externas** , escolha as políticas que você deseja habilitar.

    - **As permissões de usuários convidados são limitadas**: esta política determina permissões para convidados em seu diretório. Selecione **Sim** para bloquear convidados de determinadas tarefas de diretório, como enumerar usuários, grupos ou outros recursos de diretório. Selecione **não** para dar aos convidados o mesmo acesso aos dados do diretório como usuários regulares em seu diretório.
     - **Administradores e usuários na função de convite de convidado podem convidar**: para permitir que administradores e usuários na função "convidador de convidado" possam convidar convidados, defina essa política como **Sim**.
     - **Os membros podem convidar**: para permitir que os membros não administradores do seu diretório convidem pessoas, defina essa política como **Sim** (recomendado). Se preferir que somente os administradores sejam capazes de adicionar convidados, você pode definir essa política como **Não**. Lembre-se de que definir **Não** limitará a experiência de convidado para proprietários de equipes não administrativos; eles só poderão adicionar convidados ao Teams que já foram adicionados ao AAD pelo administrador.
     - **Convidados podem convidar**: para permitir que os convidados convidem outros convidados, defina essa política como **Sim**.
         > [!IMPORTANT]
         > Atualmente, o Teams não oferece suporte à função de emissor de convites, portanto, mesmo se você definir **Convidados possam convidar** para **Sim**, os convidados não conseguirão convidar outros convidados no Teams.
     - **Habilitar a senha de senha única para convidados (visualização)**: para obter mais informações sobre o recurso de senha de uso único, consulte [autenticação de senha única (visualização) de email](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).
     - **Restrições de colaboração**: para obter mais informações sobre como permitir ou bloquear convites para domínios específicos, consulte [permitir ou bloquear convites para usuários B2B de organizações específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).
        > [!NOTE]
        > Para obter restrições de colaboração, consulte [habilitar a colaboração externa B2B e gerenciar quem pode convidar convidados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).
      
    Para obter mais informações sobre como controlar quem pode convidar pessoas, consulte [Delegar convites para colaboração B2B do Active Directory do Azure](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).

## <a name="step-3-configure-office-365-groups"></a>Etapa 3: configurar grupos do Office 365

1. No centro de administração do Microsoft 365, vá para**configurações**de **configurações** > , clique em **Serviços**e selecione **grupos do Office 365**.

     ![A captura de tela mostra as configurações de grupos do Office 365](media/guest-access-checklist-services-settings.png)
2. Certifique-se de que a caixa de seleção **permitir que membros do grupo fora da organização do conteúdo do grupo de acesso à organização** esteja marcada. Se essa configuração não for selecionada, os convidados não poderão acessar qualquer conteúdo do grupo.

    ![A captura de tela mostra as configurações de grupos do Office 365](media/guest-access-checklist-office365.png)
3. Certifique-se de que a caixa de seleção permitir que os **proprietários do grupo Adicione pessoas fora da organização a grupos** esteja marcada. Se essa configuração não for selecionada, os proprietários da equipe não poderão adicionar novos convidados. No mínimo, essa configuração deve estar ativada para dar suporte ao acesso de convidado.

Para obter instruções detalhadas sobre como definir essas configurações, consulte [gerenciar o acesso de convidados nos grupos do Office 365](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) e [controlar o acesso de convidados a grupos do Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).

## <a name="step-4-configure-sharing-in-office-365"></a>Etapa 4: configurar o compartilhamento no Office 365 

Certifique-se de que os usuários possam adicionar convidados. Veja como:

1. No centro de administração do Microsoft 365, vá para**configurações**de **configurações** > , clique em **segurança & privacidade**e selecione **compartilhamento**.

     ![A captura de tela mostra um exemplo de configurações de serviços](media/guest-access-checklist-security-privacy-settings.png)
 
2. Marque a caixa de seleção **permitir que os usuários adicionem novos convidados a esta organização** e clique em **salvar alterações**.

     ![A captura de tela mostra um exemplo de alternância de configurações de compartilhamento](media/guest-access-checklist-sharing-setting.png)
 
    > [!NOTE]
    > Essa configuração é equivalente à configuração os **Membros podem convidar** em **configurações** > do usuário**usuários externos** do Azure AD.  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a>Etapa 5: verificar a configuração de compartilhamento no SharePoint

1. Entre no centro de administração do Microsoft 365.
2. Em **centros de administração**, selecione **SharePoint**.
3. No novo centro de administração do SharePoint, em **sites**, selecione **sites ativos**.

    ![Sites ativos no centro de administração do SharePoint](media/guest-access-checklist-SPOSettings0.png)

3. Selecione o site e, em seguida, clique em **compartilhamento**.
4. Certifique-se de que a opção está definida para **qualquer pessoa** ou **convidados novos e existentes**.

     ![A captura de tela mostra um exemplo de uma alternância de configurações do SharePoint Online](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a>Etapa 6: configurar permissões de usuário convidado

No aplicativo Teams, no nível individual da equipe, configure as permissões de convidado que controlam se os convidados podem criar, atualizar ou excluir canais. Os administradores do Team e os proprietários da equipe podem definir essas configurações.

![A captura de tela mostra um exemplo de alternância de configurações de equipe/canal](media/guest-access-checklist-TeamsSettings2.png)

Para saber mais sobre o acesso de convidado, consulte [acesso de convidado em equipes](guest-access.md) e [ative ou desative o acesso de convidado ao Microsoft Teams](set-up-guests.md).

## <a name="troubleshooting"></a>Solução de problemas

Se você tiver problemas para configurar o acesso de convidado ou adicionar convidados ao Microsoft Teams, use estes recursos para ajudá-lo:

[Solucionar problemas de acesso de convidado no Microsoft Teams](troubleshoot-guest-access.md)

[Solução de problemas do Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
