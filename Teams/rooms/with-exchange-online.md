---
title: Implantar as Salas do Microsoft Teams com o Exchange Online
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams com o Exchange Online e o Skype for Business Server local.
ms.openlocfilehash: 82fa0b1b521c7dd2feadcca2030869b746a444aa
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662306"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Implantar as Salas do Microsoft Teams com o Exchange Online

Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams com o Exchange Online e o Skype for Business Server local.
  
Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado. Este tópico aborda as implantações híbridas das Salas do Microsoft Teams com o Exchange hospedado online. Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas. O processo a seguir funcionará para várias configurações. Se o processo não for o certo para sua configuração, recomendamos que você use o Windows PowerShell para obter o mesmo resultado final que documentado aqui e para outras opções de implantação.

A maneira mais fácil de configurar contas de usuário é configurá-las usando o Windows PowerShell remoto. A Microsoft [ forneceSkypeRoomProvisioningScript.ps1, ](https://go.microsoft.com/fwlink/?linkid=870105)um script que ajudará a criar novas contas de usuário ou validar contas de recursos existentes que você tem para ajudá-lo a transformá-las em contas de usuário compatíveis com Salas do Microsoft Teams. Se preferir, siga as etapas abaixo para configurar contas que seu dispositivo Salas do Microsoft Teams usará.

## <a name="requirements"></a>Requisitos

Antes de implantar as Salas do Microsoft Teams com o Exchange Online, certifique-se de que você atendeu aos requisitos. Para obter mais informações, consulte [os requisitos de Salas do Microsoft Teams.](requirements.md)
  
Para implantar as Salas do Microsoft Teams com o Exchange Online, siga as etapas abaixo. Verifique se você tem as permissões apropriadas para executar os cmdlets associados. 

   > [!NOTE]
   >  Os [cmdlets do Azure Active Directory](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) para Windows PowerShell nesta seção (por exemplo, Set-MsolUser) foram testados na configuração de contas para dispositivos de Salas do Microsoft Teams. É possível que outros cmdlets possam funcionar, no entanto, eles ainda não foram testados neste cenário específico.

Se você implantou os Serviços de Federação do Active Directory (AD FS), talvez seja necessário converter a conta de usuário em um usuário gerenciado antes de seguir essas etapas e convertê-lo novamente em um usuário federado depois de concluir essas etapas.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Criar uma conta e definir as propriedades do Exchange

1. Inicie uma sessão remota do Windows PowerShell em um computador e conecte-se ao Exchange Online da seguinte forma:

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. Depois de estabelecer uma sessão, você criará uma nova caixa de correio e a habilitará como uma RoomMailboxAccount ou alterará as configurações de uma caixa de correio de sala existente. Isso permitirá que a conta se autenture nas Salas do Microsoft Teams.

   Se você alterar uma caixa de correio do recurso:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Se você estiver criando uma nova caixa de correio de recurso:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Para melhorar a experiência da reunião, você precisará definir as propriedades do Exchange na conta de usuário da seguinte forma:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Adicionar um endereço de e-mail à conta de domínio local

1. Na ferramenta AD Usuários e Computadores do **Active Directory,** clique com o botão direito do mouse no contêiner ou unidade organizacional em que suas contas de Salas do Microsoft Teams serão criadas, clique em Novo e, em seguida, clique em **Usuário.**
2. Digite o nome de exibição (- Identidade) do cmdlet anterior  (Set-Mailbox ou New-Mailbox) na caixa Nome completo e o alias na caixa de nome de **logon do** usuário. Clique em **Avançar**.
3. Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.

    > [!NOTE]
    > Selecionar **Senha nunca expira é** um requisito para o Skype for Business Server em Salas do Microsoft Teams. As regras do domínio podem proibir senhas que não expiram. Se sim, você precisará criar uma exceção para cada conta de usuário do Microsoft Teams Rooms.
  
4. Clique em **Concluir** para criar a conta.
5. Depois de criar a conta, execute uma sincronização de diretório. Isso pode ser feito usando [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) no PowerShell. Quando isso for concluído, vá para a página de usuários e verifique se as duas contas criadas nas etapas anteriores foram mescladas.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Atribuir uma licença do Microsoft 365 ou do Office 365

1. Primeiro, conecte-se ao Azure AD para aplicar algumas configurações de conta. Você poderá executar este cmdlet para se conectar. Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [O PowerShell 2.0 do Azure Active Directory](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) não tem suporte.

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. A conta de usuário precisa ter uma licença válida do Microsoft 365 ou do Office 365 para garantir que o Exchange e o Skype for Business Server funcionem. Se você tiver a licença, precisará atribuir um local de uso à sua conta de usuário— isso determina quais SKUs de licença estão disponíveis para sua conta. Você fará a tarefa em uma etapa a seguir.
3. Em seguida, use `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> para recuperar uma lista de SKUs disponíveis para sua organização do Microsoft 365 ou do Office 365.
4. Depois de listar as SKUs, você pode adicionar uma licença usando o `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> Cmdlet. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK). 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Habilitar a conta de usuário com o Skype for Business Server

1. Crie uma sessão remota do Windows PowerShell a partir de um computador da seguinte forma:

> [!NOTE]
> No momento, o Skype for Business Online Connector faz parte do módulo mais recente do PowerShell do Teams.
>
> Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Skype for Business Online Connector.

    ``` Powershell
    Import-Module -Name MicrosoftTeams
    $cred = Get-Credential
    $cssess = New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Para habilitar sua conta do Microsoft Teams Rooms para o Skype for Business Server, execute este comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Se você não tiver certeza de qual valor usar para o parâmetro RegistrarPool em seu ambiente, poderá obter o valor de um usuário existente do Skype for Business Server usando esse comando

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Atribuir uma licença do Skype for Business Server à sua conta do Microsoft Teams Rooms

1. Entre como administrador de locatários, abra o Centro de administração do Microsoft 365 e clique no aplicativo Administrador.
2. Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.
3. Clique na conta salas do Microsoft Teams e, em seguida, clique no ícone de caneta para editar as informações da conta.
4. Clique em **Licenças**.
5. Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice. Você terá que usar uma licença do Plano 3 se quiser usar o Enterprise Voice nas Salas do Microsoft Teams.
6. Clique em **Salvar**.

Para validação, você deve ser capaz de usar qualquer cliente do Skype for Business para entrar nessa conta.

> [!NOTE]
> Se você estiver usando SKUs E1, E3, E4 ou E5 com o Skype for Business Plano 2 com Audioconferência ou com o Sistema de Telefonia e um Plano de Chamada, eles continuarão a funcionar. No entanto, você deve considerar mudar para um modelo de licenciamento mais simples, conforme descrito na Atualização de Licenciamento de Sala de Reunião do [Teams,](rooms-licensing.md)após a expiração das licenças atuais.

> [!IMPORTANT]
> Se você estiver usando o Plano 2 do Skype for Business, só poderá usar as Salas do Microsoft Teams no modo Somente Skype for Business, o que significa que todas as suas reuniões serão reuniões do Skype for Business. Para habilitar sua sala de reunião para reuniões do Microsoft Teams, recomendamos que você compre a licença da Sala de Reunião.
  
## <a name="related-topics"></a>Tópicos relacionados

[Configurar contas para salas do Microsoft Teams](rooms-configure-accounts.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
  
[Implantar Salas do Microsoft Teams](rooms-deploy.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
