---
title: Implantar Salas do Microsoft Teams com Microsoft 365 ou Office 365
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leia este tópico para obter informações sobre como implantar o Salas do Microsoft Teams com Microsoft 365 ou Office 365, onde Teams ou Skype for Business e Exchange estão online.
ms.openlocfilehash: 948287d8a5711e1643605d147d1b25b28d764a42
ms.sourcegitcommit: 95c7603b47fcd5fba8f762a4590693ee9f026328
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2021
ms.locfileid: "61153294"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Implantar Salas do Microsoft Teams com Microsoft 365 ou Office 365

Leia este tópico para obter informações sobre como implantar o Salas do Microsoft Teams com Microsoft 365 ou Office 365, onde Microsoft Teams ou Skype for Business e Exchange estão online.

A maneira mais fácil de configurar contas de usuário é configurá-las usando Windows PowerShell. A Microsoft [forneceSkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudará a criar novas contas de usuário ou validar contas de recursos existentes que você tem para ajudá-lo a transformá-las em contas de usuário compatíveis Salas do Microsoft Teams usuário. Se preferir, siga as etapas abaixo para configurar contas que seu Salas do Microsoft Teams dispositivo usará.

## <a name="requirements"></a>Requisitos

Antes de implantar Salas do Microsoft Teams com Microsoft 365 ou Office 365, certifique-se de ter atendido aos requisitos. Para obter mais informações, [consulte Salas do Microsoft Teams requisitos](requirements.md).

Para habilitar Skype for Business, você deve ter o seguinte:

- Skype for Business Online (Plano 2, ou um plano Enterprise baseado em Enterprise) ou superior em seu Microsoft 365 ou Office 365 plano. O plano precisa permitir recursos de conferência discagem.

- Se você precisar de recursos de discagem de uma reunião, precisará de uma audioconferência e Sistema de Telefonia licença.  Se você precisar de recursos de discagem de uma reunião, precisará de uma licença de Audioconferência.

- Os usuários do locatário devem ter Exchange caixas de correio.

- Sua Salas do Microsoft Teams de usuário exige, no mínimo, uma licença Skype for Business Online (Plano 2), mas não exige uma licença Exchange Online. Consulte [Salas do Microsoft Teams para](rooms-licensing.md) obter detalhes.

Para obter detalhes sobre Skype for Business Online, consulte Skype for Business [Descrição do Serviço Online.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)

### <a name="add-a-device-account"></a>Adicionar uma conta de dispositivo

1. Conexão para Exchange Online PowerShell. Para obter instruções, [consulte Conexão Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. No Exchange Online PowerShell, crie uma nova caixa de correio de sala ou modifique uma caixa de correio de sala existente. Por padrão, as caixas de correio de sala não têm contas associadas, portanto, você precisará adicionar uma conta ao criar ou modificar uma caixa de correio de sala que permita a autenticação com o Skype Room Systems v2.

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

3. No Exchange Online PowerShell, configure as seguintes configurações na caixa de correio da sala para melhorar a experiência de reunião:

   - AutomateProcessing: AutoAccept (Os organizadores da reunião recebem a decisão de reserva de sala diretamente sem intervenção humana: free = accept; busy = decline.)

   - AddOrganizerToSubject: $false (O organizador da reunião não é adicionado ao assunto da solicitação de reunião.)

   - DeleteComments: $false (Mantenha qualquer texto no corpo da mensagem de solicitações de reunião de entrada.)

   - DeleteSubject: $false (Mantenha o assunto das solicitações de reunião de entrada.)

   - RemovePrivateProperty: $false (Garante que o sinalizador privado enviado pelo organizador da reunião na solicitação de reunião original permaneça conforme especificado.)

   - AddAdditionalResponse: $true (O texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião.)

   - AdditionalResponse: "Esta é uma Microsoft Teams de reunião!" (O texto adicional a ser acrescentado à solicitação de reunião.)

   Este exemplo configura essas configurações na caixa de correio de sala chamada Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Conexão o PowerShell do MS Online para fazer configurações do Active Directory executando o `Connect-MsolService -Credential $cred` Cmdlet do PowerShell. Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).

   > [!NOTE]
   > Azure Active Directory não há suporte para o [PowerShell 2.0.](/powershell/azure/active-directory/overview?view=azureadps-2.0)

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

6. A conta de dispositivo precisa ter uma licença Microsoft 365 ou Office 365, ou Exchange e Microsoft Teams ou Skype for Business não funcionarão. Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta). Você pode usar `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar uma lista de SKUs disponíveis para sua Microsoft 365 ou Office 365 da seguinte forma:

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Em seguida, você pode adicionar uma licença usando o `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. Este exemplo adiciona a Sala de Reunião de usuário à conta:

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Para obter instruções [detalhadas, consulte Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

   Você também pode adicionar Sistema de Telefonia recursos a essa conta, mas é preciso configurá-la primeiro. Confira [O que Sistema de Telefonia para](../what-is-phone-system-in-office-365.md) obter mais detalhes. Este exemplo adiciona o Plano de Chamada Doméstica e Internacional PSTN:

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

    > [!NOTE]
    > Se você estiver configurando Salas do Teams apenas participar Microsoft Teams reuniões, não deverá prosseguir com a etapa a seguir. O seguinte só será necessário se você também estiver habilitando o suporte para Skype for Business local.

7. Para habilitar a conta de dispositivo com Skype for Business local, certifique-se de que seu ambiente atenda aos requisitos definidos em Salas do Microsoft Teams [requisitos](requirements.md).

   Inicie uma sessão [Windows PowerShell remota](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) da seguinte forma (certifique-se de instalar Skype for Business [componentes do PowerShell Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):

   > [!NOTE]
   > O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.
   >
   > Se você estiver usando a versão pública mais [recente Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o conector Skype for Business Online.

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

   Em seguida, habilita sua Salas do Microsoft Teams de Skype for Business Server executando o seguinte cmdlet:

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > Novas contas de usuário podem não ser criadas no mesmo pool de registradores que as contas de usuário existentes no locatário. O comando acima evitará erros na configuração da conta devido a essa situação.

## <a name="validate"></a>Validar

Para validação, você deve ser capaz de usar qualquer Skype for Business cliente para entrar na conta criada.

## <a name="see-also"></a>Confira também

[Configurar contas para Salas do Microsoft Teams](rooms-configure-accounts.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)

[Implantar Salas do Microsoft Teams](rooms-deploy.md)

[Configurar um console de Salas do Microsoft Teams](console.md)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)

[Salas do Microsoft Teams licenciamento](rooms-licensing.md)
