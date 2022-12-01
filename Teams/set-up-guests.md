---
title: Ativar ou desativar o acesso do convidado no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
- chat-teams-channels-revamp
ms.localizationpriority: medium
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Saiba mais sobre como ativar ou desativar o recurso de acesso de convidado no Microsoft Teams como um administrador do Office 365.
ms.openlocfilehash: 906a5554d4dbcb03efabb2300a5a900ad3c8dc21
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69199093"
---
# <a name="turn-guest-access-in-microsoft-teams-on-or-off"></a>Ativar ou desativar o acesso do convidado no Microsoft Teams

Este artigo descreve como configurar as configurações de acesso ao convidado - incluindo chamadas, reuniões e chat - no Teams. O acesso de convidado no Teams também requer a configuração de outras configurações no Microsoft 365, incluindo configurações em Azure AD, Grupos do Microsoft 365 e SharePoint. Se você estiver pronto para começar a convidar pessoas para equipes, leia um dos seguintes:

- Para configurar o acesso de convidado do Teams para uso geral, consulte [Colaborar com convidados em uma equipe](/microsoft-365/solutions/collaborate-as-team).
- Para colaborar com uma organização parceira que usa o Azure Active Directory e permitir que os convidados se inscrevam para acesso da equipe, consulte [Criar uma extranet B2B com convidados gerenciados](/microsoft-365/solutions/b2b-extranet).

> [!NOTE]
> Se você deseja encontrar, ligar, conversar e marcar reuniões com pessoas de outras organizações, use o [acesso externo](manage-external-access.md).

## <a name="configure-guest-access-in-the-teams-admin-center"></a>Configure o acesso de convidados no centro de administração do Microsoft Teams

1. Entre no [Centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/).

2. Selecione **Usuários** > **Acesso de convidado**.

3. Defina **Permitir acesso de convidado no Teams** como **Ativado**.

    ![Permitir a opção de acesso ao convidado definida como Ativar .](media/guest-access-setting.png)

4. Em **Chamar**, **Reunião** e **Mensagens**, selecione **Ativar** ou **Desativar** para cada recurso, dependendo do que você deseja permitir para convidados.

      - **Fazer chamadas privadas** – **Ativar** essa função para permitir que os usuários façam chamadas ponto a ponto.
      - **Vídeo IP** – Ativar **essa configuração** para permitir que os convidados usem vídeo em suas chamadas e reuniões.
      - **Modo de compartilhamento de** tela – essa configuração controla a disponibilidade do compartilhamento de tela para convidados.
          - **Desativar** essa configuração para remover a capacidade de os convidados compartilharem suas telas no Teams.
          - Defina essa configuração como **Aplicativo único** para permitir o compartilhamento de aplicativos individuais.
          - Defina essa configuração como **Tela inteira** para permitir o compartilhamento completo da tela.
      - **Conheça Agora** – Ativar **essa configuração** para permitir que os convidados usem o recurso Meet Now no Microsoft Teams.
      - **Editar mensagens enviadas** - **Ativar** essa configuração para permitir que os convidados editem as mensagens enviadas anteriormente.
      - **Excluir mensagens enviadas** – ative **essa configuração** para permitir que os convidados excluam as mensagens enviadas anteriormente.
      - **Excluir chat** – Ativar **essa configuração** para permitir que os convidados excluam uma conversa de chat inteira.
      - **Chat** - **Ativar** essa configuração para oferecer aos convidados a capacidade de usar o chat no Teams.
      - **Giphy em conversas** – Ativar **essa configuração** para permitir que os convidados usem Giphys em conversas. O Giphy é um mecanismo de pesquisa e banco de dados online que permite aos usuários pesquisar e compartilhar arquivos GIF animados. Cada Giphy recebe uma classificação de conteúdo.
      - **Classificação de conteúdo para Giphy** – Selecione uma classificação na lista suspensa:
          - **Permitir todo o conteúdo** - Os convidados poderão inserir todos os Giphys nos chats, independentemente da classificação do conteúdo.
          - **Moderado** - Os convidados poderão inserir Giphys nos chats, mas o conteúdo adulto será moderadamente restringido.
          - **Estrito** – os convidados podem inserir Giphys em chats, mas serão impedidos de inserir conteúdo adulto.
      - **Memes em conversas** – Ativar **essa configuração** para permitir que os convidados usem Memes em conversas.
      - **Adesivos em conversas** – Ativar **essa configuração** para permitir que os convidados usem adesivos em conversas.
      - **Leitor imersivo para mensagens** – Ativar **essa configuração** para permitir que os convidados usem [o leitor imersivo no Teams](https://support.microsoft.com/topic/a700c0d0-bc53-4696-a94d-4fbc86ac7a9a).

    ![Configurações de permissões de convidado no Teams.](media/manage-guest-access-image1.png)

5. Selecione **Salvar**.

## <a name="turning-guest-access-off"></a>Desativando o acesso de convidado

Se você desativar o acesso de convidados no Teams, os convidados existentes perderão o acesso à equipe. No entanto, eles não são removidos da equipe. Eles ainda são visíveis para as pessoas da equipe e podem ser @mencionados. Se você ativar o acesso de convidado do Teams novamente, eles recuperarão o acesso.

Se você planeja deixar o acesso de convidados desativado, convém avisar os proprietários da equipe para remover manualmente as contas de convidado de suas equipes. Embora esses convidados não tenham acesso, ter suas contas visíveis na equipe pode causar confusão para outras pessoas da equipe.


## <a name="see-also"></a>Confira também

[Configurar a colaboração segura com o Microsoft 365](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[Bloquear convidados de uma equipe específica](/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)
