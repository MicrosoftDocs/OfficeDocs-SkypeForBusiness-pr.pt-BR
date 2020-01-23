---
title: Implantar Salas do Microsoft Teams com o Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams com o Office 365.
ms.openlocfilehash: 6b473fc54574f26909e274662f3c08c1031dfafb
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2020
ms.locfileid: "41268757"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>Implantar Salas do Microsoft Teams com o Office 365

Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams com o Office 365, em que o Microsoft Teams ou o Skype for Business e o Exchange estão online.

A maneira mais fácil de configurar contas de usuário é configurá-las usando o Windows PowerShell remoto. A Microsoft fornece [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudará a criar novas contas de usuário ou validar as contas de recursos existentes que você tem para ajudar a transformá-las em contas de usuário compatíveis do Microsoft Teams. Se preferir, você pode seguir as etapas abaixo para configurar contas que o dispositivo de salas do Microsoft Teams vai usar.

## <a name="requirements"></a>Requisitos

Antes de implantar salas do Microsoft Teams com o Office 365, certifique-se de que atenda aos requisitos. Para obter mais informações, consulte [requisitos de salas do Microsoft Teams](requirements.md).

Para habilitar o Skype for Business, você deve ter o seguinte:

- Skype for Business online (plano 2 ou plano baseado em empresas) ou superior em seu plano do Office 365. O plano precisa permitir recursos de conferência discada.

- Se precisar de recursos de discagem de uma reunião, você precisará de uma conferência de áudio e uma licença do sistema de telefonia.  Se precisar de recursos de discagem de uma reunião, você precisará de um plano de chamada internacional ou doméstico e internacional.

- Os usuários do locatário devem ter caixas de correio do Exchange.

- Sua conta de salas do Microsoft Teams requer pelo menos uma licença do Skype for Business online (plano 2), mas não requer uma licença do Exchange Online. Consulte [licenças de salas do Microsoft Teams](rooms-licensing.md) para obter detalhes.

Para obter detalhes sobre os planos do Skype for Business Online, consulte a [Descrição do serviço do Skype for Business online](https://technet.microsoft.com/library/jj822172.aspx).

### <a name="add-a-device-account"></a>Adicionar uma conta de dispositivo

1. Conecte-se ao PowerShell do Exchange Online. Para obter instruções, consulte [conectar ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

2. No PowerShell do Exchange Online, crie uma nova caixa de correio de sala ou modifique uma caixa de correio de sala existente. Por padrão, as caixas de correio da sala não têm contas associadas, portanto, você precisará adicionar uma conta ao criar ou modificar uma caixa de correio de sala que permita que ela seja autenticada com o Skype Room Systems v2.

   - Para criar uma nova caixa de correio de sala, use a seguinte sintaxe:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este exemplo cria uma nova caixa de correio de sala com as seguintes configurações:

     - Nome: Project-Rigel-01

     - Alias: ProjectRigel01

     - Conta: ProjectRigel01@contoso.onmicrosoft.com

     - Senha da conta: P@ $ $W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Para modificar uma caixa de correio de sala existente, use a seguinte sintaxe:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este exemplo habilita a conta da caixa de correio de sala existente que tem o valor do alias ProjectRigel02 e define a senha como 9898P@ $ $W 0rd. Observe que a conta será ProjectRigel02@contoso.onmicrosoft.comda por causa do valor de alias existente.

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Para obter informações detalhadas sobre a sintaxe e o parâmetro, consulte [novo-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).


3. No PowerShell do Exchange Online, defina as seguintes configurações na caixa de correio da sala para melhorar a experiência da reunião:

   - AutomateProcessing: a aceitação autoaceitar (os organizadores de reunião recebem a decisão de reserva de sala diretamente sem intervenção humana: grátis = aceitar; Busy = recusar.)

   - AddOrganizerToSubject: $false (o organizador da reunião não é adicionado ao assunto da solicitação de reunião.)

   - DeleteComments: $false (Mantenha qualquer texto no corpo da mensagem de solicitações de reunião recebidas.)

   - DeleteSubject: $false (Mantenha o assunto das solicitações de reunião recebidas.)

   - RemovePrivateProperty: $false (garante que o sinalizador particular enviado pelo organizador da reunião na solicitação de reunião original permaneça conforme especificado.)

   - AddAdditionalResponse: $true (o texto especificado pelo parâmetro AdditionalResponse é adicionado a solicitações de reunião.)

   - AdditionalResponse: "esta é uma sala de reunião do Skype!" (O texto adicional a ser adicionado à solicitação de reunião.)

   Este exemplo configura essas configurações na caixa de correio da sala chamada Project-Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Para obter informações detalhadas de sintaxe e parâmetro, consulte [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Conecte-se ao MS online PowerShell para fazer as configurações do Active `Connect-MsolService -Credential $cred` Directory executando o cmdlet do PowerShell.   Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > Não há suporte para o [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) . 

5. Se você não quiser que a senha expire, use a seguinte sintaxe:

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   Este exemplo define a senha da conta ProjectRigel01@contoso.onmicrosoft.com para nunca expirar.

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   Você também pode definir um número de telefone para a conta executando o seguinte comando:

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. A conta do dispositivo precisa ter uma licença válida do Office 365 ou o Exchange e o Microsoft Teams ou o Skype for Business não funcionarão. Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta). Você pode usar`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar uma lista de SKUs disponíveis para o seu locatário do Office 365 da seguinte maneira:

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Em seguida, você pode adicionar uma licença usando o`Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).

  ``` PowerShell
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
  ``` 
<!-- 
   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   Para obter instruções detalhadas, consulte [atribuir licenças a contas de usuário com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

7. Em seguida, você precisa habilitar a conta do dispositivo com o Skype for Business. Certifique-se de que seu ambiente atenda aos requisitos definidos nos [requisitos de salas do Microsoft Teams](requirements.md).

   Inicie uma sessão remota do [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) da seguinte maneira (certifique [-se de instalar os componentes do PowerShell do Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   Em seguida, habilite a sua conta de salas do Microsoft Teams para o Skype for Business Server executando o seguinte cmdlet:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   Obtenha as informações de RegistrarPool da nova conta de usuário que está sendo configurada, conforme mostrado neste exemplo:

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > Não é possível criar novas contas de usuário no mesmo pool de registradores como contas de usuário existentes no locatário. O comando acima impedirá erros na configuração da conta devido a essa situação.

Depois de concluir as etapas anteriores para habilitar sua conta de salas do Microsoft Teams no Microsoft Teams ou o Skype for Business Online, você precisa atribuir uma licença ao dispositivo de salas do Microsoft Teams. Usando o portal administrativo do Office 365, atribua uma licença do Skype for Business online (plano 2) ou do Skype for Business online (plano 3) ao dispositivo.

### <a name="assign-a-license-to-your-account"></a>Atribuir uma licença à conta

1. Faça logon como administrador de locatários, abra o portal administrativo do Office 365 e clique no aplicativo de administração.

2. Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.

3. Selecione a conta de salas do Microsoft Teams e, em seguida, clique ou toque no ícone de caneta, o que significa editar.

4. Clique na opção **Licenças**.

5. Na seção **atribuir licenças** , você precisa selecionar o Skype for Business online (plano 2) ou o Skype for Business online (plano 3), dependendo do seu licenciamento e do que você decidiu em termos de necessidade do Enterprise Voice. Você terá que usar uma licença do plano 3 se quiser usar o Cloud PBX em salas do Microsoft Teams. O CloudPBX será necessário como requisito mínimo para habilitar a conectividade de voz. Em seguida, configure as chamadas PSTN ou de voz híbridas com base no método de conectividade PSTN. Consulte [licenças de salas do Microsoft Teams](rooms-licensing.md) para obter mais detalhes.

6. Clique em **Salvar** para concluir a tarefa.

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>Exemplo: configuração da conta de sala no Exchange Online e no Skype for Business Online

Comandos do PowerShell do Exchange Online:

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

Comandos do PowerShell do Azure Active Directory:

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

Comando do PowerShell do Skype for Business:

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> Assim, você adiciona CloudPBX e PSTNCallingDomesticAndInternational. Além disso, será necessário usar a interface do administrador para atribuir um número de telefone.

## <a name="validate"></a>Válida

Para a validação, você deve ser capaz de usar qualquer cliente Skype for Business para entrar na conta que você criou.

## <a name="see-also"></a>Confira também

[Configurar contas para salas do Microsoft Teams](rooms-configure-accounts.md)

[Plano para salas do Microsoft Teams](rooms-plan.md)

[Implantar salas do Microsoft Teams](rooms-deploy.md)

[Configurar um console de salas do Microsoft Teams](console.md)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)

[Licenciamento de salas do Microsoft Teams](rooms-licensing.md)
