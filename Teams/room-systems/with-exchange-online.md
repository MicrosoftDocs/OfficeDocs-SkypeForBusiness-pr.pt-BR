---
title: Implantar as Salas do Microsoft Teams com o Exchange Online
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams com o Exchange Online.
ms.openlocfilehash: d2e410eeb04ac65f7fc458bc6c1d8e67579c0f8b
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774930"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Implantar as Salas do Microsoft Teams com o Exchange Online

Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams com o Exchange Online e o Skype for Business Server no local.
  
Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado. Este tópico aborda implantações híbridas de salas do Microsoft Teams com o Exchange hospedado online. Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas. O processo a seguir funcionará para várias configurações. Se o processo não está correto para a sua configuração, recomendamos que você use o Windows PowerShell para obter o mesmo resultado final conforme documentado aqui e para outras opções de implantação.

A maneira mais fácil de configurar contas de usuário é configurá-las usando o Windows PowerShell remoto. A Microsoft fornece [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudará a criar novas contas de usuário ou validar as contas de recursos existentes que você tem para ajudar a transformá-las em contas de usuário compatíveis do Microsoft Teams. Se preferir, você pode seguir as etapas abaixo para configurar contas que o dispositivo de salas do Microsoft Teams vai usar.

## <a name="requirements"></a>Requisitos

Antes de implantar salas do Microsoft Teams com o Exchange Online, verifique se você atendeu aos requisitos. Para obter mais informações, consulte [requisitos de salas do Microsoft Teams](requirements.md).
  
Para implantar salas do Microsoft Teams com o Exchange Online, siga as etapas abaixo. Verifique se você tem as permissões apropriadas para executar os cmdlets associados. 

   > [!NOTE]
   >  O [módulo do Azure Active Directory para cmdlets do Windows PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) nesta seção (por exemplo, Set-MsolUser) foram testados na configuração de contas para dispositivos de salas do Microsoft Teams. No entanto, é possível que outros cmdlets funcionem, mas não foram testados nesse cenário específico.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Criar uma conta e definir as propriedades do Exchange

1. Inicie uma sessão remota do Windows PowerShell em um computador e conecte-se ao Exchange Online da seguinte maneira:

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
Import-PSSession $Session -DisableNameChecking
```

2. Depois de estabelecer uma sessão, você criará uma nova caixa de correio e a habilitará como uma RoomMailboxAccount ou alterará as configurações de uma caixa de correio de sala existente. Isso permitirá que a conta seja autenticada em salas do Microsoft Teams.

   Se você alterar uma caixa de correio do recurso:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Se você estiver criando uma nova caixa de correio de recurso:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Para melhorar a experiência da reunião, você precisará definir as propriedades do Exchange na conta de usuário da seguinte maneira:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Adicionar um endereço de e-mail à conta de domínio local

1. Na ferramenta **ad usuários e computadores do Active Directory** , clique com o botão direito do mouse no contêiner ou na unidade organizacional em que suas contas de sala do Microsoft Teams serão criadas, clique em **novo**e clique em **usuário**.
2. Digite o nome para exibição (-identidade) do cmdlet anterior (Set-Mailbox ou New-Mailbox) na caixa **nome completo** e o alias para a caixa **nome de logon do usuário** . Clique em **Avançar**.
3. Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.

    > [!NOTE]
    > Selecionar a **senha nunca expira** é um requisito para as salas do Skype for Business Server em Microsoft Teams. As regras do domínio podem proibir senhas que não expiram. Em caso afirmativo, você precisará criar uma exceção para cada conta de usuário das salas do Microsoft Teams.
  
4. Clique em **Concluir** para criar a conta.
5. Depois de criar a conta, execute uma sincronização de diretório. Isso pode ser feito usando [set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) no PowerShell. Quando concluir, vá para a página usuários e verifique se as duas contas criadas nas etapas anteriores foram mescladas.

### <a name="assign-an-office-365-license"></a>Atribuir uma licença do Office 365

1. Primeiro, conecte-se ao Azure AD para aplicar algumas configurações de conta. Você poderá executar este cmdlet para se conectar. Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > Não há suporte para o [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) . 

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. A conta de usuário precisa ter uma licença válida do Office 365 para garantir que o Exchange e o Skype for Business Server funcionem. Se você tiver a licença, será necessário atribuir um local de uso à sua conta de usuário — isso determina quais SKUs de licença estão disponíveis para a sua conta. Você fará a atribuição em uma etapa seguinte.
3. Em seguida, use`Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> para recuperar uma lista de SKUs disponíveis para o seu locatário do Office 365.
4. Depois de listar os SKUs, você pode adicionar uma licença usando o botão`Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK). 

  ```
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Habilitar a conta de usuário com o Skype for Business Server

1. Crie uma sessão remota do Windows PowerShell a partir de um PC da seguinte maneira:

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Para habilitar a sua conta de salas do Microsoft Teams para o Skype for Business Server, execute este comando:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Se não tiver certeza de qual valor usar para o parâmetro RegistrarPool em seu ambiente, você pode obter o valor de um usuário existente do Skype for Business Server usando este comando

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Atribuir uma licença do Skype for Business Server à sua conta de salas do Microsoft Teams

1. Faça logon como administrador de locatários, abra o portal administrativo do Office 365 e clique no aplicativo de administração.
2. Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.
3. Clique na conta de salas do Microsoft Teams e, em seguida, clique no ícone de caneta para editar as informações da conta.
4. Clique em **Licenças**.
5. Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice. Você precisará usar uma licença do plano 3 se quiser usar as salas do Enterprise Voice em Microsoft Teams.
6. Clique em **Salvar**.

Para a validação, você deve ser capaz de usar qualquer cliente Skype for Business para se conectar a esta conta.
  
## <a name="see-also"></a>Confira também

[Configurar contas para salas do Microsoft Teams](room-systems-v2-configure-accounts.md)

[Plano para salas do Microsoft Teams](skype-room-systems-v2-0.md)
  
[Implantar salas do Microsoft Teams](room-systems-v2.md)
  
[Configurar um console de salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](skype-room-systems-v2.md)
