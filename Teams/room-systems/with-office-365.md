---
title: Implantar salas de equipes da Microsoft com o Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leia este tópico para obter informações sobre como implantar as salas de equipes da Microsoft com o Office 365.
ms.openlocfilehash: 462f5a6727a3c67e221b0d7ac019849ed3eb6f52
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362580"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>Implantar salas de equipes da Microsoft com o Office 365

Leia este tópico para obter informações sobre como implantar as salas de equipes da Microsoft com o Office 365, onde Teams da Microsoft ou Skype para negócios e do Exchange são ambos online.

A maneira mais fácil de configurar as contas de usuário é configurá-los usando o Windows PowerShell remoto. A Microsoft fornece [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudarão a criar novas contas de usuário ou validar contas existentes de recurso, que você ter para ajudá-lo a transformá-los em contas de usuário de salas de equipes da Microsoft compatíveis. Se você preferir, você pode seguir as etapas abaixo para configurar contas para que seu dispositivo de salas de equipes da Microsoft usará.

## <a name="requirements"></a>Requisitos

Antes de implantar salas de equipes da Microsoft com o Office 365, certifique-se de que você cumpre os requisitos. Para obter mais informações, consulte [requisitos de salas de equipes da Microsoft](requirements.md).

Para habilitar o Skype para a empresa, você deve ter o seguinte:

- Skype para negócios Online (plano 2, ou um plano de empresa) ou superior no seu plano do Office 365. O plano deve permitir que os recursos de conferência discada.

- Se você precisar de recursos de dial-in de uma reunião, você precisará uma conferência de áudio e a licença do sistema telefônico.  Se você precisar de recursos de discagem de uma reunião, será necessário um locais ou nacionais e internacionais chamar planejar.

- Os usuários de Inquilino devem ter caixas de correio do Exchange.

- Sua conta da Microsoft equipes salas exigir no mínimo um Skype licença Business Online (plano 2), mas ele não requer uma licença do Exchange Online. Para obter detalhes, consulte [Licenciamento de salas de equipes da Microsoft](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) .

Para obter detalhes sobre Skype para negócios Online planos, consulte o [Skype para negócios Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).

### <a name="add-a-device-account"></a>Adicionar uma conta de dispositivo

1. Conecte-se para o Exchange Online PowerShell. Para obter instruções, consulte [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

2. No PowerShell do Exchange Online, crie uma nova caixa de correio de sala ou modificar uma caixa de correio de sala existente. Por padrão, caixas de correio de sala não têm contas associadas, portanto, você precisará adicionar uma conta ao criar ou modificar uma caixa de correio de sala que permite que ele autenticar com sistemas de sala Skype v2.

   - Para criar uma nova caixa de correio de sala, use a seguinte sintaxe:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este exemplo cria uma nova caixa de correio de sala com as seguintes configurações:

     - Nome: Project-Rigel-01

     - Alias: ProjectRigel01

     - Conta: ProjectRigel01@contoso.onmicrosoft.com

     - Senha da conta: P@$$W0rd5959

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Para modificar uma caixa de correio de sala existente, use a seguinte sintaxe:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este exemplo habilita a conta para a caixa de correio de sala existente que tem o valor de alias ProjectRigel02 e define a senha como 9898P@$$W0rd. Observe que a conta seja ProjectRigel02@contoso.onmicrosoft.com devido ao valor existente do alias.

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Para detalhadas sobre sintaxe e informações de parâmetro, consulte [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).


3. No PowerShell do Exchange Online, defina as seguintes configurações na caixa de correio de sala para melhorar a experiência de reunião:

   - AutomateProcessing: AutoAccept (organizadores de reunião recebem a decisão de reserva de sala diretamente, sem intervenção humana: livre = aceitar; ocupado = recusar.)

   - AddOrganizerToSubject: $false (o organizador da reunião não é adicionado ao assunto da solicitação de reunião.)

   - DeleteComments: $false (mantenha qualquer texto no corpo da mensagem de entrada solicitações de reunião).

   - DeleteSubject: $false (manter o assunto de solicitações de reunião recebidas).

   - RemovePrivateProperty: $false (assegura o sinalizador particular que foi enviado pelo organizador da reunião na reunião original permanece conforme especificado de solicitação).

   - AddAdditionalResponse: $true (o texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião).

   - AdditionalResponse: "Esta é uma sala de reunião Skype!" (O texto adicional para adicionar à solicitação de reunião).

   Este exemplo configura essas configurações na caixa de correio de sala chamada Project-Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Para detalhadas sobre sintaxe e informações de parâmetro, consulte [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Conectar-se ao MS Online PowerShell para fazer configurações do Active Directory, executando o `Connect-MsolService -Credential $cred` cmdlet do powershell.   Para obter detalhes sobre o Active Directory, consulte o [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0). <!-- or [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) for the new module -->  
    1. Se você não quiser que a senha para expirar, use a seguinte sintaxe:

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   Este exemplo define a senha para a conta ProjectRigel01@contoso.onmicrosoft.com para nunca expirar.

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

6. A conta do dispositivo precisa ter uma licença válida do Office 365 ou Exchange e Microsoft Teams ou Skype para negócios não funcionará. Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta). Você pode usar`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar uma lista de SKUs disponíveis para seu locatário do Office 365, da seguinte maneira:

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

   Para obter instruções detalhadas, consulte [Atribuir licenças às contas de usuário com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

7. Em seguida, você precisará habilitar a conta de dispositivo com Skype para negócios. Certifique-se de que seu ambiente atende aos requisitos definidos nas [salas de equipes da Microsoft requisitos](requirements.md).

   Inicie uma [sessão do Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) de remota da seguinte maneira (certifique-se de [instalar o Skype para componentes de negócios Online PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   Em seguida, habilite sua conta de salas de equipes da Microsoft para Skype para Business Server executando o seguinte cmdlet:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   Obtenha as informações de RegistrarPool da nova conta de usuário sendo instalação, como mostrado neste exemplo:

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > Novas contas de usuário não podem ser criadas no mesmo pool do registrador contas de usuário existentes no inquilino. O comando acima evitará erros na configuração de conta devido a essa situação.

Depois de concluir as etapas anteriores para habilitar a sua conta de salas de equipes da Microsoft em Microsoft Teams ou Skype para Business Online, você precisa atribuir uma licença a dispositivo de salas de equipes da Microsoft. Usando o portal administrativo do Office 365, atribua a qualquer um Skype para Business Online (plano 2) ou uma Skype licença Business Online (plano 3) para o dispositivo.

### <a name="assign-a-license-to-your-account"></a>Atribuir uma licença à conta

1. Logon como um administrador de locatário, abra o Portal do Office 365 administrativas e clique no aplicativo Administração.

2. Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.

3. Selecione a conta de salas de equipes da Microsoft e, em seguida, clique ou toque no ícone de caneta, o que significa editar.

4. Clique na opção **Licenças**.

5. Na seção **Atribuir licenças** , você precisa selecionar o Skype para Business Online (plano 2) ou Skype para Business Online (plano 3), dependendo do seu licenciamento e o que você decidiu em termos de necessidade de Enterprise Voice. Você terá que usar uma licença de plano 3 se você quiser usar o PBX de nuvem em salas de equipes da Microsoft. O CloudPBX será necessário como requisito mínimo para habilitar a conectividade de voz. Em seguida, configure as chamadas PSTN ou de voz híbridas com base no método de conectividade PSTN. Consulte [licenças de salas de equipes da Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) para obter mais detalhes.

6. Clique em **Salvar** para concluir a tarefa.

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>Exemplo: Conta de sala de instalação no Exchange Online e Skype para negócios Online

Comandos do PowerShell do Exchange Online:

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

Comandos do Azure Active Directory PowerShell:

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

Skype para o comando do PowerShell de negócios:

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> Assim, você adiciona CloudPBX e PSTNCallingDomesticAndInternational. Além disso, você precisará usar a interface de administração para atribuir um número de telefone.

## <a name="validate"></a>Validar

Para validação, você deve ser capaz de usar qualquer Skype para o cliente de negócios para entrar com a conta que você criou.

## <a name="see-also"></a>Confira também

[Configurar contas para salas de equipes da Microsoft](room-systems-v2-configure-accounts.md)

[Planejar para salas de equipes da Microsoft](skype-room-systems-v2-0.md)

[Implantar salas de equipes da Microsoft](room-systems-v2.md)

[Configurar um console de salas de equipes da Microsoft](console.md)

[Gerenciar Salas do Microsoft Teams](skype-room-systems-v2.md)

[Licenciamento de salas de equipes da Microsoft](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
