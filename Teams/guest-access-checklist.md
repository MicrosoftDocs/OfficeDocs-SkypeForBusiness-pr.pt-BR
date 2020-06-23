---
title: Lista de verificação de acesso de convidados do Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Use esta lista de verificação para ajudar a configurar o acesso de convidados no Microsoft Teams.
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

Use esta lista de verificação para ajudá-lo a habilitar e configurar o acesso de convidados no Microsoft Teams. Você precisa ser um administrador global ou administrador do Teams para corrigir essas alterações.

> [!IMPORTANT]
> Talvez você precise aguardar até 24 horas para que as configurações entrem em vigor. 

Assista a este vídeo curto (5:31 minutos) para saber como habilitar o acesso de convidados no Microsoft 365, incluindo o Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a>Etapa 1: habilitar o acesso de convidados no nível de toda a organização do Teams

Para habilitar o acesso de convidados, acesse o **Centro de administração do Microsoft Teams**. 

1. No Centro de administração do Teams, selecione **Configurações em toda a organização** > **Acesso de convidados**.
2. Defina o botão **Permitir acesso de convidados no Microsoft Teams** para **Ativado**.

    ![A tela de captura mostra um exemplo de alternância de configurações do Teams](media/guest-access-checklist-set-up-guests-image1.png)

3. Na mesma página, habilite ou desabilite as configurações de **Chamada**, **Reunião** e **Mensagens** para os convidados.
4. Clique em **Salvar**.

> [!TIP]
> Se você estiver usando as configurações padrão nos Grupos do Azure Active Directory, do SharePoint Online e do Office 365, poderá configurar o acesso de convidado. Nesse caso, você pode ignorar o restante das etapas. Se você não tiver certeza ou se estiver usando as configurações personalizadas para Grupos do AAD, do SharePoint Online ou do Office 365, continue com o restante das etapas nesta lista de verificação.

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a>Etapa 2: definir as configurações do Azure Active Directory entre empresas

Estas são as configurações do Azure AD que oferecem suporte ao acesso de convidado no Teams. Depois de definir essas configurações, você poderá [Adicionar](add-guests.md) e [Gerenciar convidados](manage-guests.md) no Teams.

