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
- m365initiative-externalcollab
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
ms.localizationpriority: medium
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Saiba mais sobre como ativar ou desativar o recurso de acesso de convidado no Microsoft Teams como um administrador do Office 365.
ms.openlocfilehash: 2b444b8357d8edef9aaa1c9c8e72ae6762f5bd52
ms.sourcegitcommit: 74d3ab35c344d70b2399bc46a6ced3ab2762a470
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60138237"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Ativar ou desativar o acesso de convidados ao Microsoft Teams

> [!Note]
>
> Até **fevereiro de 2021**, o acesso de convidados é desligado por padrão. Você deve ativar o acesso de convidado para o Teams antes que os administradores ou proprietários de equipe possam adicionar convidados. Depois de ativar o acesso de convidados, pode levar algumas horas para que as alterações tenham efeito. Se os usuários  verem a mensagem Contate seu administrador quando tentarem adicionar um convidado à sua equipe, é provável que o acesso de convidados ainda não tenha sido ligado ou as configurações ainda não tenham sido efetivas.
>
> Após **fevereiro de 2021,** o acesso de convidados no Microsoft Teams será ligado por padrão para novos clientes & clientes existentes que não tenham configurado essa configuração. Quando essa alteração for implementada, se você ainda não tiver configurado o recurso de acesso de convidado no Microsoft Teams, esse recurso será habilitado em seu locatário. Se você quiser que o acesso de convidado permaneça desabilitado para sua organização, você precisará confirmar se a configuração de acesso de convidado está definida como **Desativado** em vez do **Padrão de Serviço**.

> [!IMPORTANT]
> Ativar o acesso de convidado depende das configurações no Azure Active Directory, Microsoft 365, Microsoft Office SharePoint Online e Teams. Para saber mais, confira [Colabore com os convidados em uma equipe](/microsoft-365/solutions/collaborate-as-team).

## <a name="configure-guest-access-in-the-teams-admin-center"></a>Configure o acesso de convidados no centro de administração do Microsoft Teams

1. Entre no [Centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/).

2. Selecione **Usuários**  >  **Acesso de convidado**.

3. Definir **Permitir acesso de convidado em Teams** como **On**.

    ![Permitir que a opção de acesso de convidado seja definida como On .](media/guest-access-setting.png)

4. Em **Chamando,** **Reunião** e **Mensagens,** selecione **Ligar** **ou** Desligar para cada recurso, dependendo do que você deseja permitir para convidados.

      - **Fazer chamadas privadas** – **Ativar** essa função para permitir que os usuários façam chamadas ponto a ponto.
      - **Vídeo IP** - Ativar essa configuração **para** permitir que os convidados usem vídeo em suas chamadas e reuniões.
      - **Modo de compartilhamento de** tela – Essa configuração controla a disponibilidade de compartilhamento de tela para convidados.
          - **Desativar** essa configuração para remover a capacidade de os convidados compartilharem suas telas no Teams.
          - Defina essa configuração como **Aplicativo único** para permitir o compartilhamento de aplicativos individuais.
          - Defina essa configuração como **Tela inteira** para permitir o compartilhamento completo da tela.
      - **Reunir Agora** – a opção Ativar essa configuração **para** permitir que os convidados usem o recurso Reunir Agora Microsoft Teams.
      - **Editar mensagens enviadas** - **Ativar** essa configuração para permitir que os convidados editem as mensagens enviadas anteriormente.
      - **Excluir mensagens enviadas** – Ativar essa configuração **para** permitir que os convidados excluam mensagens enviadas anteriormente.
      - **Chat** - **Ativar** essa configuração para oferecer aos convidados a capacidade de usar o chat no Teams.
      - **Giphy nas conversas** – Adíra essa configuração **para** permitir que os convidados usem Giphys em conversas. O Giphy é um mecanismo de pesquisa e banco de dados online que permite aos usuários pesquisar e compartilhar arquivos GIF animados. Cada Giphy recebe uma classificação de conteúdo.
      - **Classificação de conteúdo para Giphy** – Selecione uma classificação na lista suspensa:
          - **Permitir todo o conteúdo** - Os convidados poderão inserir todos os Giphys nos chats, independentemente da classificação do conteúdo.
          - **Moderado** - Os convidados poderão inserir Giphys nos chats, mas o conteúdo adulto será moderadamente restringido.
          - **Estrito** – Os convidados podem inserir Giphys em chats, mas serão impedidos de inserir conteúdo adulto.
      - **Memes em conversas** - Adumente essa configuração **para** permitir que os convidados usem Memes em conversas.
      - **Adesivos em conversas** – a opção Ativar essa configuração **para** permitir que os convidados usem adesivos em conversas.
      - **Leitor imersivo para** mensagens -  Ativar essa configuração para permitir que os convidados usem o leitor imersivo [em Teams](https://support.microsoft.com/topic/a700c0d0-bc53-4696-a94d-4fbc86ac7a9a).

    ![Configurações de permissões de convidado Teams.](media/manage-guest-access-image1.png)

5. Selecione **Salvar**.

## <a name="external-access-federation-vs-guest-access"></a>Acesso externo (federação) e o acesso de convidado

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a>Confira também

[Configurar a colaboração segura com o Microsoft 365](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[Bloquear convidados de uma equipe específica](/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)
