---
title: Implantar o Skype Room Systems versão 2 com o Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leia este tópico para obter informações sobre como implantar sistemas de sala Skype v2 com o Office 365.
ms.openlocfilehash: c623d689f876cfe36c7c8308a7f62526be217ec1
ms.sourcegitcommit: a9556a51f7f970fc05ab0acc9998401db3c1aa57
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2018
ms.locfileid: "22601966"
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a>Implantar o Skype Room Systems versão 2 com o Office 365 
 
Leia este tópico para obter informações sobre como implantar sistemas de sala Skype v2 com o Office 365, onde Skype para negócios e do Exchange são ambos online. 

A maneira mais fácil de configurar as contas de usuário é configurá-los usando o Windows PowerShell remoto. A Microsoft fornece [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudarão a criar novas contas de usuário ou validar contas existentes de recurso, que você ter para ajudá-lo a transformá-los em contas de usuário de v2 Skype sala sistemas compatíveis. Se você preferir, você pode seguir as etapas abaixo para configurar contas para que seu dispositivo v2 de sistemas de sala Skype usará.
  
## <a name="deploy-skype-room-systems-v2-with-office-365"></a>Implantar o Skype Room Systems versão 2 com o Office 365 

Antes de implantar sistemas de sala Skype v2 com o Office 365, certifique-se de que você cumpre os requisitos. Para obter mais informações, consulte [requisitos de v2 de sistemas de sala Skype](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Para habilitar o Skype para a empresa, você deve ter o seguinte:
  
- Skype para negócios Online (plano 2, ou um plano de empresa) ou superior no seu plano do Office 365. O plano deve permitir que os recursos de conferência discada.
    
- Se você precisar de recursos de dial-in de uma reunião, você precisará uma conferência de áudio e a licença do sistema telefônico.  Se você precisar de recursos de discagem de uma reunião, será necessário um locais ou nacionais e internacionais chamar planejar. 
    
- Os usuários de Inquilino devem ter caixas de correio do Exchange.
    
- Sua conta do Skype sala sistemas v2 exigir em um valores mínimos um Skype licença Business Online (plano 2), mas ele não requer uma licença do Exchange Online.

Para obter detalhes sobre Skype para negócios Online planos, consulte o [Skype para negócios Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).

### <a name="add-a-device-account"></a>Adicionar uma conta de dispositivo

1. Inicie uma sessão remota do Windows PowerShell em um PC e se conectar ao Exchange. Verifique se você tem as permissões apropriadas para executar os cmdlets associados. Veja a seguir alguns exemplos de cmdlets que podem ser usados e modificados em seu ambiente.
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential 
   $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. Depois de estabelecer uma sessão, você vai criar uma nova caixa de correio e habilitá-lo como um RoomMailboxAccount ou alterar as configurações de uma caixa de correio de sala existente. Isso permitirá a conta para se autenticar v2 Skype sistemas de sala.
    
  Se você estiver alterando uma caixa de correio do recurso existente:
    
```
Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

  Se você estiver criando uma nova caixa de correio de recursos:
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 
-Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Várias propriedades do Exchange deverão ser definidas na conta de dispositivo para aprimorar a experiência de reunião. Para saber quais propriedades precisam ser definidas, confira a seção Propriedades do Exchange.
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
   -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

   ```

4. Você deverá conectar-se ao Azure Active Directory para aplicar algumas configurações à conta. Para se conectar ao Azure AD, execute o seguinte cmdlet:
    
   ```
   Connect-MsolService -Credential $cred
   ```

5. 	Para a senha não expirar, execute o cmdlet Set-MsolUser com a opção PasswordNeverExpires, como a seguir:   
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```

   Você também pode definir um número de telefone para a sala da seguinte maneira:
    
   ```
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

6. A conta do dispositivo precisa ter uma licença válida do Office 365 ou Exchange e Skype para negócios não funcionará. Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta). Você pode usar o Get-MsolAccountSku para recuperar uma lista de SKUs disponíveis para seu locatário do Office 365, da seguinte maneira:
    
   ```
   Get-MsolAccountSku
   ```

   Em seguida, você pode adicionar uma licença usando o cmdlet Set-MsolUserLicense. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

7. Em seguida, você precisará habilitar a conta de dispositivo com Skype para negócios. Certifique-se de que seu ambiente atende aos requisitos definidos em [sistemas de sala Skype v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).
    
   Iniciar uma sessão do Windows PowerShell remota da seguinte maneira (certifique-se de instalar o Skype para componentes de negócios Online PowerShell):
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   Em seguida, habilite sua conta do Skype sala sistemas v2 para Skype para Business Server executando o seguinte cmdlet:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   Obtenha as informações de RegistrarPool da nova conta de usuário sendo instalação, como mostrado neste exemplo:
    
    ```
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > Novas contas de usuário não podem ser criadas no mesmo pool do registrador contas de usuário existentes no inquilino. O comando acima evitará erros na configuração de conta devido a essa situação. 
  
Depois de concluir as etapas anteriores para habilitar sua conta v2 de sistemas de sala Skype no Skype para Business Online, você precisa atribuir uma licença a dispositivo de v2 Skype sistemas de sala. Usando o portal administrativo do Office 365, atribua a qualquer um Skype para Business Online (plano 2) ou uma Skype licença Business Online (plano 3) para o dispositivo.
  
### <a name="assign-a-license-to-your-account"></a>Atribuir uma licença à conta

1. Logon como um administrador de locatário, abra o Portal do Office 365 administrativas e clique no aplicativo Administração.
    
2. Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.
    
3. Selecione a conta do Skype sala sistemas v2 e, em seguida, clique ou toque no ícone de caneta, o que significa editar.
    
4. Clique na opção **Licenças**.
    
5. Na seção **Atribuir licenças** , você precisa selecionar o Skype para Business Online (plano 2) ou Skype para Business Online (plano 3), dependendo do seu licenciamento e o que você decidiu em termos de necessidade de Enterprise Voice. Você terá que usar uma licença de plano 3 se você quiser usar o PBX de nuvem em sistemas de sala Skype v2. O CloudPBX será necessário como requisito mínimo para habilitar a conectividade de voz. Em seguida, configure as chamadas PSTN ou de voz híbridas com base no método de conectividade PSTN.
    
6. Clique em **Salvar** para concluir a tarefa.
    
## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>Exemplo: Conta de sala de instalação no Exchange Online e Skype para negócios Online

```
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com
 -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true
 -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
 
Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept 
-AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
$false -DeleteSubject $false -RemovePrivateProperty $false
 
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true 
-AdditionalResponse "This is a Rigel room!"
 
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
 
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
 
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress

```

> [!NOTE]
> Assim, você adiciona CloudPBX e PSTNCallingDomesticAndInternational. Além disso, será necessário usar a Interface do administrador para atribuir um número de telefone. 
  
## <a name="validate"></a>Validar

Para validação, você deve ser capaz de usar qualquer Skype para o cliente de negócios para entrar com a conta que você criou.


## <a name="see-also"></a>Consulte também

[Configurar contas para sistemas de sala Skype v2](room-systems-v2-configure-accounts.md)

[Planejar o Skype Room Systems versão 2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Implantar o Skype Room Systems versão 2](room-systems-v2.md)
  
[Configurar o console do Skype Room Systems versão 2](console.md)
  
[Gerenciar o Skype Room Systems versão 2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

