---
title: Implantar Salas do Microsoft Teams com Skype for Business Server
ms.author: dstrome
author: dstrome
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
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Leia este tópico para obter informações sobre como implantar Salas do Microsoft Teams com Skype for Business Server.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ee33ec1ded7e8461f629c4552236ee60828a168
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662256"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="d999a-103">Implantar Salas do Microsoft Teams com Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d999a-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="d999a-104">Este tópico explica como você adiciona uma conta de dispositivo para Salas do Microsoft Teams quando você tem uma implantação local e de floresta única.</span><span class="sxs-lookup"><span data-stu-id="d999a-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="d999a-105">Se você tiver uma implantação local de floresta única com o Exchange 2013 SP1 ou posterior e Skype for Business Server 2015 ou posterior, poderá usar os scripts Windows PowerShell fornecidos para criar contas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d999a-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="d999a-106">Se você estiver usando uma implantação de várias florestas, poderá usar cmdlets equivalentes que produzirão os mesmos resultados.</span><span class="sxs-lookup"><span data-stu-id="d999a-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="d999a-107">Esses cmdlets são descritos nesta seção.</span><span class="sxs-lookup"><span data-stu-id="d999a-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="d999a-108">Antes de começar a Salas do Microsoft Teams, certifique-se de ter as permissões certas para executar os cmdlets associados.</span><span class="sxs-lookup"><span data-stu-id="d999a-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

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

   <span data-ttu-id="d999a-109">Observe que $strExchangeServer é o FQDN (nome de domínio totalmente qualificado) do seu servidor Exchange, e o $strLyncFQDN é o FQDN da sua implantação Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d999a-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="d999a-110">Depois de estabelecer uma sessão, você criará uma nova caixa de correio e a habilitará como RoomMailboxAccount ou alterará as configurações de uma caixa de correio de sala existente.</span><span class="sxs-lookup"><span data-stu-id="d999a-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="d999a-111">Isso permitirá que a conta seja autenticada Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d999a-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="d999a-112">Se você alterar uma caixa de correio do recurso:</span><span class="sxs-lookup"><span data-stu-id="d999a-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="d999a-113">Se você estiver criando uma nova caixa de correio de recurso:</span><span class="sxs-lookup"><span data-stu-id="d999a-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="d999a-114">Você pode definir várias Exchange na conta do dispositivo para melhorar a experiência de reunião para as pessoas.</span><span class="sxs-lookup"><span data-stu-id="d999a-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="d999a-115">Para saber quais propriedades precisam ser definidas, confira a seção Propriedades do Exchange.</span><span class="sxs-lookup"><span data-stu-id="d999a-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="d999a-116">Se você decidir não ter a senha expirada, poderá definir isso com Windows PowerShell cmdlets também.</span><span class="sxs-lookup"><span data-stu-id="d999a-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="d999a-117">Para obter mais informações, confira Gerenciamento de senha.</span><span class="sxs-lookup"><span data-stu-id="d999a-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="d999a-118">Habilita a conta no Active Directory para que ela seja autenticada Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d999a-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="d999a-119">Habilita a conta de dispositivo com Skype for Business Server habilitando sua conta do Salas do Microsoft Teams Active Directory em um pool Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="d999a-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="d999a-120">Você deverá usar o endereço do protocolo SIP e o controlador de domínio do projeto</span><span class="sxs-lookup"><span data-stu-id="d999a-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="d999a-121">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="d999a-121">**Optional.**</span></span> <span data-ttu-id="d999a-122">Você também pode permitir Salas do Microsoft Teams fazer e receber chamadas telefônicas PSTN (rede telefônica pública comutado) habilitando Enterprise Voice para sua conta.</span><span class="sxs-lookup"><span data-stu-id="d999a-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="d999a-123">Enterprise Voice não é um requisito para Salas do Microsoft Teams, mas se você quiser a funcionalidade de discagem PSTN para o cliente Salas do Microsoft Teams, veja como habilita-la:</span><span class="sxs-lookup"><span data-stu-id="d999a-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="d999a-p106">Novamente, será necessário substituir o controlador de domínio fornecido e os exemplos de números de telefone por suas próprias informações. O valor do parâmetro $true permanece o mesmo.</span><span class="sxs-lookup"><span data-stu-id="d999a-p106">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="d999a-126">Exemplo: configuração de conta de sala Exchange e Skype for Business Server local</span><span class="sxs-lookup"><span data-stu-id="d999a-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="d999a-127">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d999a-127">Related topics</span></span>

[<span data-ttu-id="d999a-128">Configurar contas para Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d999a-128">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="d999a-129">Planejar as Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d999a-129">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="d999a-130">Implantar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d999a-130">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="d999a-131">Configurar um console de Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d999a-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="d999a-132">Gerenciar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d999a-132">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
