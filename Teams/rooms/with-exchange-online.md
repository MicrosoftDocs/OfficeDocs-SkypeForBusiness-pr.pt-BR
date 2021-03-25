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
ms.openlocfilehash: 5e3446349be8aaef666c02c73370758027736181
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117339"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Implantar as Salas do Microsoft Teams com o Exchange Online

Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams com o Exchange Online e o Skype for Business Server local.
  
Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado. Este tópico aborda implantações híbridas para Salas do Microsoft Teams com o Exchange hospedado online. Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas. O processo a seguir funcionará para várias configurações. Se o processo não estiver correto para sua instalação, recomendamos que você use o Windows PowerShell para obter o mesmo resultado final documentado aqui e para outras opções de implantação.

A maneira mais fácil de configurar contas de usuário é configurá-las usando Windows PowerShell. A Microsoft [ forneceSkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudará a criar novas contas de usuário ou validar contas de recursos existentes que você tem para ajudá-lo a transformá-las em contas de usuário compatíveis do Microsoft Teams Rooms. Se preferir, siga as etapas abaixo para configurar contas que o dispositivo salas do Microsoft Teams usará.

## <a name="requirements"></a>Requisitos

Antes de implantar salas do Microsoft Teams com o Exchange Online, certifique-se de ter atendido aos requisitos. Para obter mais informações, consulte [Requisitos de Salas do Microsoft Teams.](requirements.md)
  
Para implantar salas do Microsoft Teams com o Exchange Online, siga as etapas abaixo. Verifique se você tem as permissões apropriadas para executar os cmdlets associados. 

   > [!NOTE]
   >  O [Módulo do Azure Active Directory para Windows PowerShell cmdlets](/powershell/azure/active-directory/overview?view=azureadps-1.0) nesta seção (por exemplo, Set-MsolUser) foi testado na configuração de contas para dispositivos de Salas do Microsoft Teams. É possível que outros cmdlets funcionem, no entanto, eles não foram testados neste cenário específico.

Se você implantou os Serviços de Federação do Active Directory (AD FS), talvez seja necessário converter a conta de usuário em um usuário gerenciado antes de seguir essas etapas e converter o usuário de volta em um usuário federado depois de concluir essas etapas.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Criar uma conta e definir as propriedades do Exchange

1. Inicie uma sessão de Windows PowerShell remota em um computador e conecte-se ao Exchange Online da seguinte forma:

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. Depois de estabelecer uma sessão, você criará uma nova caixa de correio e a habilitará como RoomMailboxAccount ou alterará as configurações de uma caixa de correio de sala existente. Isso permitirá que a conta se autenture em Salas do Microsoft Teams.

   Se você alterar uma caixa de correio do recurso:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Se você estiver criando uma nova caixa de correio de recurso:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Para melhorar a experiência de reunião, você precisará definir as propriedades do Exchange na conta de usuário da seguinte forma:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Adicionar um endereço de e-mail à conta de domínio local

1. Na ferramenta AD Usuários e Computadores do **Active Directory,** clique com o botão direito do mouse no contêiner ou unidade organizacional em que suas contas de Salas do Microsoft Teams serão criadas, clique em Novo e em **Usuário**. 
2. Digite o nome de exibição (- Identity ) do cmdlet anterior (Set-Mailbox ou New-Mailbox) na caixa **Nome** completo e o alias na caixa Nome de **logon do** usuário. Clique em **Avançar**.
3. Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.

    > [!NOTE]
    > Selecionar **Senha nunca expira é** um requisito para o Skype for Business Server em Salas do Microsoft Teams. As regras do domínio podem proibir senhas que não expiram. Em caso afirmado, você precisará criar uma exceção para cada conta de usuário do Microsoft Teams Rooms.
  
4. Clique em **Concluir** para criar a conta.
5. Depois de criar a conta, execute uma sincronização de diretório. Isso pode ser feito usando [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) no PowerShell. Quando isso for concluído, vá para a página usuários e verifique se as duas contas criadas nas etapas anteriores foram mescladas.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Atribuir uma licença do Microsoft 365 ou Office 365

1. Primeiro, conecte-se ao Azure AD para aplicar algumas configurações de conta. Você poderá executar este cmdlet para se conectar. Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).

   > [!NOTE]
   > [Não há suporte para o PowerShell 2.0 do Azure Active Directory.](/powershell/azure/active-directory/overview?view=azureadps-2.0)

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. A conta de usuário precisa ter uma licença válida do Microsoft 365 ou office 365 para garantir que o Exchange e o Skype for Business Server funcionem. Se você tiver a licença, precisará atribuir um local de uso à sua conta de usuário— isso determina quais SKUs de licença estão disponíveis para sua conta. Você fará a atribuição em uma etapa a seguir.
3. Em seguida, use `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> para recuperar uma lista de SKUs disponíveis para sua organização do Microsoft 365 ou Office 365.
4. Depois de listar as SKUs, você pode adicionar uma licença usando o `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK). 

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

1. Crie uma sessão Windows PowerShell remota de um computador da seguinte forma:

> [!NOTE]
> O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.
>
> Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Conector do Skype for Business Online.

    ``` Powershell
    # When using Teams PowerShell Module
    Import-Module MicrosoftTeams
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

2. Para habilitar sua conta de Salas do Microsoft Teams para o Skype for Business Server, execute este comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Se você não tiver certeza de qual valor usar para o parâmetro RegistrarPool em seu ambiente, poderá obter o valor de um usuário existente do Skype for Business Server usando este comando

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Atribuir uma licença do Skype for Business Server à sua conta do Microsoft Teams Rooms

1. Faça logoff como administrador de locatário, abra o Centro de administração do Microsoft 365 e clique no aplicativo Administrador.
2. Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.
3. Clique na conta salas do Microsoft Teams e clique no ícone de caneta para editar as informações da conta.
4. Clique em **Licenças**.
5. Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice. Você terá que usar uma licença do Plano 3 se quiser usar Enterprise Voice salas do Microsoft Teams.
6. Clique em **Salvar**.

Para validação, você deve ser capaz de usar qualquer cliente do Skype for Business para fazer logoff nessa conta.

> [!NOTE]
> Se você estiver usando atualmente SKUs E1, E3, E4 ou E5 com Skype for Business Plan 2 com Audioconferência ou com o Sistema de Telefonia e um Plano de Chamadas, eles continuarão a funcionar. No entanto, você deve considerar a mudança para um modelo de licenciamento mais simples, conforme descrito em Atualização de Licenciamento de Sala de Reunião do [Teams](rooms-licensing.md), depois que as licenças atuais expirarem.

> [!IMPORTANT]
> Se você estiver usando o Skype for Business Plan 2, só poderá usar as Salas do Microsoft Teams no modo Somente Skype for Business, o que significa que todas as suas reuniões serão reuniões do Skype for Business. Para habilitar sua sala de reunião para reuniões do Microsoft Teams, recomendamos que você compre a licença da Sala de Reunião.
  
## <a name="related-topics"></a>Tópicos relacionados

[Configurar contas para salas do Microsoft Teams](rooms-configure-accounts.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
  
[Implantar Salas do Microsoft Teams](rooms-deploy.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)