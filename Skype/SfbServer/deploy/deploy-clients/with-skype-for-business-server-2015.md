---
title: Implantar o Skype Room Systems versão 2 com o Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Leia este tópico para obter informações sobre como implantar sistemas de sala Skype v2 com Skype para Business Server 2015.
ms.openlocfilehash: 9705d849027f03a4d4befc6c433f0fe6fb4bc414
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568253"
---
# <a name="deploy-skype-room-systems-v2-with-skype-for-business-server-2015"></a><span data-ttu-id="55a1c-103">Implantar o Skype Room Systems versão 2 com o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="55a1c-103">Deploy Skype Room Systems v2 with Skype for Business Server 2015</span></span>
 
<span data-ttu-id="55a1c-104">Leia este tópico para obter informações sobre como implantar sistemas de sala Skype v2 com Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="55a1c-104">Read this topic for information on how to deploy Skype Room Systems v2 with Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="55a1c-105">Este tópico explica como adicionar uma conta de dispositivo para sistemas de sala Skype v2 quando você tem uma implantação de floresta única, no local.</span><span class="sxs-lookup"><span data-stu-id="55a1c-105">This topic explains how you add a device account for Skype Room Systems v2 when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="55a1c-106">Se você tiver uma floresta única, a implantação no local com Exchange 2013 SP1 ou posterior e Skype para Business Server 2015 ou posterior, você pode usar os scripts do Windows PowerShell fornecidos para criar contas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="55a1c-106">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="55a1c-107">Se você estiver usando uma implantação de várias floresta, você pode usar os cmdlets equivalentes que produzirá os mesmos resultados.</span><span class="sxs-lookup"><span data-stu-id="55a1c-107">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="55a1c-108">Esses cmdlets são descritos nesta seção.</span><span class="sxs-lookup"><span data-stu-id="55a1c-108">Those cmdlets are described in this section.</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-skype-for-business-server-2015"></a><span data-ttu-id="55a1c-109">Implantar o Skype Room Systems versão 2 com o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="55a1c-109">Deploy Skype Room Systems v2 with Skype for Business Server 2015</span></span>

