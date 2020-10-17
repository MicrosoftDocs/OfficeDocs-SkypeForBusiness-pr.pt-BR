---
title: Ativar ou desativar o acesso de convidados ao Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Saiba mais sobre como ativar ou desativar o recurso de acesso de convidado no Microsoft Teams como um administrador do Office 365.
ms.openlocfilehash: 54d7461e9e03cd22900e07aca7ad2d12712faab7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508058"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Ativar ou desativar o acesso de convidados ao Microsoft Teams

Por padrão, o acesso de convidado está desativado. Você deve habilitar o acesso de convidado para equipes para que administradores ou proprietários de equipe possam adicionar convidados.

Depois de ativar o acesso de convidado, pode levar algumas horas para que as alterações entrem em vigor. Se um usuário vir a mensagem "entrar em contato com seu administrador" ao tentar adicionar um convidado à equipe, é provável que o acesso de convidado não tenha sido ativado ou que as configurações ainda não estejam efetivas.

> [!IMPORTANT]
> Ativar o acesso de convidado depende das configurações no Azure Active Directory, Microsoft 365, SharePoint e Teams. Para obter mais informações, consulte [colaborar com convidados em uma equipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).

## <a name="configure-guest-access-in-the-teams-admin-center"></a>Configurar o acesso de convidado no centro de administração do teams

1. Entre no centro de [Administração do Microsoft Teams](https://admin.teams.microsoft.com/).

2. Selecione **Configurações em toda a organização** > **Acesso de convidados**.

3. Defina **permitir acesso de convidado no Microsoft Teams** como **ativado**.

    ![Permita que a opção de acesso de convidados seja definida como Ativada ](media/set-up-guests-image1.png)

4. Em **chamadas**, **reuniões**e **mensagens**, selecione **Ativar** ou **desativar** para cada recurso, dependendo do que você deseja permitir para usuários convidados.

      - **Fazer chamadas privadas** – **Ativar** essa função para permitir que os usuários façam chamadas ponto a ponto.
      - **Permitir vídeo IP** - **Ativar** essa configuração para permitir que os convidados usem vídeos em suas chamadas e reuniões.
      - **Modo de compartilhamento de tela** – Essa configuração controla a disponibilidade do compartilhamento de tela para usuários convidados. 
          - **Desativar** essa configuração para remover a capacidade de os convidados compartilharem suas telas no Teams. 
          - Defina essa configuração como **Aplicativo único** para permitir o compartilhamento de aplicativos individuais. 
          - Defina essa configuração como **Tela inteira** para permitir o compartilhamento completo da tela.
      - **Permitir Reunir Agora** - **Ativar** essa configuração para permitir que os convidados usem o recurso Reunir Agora no Microsoft Teams.
      - **Editar mensagens enviadas** - **Ativar** essa configuração para permitir que os convidados editem as mensagens enviadas anteriormente.
      - **Os convidados podem excluir mensagens enviadas** - **Ativar** essa configuração para permitir que os convidados excluam mensagens enviadas anteriormente.
      - **Chat** - **Ativar** essa configuração para oferecer aos convidados a capacidade de usar o chat no Teams.
      - **Usar Giphys em conversas** - **Ativar** essa configuração para permitir que os convidados usem Giphys nas conversas. O Giphy é um mecanismo de pesquisa e banco de dados online que permite aos usuários pesquisar e compartilhar arquivos GIF animados. Cada Giphy recebe uma classificação de conteúdo.
      - **Classificação de conteúdo para Giphy** – Selecione uma classificação na lista suspensa:
          - **Permitir todo o conteúdo** - Os convidados poderão inserir todos os Giphys nos chats, independentemente da classificação do conteúdo.
          - **Moderado** - Os convidados poderão inserir Giphys nos chats, mas o conteúdo adulto será moderadamente restringido.
          - **Estrito** - Os convidados poderão inserir Giphys nos chats, mas serão impedidos de inserir conteúdo adulto.
      - **Usar memes em conversas** - **Ativar** essa configuração para permitir que os convidados usem memes nas conversas.
      - **Usar Figurinhas em conversas** - **Ativar** essa configuração para permitir que os convidados usem figurinhas nas conversas. 

    ![Configurações de permissões de convidado no Teams](media/manage-guest-access-image1.png)

5. Clique em **Salvar**.

## <a name="external-access-federation-vs-guest-access"></a>Acesso externo (federação) e o acesso de convidado

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a>Confira também

[Configurar a colaboração segura com o Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[Bloquear usuários convidados de uma equipe específica](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)