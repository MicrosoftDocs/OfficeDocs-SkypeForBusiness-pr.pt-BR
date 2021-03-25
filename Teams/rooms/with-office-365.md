---
title: Implantar salas do Microsoft Teams com o Microsoft 365 ou Office 365
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
ms.openlocfilehash: b5cfaab64840fe72dc989f00ed41760058afc765
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117329"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Implantar salas do Microsoft Teams com o Microsoft 365 ou Office 365

Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams com o Microsoft 365 ou o Office 365, onde o Microsoft Teams ou o Skype for Business e o Exchange estão online.

A maneira mais fácil de configurar contas de usuário é configurá-las usando Windows PowerShell. A Microsoft [ forneceSkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudará a criar novas contas de usuário ou validar contas de recursos existentes que você tem para ajudá-lo a transformá-las em contas de usuário compatíveis do Microsoft Teams Rooms. Se preferir, siga as etapas abaixo para configurar contas que o dispositivo salas do Microsoft Teams usará.

## <a name="requirements"></a>Requisitos

Antes de implantar salas do Microsoft Teams com o Microsoft 365 ou o Office 365, certifique-se de ter atendido aos requisitos. Para obter mais informações, consulte [Requisitos de Salas do Microsoft Teams.](requirements.md)

Para habilitar o Skype for Business, você deve ter o seguinte:

- Skype for Business Online (Plano 2 ou um plano baseado em Empresa) ou superior em seu plano do Microsoft 365 ou Office 365. O plano precisa permitir recursos de conferência discagem.

- Se você precisar de recursos de discagem de uma reunião, precisará de uma licença de Audioconferência e sistema de telefonia.  Se você precisar de recursos de discagem de uma reunião, precisará de uma licença de Audioconferência.

- Os usuários de locatários devem ter caixas de correio do Exchange.

- Sua conta do Microsoft Teams Rooms exige no mínimo uma licença do Skype for Business Online (Plano 2), mas não exige uma licença do Exchange Online. Confira [licenças do Microsoft Teams Rooms](rooms-licensing.md) para obter detalhes.

Para obter detalhes sobre planos do Skype for Business Online, consulte [a Descrição do serviço do Skype for Business Online.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)

### <a name="add-a-device-account"></a>Adicionar uma conta de dispositivo

1. Conecte-se ao PowerShell do Exchange Online. Para obter instruções, [consulte Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. No PowerShell do Exchange Online, crie uma nova caixa de correio de sala ou modifique uma caixa de correio de sala existente. Por padrão, as caixas de correio de sala não têm contas associadas, portanto, você precisará adicionar uma conta ao criar ou modificar uma caixa de correio de sala que permita a autenticação com o Skype Room Systems v2.

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

   Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

3. No PowerShell do Exchange Online, configure as seguintes configurações na caixa de correio da sala para melhorar a experiência de reunião:

   - AutomateProcessing: AutoAccept (Os organizadores da reunião recebem a decisão de reserva de sala diretamente sem intervenção humana: free = accept; busy = decline.)

   - AddOrganizerToSubject: $false (O organizador da reunião não é adicionado ao assunto da solicitação de reunião.)

   - DeleteComments: $false (Mantenha qualquer texto no corpo da mensagem de solicitações de reunião de entrada.)

   - DeleteSubject: $false (Mantenha o assunto das solicitações de reunião de entrada.)

   - RemovePrivateProperty: $false (Garante que o sinalizador privado enviado pelo organizador da reunião na solicitação de reunião original permaneça conforme especificado.)

   - AddAdditionalResponse: $true (O texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião.)

   - AdditionalResponse: "Esta é uma sala de reunião do Skype!" (O texto adicional a ser acrescentado à solicitação de reunião.)

   Este exemplo configura essas configurações na caixa de correio de sala chamada Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Conecte-se ao MS Online PowerShell para fazer configurações do Active Directory executando o `Connect-MsolService -Credential $cred` cmdlet do PowerShell. Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).

   > [!NOTE]
   > [Não há suporte para o PowerShell 2.0 do Azure Active Directory.](/powershell/azure/active-directory/overview?view=azureadps-2.0)

5. Se você não quiser que a senha expire, use a seguinte sintaxe:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   Este exemplo define a senha da conta Rigel1@contoso.onmicrosoft.com nunca expirar.

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
> Se a senha não estiver definida como Nunca Expirar, a conta não entrará mais no dispositivo quando a conta atingir o período de expiração. Em seguida, a senha precisará ser alterada para a conta e também atualizada localmente no dispositivo MTR.

6. A conta de dispositivo precisa ter uma licença válida do Microsoft 365 ou Office 365, ou Exchange e Microsoft Teams ou Skype for Business não funcionarão. Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta). Você pode usar `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar uma lista de SKUs disponíveis para sua organização do Microsoft 365 ou Office 365 da seguinte forma:

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Em seguida, você pode adicionar uma licença usando o `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. Este exemplo adiciona a licença da Sala de Reunião à conta:

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Para obter instruções [detalhadas, consulte Atribuir licenças a contas de usuário com o Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

   Você também pode adicionar recursos do Sistema de Telefonia a essa conta, mas precisa configurá-lo primeiro. Confira [O que é o Sistema de Telefonia?](../what-is-phone-system-in-office-365.md) para obter mais detalhes. Este exemplo adiciona o Plano de Chamada Doméstica e Internacional PSTN:

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. Em seguida, você precisa habilitar a conta de dispositivo com o Skype for Business. Certifique-se de que seu ambiente atenda aos requisitos definidos nos [requisitos de Salas do Microsoft Teams.](requirements.md)

   Inicie uma sessão [de Windows PowerShell remota](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) da seguinte forma (certifique-se de instalar componentes do [PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)do Skype for Business Online ):

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

   Obtenha as informações do RegistradorPool da nova conta de usuário que está sendo configurada, conforme mostrado neste exemplo:

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   Em seguida, habilita a conta salas do Microsoft Teams para o Skype for Business Server executando o seguinte cmdlet:

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