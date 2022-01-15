---
title: Implantar Salas do Microsoft Teams com o Office 365
ms.author: v-lanac
author: lanachin
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
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leia este tópico para obter informações sobre como implantar Salas do Microsoft Teams com Office 365.
ms.openlocfilehash: d4c66fb863c5c41a717808ddca43002752510fb5
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2022
ms.locfileid: "62056021"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>Implantar Salas do Microsoft Teams com o Office 365

Leia este tópico para obter informações sobre como implantar Salas do Microsoft Teams com Office 365.

## <a name="requirements"></a>Requisitos

Antes de implantar Salas do Microsoft Teams com Office 365, certifique-se de ter atendido aos requisitos. Para obter mais informações, [consulte Salas do Microsoft Teams requisitos](requirements.md).

### <a name="add-a-resource-account"></a>Adicionar uma conta de recurso

1. Conexão para Exchange Online PowerShell. Para obter instruções, [consulte Conexão Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

2. No Exchange Online PowerShell, crie uma nova caixa de correio de sala ou modifique uma caixa de correio de sala existente. Por padrão, as caixas de correio de sala não têm contas associadas. Você precisará adicionar uma conta ao criar ou modificar uma caixa de correio de sala que permita a autenticação.

   - Para criar uma nova caixa de correio de sala, use a seguinte sintaxe:

     ``` PowerShell
     New-Mailbox -Name '<Unique Name>' -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este exemplo cria uma nova caixa de correio de sala com as seguintes configurações:

     - Nome: Sala de Conferência 01

     - Alias: ConferenceRoom01

     - Conta: ConferenceRoom01@contoso.com

     - Senha da conta: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name 'Conference Room 01' -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Para modificar uma caixa de correio de sala existente, use a seguinte sintaxe:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este exemplo habilita a conta para a caixa de correio de sala existente que tem o valor de alias ConferenceRoom02 e define a senha como 9898P@$$W 0rd.

     ``` PowerShell
     Set-Mailbox -Identity 'ConferenceRoom02' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).


3. No Exchange Online PowerShell, configure as seguintes configurações na caixa de correio da sala para melhorar a experiência de reunião:

   - AutomateProcessing: AutoAccept (A caixa de correio faz automaticamente uma decisão de reserva de sala diretamente sem intervenção humana.)

   - AddOrganizerToSubject: $false (O organizador da reunião não é adicionado ao assunto da solicitação de reunião.)

   - DeleteComments: $false (Mantenha qualquer texto no corpo da mensagem de solicitações de reunião de entrada.)

   - DeleteSubject: $false (Mantenha o assunto das solicitações de reunião de entrada.)

   - RemovePrivateProperty: $false (Garante que o sinalizador privado enviado pelo organizador da reunião na solicitação de reunião original permaneça conforme especificado.)

   - AddAdditionalResponse: $true (O texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião.)

   - AdditionalResponse: "Esta é uma Microsoft Teams de reunião!" (O texto adicional a ser acrescentado à solicitação de reunião.)

   Este exemplo configura essas configurações na caixa de correio de sala chamada Project-Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity 'ConferenceRoom01' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse 'This is a Microsoft Teams meeting room!'
   ```

   Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).
   
4. Conexão para o MS Online PowerShell definir valores do Active Directory executando o cmdlet 'Conexão-MsolService -Credential $cred'. Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > Azure Active Directory não há suporte para o [PowerShell 2.0.](/powershell/azure/active-directory/overview?view=azureadps-2.0) 

5. É fortemente incentivado desabilitar a expiração de senha em Salas do Teams contas. Veja a seguir um exemplo de como desabilitar a expiração de senha para a conta ConferenceRoom01:

    ``` PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```


1. A conta de recurso precisa ter uma licença Office 365 para se conectar ao Microsoft Teams. Você também precisa atribuir um local de uso à sua conta de dispositivo— isso determina quais SKUs de licença estão disponíveis para sua conta. Você pode usar `Get-MsolAccountSku` para recuperar uma lista de SKUs disponíveis para seu Office 365 locatário. Você pode adicionar uma licença usando `Set-MsolUserLicense` o cmdlet.

   Este exemplo atribui a Sala de Reunião a um usuário com base nos EUA.

  ``` PowerShell
   Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
  ``` 


   Para obter instruções [detalhadas, consulte Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).


## <a name="validate"></a>Validar

Para validação, você deve ser capaz de usar qualquer Microsoft Teams cliente para entrar na conta criada.

## <a name="see-also"></a>Confira também
[Atualizar caixas de correio de sala com metadados adicionais para fornece uma melhor experiência de pesquisa e sugestão de sala](/powershell/module/exchange/set-place)

[Configurar contas para Salas do Microsoft Teams](rooms-configure-accounts.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)

[Implantar Salas do Microsoft Teams](rooms-deploy.md)

[Configurar um console de Salas do Microsoft Teams](console.md)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)

[Salas do Microsoft Teams licenciamento](rooms-licensing.md)
