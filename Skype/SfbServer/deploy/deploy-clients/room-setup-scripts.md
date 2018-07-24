---
title: Scripts de configuração da sala do Sistema de Salas do Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a66067d2-22b0-48f1-a5d0-e0cd0ece2e5a
description: Leia este tópico para encontrar scripts de amostra para o provisionamento das contas do Sistema de Salas do Skype.
ms.openlocfilehash: 2102a9aa306b7d545ce299b0c0808d6129cbbb02
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997843"
---
# <a name="skype-room-system-room-setup-scripts"></a><span data-ttu-id="afc0f-103">Scripts de configuração da sala do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="afc0f-103">Skype Room System room setup scripts</span></span>
 
<span data-ttu-id="afc0f-104">Leia este tópico para encontrar scripts de amostra para o provisionamento das contas do Sistema de Salas do Skype.</span><span class="sxs-lookup"><span data-stu-id="afc0f-104">Read this topic to find sample scripts for provisioning Skype Room System accounts.</span></span>
  
<span data-ttu-id="afc0f-105">Esta seção demonstra os scripts de amostra que podem ser usados para provisionar contas do sistema do Skype sala.</span><span class="sxs-lookup"><span data-stu-id="afc0f-105">This section illustrates sample scripts that can be used to provision Skype Room System accounts.</span></span> <span data-ttu-id="afc0f-106">Esses scripts são apenas para fins ilustrativos e devem ser utilizados apenas após consulta com o seu especialista em TI ou administrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="afc0f-106">These scripts are for illustrative purposes only and should be used only after consulting with your IT expert or domain administrator.</span></span>
  
## <a name="example-setup-script-skype-for-business-and-exchange-server-on-premises"></a><span data-ttu-id="afc0f-107">Script de configuração de exemplo: Skype para Exchange Server (no local) e de negócios</span><span class="sxs-lookup"><span data-stu-id="afc0f-107">Example Setup Script: Skype for Business and Exchange Server (On Premises)</span></span>

```
# On Exchange 
Set-Mailbox -Identity confroom@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a 
Lync Meeting to take advantage of enhanced meeting experience from LRS"

Set-CalendarProcessing -id confroom@contoso.com -RemovePrivateProperty $false -AddOrganizerToSubject $false -AddAdditionalResponse 
$true -AdditionalResponse "This is an LRS room!" -DeleteSubject $false -AutomateProcessing AutoAccept 
# The following is used to preserve the Lync Meeting invitations - so create these based on your Lync Federated partners# Per Lync Federated Partner as a Recommended Practice to ensure Meetings show in Lync with Join#New-RemoteDomain -DomainName Microsoft.com -Name Microsoft$true#Set-RemoteDomain -Identity Microsoft -TNEFEnabled $true
Set-ADAccountPassword -Identity "conference room"# Paste the next command on its own. Enter a blank password first, then enter the new password "password" twiceEnable-ADAccount -Identity "confroom"# On LyncEnable-CsMeetingRoom -SipAddress "sip:confroom@contoso.com" -RegistrarPool cie-srv-02.contoso.com -Identity 'conference room' 
Set-CsMeetingRoom -Identity "conference room" -LineURI "tel:+14255551669;ext=1669" -EnterpriseVoiceEnabled $true
```

## <a name="example-setup-script-skype-for-business-and-exchange-server-online"></a><span data-ttu-id="afc0f-108">Script de configuração de exemplo: Skype para comerciais e de servidor do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="afc0f-108">Example Setup Script: Skype for Business and Exchange Server Online</span></span>

<span data-ttu-id="afc0f-109">Certifique-se de que você já analisou os seguintes pré-requisitos antes de executar o script:</span><span class="sxs-lookup"><span data-stu-id="afc0f-109">Make sure you've reviewed the following prerequisites before running the script:</span></span>
  
- <span data-ttu-id="afc0f-110">Assistente de Conexão do Microsoft Online Services para Profissionais de TI BETA</span><span class="sxs-lookup"><span data-stu-id="afc0f-110">Microsoft Online Services Sign-In Assistant for IT Professionals BETA</span></span>
    
- <span data-ttu-id="afc0f-111">Módulo do Active Directory do Windows Azure para Windows PowerShell (versão de 64 bits) ou (versão de 32 bits)</span><span class="sxs-lookup"><span data-stu-id="afc0f-111">Windows Azure Active Directory Module for Windows PowerShell (64-bit version) or (32-bit version)</span></span>
    
- <span data-ttu-id="afc0f-112">Módulo Windows PowerShell para o Lync Online</span><span class="sxs-lookup"><span data-stu-id="afc0f-112">Windows PowerShell Module for Lync Online</span></span>
    
- <span data-ttu-id="afc0f-113">Reinicie se necessário</span><span class="sxs-lookup"><span data-stu-id="afc0f-113">Reboot if needed</span></span>
    
```
# Note you have to enter each command one at a time and update any bold fields for your environment
$rm="LyncRoom"
$org='YourTenantName.onmicrosoft.com'
$rmURI="$rm@$org"$newpass='MyPass@word1'# This Section Signs into Remote PowerShell
$cred=Get-Credential admin@$org
$sess=New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication basic -ConnectionUri https://ps.outlook.com/powershell
Import-PSSession $sess
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred
Import-PSSession $cssess -AllowClobber
Connect-MsolService -Credential $cred# This Section Create the Calendar Mailbox and Enables it for Lync
New-Mailbox -MicrosoftOnlineServicesID $rmURI -room -Name $rm -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
 -EnableRoomMailboxAccount $true

Set-CalendarProcessing -Identity $rmURI -DeleteSubject $false -AutomateProcessing AutoAccept 
Set-CalendarProcessing -Identity $rmURI -RemovePrivateProperty $false -AddOrganizerToSubject $false -AddAdditionalResponse $true -AdditionalResponse
 "This is an LRS room!"# Configure the Account to Not Expire
Set-MsolUser -UserPrincipalName $rm -PasswordNeverExpires $true# You need to detect your Lync Pool Registrar name. Using a normal Offic365/LyncOnline user account from your tenant, run the next command and update the RegistrarPool value for the second command coming up
Get-CsOnlineUser -Identity 'admin@YourTenantName.onmicrosoft.com' | fl *registrar*# Update with above result
Enable-CsMeetingRoom -Identity $rmURI -RegistrarPool "sippoolsn20a07.infra.lync.com" -SipAddressType EmailAddress
# If the previous command fails with an error regarding the account name not being found you might need to wait and try again in a few minutes. If you wait too long, you'll need to sign in again to remote PowerShell as detailed above.
```


