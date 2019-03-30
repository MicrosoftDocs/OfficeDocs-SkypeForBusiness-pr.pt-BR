---
title: Implantar salas de equipes da Microsoft com Skype para Business Server
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
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Leia este tópico para obter informações sobre como implantar o Microsoft salas de equipes com Skype para Business Server.
ms.openlocfilehash: e5ba372a5990f7c63827f1f8b0426e67ae48b620
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012473"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="b31a0-103">Implantar salas de equipes da Microsoft com Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="b31a0-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="b31a0-104">Este tópico explica como adicionar uma conta de dispositivo para salas de equipes da Microsoft quando você tem uma implantação de floresta única, no local.</span><span class="sxs-lookup"><span data-stu-id="b31a0-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="b31a0-105">Se você tiver uma floresta única, a implantação no local com Exchange 2013 SP1 ou posterior e Skype para Business Server 2015 ou posterior, você pode usar os scripts do Windows PowerShell fornecidos para criar contas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b31a0-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="b31a0-106">Se você estiver usando uma implantação de várias floresta, você pode usar os cmdlets equivalentes que produzirá os mesmos resultados.</span><span class="sxs-lookup"><span data-stu-id="b31a0-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="b31a0-107">Esses cmdlets são descritos nesta seção.</span><span class="sxs-lookup"><span data-stu-id="b31a0-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="b31a0-108">Antes de começar a implantar o Microsoft equipes salas, certifique-se de que você tem as permissões corretas para executar os cmdlets associados.</span><span class="sxs-lookup"><span data-stu-id="b31a0-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

   ``` Powershell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

   <span data-ttu-id="b31a0-109">Observe que $strExchangeServer é o nome de domínio totalmente qualificado (FQDN) do seu servidor Exchange e $strLyncFQDN é o FQDN do seu Skype para implantação de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="b31a0-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="b31a0-110">Depois de estabelecer uma sessão, você vai criar uma nova caixa de correio e habilitá-lo como um RoomMailboxAccount ou alterar as configurações de uma caixa de correio de sala existente.</span><span class="sxs-lookup"><span data-stu-id="b31a0-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="b31a0-111">Isso permitirá a conta autenticar a salas de equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b31a0-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="b31a0-112">Se você alterar uma caixa de correio do recurso:</span><span class="sxs-lookup"><span data-stu-id="b31a0-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="b31a0-113">Se você estiver criando uma nova caixa de correio de recursos:</span><span class="sxs-lookup"><span data-stu-id="b31a0-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="b31a0-114">Você pode definir várias propriedades do Exchange na conta do dispositivo para melhorar a experiência de reunião para as pessoas.</span><span class="sxs-lookup"><span data-stu-id="b31a0-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="b31a0-115">Para saber quais propriedades precisam ser definidas, confira a seção Propriedades do Exchange.</span><span class="sxs-lookup"><span data-stu-id="b31a0-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="b31a0-116">Se você decidir que a senha não expirar, você pode definir que com os cmdlets do Windows PowerShell muito.</span><span class="sxs-lookup"><span data-stu-id="b31a0-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="b31a0-117">Para obter mais informações, confira Gerenciamento de senha.</span><span class="sxs-lookup"><span data-stu-id="b31a0-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="b31a0-118">Habilite a conta no Active Directory para que ele irá autenticar a salas de equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b31a0-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="b31a0-119">Habilite a conta de dispositivo com Skype para Business Server, permitindo que sua conta do Active Directory do Microsoft equipes salas em um Skype para pool de servidores de negócios:</span><span class="sxs-lookup"><span data-stu-id="b31a0-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="b31a0-120">Você deverá usar o endereço do protocolo SIP e o controlador de domínio do projeto</span><span class="sxs-lookup"><span data-stu-id="b31a0-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="b31a0-121">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="b31a0-121">**Optional.**</span></span> <span data-ttu-id="b31a0-122">Você também pode permitir salas de equipes da Microsoft fazer e receber telefonemas do telefônica pública comutada (PSTN) de rede, permitindo que o Enterprise Voice para sua conta.</span><span class="sxs-lookup"><span data-stu-id="b31a0-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="b31a0-123">Enterprise Voice não é um requisito para salas de equipes da Microsoft, mas se você deseja as funcionalidades de discagem de PSTN para o cliente Microsoft equipes salas, aqui está como ativá-la:</span><span class="sxs-lookup"><span data-stu-id="b31a0-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="b31a0-p106">Novamente, será necessário substituir o controlador de domínio fornecido e os exemplos de números de telefone por suas próprias informações. O valor do parâmetro $true permanece o mesmo.</span><span class="sxs-lookup"><span data-stu-id="b31a0-p106">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="b31a0-126">Exemplo: configuração de conta de sala no Exchange e Skype para Business Server no local</span><span class="sxs-lookup"><span data-stu-id="b31a0-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

``` Powershell
New-Mailbox -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
-UserPrincipalName rigel1@contoso.com

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false
-RemovePrivateProperty $false
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

Enable-CsMeetingRoom -Identity rigel1@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity rigel1 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -PolicyName dk -Identity rigel1
Grant-CsDialPlan -PolicyName e15dp2.contoso.com -Identity rigel1
```

## <a name="see-also"></a><span data-ttu-id="b31a0-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b31a0-127">See also</span></span>

[<span data-ttu-id="b31a0-128">Configurar contas para salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b31a0-128">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="b31a0-129">Planejar para salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b31a0-129">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="b31a0-130">Implantar salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b31a0-130">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="b31a0-131">Configurar um console de salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b31a0-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="b31a0-132">Gerenciar salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b31a0-132">Manage Microsoft Teams Rooms</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)