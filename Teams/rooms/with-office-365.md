---
title: Implantar salas do Microsoft Teams com o Microsoft 365 ou o Office 365
ms.author: v-cichur
author: cichur
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
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams com o Microsoft 365 ou o Office 365, onde o Teams ou o Skype for Business e o Exchange estão online.
ms.openlocfilehash: 4ec54763379e4a13a69eb3e08019924708873faf
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196205"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Implantar salas do Microsoft Teams com o Microsoft 365 ou o Office 365

Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams com o Microsoft 365 ou o Office 365, onde o Microsoft Teams ou o Skype for Business e o Exchange estão online.

A maneira mais fácil de configurar contas de usuário é configurá-las usando o Windows PowerShell remoto. A Microsoft [ forneceSkypeRoomProvisioningScript.ps1, ](https://go.microsoft.com/fwlink/?linkid=870105)um script que ajudará a criar novas contas de usuário ou validar contas de recursos existentes que você tem para ajudá-lo a transformá-las em contas de usuário compatíveis com Salas do Microsoft Teams. Se preferir, siga as etapas abaixo para configurar as contas que seu dispositivo Salas do Microsoft Teams usará.

## <a name="requirements"></a>Requisitos

Antes de implantar as Salas do Microsoft Teams com o Microsoft 365 ou o Office 365, certifique-se de que você atendeu aos requisitos. Para obter mais informações, consulte [os requisitos de Salas do Microsoft Teams.](requirements.md)

Para habilitar o Skype for Business, você deve ter o seguinte:

- Skype for Business Online (Plano 2 ou um plano baseado em empresas) ou superior em seu plano Microsoft 365 ou Office 365. O plano precisa permitir recursos de conferência discado.

- Se precisar de recursos de discagem de uma reunião, você precisará de uma licença de Audioconferência e sistema de telefonia.  Se precisar de recursos de discagem de uma reunião, você precisará de uma licença de Audioconferência.

- Os usuários do locatário devem ter caixas de correio do Exchange.

- Sua conta do Microsoft Teams Rooms requer no mínimo uma licença do Skype for Business Online (Plano 2), mas não requer uma licença do Exchange Online. Confira [as licenças de Salas do Microsoft Teams](rooms-licensing.md) para obter detalhes.

Para obter detalhes sobre os planos do Skype for Business Online, consulte a Descrição [do serviço Skype for Business Online.](https://technet.microsoft.com/library/jj822172.aspx)

### <a name="add-a-device-account"></a>Adicionar uma conta de dispositivo

1. Conecte-se ao PowerShell do Exchange Online. Para obter instruções, [consulte Conectar-se ao PowerShell do Exchange Online.](https://go.microsoft.com/fwlink/p/?linkid=396554)

2. No PowerShell do Exchange Online, crie uma nova caixa de correio de sala ou modifique uma caixa de correio de sala existente. Por padrão, as caixas de correio de sala não têm contas associadas, portanto, você precisará adicionar uma conta ao criar ou modificar uma caixa de correio de sala que permita autenticar com o Skype Room Systems v2.

   - Para criar uma nova caixa de correio de sala, use a seguinte sintaxe:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este exemplo cria uma nova caixa de correio de sala com as seguintes configurações:

     - Nome: Rigel-01

     - Alias: Rigel1

     - Conta: Rigel1@contoso.onmicrosoft.com

     - Senha da conta: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Para modificar uma caixa de correio de sala existente, use a seguinte sintaxe:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este exemplo habilita a conta para a caixa de correio de sala existente que tem o valor de alias Rigel2 e define a senha como 9898P@$$W 0rd. Observe que a conta será Rigel2@contoso.onmicrosoft.com devido ao valor de alias existente.

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [Caixa de Correio Nova](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)

3. No PowerShell do Exchange Online, configure as seguintes configurações na caixa de correio da sala para melhorar a experiência da reunião:

   - AutomateProcessing: AutoAccept (organizadores da reunião recebem a decisão de reserva da sala diretamente sem intervenção humana: gratuito = aceitar; ocupado = recusar.)

   - AddOrganizerToSubject: $false (O organizador da reunião não é adicionado ao assunto da solicitação de reunião.)

   - DeleteComments: $false (Mantenha qualquer texto no corpo da mensagem de solicitações de reunião recebidas.)

   - DeleteSubject: $false (Mantenha o assunto das solicitações de reunião recebidas.)

   - RemovePrivateProperty: $false (Garante o sinalizador particular que foi enviado pelo organizador da reunião na solicitação de reunião original permanece como especificado.)

   - AddAdditionalResponse: $true (O texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião.)

   - AdicionalResponse: "Esta é uma sala de reunião do Skype!" (O texto adicional a ser acrescentado à solicitação de reunião.)

   Este exemplo configura essas configurações na caixa de correio da sala chamada Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [Set-CalendarProcessing.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. Conecte-se ao PowerShell do MS Online para fazer configurações do Active Directory executando o `Connect-MsolService -Credential $cred` cmdlet do PowerShell. Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Não há suporte para o PowerShell 2.0 do Azure Active Directory.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)

5. Se você não quiser que a senha expire, use a seguinte sintaxe:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   Este exemplo define a senha para a conta Rigel1@contoso.onmicrosoft.com nunca expirar.

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   Você também pode definir um número de telefone para a conta executando o seguinte comando:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

> [!NOTE]
> Se a senha não estiver definida como Nunca Expirar, a conta não entrará mais no dispositivo quando a conta atingir o período de vencimento. Em seguida, a senha precisará ser alterada para a conta e também atualizada localmente no dispositivo MTR.

6. A conta do dispositivo precisa ter uma licença válida do Microsoft 365 ou do Office 365, ou o Exchange e o Microsoft Teams ou o Skype for Business não funcionarão. Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta). Você pode usar `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar uma lista de SKUs disponíveis para sua organização do Microsoft 365 ou do Office 365 da seguinte forma:

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Em seguida, você pode adicionar uma licença usando o `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> Cmdlet. Este exemplo adiciona a licença da Sala de Reunião à conta:

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Para obter instruções [detalhadas, consulte Atribuir licenças a contas de usuário com o PowerShell do Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

   Você também pode adicionar recursos do Sistema de Telefonia a essa conta, mas precisa configurá-lo primeiro. Veja [o que é o Sistema de Telefonia?](../what-is-phone-system-in-office-365.md) Para obter mais detalhes. Este exemplo adiciona o Plano de Chamada PSTN Doméstico e Internacional:

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. Em seguida, você precisa habilitar a conta do dispositivo com o Skype for Business. Certifique-se de que seu ambiente atenda aos requisitos definidos nos [requisitos de Salas do Microsoft Teams.](requirements.md)

   Inicie uma sessão remota [do Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) da seguinte forma (instale os componentes do PowerShell do [Skype for Business Online):](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)

> [!NOTE]
> No momento, o Skype for Business Online Connector faz parte do módulo mais recente do PowerShell do Teams.
>
> Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Skype for Business Online Connector.

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess = New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   Obtenha as informações do RegistradorPool da nova conta de usuário que está sendo configurada, conforme mostrado neste exemplo:

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   Em seguida, habilita sua conta do Microsoft Teams Rooms para o Skype for Business Server executando o seguinte cmdlet:

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > Novas contas de usuário podem não ser criadas no mesmo pool de registradores que as contas de usuário existentes no locatário. O comando acima evitará erros na configuração da conta devido a essa situação.

## <a name="validate"></a>Validar

Para validação, você deve ser capaz de usar qualquer cliente do Skype for Business para entrar na conta criada.

## <a name="see-also"></a>Confira também

[Configurar contas para salas do Microsoft Teams](rooms-configure-accounts.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)

[Implantar Salas do Microsoft Teams](rooms-deploy.md)

[Configurar um console de Salas do Microsoft Teams](console.md)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)

[Licenciamento de Salas do Microsoft Teams](rooms-licensing.md)