<span data-ttu-id="55a1c-110">Antes de implantar sistemas de sala Skype v2 com Skype para Business Server 2015, certifique-se de que você cumpre os requisitos.</span><span class="sxs-lookup"><span data-stu-id="55a1c-110">Before you deploy Skype Room Systems v2 with Skype for Business Server 2015, be sure you have met the requirements.</span></span> <span data-ttu-id="55a1c-111">Para obter mais informações, consulte [requisitos de v2 de sistemas de sala Skype](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55a1c-111">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="55a1c-112">Antes de começar a implantar sistemas de sala Skype v2, certifique-se de que você tem as permissões corretas para executar os cmdlets associados.</span><span class="sxs-lookup"><span data-stu-id="55a1c-112">Before you begin to deploy Skype Room Systems v2, be sure you have the right permissions to run the associated cmdlets.</span></span>
  
1. <span data-ttu-id="55a1c-113">Iniciar uma sessão remota do Windows PowerShell a partir de um PC e se conectar ao Exchange.</span><span class="sxs-lookup"><span data-stu-id="55a1c-113">Start a remote Windows PowerShell session from a PC and connect to Exchange.</span></span> 
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
 
   ```

   <span data-ttu-id="55a1c-114">Observe que $strExchangeServer é o nome de domínio totalmente qualificado (FQDN) do seu servidor Exchange e $strLyncFQDN é o FQDN do seu Skype para implantação Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="55a1c-114">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server 2015 deployment.</span></span>
    
2. <span data-ttu-id="55a1c-115">Depois de estabelecer uma sessão, você vai criar uma nova caixa de correio e habilitá-lo como um RoomMailboxAccount ou alterar as configurações de uma caixa de correio de sala existente.</span><span class="sxs-lookup"><span data-stu-id="55a1c-115">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="55a1c-116">Isso permitirá a conta para se autenticar v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="55a1c-116">This will allow the account to authenticate to Skype Room Systems v2.</span></span>
    
    <span data-ttu-id="55a1c-117">Se você alterar uma caixa de correio do recurso:</span><span class="sxs-lookup"><span data-stu-id="55a1c-117">If you're changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="55a1c-118">Se você estiver criando uma nova caixa de correio de recursos:</span><span class="sxs-lookup"><span data-stu-id="55a1c-118">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room 
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="55a1c-119">Você pode definir várias propriedades do Exchange na conta do dispositivo para melhorar a experiência de reunião para as pessoas.</span><span class="sxs-lookup"><span data-stu-id="55a1c-119">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="55a1c-120">Para saber quais propriedades precisam ser definidas, confira a seção Propriedades do Exchange.</span><span class="sxs-lookup"><span data-stu-id="55a1c-120">You can see which properties need to be set in the Exchange properties section.</span></span>
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="55a1c-121">Se você decidir que a senha não expirar, você pode definir que com os cmdlets do Windows PowerShell muito.</span><span class="sxs-lookup"><span data-stu-id="55a1c-121">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="55a1c-122">Para obter mais informações, confira Gerenciamento de senha.</span><span class="sxs-lookup"><span data-stu-id="55a1c-122">See Password management for more information.</span></span>
    
   ```
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="55a1c-123">Habilite a conta no Active Directory para que ele irá autenticar para sistemas de sala Skype v2.</span><span class="sxs-lookup"><span data-stu-id="55a1c-123">Enable the account in Active Directory so it will authenticate to Skype Room Systems v2.</span></span>
    
   ```
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="55a1c-124">Habilite a conta de dispositivo com Skype para Business Server 2015, permitindo que sua conta do Skype sala sistemas v2 do Active Directory em um Skype para Business Server 2015 pool:</span><span class="sxs-lookup"><span data-stu-id="55a1c-124">Enable the device account with Skype for Business Server 2015 by enabling your Skype Room Systems v2 Active Directory account on a Skype for Business Server 2015 pool:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com 
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="55a1c-125">Você deverá usar o endereço do protocolo SIP e o controlador de domínio do projeto</span><span class="sxs-lookup"><span data-stu-id="55a1c-125">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span> 
    
7. <span data-ttu-id="55a1c-126">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="55a1c-126">**Optional.**</span></span> <span data-ttu-id="55a1c-127">Você também pode permitir que os sistemas de sala Skype v2 fazer e receber telefonemas do telefônica pública comutada (PSTN) de rede, permitindo que o Enterprise Voice para sua conta.</span><span class="sxs-lookup"><span data-stu-id="55a1c-127">You can also allow Skype Room Systems v2 to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="55a1c-128">Enterprise Voice não é um requisito para sistemas de sala Skype v2, mas se você deseja as funcionalidades de discagem de PSTN para o cliente do Skype sala sistemas v2, aqui está como ativá-la:</span><span class="sxs-lookup"><span data-stu-id="55a1c-128">Enterprise Voice isn't a requirement for Skype Room Systems v2, but if you want PSTN dialing functionality for the Skype Room Systems v2 client, here's how to enable it:</span></span>
    
   ```
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="55a1c-p107">Novamente, será necessário substituir o controlador de domínio fornecido e os exemplos de números de telefone por suas próprias informações. O valor do parâmetro $true permanece o mesmo.</span><span class="sxs-lookup"><span data-stu-id="55a1c-p107">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>
    
## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-2015-on-premises"></a><span data-ttu-id="55a1c-131">Exemplo: configuração de conta de sala no Exchange e Skype para 2015 do servidor de negócios no local</span><span class="sxs-lookup"><span data-stu-id="55a1c-131">Sample: room account setup in Exchange and Skype for Business Server 2015 on premises</span></span>

```
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

## <a name="see-also"></a><span data-ttu-id="55a1c-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="55a1c-132">See also</span></span>

[<span data-ttu-id="55a1c-133">Planejar a sala Skype v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="55a1c-133">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="55a1c-134">Implantar Skype sala v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="55a1c-134">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="55a1c-135">Configurar um console v2 de sistemas de sala do Skype</span><span class="sxs-lookup"><span data-stu-id="55a1c-135">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="55a1c-136">Gerenciar Skype sala v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="55a1c-136">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)