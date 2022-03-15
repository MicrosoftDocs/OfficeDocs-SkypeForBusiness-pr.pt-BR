---
title: Criando Microsoft Teams contas de recursos para barras de colaboração para Microsoft Teams usando o PowerShell
ms.author: czawideh
author: cazawideh
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leia este tópico para obter informações sobre como implantar barras de colaboração para Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0bbafdfbfc9fb7e9b637216aeb9e5a0d6b470533
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503908"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>Criar uma Microsoft 365 de recursos usando o PowerShell

Leia este tópico para obter informações sobre como criar contas de recursos para barras de colaboração para Microsoft Teams usando o PowerShell.

A maneira mais fácil de criar uma conta de recurso é usando o Centro de administração do Microsoft 365. [Consulte este artigo sobre como fazer isso](resource-account-ui.md).

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>Requisitos

Antes de implantar Salas do Microsoft Teams com Office 365, certifique-se de ter atendido aos requisitos. Para obter mais informações, [consulte Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).

- Se você precisar de recursos PSTN para a barra de colaboração, precisará Sistema de Telefonia licença.

- Suas contas de recurso devem ter Exchange caixas de correio. Como são contas de recurso, nenhuma Exchange é necessária. Recomendamos o uso da licença salas de reunião para contas de recursos.


### <a name="add-a-resource-account"></a>Adicionar uma conta de recurso

1. Conexão para Exchange Online PowerShell. Para obter instruções, [consulte Conexão para Exchange Online PowerShell](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).

2. No Exchange Online PowerShell, crie uma nova caixa de correio de sala ou modifique uma caixa de correio de sala existente.

   - Para criar uma nova caixa de correio de sala, use a seguinte sintaxe:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este exemplo cria uma nova caixa de correio de sala com as seguintes configurações:

     - Nome: Huddle-Room-01

     - Alias: HuddleRoom01

     - Conta: huddleroom01@contoso.onmicrosoft.com

     - Senha da conta: P@$$W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - Para modificar uma caixa de correio de sala existente, use a seguinte sintaxe:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este exemplo habilita a conta para a caixa de correio de sala existente que tem o valor de alias HuddleRoom02 e define a senha como 808P@$$W 0rd. Observe que a conta será HuddleRoom02@contoso.onmicrosoft.com devido ao valor de alias existente.

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).


3. No Exchange Online PowerShell, configure as seguintes configurações na caixa de correio da sala para melhorar a experiência de reunião:

   - AutomateProcessing: AutoAccept (Os organizadores da reunião recebem a decisão de reserva de sala diretamente sem intervenção humana: free = accept; busy = decline.)

   - AddOrganizerToSubject: $false (O organizador da reunião não é adicionado ao assunto da solicitação de reunião.)

   - DeleteComments: $false (Mantenha qualquer texto no corpo da mensagem de solicitações de reunião de entrada.)

   - DeleteSubject: $false (Mantenha o assunto das solicitações de reunião de entrada.)

   - RemovePrivateProperty: $false (Garante que o sinalizador privado enviado pelo organizador da reunião na solicitação de reunião original permaneça conforme especificado.)

   - AddAdditionalResponse: $true (O texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião.)

   - AdditionalResponse: "Esta sala tem uma barra de colaboração para Microsoft Teams!" (O texto adicional a ser acrescentado à solicitação de reunião.)

   Este exemplo configura essas configurações na caixa de correio de sala chamada Huddle-Room-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Conexão ao PowerShell do MS Online para fazer configurações do Active Directory executando o `Connect-MsolService -Credential $cred` cmdlet do powershell.   Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > Azure Active Directory não há suporte para o [PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0). 

5. De definir a senha huddleroom01@contoso.onmicrosoft.com não expirar usando a seguinte sintaxe:

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. A conta de recurso precisa ter uma licença Office 365, preferencialmente a Sala de Reunião SKU. Você também precisa atribuir um local de uso à sua conta de dispositivo— isso determina quais SKUs de licença estão disponíveis para sua conta. Você pode usar `Get-MsolAccountSku` para recuperar uma lista de SKUs disponíveis para seu Office 365 locatário.

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    Você pode atribuir a licença usando Set-MsolUserLicense. 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   Para obter instruções [detalhadas, consulte Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).




[Configurar contas para barras de colaboração para Microsoft Teams usando o PowerShell](resource-account-ps.md)

[Implantar barras de colaboração para Microsoft Teams](collab-bar-deploy.md)

[Barras de colaboração para Microsoft Teams Licenciamento](../rooms/rooms-licensing.md)