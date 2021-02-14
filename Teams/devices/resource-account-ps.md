---
title: Criando Contas de Recursos do Microsoft Teams para barras de colaboração do Microsoft Teams usando o PowerShell
ms.author: mitressl
author: flinchbot
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leia este tópico para obter informações sobre como implantar barras de colaboração para o Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268009"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>Criar uma conta de recurso do Microsoft 365 usando o PowerShell

Leia este tópico para obter informações sobre como criar contas de recursos para barras de colaboração do Microsoft Teams usando o PowerShell.

A maneira mais fácil de criar uma conta de recurso é usando o Centro de administração do Microsoft 365. [Confira este artigo sobre como fazer isso.](resource-account-ui.md)

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>Requisitos

Antes de implantar as Salas do Microsoft Teams com o Office 365, certifique-se de que você atendeu aos requisitos. Para obter mais informações, consulte [Implantar barras de colaboração para o Microsoft Teams.](collab-bar-deploy.md)

- Se precisar de recursos PSTN para a barra de colaboração, você precisará de licença do Sistema de Telefonia.

- Suas contas de recursos devem ter caixas de correio do Exchange. Como são contas de recursos, nenhuma licença do Exchange é necessária. Recomendamos o uso da licença de Salas de Reunião para contas de recursos.


### <a name="add-a-resource-account"></a>Adicionar uma conta de recurso

1. Conecte-se ao PowerShell do Exchange Online. Para obter instruções, consulte [Conectar-se ao PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)

2. No PowerShell do Exchange Online, crie uma nova caixa de correio de sala ou modifique uma caixa de correio de sala existente.

   - Para criar uma nova caixa de correio de sala, use a seguinte sintaxe:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este exemplo cria uma nova caixa de correio de sala com as seguintes configurações:

     - Nome: Desaconsupo-sala-01

     - Alias: Alias: AliasRoom01

     - Conta: huddleroom01@contoso.onmicrosoft.com

     - Senha da conta: P@$$W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - Para modificar uma caixa de correio de sala existente, use a seguinte sintaxe:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este exemplo habilita a conta para a caixa de correio de sala existente que tem o valor de alias Desarmado02 e define a senha como 808P@$$W 0rd. Observe que a conta será HuddleRoom02@contoso.onmicrosoft.com devido ao valor de alias existente.

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [Caixa de](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) Correio Nova e [Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)


3. No PowerShell do Exchange Online, configure as seguintes configurações na caixa de correio da sala para melhorar a experiência da reunião:

   - AutomateProcessing: AutoAccept (organizadores da reunião recebem a decisão de reserva da sala diretamente sem intervenção humana: gratuito = aceitar; ocupado = recusar.)

   - AddOrganizerToSubject: $false (O organizador da reunião não é adicionado ao assunto da solicitação de reunião.)

   - DeleteComments: $false (Mantenha qualquer texto no corpo da mensagem das solicitações de reunião recebidas.)

   - DeleteSubject: $false (Mantenha o assunto das solicitações de reunião recebidas.)

   - RemovePrivateProperty: $false (Garante o sinalizador particular que foi enviado pelo organizador da reunião na solicitação de reunião original permanece como especificado.)

   - AddAdditionalResponse: $true (O texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião.)

   - AdicionalResponse: "Esta sala tem uma barra de colaboração para o Microsoft Teams!" (O texto adicional a ser acrescentado à solicitação de reunião.)

   Este exemplo configura essas configurações na caixa de correio da sala chamada Mailbox-Room-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [Set-CalendarProcessing.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. Conecte-se ao PowerShell do MS Online para criar configurações do Active Directory executando o `Connect-MsolService -Credential $cred` cmdlet do PowerShell.   Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [O PowerShell 2.0 do Azure Active Directory](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) não tem suporte. 

5. De definir a senha huddleroom01@contoso.onmicrosoft.com não expirar usando a seguinte sintaxe:

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. A conta de recurso precisa ter uma licença válida do Office 365, de preferência a SKU da Sala de Reunião. Você também precisa atribuir um local de uso à sua conta de dispositivo— isso determina quais SKUs de licença estão disponíveis para sua conta. Você pode usar `Get-MsolAccountSku` para recuperar uma lista de SKUs disponíveis para seu locatário do Office 365.

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    Você pode atribuir a licença usando Set-MsolUserLicense. 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   Para obter instruções [detalhadas, consulte Atribuir licenças a contas de usuário com o PowerShell do Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)




[Configurar contas para barras de colaboração do Microsoft Teams usando o PowerShell](resource-account-ps.md)

[Implantar barras de colaboração para o Microsoft Teams](collab-bar-deploy.md)

[Barras de colaboração para licenciamento do Microsoft Teams](../rooms/rooms-licensing.md)


