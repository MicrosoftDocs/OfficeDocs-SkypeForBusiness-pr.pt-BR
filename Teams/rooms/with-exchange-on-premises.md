---
title: Implantar Salas do Microsoft Teams com Exchange local (Híbrido)
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Leia este tópico para obter informações sobre como implantar Salas do Microsoft Teams em um ambiente híbrido com Exchange local.
ms.openlocfilehash: ea05ef6b6bf6e13ee907d84d1d48200c0cea5a09
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767224"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises-hybrid"></a>Implantar Salas do Microsoft Teams com Exchange local (Híbrido)

Leia este tópico para obter informações sobre como implantar Salas do Microsoft Teams em um ambiente híbrido com Exchange local e Microsoft Teams.
  
Se sua organização tiver uma combinação de serviços, com alguns locais hospedados e alguns hospedados online, sua configuração dependerá de onde cada serviço está hospedado. Este tópico aborda implantações híbridas para Salas do Microsoft Teams com Exchange hospedados no local. Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas. O processo a seguir funcionará para várias configurações. Se o processo não estiver correto para sua instalação, recomendamos que você use o Windows PowerShell para obter o mesmo resultado final como documentado aqui e para outras opções de implantação.
  
## <a name="requirements"></a>Requisitos

Antes de implantar Salas do Microsoft Teams com Exchange local, certifique-se de ter atendido aos requisitos. Para obter mais informações, [consulte Salas do Microsoft Teams requisitos](requirements.md).

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Habilitar a caixa de correio remota e as propriedades definidas

1. [Abra o Shell de Gerenciamento Exchange ou](/powershell/exchange/exchange-server/open-the-exchange-management-shell) conecte-se ao seu servidor Exchange usando o [PowerShell remoto.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. No Exchange PowerShell, crie uma nova caixa de correio de sala ou modifique uma caixa de correio de sala existente. Por padrão, as caixas de correio de sala não têm contas associadas, portanto, você precisará adicionar uma conta ao criar ou modificar uma caixa de correio de sala que permita a autenticação com Microsoft Teams.

   - Para criar uma nova caixa de correio de sala, use a seguinte sintaxe:

     ``` PowerShell
     New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```
     
     Este exemplo cria uma nova caixa de correio de sala com as seguintes configurações:

     - Conta: ConferenceRoom01@contoso.com
  
     - Nome: ConferenceRoom01

     - Alias: ConferenceRoom01

     - Senha da conta: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Para modificar uma caixa de correio de sala existente, use a seguinte sintaxe:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     Este exemplo habilita a conta para a caixa de correio de sala existente que tem o valor de alias ConferenceRoom02 e define a senha como 9898P@$$W 0rd. Observe que a conta será ConferenceRoom02@contoso.com devido ao valor de alias existente.

     ``` PowerShell
     Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

3. No Exchange PowerShell, configure as seguintes configurações na caixa de correio da sala para melhorar a experiência de reunião:

   - AutomateProcessing: AutoAccept (Os organizadores da reunião recebem as decisões de reserva de sala diretamente sem intervenção humana.)

   - AddOrganizerToSubject: $false (O organizador da reunião não é adicionado ao assunto da solicitação de reunião.)

   - DeleteComments: $false (Mantenha qualquer texto no corpo da mensagem de solicitações de reunião de entrada.)

   - DeleteSubject: $false (Mantenha o assunto das solicitações de reunião de entrada.)

   - RemovePrivateProperty: $false (Garante que o sinalizador privado enviado pelo organizador da reunião na solicitação de reunião original permaneça conforme especificado.)

   - AddAdditionalResponse: $true (O texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião.)

   - AdditionalResponse: "Esta é uma Microsoft Teams de reunião!" (O texto adicional a ser acrescentado à solicitação de reunião.)

   Este exemplo configura essas configurações na caixa de correio de sala chamada ConferenceRoom01.

   ```PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="set-password-to-never-expire"></a>Definir senha para nunca expirar

1. Na ferramenta **Usuários e Computadores** do Active Directory, encontre a conta Salas do Microsoft Teams, clique com o botão direito do mouse e selecione **Propriedades**.

2. Selecione a **caixa de seleção Senha nunca expira e** clique em **OK**.

   > [!NOTE]
   > Selecionar **Senha nunca expira** é um requisito para Salas do Microsoft Teams. As regras do domínio podem proibir senhas que não expiram. Em caso afirmado, você precisará criar uma exceção para cada Salas do Microsoft Teams conta.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Atribuir uma Microsoft 365 ou Office 365 licença

1. Conexão para Azure Active Directory. Para obter detalhes Azure Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > Azure Active Directory não há suporte para o [PowerShell 2.0.](/powershell/azure/active-directory/overview?view=azureadps-2.0) 

2. A conta de recurso precisa ter uma licença Microsoft 365 ou Office 365, ou Exchange e Microsoft Teams não funcionarão. Se você tiver a licença, precisará atribuir um local de uso à sua conta de recurso— isso determina quais SKUs de licença estão disponíveis para sua conta. Você pode usar `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> para recuperar uma lista de SKUs disponíveis.

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

3. Em seguida, você pode adicionar uma licença usando o `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. Este exemplo adiciona a Sala de Reunião de usuário à conta:

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName "ConferenceRoom01@contoso.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Para obter instruções [detalhadas, consulte Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

Para validação, você deve ser capaz de usar qualquer cliente para fazer logoff nessa conta.
  
## <a name="related-topics"></a>Tópicos relacionados

[Configurar contas para Salas do Microsoft Teams](rooms-configure-accounts.md)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
  
[Implantar Salas do Microsoft Teams](rooms-deploy.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
