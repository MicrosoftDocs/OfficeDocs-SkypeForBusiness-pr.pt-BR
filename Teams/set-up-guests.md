---
title: Ativar ou desativar o acesso de convidado ao Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
MS.collection:
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
ms.openlocfilehash: 240e93d5f6329090940e6bf49cb2d6a4ee46ce2f
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2019
ms.locfileid: "35221447"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Ativar ou desativar o acesso de convidado ao Microsoft Teams
===================================================

Como administrador do Office 365, você precisa habilitar o recurso de convidados para que você ou os usuários da sua organização (especificamente os proprietários de equipe) possam adicionar convidados.

As configurações do convidado são definidas no Azure Active Directory. Leva entre 2 e 24 horas para que as alterações entrem em vigor na sua organização do Office 365. Se um usuário vir a mensagem "entrar em contato com seu administrador" ao tentar adicionar um convidado à equipe, é provável que o recurso convidado ainda não tenha sido habilitado ou que as configurações ainda não sejam efetivadas.

> [!IMPORTANT]
> Para habilitar a experiência completa do recurso de acesso de convidados, é importante compreender a dependência de autorização básica entre o Microsoft Teams, o Azure Active Directory e o Office 365. Para obter mais informações, consulte [Autorizar acesso de convidados no Microsoft Teams](Teams-dependencies.md).

## <a name="guest-access-vs-external-access-federation"></a>Acesso de convidado vs. acesso externo (federação)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a>Configurar o acesso de convidado no centro de administração do Microsoft Teams

1.  Entre no centro de administração do Microsoft Teams.

2.   > Selecione **configurações de toda a organização****acesso de convidado**.

3. Defina o botão de alternância **permitir acesso de convidado no Microsoft Teams** como **ativado**.

    ![Opção permitir acesso de convidado definido como ativado ](media/set-up-guests-image1.png)

4.  Defina as alternâncias em **chamada**, **reunião**e **mensagens** para **ativado** ou **desativado**, dependendo das funcionalidades que você deseja permitir para os usuários convidados.

    - **Faça chamadas privadas** -Ative essa configuração **** para permitir que os convidados façam chamadas ponto a ponto.
    - **Permitir vídeo por IP** -Ative esta **** configuração para permitir que os convidados usem vídeo em suas chamadas e reuniões.
    - **Modo de compartilhamento de tela** – essa configuração controla a disponibilidade de compartilhamento de tela para usuários convidados. 
       - Transforme essa configuração **** como desabilitada para remover a capacidade dos convidados de compartilhar suas telas no Teams. 
       - Ative essa configuração para **um único aplicativo** para permitir o compartilhamento de aplicativos individuais. 
       - Transforme essa configuração em **tela inteira** para permitir o compartilhamento de tela completo.
    - **Permitir reunião agora** – Ative essa configuração **** para permitir que os convidados usem o recurso reunir agora no Microsoft Teams.
    - **Editar mensagens enviadas** -Ative essa configuração **** para permitir que os convidados editem as mensagens que enviaram anteriormente.
    - **Convidados podem excluir mensagens enviadas** – Ative essa configuração **** para permitir que os convidados excluam mensagens que enviaram anteriormente.
    - **Chat** – Ative essa configuração **** para dar aos convidados a capacidade de usar o chat no Microsoft Teams.
    - **Use o Giphys em conversas** – Ative essa **** configuração para permitir que os convidados usem o Giphys nas conversas. O Giphy é um banco de dados online e um mecanismo de pesquisa que permite aos usuários procurar e compartilhar arquivos GIF animados. Cada Giphy é atribuído a uma classificação de conteúdo.
    - **Classificação de conteúdo do Giphy** – selecione uma classificação na lista suspensa:
       - **Permitir todo o conteúdo** -convidados poderão inserir todos os Giphys em chats, independentemente da classificação de conteúdo.
       - **Moderado** -convidados poderão inserir Giphys em chats, mas serão moderadamente restritos ao conteúdo somente para adultos.
       - **Estrito** – os convidados poderão inserir Giphys em chats, mas não poderão inserir conteúdo somente para adultos.
    - **Usar o memes em conversas** -Ative essa **** configuração para permitir que os convidados usem o memes nas conversas.
    - **Use adesivos em conversas** – Ative essa **** configuração para permitir que os convidados usem adesivos nas conversas. 


5.  Clique em **Salvar**.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Usar o PowerShell para ativar ou desativar o acesso ao convidado

1.  Baixe o módulo PowerShell do Skype for Business online emhttps://www.microsoft.com/en-us/download/details.aspx?id=39366
 
2.  Conecte uma sessão do PowerShell ao ponto de extremidade do Skype for Business online.

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  Verifique a configuração e, `AllowGuestUser` se `$False`estiver, use o cmdlet [set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) para defini- `$True`la.

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
Agora você pode ter usuários convidados no Teams para sua organização.

## <a name="more-information"></a>Mais informações

Assista ao vídeo a seguir para obter mais detalhes sobre o acesso de convidados.

|  |  |
|---------|---------|
| Adição de convidados no Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
