---
title: Ativar ou desativar o acesso de convidados ao Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Habilitar ou desabilitar o recurso de acesso de convidados no Microsoft Teams
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
appliesto:
- Microsoft Teams
ms.openlocfilehash: f00b585b1473a366769650c2a59f6dee2a9d3bea
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36242616"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Ativar ou desativar o acesso de convidados ao Microsoft Teams
===================================================

Como administrador do Office 365, você precisa habilitar o recurso de convidados para que você ou os usuários da sua organização (especificamente os proprietários de equipe) possam adicionar convidados.

As configurações do convidado são definidas no Azure Active Directory. Leva entre 2 e 24 horas para que as alterações entrem em vigor na sua organização do Office 365. Se um usuário vir a mensagem “Entre em contato com o seu administrador” ao tentar adicionar um convidado para a sua equipe, é provável que o recurso de convidado não tenha sido ativado ou as configurações ainda não entraram em vigor.

> [!IMPORTANT]
> Para habilitar a experiência completa do recurso de acesso de convidados, é importante compreender a dependência de autorização básica entre o Microsoft Teams, o Azure Active Directory e o Office 365. Para obter mais informações, consulte [Autorizar acesso de convidados no Microsoft Teams](Teams-dependencies.md).

## <a name="guest-access-vs-external-access-federation"></a>Acesso de convidado vs. acesso externo (federação)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a>Configure o acesso de convidados no centro de administração do Microsoft Teams

1.  Entre no centro de administração do Microsoft Teams.

2.  Selecione **Configurações em toda a organização** > **Acesso de convidados**.

3. Defina o botão de alternância **Permitir acesso de convidados no Microsoft Teams** para **Ativado**.

    ![Permita que a opção de acesso de convidados seja definida como Ativada ](media/set-up-guests-image1.png)

4.  Defina as alternâncias em **Chamada**, **Reunião** e **Mensagens** como **Ativada** ou **Desativada**, dependendo dos recursos que você deseja permitir aos usuários convidados.

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


5.  Clique em **Salvar**.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Use o PowerShell para ativar ou desativar o acesso de convidados

1.  Baixe o módulo PowerShell do Skype for Business Online em https://www.microsoft.com/en-us/download/details.aspx?id=39366
 
2.  Conecte uma sessão do PowerShell ao ponto de extremidade do Skype for Business Online.

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  Verifique sua configuração e se `AllowGuestUser` for `$False`, use o cmdlet [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) para defini-lo como `$True`.

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
Agora você pode ter usuários convidados no Teams da sua organização.

## <a name="more-information"></a>Mais informações

Assista ao vídeo a seguir para obter mais detalhes sobre o acesso de convidados.

|  |  |
|---------|---------|
| Adição de convidados no Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
