---
title: Ativar ou desativar o acesso de convidados ao Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Saiba mais sobre como ativar ou desativar o recurso de acesso de convidado no Microsoft Teams como um administrador do Office 365.
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 297a101389de2e1609697ffa2c30a2a8b7a84080
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2020
ms.locfileid: "45042773"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Ativar ou desativar o acesso de convidados ao Microsoft Teams
===================================================

Por padrão, o acesso de convidado está desativado. Como o Microsoft 365 ou o administrador do Office 365, você deve ativar o acesso de convidado para Teams para que os proprietários do administrador ou da equipe possam adicionar convidados. Para ativar o acesso de convidado, use a [lista de verificação de acesso de convidado](guest-access-checklist.md). 

Depois de ativar o acesso de convidado, pode levar algumas horas para que as alterações entrem em vigor. Se um usuário vir a mensagem "entrar em contato com seu administrador" ao tentar adicionar um convidado à equipe, é provável que o acesso de convidado não tenha sido ativado ou que as configurações ainda não estejam efetivas.

> [!IMPORTANT]
> Ativar o acesso de convidado depende das configurações do Azure Active Directory, do Microsoft 365 ou do Office 365, do SharePoint Online e do teams. Para obter mais informações, consulte [autorizar o acesso de convidado no Microsoft Teams](Teams-dependencies.md).



## <a name="configure-guest-access-in-the-teams-admin-center"></a>Configurar o acesso de convidado no centro de administração do teams

1. Entre no centro de administração do Microsoft Teams.

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

5. Clique em **Salvar**.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Use o PowerShell para ativar ou desativar o acesso de convidados

Ler [usar o PowerShell para ativar ou desativar o acesso ao convidado](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)


## <a name="video-adding-guests-in-teams"></a>Vídeo: como adicionar convidados no Microsoft Teams

|  |  |
|---------|---------|
| Adição de convidados no Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 


## <a name="external-access-federation-vs-guest-access"></a>Acesso externo (federação) e o acesso de convidado

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]