1. Acesse o [Portal do Azure](https://portal.azure.com) como administrador de locatários.
2. Selecione **Azure Active Directory** > **Usuários** > **Configurações do usuário**.
3. Em **Usuários externos**, selecione **Gerenciar as configurações de colaboração externa**.
   > [!NOTE]
   > As **Configurações de colaboração externas** também estão disponíveis na página **Relações organizacionais**. No Azure Active Directory, em **Gerenciar**, acesse **Relações organizacionais** > **Configurações**.
4. Na página **Configurações de colaboração externas**, escolha as políticas que você deseja habilitar.

    - **As permissões de usuários convidados são limitadas**: essa política determina permissões para convidados em seu diretório. Selecione **Sim** para bloquear os convidados de determinadas tarefas de diretório, como enumerar usuários, grupos ou outros recursos de diretório. Selecione **Não** para conceder aos convidados o mesmo acesso aos dados de diretório que os usuários comuns têm em seu diretório.
     - **Administradores e usuários na função de emissor do convite podem convidar**: defina esta política como **Sim** para permitir que os administradores e usuários na função de "Emissor de Convite" possam convidar pessoas.
     - **Os membros podem convidar**: para permitir que os membros não administradores do seu diretório convidem pessoas, defina essa política como **Sim** (recomendado). Se preferir que somente os administradores sejam capazes de adicionar convidados, você pode definir essa política como **Não**. Lembre-se de que definir **Não** limitará a experiência de convidado para proprietários de equipes não administrativos; eles só poderão adicionar convidados ao Teams que já foram adicionados ao AAD pelo administrador.
     - **Os convidados podem convidar**: defina essa política como **Sim** para permitir que os convidados convidem outras pessoas.
         > [!IMPORTANT]
         > Atualmente, o Teams não oferece suporte à função de emissor de convites, portanto, mesmo se você definir **Convidados possam convidar** para **Sim**, os convidados não conseguirão convidar outros convidados no Teams.
     - **Habilitar senha de uso único por email para convidados (versão prévia)**: para obter mais informações sobre o recurso de senha de uso único, confira [Autenticação de senha de uso de único por email (versão prévia)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).
     - **Restrições de colaboração**: para saber mais sobre como permitir ou bloquear convites para domínios específicos, confira [Permitir ou bloquear convites para usuários B2B de organizações específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).
        > [!NOTE]
        > Para obter restrições de colaboração, confira [Habilitar colaboração externa B2B e gerenciar quem pode convidar convidados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).
      
    Para obter mais informações sobre como controlar quem pode convidar pessoas, confira [Delegar convites para colaboração B2B do Active Directory do Azure](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).

## <a name="step-3-configure-office-365-groups"></a>Etapa 3: configurar os Grupos do Office 365

1. No Centro de administração do Microsoft 365, acesse **Configurações** > **Configurações**, clique em **Serviços** e, em seguida, **Grupos do Office 365**.

     ![A captura de tela mostra as configurações dos Grupos do Office 365](media/guest-access-checklist-services-settings.png)
2. Verifique se a caixa de seleção **Permitir que os membros do grupo fora da organização acessem o conteúdo do grupo** foi selecionada. Se essa configuração não for selecionada, os convidados não poderão acessar nenhum conteúdo do grupo.

    ![A captura de tela mostra as configurações dos Grupos do Office 365](media/guest-access-checklist-office365.png)
3. Verifique se a caixa de seleção **Permitir que os proprietários do grupo adicionem pessoas de fora da organização aos grupos** foi selecionada. Se essa configuração não for selecionada, os proprietários de grupos não poderão adicionar novos convidados. No mínimo, essa configuração deve estar ativada para oferecer suporte ao acesso de convidados.

Para obter instruções detalhadas sobre como definir essas configurações, confira [Gerenciar o acesso de convidados nos Grupos do Office 365](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) e [Controlar o acesso de convidados nos Grupos do Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).

## <a name="step-4-configure-sharing-in-office-365"></a>Etapa 4: configurar o compartilhamento no Office 365 

Certifique-se de que os usuários possam adicionar convidados. Veja como:

1. No Centro de administração do Microsoft 365, acesse **Configurações** > **Configurações**, clique em **Segurança e privacidade** e, em seguida, **Compartilhamento**.

     ![A tela de captura mostra um exemplo de configurações de serviços](media/guest-access-checklist-security-privacy-settings.png)
 
2. Marque a caixa de seleção **Permitir que os usuários adicionem novos convidados a esta organização** e, em seguida, clique em **Salvar alterações**.

     ![A tela de captura mostra um exemplo de alternância de configurações de compartilhamento](media/guest-access-checklist-sharing-setting.png)
 
    > [!NOTE]
    > Essa configuração é equivalente à configuração **Membros podem convidar** em **Configurações do usuário** > **Usuários externos** no Azure AD.  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a>Etapa 5: verificar a configuração de compartilhamento do SharePoint

1. Acesse o Centro de administração do Microsoft 365.
2. Em **Centros de Administração**, selecione **SharePoint**.
3. No novo Centro de administração do SharePoint, em **Sites**, selecione **Sites ativos**.

    ![Sites ativos no Centro de administração do SharePoint](media/guest-access-checklist-SPOSettings0.png)

3. Selecione o site e clique em **Compartilhamento**.
4. Verifique se a opção está definida como **Qualquer pessoa** ou **Convidados novos e existentes**.

     ![A tela de captura mostra um exemplo de alternância de configurações do SharePoint Online](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a>Etapa 6: configurar permissões de usuário convidado

No aplicativo Teams, no nível da equipe individual, configure as permissões de convidado que controlam se os convidados podem criar, atualizar ou excluir canais. Os administradores do Teams, bem como os proprietários da equipe, podem definir essas configurações.

![A tela de captura mostra um exemplo de alternância de configurações da equipe/canal](media/guest-access-checklist-TeamsSettings2.png)

Para saber mais sobre o acesso de convidados, confira o [Acesso de convidados no Teams](guest-access.md) e [Ativar ou desativar o acesso de convidados no Microsoft Teams](set-up-guests.md).

## <a name="troubleshooting"></a>Solução de problemas

Se você tiver problemas para configurar o acesso de convidados ou ao adicionar convidados no Temas, use estes recursos para ajudá-lo:

[Solucionar problemas com o acesso de convidados no Microsoft Teams](troubleshoot-guest-access.md)

[Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
