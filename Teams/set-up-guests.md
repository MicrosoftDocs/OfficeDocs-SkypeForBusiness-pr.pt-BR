---
title: Habilitar ou desabilitar o acesso de convidados no Microsoft Teams
author: LaithAlShamri
ms.author: lolaj
manager: serdars
ms.date: 10/11/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Habilitar ou desabilitar o recurso de acesso de convidados no Microsoft Teams
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ab67b3fa9ad58c1aa3e8fdd254e3b3515743b4c
ms.sourcegitcommit: 9dd5d8fe6888f0c7d2df1e40fdd8b4c80512f8f9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/11/2018
ms.locfileid: "25498117"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a>Habilitar ou desabilitar o acesso de convidados no Microsoft Teams
======================================

Como administrador do Office 365, você precisa habilitar o recurso de convidados para que você ou os usuários da sua organização (especificamente os proprietários de equipe) possam adicionar convidados. 

As configurações do convidado são definidas no Azure Active Directory. Leva entre 2 e 24 horas para que as alterações entrem em vigor na sua organização do Office 365. Se um usuário vir a mensagem “Entre em contato com o seu administrador” ao tentar adicionar um convidado para a sua equipe, aparentemente o recurso de convidados não foi habilitado ou as configurações ainda não entraram em vigor.


> [!IMPORTANT]
> Para habilitar a experiência completa do recurso de acesso de convidados, é importante compreender a dependência de autorização básica entre o Microsoft Teams, o Azure Active Directory e o Office 365. Para obter mais informações, consulte [Autorizar acesso de convidados no Microsoft Teams](Teams-dependencies.md).

## <a name="configure-guest-access-in-the-teams--skype-for-business-admin-center"></a>Configurar o acesso de convidado na equipes & Skype para o Centro de administração de negócios

1.  Entrar no equipes & Skype para centro de administração de negócios.

2.  Selecione **configurações de toda a organização** > **acesso de convidado**.

3. Defina a opção de alternância de **Permitir o acesso de convidado em equipes da Microsoft** para **ativado**.

    ![Permitir a opção de acesso de convidado definida como em ](media/set-up-guests-image1.png)

4.  Defina a alterna para **chamar**, **reuniões**e **mensagens** para **ou **desativado**,** dependendo do acesso que você deseja permitir.

5.  Clique em **Salvar**.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Usar o PowerShell para ativar ou desativar o acesso de convidado

1.  Baixe o Skype para o módulo de PowerShell Online de negócios dahttps://www.microsoft.com/en-us/download/details.aspx?id=39366
 
2.  Conecte-se uma sessão do PowerShell para o Skype para ponto de extremidade Business Online.

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  Verificar sua configuração e se `AllowGuestUser` é `$False`, use o cmdlet [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) para defini-la como `$True`.

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
    AllowTBotProactiveMessaging      : False
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
Agora você pode ter usuários convidados em equipes para sua organização.

## <a name="more-information"></a>Mais informações

Assista o vídeo a seguir para obter mais detalhes sobre o acesso de convidado.

|  |  |
|---------|---------|
| Adição de convidados no Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
